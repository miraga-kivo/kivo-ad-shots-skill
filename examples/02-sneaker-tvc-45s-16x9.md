# 示例 2：45 s 运动鞋 TVC（FPV 航拍 + 产品动态跟踪 + 超现实转场）

> 虚构品牌 `{BRAND}`，产品 `{PRODUCT}`：跑鞋。卖点只用 Brief 提供的 `{SELLING_POINT_1}`（例：轻量）、`{SELLING_POINT_2}`（例：回弹）。

## Brief
- 16:9，45 s，音乐驱动，结尾口号由用户提供（后期加字）
- 素材锁定：`@[产品]` 侧面、正面、鞋底、45° 共 4 张；`@[跑者]` 正脸、全身同一服装 2 张；`@[城市]` 清晨街道 1 张
- 结构借鉴"第一人称、脚步触发场景变换"的思路；建议先做白模预演锁定 FPV 路径

## 分镜（时间码）

| 时间码 | 镜头 | 画面 | 特殊镜头 | 声音 | 目的 |
|---|---|---|---|---|---|
| 0–5 s | 航拍 | 黎明城市，FPV 从高楼顶俯冲穿过两楼间隙，拉平贴地追上跑者 | 航拍·FPV 俯冲 | 低频铺底 | 开场钩子 |
| 5–9 s | 低机位跟拍 | 贴地跟随跑鞋落地，脚步溅起水花 | 产品跟随 | 脚步声入节拍 | 产品登场 |
| 9–15 s | POV | 第一人称跑步，每一步落地，地面扩散变为森林小径 | 超现实·场景变形 | 鼓点 | 情绪推进（clip1 结尾：鞋落地特写） |
| 15–20 s | 特写 | 鞋落地（接力帧）→ 速度骤降超慢动作，中底压缩回弹 | 速度变化 | 节奏停顿 | {SELLING_POINT_2} |
| 20–26 s | POV | 继续奔跑，脚步触发森林→海边栈道→沙漠山脊 | 超现实·场景变形 | 音乐加速 | 情绪高潮 |
| 26–30 s | 航拍 | 无人机环绕山脊上的跑者 180° | 航拍·环绕 | 高潮 | 世界观（clip2 结尾：跑者停下，鞋居中） |
| 30–37 s | 产品 | 鞋零件悬浮分散后依次飞回组装（仅外部部件：鞋面、中底、外底、鞋带） | 超现实·零件组装 | 机械质感音效 | {SELLING_POINT_1} |
| 37–45 s | 产品 | 机械臂式环绕鞋子急停正面，轮廓光，背景留白 | 产品动态跟踪·环绕 | 收尾 | 落版（口号后期加） |

## Clip 切分（`seedance`，16:9）
- Clip 1：0–15 s（15 s）
- Clip 2：15–30 s（15 s），接力帧 = Clip 1 结尾的鞋落地特写
- Clip 3：30–45 s（15 s），接力帧 = Clip 2 结尾鞋居中画面
- 若 FPV 在 15 s 内不稳定，把 0–5 s 单独做成 5 s clip，并以白模视频作参考

## Clip 1 提示词
```
中文：16:9 电影感，清晨冷色调。0–5 s FPV 穿越机从高楼顶部俯冲而下，从两栋楼之间的缝隙中间穿过，不接触墙面，随后拉平贴近地面高速追上 @[跑者]；5–9 s 低机位贴地跟拍 @[产品] 跑鞋落地，溅起细小水花，慢动作；9–15 s 第一人称主观视角奔跑，每一步落地时地面向外波纹扩散，城市街道逐步变为森林小径，结尾停在鞋子落地的低角度特写。保持 @[跑者] 外观与 @[产品] 外形、配色一致；无文字、无水印、无其他品牌标识。
EN: 16:9 cinematic, cool dawn grade. 0–5s FPV drone dives from a rooftop, threads through the middle of a gap between two buildings without touching the walls, levels out low and chases @[runner] at speed; 5–9s ground-level tracking on @[product] shoe landing, small splash, slow motion; 9–15s first-person POV running, each footfall sends a ripple outward and the city street transforms into a forest trail, ending on a low-angle close-up of the shoe landing. Keep @[runner] appearance and @[product] shape and colorway consistent; no text, no watermark, no other brand marks.
```

## Clip 2 提示词（节选）
```
中文：以 @[接力帧] 构图开场。0–5 s 鞋子落地瞬间速度骤降为超慢动作，中底被压缩后回弹（示意），随后恢复正常速度；5–11 s 第一人称奔跑，脚步依次触发森林→海边栈道→沙漠山脊的形状匹配转场，镜头运动不中断；11–15 s 无人机以山脊上的 @[跑者] 为中心匀速环绕 180°，跑者停下，结尾鞋子位于画面中心。
EN: Open on @[handoff_frame]. 0–5s the shoe lands and the shot ramps into extreme slow motion, midsole compresses and rebounds (illustrative), then back to real time; 5–11s first-person running, footfalls trigger shape-matched transitions forest → seaside boardwalk → desert ridge, camera move uninterrupted; 11–15s drone orbits @[runner] on the ridge 180° at constant speed, runner stops, ending with the shoe centered.
```

## Clip 3 提示词（节选）
```
中文：纯深灰背景。0–7 s @[产品] 的外部部件（鞋面、中底、外底、鞋带）在空中悬浮分散，随后依次飞回组装成完整跑鞋；7–15 s 机械臂式高速环绕，从低角度旋到侧面并急停在 45° 英雄构图，轮廓光，地面柔和反射，画面右侧留白。不要编造内部结构；Logo 只在原有位置、不镜像。
EN: Dark grey seamless. 0–7s external parts of @[product] (upper, midsole, outsole, laces) float exploded, then fly back in sequence to assemble the full shoe; 7–15s robotic-arm fast orbit from low angle to side, snapping to a 45° hero frame, rim light, soft floor reflection, empty space on the right. Do not invent internal structure; logo only in its original position, never mirrored.
```

## 预算流程
首批 Draft = Clip 1 的 0–5 s FPV 段（单独 5 s，480p，count 1）或整条 Clip 1，二选一，按报价和上限决定。通过后再做 Clip 2/3；成片逐条二次确认。
