# 特殊镜头效果配方

三大类、七种镜头。每种给出：替代了什么真实拍摄、提示词配方（中/英）、推荐模型与参数、常见翻车与修法、QC、怎么用进广告。
默认视频模型 `seedance`（4–30 s，480p Draft → 1080p 成片，5 种画幅）；短镜头、只需 16:9/9:16 时可考虑 `gemini-omni`（3–15 s）。
参数以实时目录为准。**所有生成都先走 SKILL.md 的报价 + 上限流程。**

通用原则：
- 一个特殊镜头 clip 建议 4–8 s，只做一个主运镜；复杂路径先做白模预演（`miraga-kivo/kivo-white-model-video-skill`），再把白模视频作为视频参考（Seedance 视频参考每段 2–30 s）。
- 产品出现的特殊镜头一定挂 `@[产品]` 参考，并在提示词结尾写保持外形/颜色/标签。
- 写清速度：`缓慢 slow` / `匀速 steady` / `急速 rapid`，以及是否慢动作 `slow motion`、`speed ramp`。

---

## 一、极限视角类（需要专业设备与复杂拍摄条件）

### 1. 航拍 Aerial

**替代：** 无人机/直升机航拍，需要飞手、空域许可、天气窗口、FPV 竞速机与备用机，成本高、可重拍性差。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 升起揭示 drone reveal | 无人机从{前景遮挡物}后缓慢升起，揭示{远景}，结束于宏大全景 | Drone slowly rises from behind {foreground}, revealing {vista}, ending on an epic wide |
| 正俯拍 top-down | 90° 垂直俯拍，镜头缓慢旋转并上升，{主体}在画面中心呈几何图案 | 90° top-down overhead, slow rotation while ascending, {subject} centered as a graphic pattern |
| FPV 俯冲 FPV dive | FPV 穿越机从高处俯冲而下，贴近{地面/建筑}高速穿梭，穿过{缝隙}后拉平跟随{主体} | FPV drone dives from height, skims {ground/buildings} at high speed, threads through {gap}, levels out to chase {subject} |
| 环绕 orbit | 无人机以{主体}为中心匀速环绕 180°，高度保持不变，背景视差明显 | Drone orbits {subject} 180° at constant speed and altitude, strong background parallax |

**参数：** 16:9（TVC）或 9:16（信息流）；4–8 s；FPV 用 5–6 s 防止路径失控。
**常见翻车 → 修法：**
- 地形/建筑在运动中"融化"变形 → 缩短时长、降低速度描述、减少场景元素；用白模定路径。
- 主体在环绕中变样 → 挂主体参考图，写"始终保持同一{主体}"；环绕角度从 360° 降到 90–180°。
- FPV 穿越时穿模 → 明确"从{缝隙}中间穿过，不接触"；或在缝隙处做遮挡转场。
**QC：** 地平线是否稳定（除非有意倾斜）、比例尺是否合理（车辆/人与建筑比例）、视差方向正确、无闪烁。
**用进广告：** TVC 开场揭示世界观；汽车片长镜头首段；信息流用 FPV 俯冲作 0–3 s 钩子。

### 2. 水下 Underwater

**替代：** 水下摄影需要防水罩、潜水员、水箱或开放水域、安全员，灯光难控。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 焦散光 caustics | 阳光穿过水面，在{主体}和沙底投下流动的焦散光纹 | Sunlight through the surface casts moving caustic patterns over {subject} and the sandy floor |
| 气泡 bubbles | {产品}落入水中，带起一串细密气泡缓慢上升，慢动作 | {product} plunges into water, trailing fine bubbles that rise slowly, slow motion |
| 悬浮颗粒 particulate | 水中漂浮细小颗粒，蓝绿色调，体积光束 | Fine suspended particles, teal-blue grade, volumetric light shafts |
| 破水面 surface break | 半水下分割镜头，镜头从水下向上冲破水面，水珠挂在镜头上 | Split-level over-under shot, camera rises and breaks the surface, droplets on the lens |

**参数：** 4–6 s；慢动作提升质感；产品入水镜头建议 9:16 或 1:1 做钩子。
**常见翻车 → 修法：**
- 气泡方向错误（往下走）或像烟雾 → 写"气泡向上浮起、圆形、透明"。
- 产品在水中颜色偏移过大 → 写"产品颜色保持真实，仅受轻微蓝色环境光"；后期调色。
- 头发/布料像在空气中 → 写"头发在水中缓慢漂浮"。
- 破水面的分割线错乱 → 缩短到 3–4 s，单一上升动作。
**QC：** 光线方向来自上方、气泡上浮、颗粒随水流缓动、产品标签可辨且未变形。
**用进广告：** 饮料/护肤（清爽、补水）、防水产品演示（仅在用户确认具备防水特性时）、品牌片转场。

### 3. 微距 Macro

