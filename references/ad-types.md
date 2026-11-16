# 广告类型模板

占位符：`{BRAND}` 品牌名（按用户提供的拼写）、`{PRODUCT}` 产品名、`{SELLING_POINT_n}` 用户提供的卖点、
`@[产品]` / `@[人物]` / `@[场景]` 为已锁定的 Kivo 素材引用。所有卖点、数字、认证只能来自用户 Brief。

通用提示词骨架（视频）：

```
中文：[时间码] [景别+机位+运镜]，[主体]在[场景]中[动作]，[光线]，[质感/色调]。保持 @[产品] 外形、颜色、标签与参考一致；画面无文字、无水印、无其他品牌标识。
EN: [timecode] [shot size + angle + camera move], [subject] [action] in [setting], [lighting], [look/grade]. Keep @[product] shape, color and label identical to the reference; no on-screen text, no watermark, no other brand marks.
```

---

## A. 品牌 TVC（故事驱动）

**适用：** 品牌形象、新品发布、节日片。16:9 为主，30–60 s。

**结构（多镜头版，约 25–30 个镜头单元）：**

| 段落 | 时长占比 | 内容 |
|---|---|---|
| 开场 | 10–15% | 建立世界观：大场景/特殊镜头开场（航拍揭示、微距入画） |
| 冲突/需求 | 20% | 人物在情境里遇到需求，产品尚未出现或只露局部 |
| 产品登场 | 25% | 产品英雄镜头（动态跟踪、旋转），带出 1–2 个卖点 |
| 情绪高潮 | 30% | 产品改变情境：转场、超现实变化、节奏加快 |
| 落版 | 10–15% | 产品 + Logo + 口号（后期加字） |

**做法：**
- 先锁定约 4–6 张参考图（产品多角度、主场景、情绪/色调参考），所有 clip 复用。
- 镜头单元多而短（1–2 s）时，把 4–8 个单元写进一个 10–15 s clip 的提示词，按时间码分句；切点卡音乐节拍。

**变体：第一人称触发式转场**
主观视角（POV）行进，每一个动作（脚步、开门、按键）触发场景变化，产品是不变的锚点。适合运动鞋、耳机、汽车。

```
中文：第一人称主观视角，镜头随步伐轻微起伏，脚穿 @[产品] 踏在湿润的城市人行道上；每一次落脚，脚下地面向外扩散变成{新场景}，鞋子保持不变，节奏随鼓点。
EN: First-person POV, gentle step bob, feet wearing @[product] land on a wet city sidewalk; with each footfall the ground ripples outward and transforms into {new scene} while the shoe stays unchanged, cut to the drum beat.
```

**变体：长镜头版（如汽车 60 s）**
拆 3 段约 20 s 的连续运镜（例如 0–20 s / 20–40 s / 40–60 s），每段只写一条连续机位路径；段间在相同构图处接（见 SKILL.md Step 5）。

```
中文：单个连续长镜头，无剪切。0–6 s 无人机从山脊后升起揭示盘山公路；6–14 s 下降并贴近，跟随 @[产品] 车辆侧面同速平移；14–20 s 绕到车头前方缓慢后拉，结束于车头三分之二构图。
EN: One continuous take, no cuts. 0–6s drone rises over a ridge to reveal a mountain road; 6–14s descends and tracks alongside @[product] car at matching speed; 14–20s swings to the front and slowly pulls back, ending on a front three-quarter framing.
```

---

## B. 信息流广告（9:16，15 / 30 / 45 s）

**节拍图（15 s 一条；30 s/45 s = 2/3 条 15 s clip 接力）：**

| 时间 | 节拍 | 要点 |
|---|---|---|
| 0–3 s | 钩子 | 最强视觉：微距液体、超现实变化、反常识画面；第一帧就要有信息 |
| 3–6 s | 氛围/痛点 | 场景、人群、情绪 |
| 6–11 s | 高潮/卖点 | 制作过程、功能演示、产品英雄镜头 |
| 11–13 s | 使用瞬间 | 人物享受/使用，表情反应 |
| 13–15 s | CTA | 产品 + 包装正面 + 留出字幕/按钮区域 |

**30 s：** clip1 钩子+氛围，clip2 卖点演示+使用，后面接 CTA；**45 s：** 3 条 15 s，可做"钩子 → 三段卖点 → CTA"。

**要点：** 画面主体放中间 60%，上 15%、下 20% 留给平台 UI；字幕后期加；前 3 s 不要黑场或 Logo 慢出。

```
中文：竖屏 9:16。0–3 s 极近微距，冰块落入 @[产品] 饮品，液体溅起慢动作；3–6 s 午后阳光下的街角咖啡桌，人物伸手拿杯；6–11 s 制作过程特写：倒入、分层、搅拌；11–13 s 人物喝下一口，微笑；13–15 s 产品正面居中，背景虚化，画面上下留白。
EN: Vertical 9:16. 0–3s extreme macro, ice drops into @[product] drink, slow-motion splash; 3–6s sunlit street-corner café table, a hand reaches for the cup; 6–11s making-of close-ups: pour, layering, stir; 11–13s person sips and smiles; 13–15s product front-facing, centered, background blurred, clean space top and bottom.
```

---

## C. 产品测评 / 演示广告

