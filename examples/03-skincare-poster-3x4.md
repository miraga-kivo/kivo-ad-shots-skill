# 示例 3：3:4 护肤品海报（Seedream，包装严格还原）

> 虚构品牌 `{BRAND}`，产品 `{PRODUCT}`：洁面乳。标题与卖点由用户提供：`{HEADLINE}`、`{SUBLINE}`、`{SELLING_POINT_1..3}`。不出现价格、认证、功效数据。

## Brief
- `seedream-5-5`，`stage=asset`，3:4，2K（1728×2304），png，count 1
- 参考（≤4 张）：`@[产品]` 正面高清图 1 张（必须）、可选侧面 1 张、风格参考 1 张
- 特殊镜头的静帧化：水下焦散 + 微距水珠

## 版式

| 层级 | 内容 | 位置 |
|---|---|---|
| 主标题 | {HEADLINE} | 上 1/3 留白（后期排字） |
| 副标题 | {SUBLINE} | 主标题下 |
| 卖点标签 | {SELLING_POINT_1..3} | 产品右侧留白区 |
| 产品 | 包装正面，占画面约 40% | 中下，略偏左 |
| Logo | {BRAND} | 底部（后期放矢量 Logo） |

## 提示词
```
中文：3:4 竖版护肤品海报。以 @[产品] 为唯一产品参考，严格保持包装的形状、比例、颜色、标签排版与文字，不改动、不增加任何元素。产品正面朝向镜头，立于浅水面上，周围有细小水珠，微距质感；上方阳光穿过水面在背景形成柔和流动的焦散光纹，淡蓝与白色调，干净清透。画面上方 1/3 和产品右侧留出干净留白用于排版。不要任何文字、价格、认证标志、二维码、水印或其他品牌。
EN: 3:4 vertical skincare poster. Use @[product] as the only product reference and preserve the packaging shape, proportions, colors, label layout and text exactly; alter or add nothing. Product front-facing, standing on a shallow water surface with fine droplets around it, macro feel; sunlight through water casts soft moving caustics in the background, pale blue and white palette, clean and fresh. Leave the top third and the area right of the product clean for layout. No text, prices, certification marks, QR codes, watermarks or other brands.
```

## 流程
1. 先对这张图报价（`seedream-5-5`，`stage=asset`，2K，3:4，png，count 1），把 credits（及报价中的美元，如有）给用户看，等用户给出数字上限后再生成 1 张。
2. QC：包装逐项比对（瓶形、盖子、颜色、Logo、标签文字）；不一致则改提示词重做，或后期把真实包装合成进去。
3. 后期排版：标题、卖点、Logo；跑合规清单（ad-types.md）。
4. 如需一套详情页：按"一图一卖点"每张单独报价、单独生成，复用同一产品参考和光线描述。
