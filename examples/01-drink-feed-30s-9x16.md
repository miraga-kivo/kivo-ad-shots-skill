# 示例 1：30 s 竖屏信息流广告（饮品，微距 + 延时）

> 虚构品牌 `{BRAND}`，产品 `{PRODUCT}`：瓶装气泡茶。卖点只用 Brief 提供的两条：`{SELLING_POINT_1}`（例：真茶冷萃）、`{SELLING_POINT_2}`（例：低糖）。不加任何数据或认证。

## Brief
- 平台：抖音 / TikTok，9:16，30 s，有音乐无口播，字幕后期加
- 素材锁定：`@[产品]` 瓶身正面、45°、标签特写（3 张，一图一任务检查）；`@[场景]` 城市天台黄昏 1 张
- 特殊镜头：微距（钩子、制作）、延时（氛围）、产品英雄旋转（CTA）

## 分镜（时间码）

| 时间码 | 镜头 | 画面 | 特殊镜头 | 声音 | 字幕（后期） | 目的 |
|---|---|---|---|---|---|---|
| 0–3 s | 极近微距 | 冰块落入杯中，茶汤溅起，气泡升腾 | 微距·液体 | 冰块声 + 鼓点进 | — | 钩子 |
| 3–6 s | 特写 | 瓶身凝结水珠缓缓滑落，焦点从水珠转到标签 | 微距·焦点转移 | 气泡声 | {SELLING_POINT_1} | 卖点 1 |
| 6–10 s | 全景 | 天台从午后到黄昏，云层流动，城市灯亮起 | 延时·日转夜 | 音乐铺开 | — | 氛围 |
| 10–15 s | 中景 | 朋友举瓶碰杯，夕阳逆光 | — | 碰瓶声 | — | 使用瞬间（clip1 结尾：瓶子居中特写） |
| 15–19 s | 特写 | 瓶子居中（接力帧开场），茶汤倒入透明杯，分层 | 微距·液体 | 倒水声 | {SELLING_POINT_2} | 卖点 2 |
| 19–24 s | 中近景 | 人物喝一口，表情放松，背景城市夜景虚化 | 推镜 | 音乐高潮 | — | 情绪 |
| 24–30 s | 产品 | 瓶子悬浮缓慢自转，轮廓光，上下留白 | 产品英雄旋转 | 收尾音 | {BRAND} + CTA | 落版 |

## Clip 切分
- Clip 1：0–15 s（`seedance`，9:16，15 s）
- Clip 2：15–30 s（`seedance`，9:16，15 s），参考里加入 Clip 1 最后一帧作为接力帧

## Clip 1 提示词
```
中文：竖屏 9:16。0–3 s 极近微距，冰块落入透明杯中的茶汤，慢动作溅起，细密气泡上升；3–6 s 特写 @[产品] 瓶身，凝结水珠缓慢滑落，2 s 时焦点从水珠转移到标签；6–10 s @[场景] 天台固定机位延时，午后到黄昏，云层快速流动，城市灯光逐一亮起；10–15 s 中景，两位朋友在夕阳逆光下举起 @[产品] 碰瓶，结尾镜头推近停在瓶子居中特写。保持 @[产品] 瓶形、颜色、标签与参考一致；画面无文字、无水印、无其他品牌。
EN: Vertical 9:16. 0–3s extreme macro, ice drops into tea in a clear glass, slow-motion splash, fine bubbles rising; 3–6s close-up of @[product] bottle, condensation droplets slide down, at 2s focus racks from droplets to label; 6–10s locked-off timelapse on the @[scene] rooftop, afternoon to dusk, clouds streaming, city lights switching on; 10–15s medium shot, two friends clink @[product] bottles against the sunset backlight, ending on a push-in to a centered bottle close-up. Keep @[product] shape, color and label identical to the reference; no on-screen text, no watermark, no other brands.
```

## Clip 2 提示词
```
中文：竖屏 9:16，以 @[接力帧] 的构图开场：瓶子居中特写。0–4 s 茶汤从 @[产品] 倒入透明杯，微距，液体分层，高光闪烁；4–9 s 中近景缓慢推镜，人物喝一口后放松微笑，背景城市夜景虚化成光斑；9–15 s @[产品] 在深色纯背景前悬浮缓慢自转一周，轮廓光勾边，画面上方和下方留出干净空间。保持产品与参考一致；画面无文字、无水印。
EN: Vertical 9:16, open on the framing of @[handoff_frame]: centered bottle close-up. 0–4s macro pour from @[product] into a clear glass, layered liquid, glinting highlights; 4–9s slow push-in, person sips and relaxes into a smile, city night bokeh behind; 9–15s @[product] floats and slowly spins 360° on a dark seamless backdrop, rim light, clean space top and bottom. Keep the product identical to the reference; no text, no watermark.
```

## 预算流程
1. 首批 Draft：只跑 Clip 1（含微距+延时，风险最高），480p，count 1 → 报价 → 等用户上限。
2. Clip 1 通过 → 抽最后一帧上传为接力帧 → Clip 2 报价 → Draft。
3. 两条都通过 → 分别以 `stage=production` + 各自 `sourceJobId` + 1080p 报价 → 二次确认 → 升级。
4. 后期：字幕、Logo、CTA、9:16 安全区检查、合规清单。