**结构：** 每个镜头证明一个卖点，用"可视化测试"代替口播断言。15–60 s，9:16 或 16:9。

| 卖点类型 | 可视化方式 |
|---|---|
| 面料/材质 | 微距纹理 + 手指拉伸/揉搓 |
| 防水/防污 | 水珠在表面滚落（仅当用户确认产品具备该特性） |
| 轻便/收纳 | 折叠收进口袋，时间压缩 |
| 透气/散热 | 可视化气流粒子（标注为示意，不作测量结论） |
| 耐用 | 重复动作的快剪 |

**规则：** 不画出实验数据、测试曲线、"实验室认证"之类没有提供的证据；示意性可视化要在字幕标注"示意"。
用 24 个左右时间码镜头时，按 3–5 个镜头一组写成 10–15 s clip。

```
中文：0–2 s 微距：手指捏起 @[产品] 面料，纹理清晰；2–4 s 水珠落在面料上成珠滚落（示意）；4–6 s 人物把外套折小塞进背包侧袋；6–8 s 户外阳光下人物穿着行走，镜头侧面跟拍。
EN: 0–2s macro: fingers pinch the @[product] fabric, weave clearly visible; 2–4s water drops bead and roll off the fabric (illustrative); 4–6s person folds the jacket small into a backpack side pocket; 6–8s person walks outdoors in sunlight wearing it, side tracking shot.
```

---

## D. 真实感美妆 / 生活方式氛围片

**适用：** 后台、化妆间、日常 vlog 质感；常用 3:4 或 9:16，约 20 s，无对白、只有音乐。

**要点：** 手持纪录感（轻微晃动）、自然窗光或化妆镜灯、浅景深、真实皮肤纹理（不过度磨皮）、偶尔焦点漂移；
动作日常（上妆、对镜整理、转身被叫走）。避免"广告感"打光。

```
中文：3:4 画幅，手持纪录片质感，后台化妆间，化妆镜灯泡暖光。模特闭眼，化妆师用刷子轻扫眼影，镜头缓慢绕到镜子反射；焦点从刷子转移到模特睫毛。真实皮肤纹理，轻微胶片颗粒，无对白，环境声轻。
EN: 3:4, handheld documentary feel, backstage makeup room, warm vanity-bulb light. Model with eyes closed while an artist sweeps eyeshadow; camera drifts around to the mirror reflection; focus racks from brush to lashes. Real skin texture, light film grain, no dialogue, soft ambience.
```

---

## E. 电商详情页套图与海报（Seedream）

模型：`seedream-5-5`（默认），`stage=asset`；1K / 2K，png / jpeg；画幅 1:1、3:4、4:3、9:16、16:9；参考图 ≤4。

### E1 详情页套图：一图一卖点
- 同一产品渲染（相同参考图、相同光线描述、相同背景色系）贯穿整套。
- 典型 6–8 张：主图（白底/浅色）→ 卖点 1…n（每张一个特写+情境）→ 细节/材质 → 使用场景 → 规格/包装（文字后期排）。
- 每张单独一个任务，逐张检查后再做下一张。

### E2 海报：文字层级
| 层级 | 内容 | 位置建议 |
|---|---|---|
| 1 主标题 | {BRAND} 口号（用户提供） | 上 1/3 |
| 2 副标题 | 一句补充 | 主标题下 |
| 3 卖点标签 | 2–3 个短标签（用户提供） | 产品两侧或下方 |
| 4 产品 | 包装正面，占画面 35–50% | 中下 |
| 5 Logo / 信息 | Logo、规格 | 底部 |

建议：**生成时只留出文字区域**（"上方留出干净的大面积留白"），中文/精确文字后期排版更可靠；若要模型生成文字，只放短英文标题，并逐字核对。

### E3 包装严格还原
```
中文：以 @[产品] 为唯一产品参考，严格保持包装的形状、比例、颜色、标签排版与文字，不改动、不增加任何元素。产品正面朝向镜头，置于{场景}，{光线}。画面上方 1/3 留出干净留白用于标题。不要出现其他品牌、水印、二维码、价格或认证标志。
EN: Use @[product] as the only product reference and preserve the packaging shape, proportions, colors, label layout and text exactly; do not alter or add anything. Product front-facing, placed in {scene}, {lighting}. Leave the top third clean for a headline. No other brands, watermarks, QR codes, prices or certification marks.
```
QC：包装与参考逐项比对（形状、盖子、颜色、Logo、标签文字）；不一致就重做或后期把真实包装合成上去。

---

## 合规检查清单（每次交付前）

- [ ] 所有功效、数据、价格、优惠、认证、奖项、"第一/最"等用语都来自用户提供的材料；没有就删除。
- [ ] {BRAND} / {PRODUCT} 拼写、大小写与用户提供的一致。
- [ ] 画面里没有其他品牌的 Logo、包装、可识别商标（含路牌、衣服）。
- [ ] 没有水印、二维码、平台角标、伪造的 UI 或价格牌。
- [ ] 真人肖像有授权；生成人物不刻意模仿真实名人。
- [ ] 示意性可视化（气流、防护层等）已标注"示意"。
- [ ] 食品、药品、化妆品、儿童用品等受监管品类：不出现医疗/治疗暗示，提醒用户按投放地区法规自审。
- [ ] 音乐、配音、字体有使用权。