**替代：** 微距镜头、探针镜头、高速摄影机与精密灯光，景深极浅、对焦难。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 浅景深 shallow DOF | 极近微距，{主体}局部清晰，前后迅速虚化成奶油般光斑 | Extreme macro, a sliver of {subject} sharp, foreground and background melting into creamy bokeh |
| 纹理 texture | 微距缓慢横移扫过{材质}表面，纤维/颗粒清晰可见，侧逆光勾出纹理 | Slow macro slide across {material}, fibers/grain crisp, raking side-back light reveals texture |
| 液体/水滴 liquid/droplet | 一滴{液体}落在{表面}上，慢动作溅开成皇冠形，高光闪烁 | A droplet of {liquid} hits {surface}, slow-motion crown splash, glinting highlights |
| 焦点转移 focus pull | 焦点从前景{A}平滑转移到后景{B}，A 逐渐虚化 | Focus racks smoothly from foreground {A} to background {B}, A softening |

**参数：** 4–6 s；液体溅射写 slow motion；1080p 成片对纹理更有利。
**常见翻车 → 修法：**
- 纹理变成"塑料感"或重复图案 → 写具体材质（"针织棉纤维""磨砂玻璃"）并加侧逆光；挂实拍材质参考图。
- 液体物理怪异（倒流、凝固）→ 单一事件、写"重力向下"；时长缩短。
- 焦点转移不发生 → 前后景物体都要在提示词里命名，并写时间点"2 s 时焦点转到…"。
- 微距下 Logo/文字乱码 → 避开文字区域，或后期合成。
**QC：** 景深是否足够浅、焦点落在正确部位、液体运动符合重力、产品局部与参考一致。
**用进广告：** 信息流钩子（水滴、气泡、奶油）、测评广告材质证明、美妆质地展示。

---

## 二、高精密运镜类（需要摄影、灯光、机械臂或多机位配合）

### 4. 摇臂 / 滑轨 Crane / Slider

**替代：** 摇臂、电控滑轨、轨道车，需要场地铺轨、配重、操作员与多次排练。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 摇臂升起揭示 crane-up reveal | 镜头从{主体}腰部高度平稳升起越过{前景}，揭示身后的{场景}，过程中镜头轻微下俯 | Camera booms up smoothly from waist height over {foreground}, revealing {scene} behind, tilting down slightly as it rises |
| 横向滑轨视差 lateral slide | 滑轨匀速横移，前景{物体}快速掠过，主体保持构图中心，背景缓慢移动形成视差 | Steady lateral slider move, foreground {object} passes quickly, subject held center, background drifts slowly for parallax |
| 推镜 push-in | 缓慢匀速推近{主体}，从中景推到特写，背景逐渐虚化 | Slow, steady push-in on {subject} from medium to close-up, background softening |

**参数：** 5–8 s；运动描述务必加"平稳 smooth / 匀速 steady / 无抖动 no shake"。
**常见翻车 → 修法：**
- 运动不够平稳像手持 → 明确"电控滑轨/摇臂，完全平稳"；去掉"动感"类词。
- 视差错误（背景比前景快）→ 写清前中后景各是什么、谁快谁慢。
- 推镜过程中主体变形 → 推近幅度减小（中景→近景），挂主体参考。
**QC：** 速度曲线平滑（起止有缓入缓出）、视差层次正确、主体不变形、地平线水平。
**用进广告：** TVC 场景揭示、落版前推向产品、美妆/生活方式片的优雅过渡。

### 5. 产品动态跟踪 Product motion tracking

**替代：** 高速机械臂（运动控制）+ 转台 + 精密打光，用于产品旋转、跟拍飞行、速度变化。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 机械臂环绕 robotic orbit | 机械臂式高速环绕 @[产品]，从低角度快速旋到顶部，结束时急停在产品正面 | Robotic-arm style fast orbit around @[product], sweeping from low angle to top, snapping to a stop on the front |
| 跟随穿越 follow-through | 镜头紧跟飞出的 @[产品]，随它穿过{场景元素}，保持产品在画面中心 | Camera tightly chases the airborne @[product] through {elements}, keeping it centered |
| 速度变化 speed ramp | 正常速度接近 → 骤降为超慢动作展示{细节} → 再加速离开 | Real-time approach → ramps into extreme slow motion on {detail} → ramps back up and exits |
| 英雄旋转 hero spin | @[产品] 在纯色背景上悬浮缓慢自转一周，轮廓光勾边，地面有柔和反射 | @[product] floats and slowly spins 360° on a seamless backdrop, rim light, soft floor reflection |

**参数：** 4–6 s；产品类建议 1:1 或 16:9 做主片、9:16 做信息流；英雄旋转用 4–5 s 降低变形风险。
**常见翻车 → 修法：**
- 旋转时背面"编造"出不存在的结构 → 提供背面参考图；或把旋转角度降到 90–180°，只露已知面。
- Logo 在旋转中乱码/镜像 → 写"Logo 只在正面出现，不镜像"；后期贴真实 Logo。
- 速度变化不明显 → 用时间码写"0–1.5 s 正常速度，1.5–4 s 超慢动作，4–5 s 加速"。
- 鞋/车等运动产品变形 → 一个 clip 只做一个动作，配合白模路径。
**QC：** 产品每个可见面与参考一致、无多余部件、反射与光线一致、急停后画面稳定。
**用进广告：** 所有类型的"产品登场"与落版；测评广告卖点特写；运动鞋/数码/汽车 TVC 核心镜头。

