# Kivo MCP：本 skill 用到的工具与实测参数

核对时间：2026-11-16（Asia/Shanghai）。方法：工具发现 + 只读 `kivo_catalog_get` / `kivo_projects_list` / `kivo_prompts_list`
+ `kivo_jobs_quote`（报价不生成、不预扣）。**没有**调用 `kivo_jobs_create`、`kivo_payments_checkout` 或任何写入/生成工具。
以下数值是运行时快照，每次使用前重读目录。

连接：Kivo MCP 服务（Streamable HTTP）`https://kivst.com/mcp`，按 [Kivo 连接指南](https://kivst.com/en/mcp) 走宿主的 OAuth。
不同宿主的工具前缀可能不同，先做工具发现，不要自造工具或字段。

## 工具（28 个，按用途）

- 账户/目录：`kivo_account_get`、`kivo_catalog_get`、`kivo_credits_list`、`kivo_orders_list`、`kivo_payments_checkout`（**不要调用**）
- 项目：`kivo_projects_list`、`kivo_projects_get`、`kivo_projects_create`、`kivo_projects_update`
- 素材：`kivo_assets_prepare`、`kivo_assets_complete`、`kivo_assets_list`、`kivo_assets_url`、`kivo_assets_addToLibrary`、
  `kivo_assets_removeFromLibrary`、`kivo_assets_rename`、`kivo_assets_delete`
- 提示词：`kivo_prompts_save`、`kivo_prompts_list`、`kivo_prompts_history`、`kivo_prompts_delete`、`kivo_prompts_optimize`
- 任务：`kivo_jobs_quote`、`kivo_jobs_create`、`kivo_jobs_get`、`kivo_jobs_list`、`kivo_jobs_cancel`、`kivo_jobs_favorite`

## quote / create 字段

- quote 必填 `projectId`、`modelId`；create 另需 `name`、`idempotencyKey`、`acceptedCredits`、`billingVersion`、`modelVersion`。
- 可选：`stage`（`asset` | `draft` | `production`）、`promptText`、`referenceIds`（≤15，唯一）、`promptId`、`promptVersion`、
  `sourceJobId`、`parameters`、`retryOf`、`promptOptimization`。不允许额外字段。
- `parameters` 只能有：`resolution`、`ratio`、`duration`、`count`（1–10）、`format`、`generateAudio`、`layerDecomposition`。
- 分辨率取值：直接生成用 `assetResolutions`，Draft 用 `draft.resolution(s)`，成片用 `draft.finalResolution(s)`；保持 `4K` 等拼写。
- `stage=production` 需要同模型、成功、未过期的 Kivo `sourceJobId`，继承时长和参考。

## 目录快照（2026-11-16）

目录版本 `2026-11-12-seedream-layers`；计费版本 `2026-11-08-starter-120`；`creditsPerUsd` 70；
限制：`maxJobsPerRequest` 10、`maxActiveJobsPerAccount` 50、`projectMembers` 100。

| modelId | 名称 | 类型 | 画幅 | 时长 | 分辨率 | 参考 |
|---|---|---|---|---|---|---|
| `seedream-5-5` | Seedream 5.5（**默认图像**） | image | 1:1, 16:9, 9:16, 4:3, 3:4 | — | 1K / 2K；png / jpeg | 图像 ≤4 |
| `seedream` | Seedream 5.0 Pro | image | 同上 | — | 1K / 2K | 图像 ≤4 |
| `seedance` | Seedance 2.5（**默认视频**） | video | 16:9, 9:16, 1:1, 4:3, 3:4 | 4–30 s，步长 1 | 480p / 720p / 1080p；Draft 480p → 成片 1080p；mp4 / mov | 图像 ≤15；视频 ≤10（每段 2–30 s，合计 ≤30 s，宽高比 0.4–2.5）；音频 ≤10（合计 ≤30 s）；depth；总计 ≤15 |
| `gemini-omni` | Gemini Omni 1.2 Flash | video | 16:9, 9:16 | 3–15 s | 直接 360p / 720p；Draft 360p / 720p → 成片 1080p / 4K | 图像 ≤6；视频 ≤3（每段 ≤3 s，合计 ≤9 s；输出 >10 s 时只能 1 段）；总计 ≤9 |
| `audio-create` | Seed Audio 1.0 | audio | — | 2–120 s | wav / mp3 | 音频 ≤3 |
| `vda-small` | Video Depth | 深度视频 | source | 0.1–30 s | source | 视频 1 段；标价 0 |

其他：Seedance `defaultGenerateAudio: true`，`referenceMode: "reference"`；Omni `alwaysGenerateAudio: true`；
两个视频模型 Draft `ttlSeconds` 604800（7 天）。Seedream 支持 `layerDecomposition`（分层，最多 17 张输出；用 `stage=asset`、
`count=1`、`format=png`、不传 `ratio`、恰好 1 张参考图）。提示词上限 12000 字符（audio 3000）。

> 模型 ID 注意：视频模型的 ID 是 `seedance`（显示名 Seedance 2.5），不是 `seedance-2.5`。

## 实测报价

| 请求 | 结果 |
|---|---|
| `seedream-5-5`，`stage=asset`，2K，3:4，png，count 1 | `perCandidate` 10，`totalCredits` 10（按 70 credits/USD 参考约 US$0.14） |
| `seedance` 视频报价（draft/asset，多种参数组合，含已保存提示词） | 均返回 `INVALID_FORMAT`，未拿到视频报价 |

视频报价失败原因未查明（可能是宿主传参格式或服务端校验问题）。实际使用时：先 `kivo_prompts_save` 保存提示词，用返回的
`promptId`/`promptVersion` 做 Draft 报价；仍报错就把错误原样告诉用户并停下，**不要**凭目录里的 `basePriceCredits` 自行估价后直接生成。

## 计费事实

- 成功生成并保存后扣**项目创建者**的 credits；失败不扣费；报价不启动任务、不预扣。
- 目录里有 `paymentsEnabled` 和积分包信息，但不要据此引导用户购买；不要调用 `kivo_payments_checkout`。