---

## 三、后期合成类（现实中难直接拍到的时间变化、物理状态或场景转换）

### 6. 延时 Timelapse

**替代：** 数小时到数天的固定机位拍摄、电控延时轨道、天气等待；生长/腐败类需要实验环境。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 日转夜 day-to-night | 固定机位延时，{城市/场景}从黄昏过渡到夜晚，天空颜色渐变，灯光逐一亮起 | Locked-off timelapse, {city/scene} transitions from dusk to night, sky gradient shifts, lights switch on one by one |
| 云流 clouds | 延时摄影，云层快速流动掠过{山峰/建筑}，光影在地面快速移动 | Timelapse, clouds stream fast over {peak/building}, light and shadow race across the ground |
| 生长/衰变 growth/decay | 延时，{植物/水果}从{状态A}变化到{状态B}，固定微距机位 | Timelapse, {plant/fruit} transforms from {state A} to {state B}, locked macro framing |
| 移动延时 hyperlapse | 移动延时，镜头沿{街道}稳定前进，行人车流成为拖影，画面有节奏地跳进 | Hyperlapse, camera advances steadily down {street}, people and traffic become streaks, rhythmic jumps forward |

**参数：** 5–8 s；"固定机位 locked-off"与"移动延时 hyperlapse"不要混在同一 clip。
**常见翻车 → 修法：**
- 画面变成普通实时视频 → 加"延时摄影、时间快速流逝、云层快速流动、车灯拖影"等可见证据。
- 建筑/背景随时间变形 → 写"建筑与机位完全固定，只有光线与天空变化"。
- 生长过程不连续/突然跳变 → 状态 A→B 之间写一个中间状态；时长加到 8 s。
**QC：** 机位稳定（或移动方向一致）、光线变化单调连续、背景结构不变形、时间流逝清晰可读。
**用进广告：** 饮品/茶饮"从清晨到夜晚的陪伴"、产品耐久性示意（标注示意）、品牌片段落转场。

### 7. 后期合成 / 超现实场景 Surreal compositing

**替代：** 绿幕、三维动画、特效合成团队，需要建模、跟踪、渲染，周期长。

| 子镜头 | 中文配方 | English recipe |
|---|---|---|
| 尺度反差 scale play | 巨大的 @[产品] 矗立在{城市/自然}中，行人如蚂蚁般在旁边经过，真实光影与阴影 | A giant @[product] stands in {city/landscape}, tiny pedestrians pass by, realistic light and cast shadows |
| 反物理 impossible physics | {液体/物体}逆重力向上流动/悬停，围绕 @[产品] 形成螺旋 | {liquid/objects} flow upward / hover against gravity, spiraling around @[product] |
| 场景变形转场 scene morph | 镜头推进，{场景A}的{元素}无缝变形为{场景B}的{元素}，镜头运动不中断 | As the camera pushes in, {element} of {scene A} seamlessly morphs into {element} of {scene B}, camera move uninterrupted |
| 零件悬浮组装 floating parts assembly | @[产品] 的零件在空中悬浮分散，随后依次飞回组合成完整产品，结束于英雄构图 | @[product] parts float exploded in mid-air, then fly back in sequence to assemble the complete product, ending on a hero frame |

**参数：** 5–8 s；变形转场适合做 clip 之间的接力（clip N 结尾的元素 = clip N+1 开头的元素）。
**常见翻车 → 修法：**
- 尺度反差缺少阴影/接触，像贴图 → 写"产品底部与地面接触，投下与环境一致的阴影"。
- 变形过程糊成一团 → 两个场景的形状要相似（圆→圆、竖→竖）；写"形状对应的匹配转场 match cut"。
- 零件组装编造了不存在的内部结构 → 只用外部可见部件（盖子、外壳、配件），避免拆解内部；没有结构图就不做爆炸图。
- 超现实过度导致产品认不出 → 产品本体保持真实，只让环境超现实。
**QC：** 产品本体与参考一致、光照方向统一、物理"有意违反"而不是"出错"、转场两端画面可独立成立。
**用进广告：** 信息流钩子（尺度反差）、TVC 情绪高潮、运动鞋 POV 触发式变换、数码/家电卖点组装。

---

## 组合建议

| 广告类型 | 推荐组合 |
|---|---|
| 品牌 TVC | 航拍揭示开场 → 摇臂/推镜叙事 → 产品动态跟踪登场 → 超现实高潮 → 推镜落版 |
| 信息流 9:16 | 微距或尺度反差钩子 → 延时/氛围 → 产品英雄旋转 → CTA |
| 测评/演示 | 微距材质 → 水下/液体示意 → 速度变化特写 |
| 美妆/生活方式 | 微距质地 + 推镜，克制使用超现实 |
| 海报（静帧） | 微距质感、水下焦散、尺度反差、零件悬浮都可用 Seedream 静帧实现 |

预算建议：先 Draft 最难的一个特殊镜头；它通过了，再铺开其余镜头。
