---
title: 自定义披风
description: GadgetsMenu 允许您使用粒子来打造自己的披风，通过六种动画模式在同一件披风上叠加组合。
group: custom-cosmetic-items
keywords: 自定义披风, 自定义化妆品
topics:
 - 自定义披风
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom-cloaks.yml` 文件中创建自己的披风。

>[Warning] {{title: 警告}} 在设置自定义披风之前，请确保您已阅读完整个页面。

一件自定义披风由一个或多个**动画层**构成。每一层都会选择一种动画模式、一种粒子效果以及各自的设置，因此同一件披风可以在您背后展示斗篷的同时，让粒子环绕在您周围。

披风的配置键（例如 `Infernal-Wings`）是它的内部名称，**必须唯一**。如果自定义披风重复使用了内置披风的名称（`Superhero`、`Mystical`、`Firewings`、`Vampire Wings`、`Frosty`、`Icewings`、`Shaman`、`Firerings`、`Scanner`、`Archangel`、`Yin and Yang`、`Flame of the Titans`），该披风将被跳过并在控制台输出警告，因为两件同名的披风会破坏菜单点击和已装备披风的查找。

>[Warning] {{title: 警告}} `custom-cloaks.yml` 仅在服务器启动时读取。编辑该文件后请重启服务器。

## 配置
```yaml
# Please do not change this.
Custom-Cloaks:
  # This name will store in GadgetsMenu cache and use for mystery boxes,
  # so do not use the same name!
  Infernal-Wings:

    # The name of the cloak.
    Name: '&4Infernal Wings Cloak'

    # The material of the cloak that will show in gui menu.
    # Material Format: [Material]:[Material Data]
    Material: BLAZE_POWDER

    # The permission of the cloak.
    # If you remove this line, the permission will be
    # 'gadgetsmenu.cloaks.infernalwings' (the name in lowercase,
    # with spaces and dashes removed).
    Permission: gadgetsmenu.cloaks.infernalwings

    # The price of the cloak.
    Mystery Dust: 75

    # The rarity of the cloak.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Legendary

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this cloak found in mystery boxes?
    CanBeFound: true

    # Can player get this cloak by purchasing it using mystery dust?
    Purchasable: true

    # The lore of the cloak.
    Lore:
      Locked:
      - '&7Vast wings of smouldering ash'
      - '&7unfurl from your shoulders.'
      Unlocked:
      - '&7Vast wings of smouldering ash'
      - '&7unfurl from your shoulders.'

    # The particle effect of the cloak.
    # This is also the default particle for every layer
    # that does not set its own.
    Particle: REDSTONE

    # How many ticks should wait before the animation updates?
    # 20 ticks = 1 second. Lower value = smoother but heavier.
    Repeat-Delay: 3

    # The animation mode of the cloak.
    # Animation-Mode: GRID, PICTURE, ORBIT, SPIRAL, SCATTER, SPHERE
    Animation-Mode: GRID

    # The colour of the particles. Only works with the REDSTONE particle.
    # This is used whenever Color-Cycle is false.
    Color: '#FF3300'

    # Cycle the cloak through a list of colours over time.
    Color-Cycle: true

    # How many animation updates between each colour change?
    # Higher value = slower colour change.
    Color-Cycle-Speed: 4

    # The list of colours to cycle through.
    Colors:
    - '#FF2A00'
    - '#FF5A00'
    - '#FF8C1A'
    - '#FFB733'
    - '#FF8C1A'
    - '#FF5A00'

    # The distance between each particle, in blocks.
    Spacing: 0.2

    # The Y offset of the top row from the player's feet.
    # 1.3 = chest height, 1.8 = above head, 2.5 = well above head.
    Y-Start: 2.0

    # How much the lower rows curve behind the player.
    # Lower value = more curve, higher value = flatter.
    Angle-Distance: 24

    # How many particles to spawn per grid cell.
    Particle-Count: 2

    # The shape of the cloak, one line per row, top row first.
    # '1' = a particle, '0' = empty.
    Shape:
    - '1,0,0,0,0,0,0,0,0,0,0,0,0,0,1'
    - '1,1,0,0,0,0,0,0,0,0,0,0,0,1,1'
    - '1,1,1,0,0,0,1,0,1,0,0,0,1,1,1'
    - '1,1,1,1,0,1,1,0,1,1,0,1,1,1,1'
    - '1,1,1,1,1,1,1,0,1,1,1,1,1,1,1'
    - '0,1,1,1,1,1,1,0,1,1,1,1,1,1,0'
    - '0,0,1,1,1,1,1,0,1,1,1,1,1,0,0'
    - '0,1,0,1,0,1,1,0,1,1,0,1,0,1,0'
    - '0,0,0,0,0,0,1,0,1,0,0,0,0,0,0'
```

## 基本属性

无论使用哪种动画模式，这些属性都适用于每一件披风。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 说明 |
| -------- |:----:| ----------- |
| `Name` | 字符串 | 披风的显示名称。 |
| `Material` | 字符串 | 菜单物品的材料，或使用 `head:<texture>` 表示玩家头颅。 |
| `Permission` | 字符串 | 装备该披风所需的权限节点。如果省略，GadgetsMenu 会写回 `gadgetsmenu.cloaks.<name>`，即名称全部小写并移除空格和短横线。 |
| `Mystery Dust` | 整数 | 披风的价格。 |
| `Rarity` | 字符串 | `Common`、`Rare`、`Epic` 或 `Legendary`。 |
| `Enabled` | 布尔值 | 设置为 true 以向玩家显示此披风。 |
| `CanBeFound` | 布尔值 | 此披风能否从神秘箱中获得？ |
| `Purchasable` | 布尔值 | 玩家能否使用 Mystery Dust 购买此披风？ |
| `Lore.Locked` | 字符串列表 | 披风处于锁定状态时显示的说明文字。 |
| `Lore.Unlocked` | 字符串列表 | 披风解锁之后显示的说明文字。 |
| `Particle` | 字符串 | 披风的粒子效果，同时也是所有未单独设置粒子的层的默认值。 |
| `Repeat-Delay` | 整数 | 两次动画更新之间的刻数。`1` 表示每刻更新一次，`20` 表示每秒更新一次。低于 `1` 的值会被提升为 `1`。 |
</div>

## 形状格式

有两种模式会读取 `Shape`：`GRID` 和 `PICTURE`。编写形状有两种方式。

### 调色板（推荐，可读性更好）

定义一个 `Palette`，把**一个字符对应一种颜色**，然后像画图一样写出形状。一个字符就是一个单元格，`.`（或空格）表示留空。

```yaml
Palette:
  k: '#3C0C14'   # 描边
  r: '#D6283C'   # 主体
  w: '#FFF0F2'   # 高光
Shape:
- '..kkk.....kkk..'
- '.krrrk...krrrk.'
- 'krwwrrk.krrrrrk'
- 'krrrrrrrrrrrrrk'
- '.krrrrrrrrrrrk.'
- '..krrrrrrrrrk..'
- '...krrrrrrrk...'
- '....krrrrrk....'
- '.....krrrk.....'
- '......krk......'
```

配置文件里的形状和它在游戏里的样子一致，因此您可以直接用肉眼编辑。**只有定义了 `Palette` 才会把该图层切换为字符模式。**

- `.`、空格和 `0` 在任何模式下都表示留空，因此不能把它们用作调色板的键。
- 当 `#`、`x`、`X` 和 `1` 不在调色板中时，表示“用该图层的 `Color` 填充”，所以单色形状不需要写调色板。
- 其他不在调色板中的字符会被留空，并在控制台警告中逐一列出，这样打错字会主动告诉您，而不是悄悄消失。
- 在单色的 `GRID` 模式中，任何非留空字符都算作已填充。
- 在 YAML 中有特殊含义的调色板键需要加引号。`'#'` 需要引号，字母和数字不需要。
- 各行长度不必完全一致。较短的行会被自动补齐，并通过警告告诉您是哪个形状，但保持长度一致才能让图案更易读。

>[Tip] {{title: 为什么这很重要}} 内置的 Clover 披风是 21 × 25 的网格。若用逗号分隔的十六进制来写，大约需要 25 行、共约 4,200 个字符。改用字符图案只需约 525 个字符，而且您能直接从中看出三叶草的形状。

### 逗号分隔（原有格式）

如果没有 `Palette`，`GRID` 会继续沿用原有格式，即每个单元格用逗号分隔。`PICTURE` 始终读取字符图案，因此必须配合 `Palette` 使用。

```yaml
Shape:
- '0,#FF3366,#FF3366,0'
- '#FF3366,#FF6699,#FF3366,#FF3366'
```

## 动画模式

动画模式通过 `Animation-Mode` 设置。共有 **6 种模式**。

### 1. GRID

在玩家身后绘制一个单色的平面粒子网格，类似内置的 Superhero 披风。整个形状可以通过[颜色循环](#color-cycling)进行动画处理。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Color` | 十六进制字符串 | `#FF0000` | 粒子的颜色。仅对 `REDSTONE` 粒子有效。 |
| `Spacing` | 双精度 | `0.2` | 粒子之间的距离，单位为方块。 |
| `Y-Start` | 双精度 | `1.3` | 顶行相对于玩家脚部的 Y 轴偏移。 |
| `Angle-Distance` | 整数 | `20` | 下方各行在玩家身后弯曲的程度。值越低弯曲越大。 |
| `Particle-Count` | 整数 | `3` | 每个网格单元的粒子数量。控制形状看起来的密实程度。 |
| `Shape` | 字符串列表 | — | 网格的各行，从顶行开始。每个单元为 `1`（填充）或 `0`（空）。 |
</div>

```yaml
Animation-Mode: GRID
Color: '#FF0000'
Shape:
- '1,1,1,1,1'    # Row 1 (top)
- '1,1,1,1,1'    # Row 2
- '1,1,1,1,1'    # Row 3
- '1,1,1,1,1'    # Row 4
- '0,1,1,1,0'    # Row 5, tapered
- '0,0,1,0,0'    # Row 6 (bottom), pointed
```

`x` 和 `true` 可以代替 `1`，`false` 可以代替 `0`。

### 2. PICTURE

**要绘制图案，请使用这个模式。** 它把像素图平贴在玩家背后，也正是内置的 Melon、Clover、Strawberry、Snow Globe、Popcorn 和 Bubble Tea 披风所使用的渲染方式，因此用它做出的自定义披风，悬挂方式和转向表现与那些披风完全一致。

本模式取代了旧的 `COLOR_GRID`，后者做的是同一件事，但参数更难用。如果您的配置仍在使用它，请参阅[从 COLOR_GRID 迁移](#从-color_grid-迁移)。

<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| ---- |:----:|:------:| ---- |
| `Palette` | 配置节 | — | 一个字符对应一种颜色，详见[形状格式](#形状格式)。 |
| `Shape` | 字符串列表 | — | 网格的每一行，从顶行开始，一个字符对应一个单元格。 |
| `Space` | 双精度 | `0.13` | 相邻单元格之间的距离（方块），图案大小由它决定。 |
| `Tilt` | 双精度 | `20.0` | 图案向后倾斜的角度，让它朝向天空。 |
| `Bottom-Height` | 双精度 | `0.15` | **底行**距离脚部的高度。 |
| `Top-Back` | 双精度 | `0.25` | 顶行位于肩膀后方多远处。 |
| `Rotation` | 双精度 | `0.0` | 图案在自身平面内旋转的角度。正值表示从观察者视角看是顺时针；内置的三叶草使用 `30`，珍珠奶茶使用 `-30`。 |
| `Particle-Count` | 整数 | `1` | 每个单元格的粒子数，保持 `1` 即可。 |
</div>

```yaml
Animation-Mode: PICTURE
Palette:
  g: '#50C341'   # 瓜皮
  y: '#F0EB78'
  p: '#F5A5BE'
  e: '#E12D37'   # 果肉
Space: 0.13
Tilt: 20.0
Bottom-Height: 0.15
Top-Back: 0.25
Shape:
- '....ggggggggg....'
- '..ggyyyyyyyyygg..'
- '.gyyppppppppppyg.'
- 'gyppeeeeeeeeeppyg'
- 'gyppeeeeeeeeeppyg'
- '.gyppeeeeeeeppyg.'
- '..ggyppeeeppygg..'
- '....gggyyyggg....'
- '......ggggg......'
```

**尺寸控制。** 图案的宽度为 `（列数 - 1）× Space` 个方块。在默认的 `Space: 0.13` 下，21 列的形状大约宽 2.6 个方块，差不多是两肩宽度再加一点余量。

- `Space` 取 **0.12 到 0.14**，在完整尺寸下看起来是连成一片的。
- `Space` 取 **0.09 到 0.10** 适合小徽章。如果还要更小，请保持单元格数量不变；把网格一起缩小才是让图案糊掉的原因。
- 大于 `0.14` 就会变得稀疏发散。

**朝向。** 形状是按照站在玩家背后的人所看到的样子书写的，因此您写成什么样，旁观者就看到什么样。配置里的左边就是画面上的左边。

>[Warning] {{title: 警告}} `PICTURE` 会为每个单元格单独上色，因此 `Color-Cycle` 在该模式下无效。若想让整个形状循环变色，请使用 `GRID`。

### 3. ORBIT

粒子以环形臂的形式围绕玩家旋转，类似内置的 Firerings 和 Dark Energy 披风。启用 `Orbit-Y-Oscillation` 会让这些臂在旋转的同时上下起伏，从而勾勒出螺旋轨迹。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Orbit-Radius` | 双精度 | `1.2` | 环绕的半径，单位为方块。 |
| `Orbit-Arms` | 整数 | `2` | 同时环绕的臂数量。低于 `1` 时会被提升为 `1`。 |
| `Orbit-Speed` | 整数 | `3` | 旋转速度。数值越大越快。 |
| `Orbit-Y-Base` | 双精度 | `1.0` | 环绕的基准高度偏移。 |
| `Orbit-Y-Oscillation` | 布尔值 | `false` | 让这些臂上下起伏。 |
| `Orbit-Y-Min` | 双精度 | `0.0` | 起伏的最低点。 |
| `Orbit-Y-Max` | 双精度 | `1.5` | 最高点。如果它低于 `Orbit-Y-Min`，两者会被自动互换。 |
| `Orbit-Y-Step` | 双精度 | `0.05` | 每次更新时这些臂在垂直方向移动的距离。必须大于 `0`。 |
</div>

```yaml
Animation-Mode: ORBIT
Orbit-Radius: 1.3
Orbit-Arms: 6
Orbit-Speed: 2
Orbit-Y-Base: 0.2
Orbit-Y-Oscillation: true
Orbit-Y-Min: 0.0
Orbit-Y-Max: 2.0
Orbit-Y-Step: 0.045
```

### 4. SPIRAL

一圈粒子沿玩家身体上下扫动，类似内置的 Scanner 和 Candy Spiral 披风。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Spiral-Radius` | 双精度 | `0.6` | 圆环的半径，单位为方块。 |
| `Spiral-Ring-Points` | 整数 | `9` | 构成圆环的粒子数量。数值越大看起来越密实。 |
| `Spiral-Particle-Count` | 整数 | `25` | 圆环缠绕的紧密程度。至少为 `1`。 |
</div>

```yaml
Animation-Mode: SPIRAL
Spiral-Radius: 0.85
Spiral-Ring-Points: 14
Spiral-Particle-Count: 45
```

### 5. SCATTER

每次更新时，粒子会随机分布在玩家周围的一个立方区域内，类似内置的 Blizzard 和 Swarm 披风。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Scatter-Count` | 整数 | `20` | 每次更新生成的粒子数量。 |
| `Scatter-Radius-X` | 双精度 | `2.0` | X 轴方向的水平散布范围。 |
| `Scatter-Radius-Y` | 双精度 | `3.0` | 垂直散布范围，从玩家脚部向上计算。 |
| `Scatter-Radius-Z` | 双精度 | `2.0` | Z 轴方向的水平散布范围。 |
</div>

```yaml
Animation-Mode: SCATTER
Particle: PORTAL
Scatter-Count: 30
Scatter-Radius-X: 2.0
Scatter-Radius-Y: 3.0
Scatter-Radius-Z: 2.0
```

### 6. SPHERE

两个旋转的圆环，一个位于腰部，一个位于头顶，共同构成一个围绕玩家转动的笼状结构。类似内置的 Snowball 披风。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Sphere-Radius` | 双精度 | `1.0` | 圆环的半径，单位为方块。 |
| `Sphere-Points` | 整数 | `12` | 构成每个圆环的粒子数量。 |
| `Sphere-Speed` | 双精度 | `0.15` | 每次更新的旋转速度。 |
</div>

```yaml
Animation-Mode: SPHERE
Color: '#B14BFF'
Sphere-Radius: 1.15
Sphere-Points: 20
Sphere-Speed: 0.11
```

## 颜色循环

颜色循环会让披风随时间在一组颜色之间变化。它适用于 `GRID`、`ORBIT`、`SPIRAL`、`SCATTER` 和 `SPHERE`，并且只对 `REDSTONE` 粒子有效。它在 `PICTURE` 中无效，因为该模式会单独为每个单元上色。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Color-Cycle` | 布尔值 | `false` | 开启颜色循环。 |
| `Color-Cycle-Speed` | 整数 | `1` | 每次变色之间间隔的动画更新次数。数值越大越慢。低于 `1` 时会被提升为 `1`。 |
| `Colors` | 字符串列表 | — | 用于循环的颜色。如果所有条目都无效，该层将回退使用 `Color`。 |
</div>

```yaml
Color-Cycle: true
Color-Cycle-Speed: 5
Colors:
- '#FF3333'
- '#FF8833'
- '#FFDD33'
- '#33DD33'
- '#33DDDD'
- '#3366FF'
```

该列表会从最后一种颜色直接绕回第一种。如果您希望颜色平缓过渡而不是突然跳变，可以在末尾再把色板倒着走一遍，例如使用 `red, orange, gold, orange` 而不是 `red, orange, gold`。

## 多层披风

在 `Layers` 下列出多个动画，一件披风就可以同时运行多种动画。每一层都有自己的 `Animation-Mode`、自己的 `Particle` 以及各自的模式设置。未设置 `Particle` 的层会继承披风根级的 `Particle`。

不使用层时，动画设置位于披风的顶层。使用层时，这些设置移到 `Layers.<Layer Name>` 之下。层名称仅仅是标签，因此您可以随意命名。

```yaml
Custom-Cloaks:
  Seraph-Aegis:
    Name: '&eSeraph Aegis Cloak'
    Material: GOLDEN_APPLE
    Permission: gadgetsmenu.cloaks.seraphaegis
    Mystery Dust: 120
    Rarity: Legendary
    Enabled: false
    CanBeFound: true
    Purchasable: true
    Lore:
      Locked:
      - '&7Gilded wings, a turning halo'
      - '&7and a drift of holy motes.'
      Unlocked:
      - '&7Gilded wings, a turning halo'
      - '&7and a drift of holy motes.'

    # Inherited by any layer that does not set its own Particle.
    Particle: REDSTONE

    # Repeat-Delay is set once for the whole cloak.
    # There is no per-layer Repeat-Delay.
    Repeat-Delay: 3

    Layers:
      # Layer 1: gilded wings across the back.
      Wings:
        Animation-Mode: PICTURE
        Palette:
          e: '#D9A62E'
          r: '#F5C34B'
          a: '#FFE08A'
          g: '#FFF3C4'
          w: '#FFFFFF'
        Space: 0.2
        Tilt: 20.0
        Bottom-Height: 0.35
        Particle-Count: 2
        Shape:
        - 'e.............e'
        - 'er...........re'
        - 'era...w.w...are'
        - 'erag.ww.ww.gare'
        - 'eragwww.wwwgare'
        - '.eragww.wwgare.'
        - '..eragw.wgare..'
        - '.e.e.ra.ar.e.e.'
        - '......r.r......'

      # Layer 2: a halo turning above the head.
      # A tight radius with a high Y-Base puts the ring over the player.
      Halo:
        Animation-Mode: ORBIT
        Particle: FIREWORKS_SPARK
        Orbit-Radius: 0.55
        Orbit-Arms: 8
        Orbit-Speed: 4
        Orbit-Y-Base: 2.35
        Orbit-Y-Oscillation: false

      # Layer 3: motes drifting in the surrounding air.
      # Keep ambient layers low, they run on every update too.
      Motes:
        Animation-Mode: SCATTER
        Particle: ENCHANTMENT_TABLE
        Scatter-Count: 6
        Scatter-Radius-X: 1.6
        Scatter-Radius-Y: 2.6
        Scatter-Radius-Z: 1.6
```

## 内置示例

GadgetsMenu 首次生成 `custom-cloaks.yml` 时，会为**每种动画类型各写入一件展示用披风**。每一件都是可以直接启用的成品效果，让您在编写自己的披风之前先看看可用的实例。它们全部以 `Enabled: false` 的状态提供。
<div class="md-table-max-content md-table-no-bg-color">

| 披风 | 模式 | 效果 | 同时演示 |
| ----- |:----:| ------ | ---------- |
| `Infernal-Wings` | `GRID` | 破碎的恶魔之翼剪影，在余烬般的色彩中明灭起伏。 | 在 `1`/`0` 形状上使用 `Color-Cycle` |
| `Phoenix-Wings` | `PICTURE` | 同样的翼展，核心炽白，翼尖渐变为暗红余烬。 | 六色 `Palette` 渐变 |
| `Pixel-Heart` | `PICTURE` | 15 × 13 的像素爱心，带描边与高光，共 122 个粒子。 | `Palette` 搭配字符图案 `Shape` |
| `Astral-Helix` | `ORBIT` | 六条臂在环绕的同时从脚踝扫向头顶，勾勒出上升的螺旋。 | `Orbit-Y-Oscillation` 搭配 `Color-Cycle` |
| `Aurora-Scanner` | `SPIRAL` | 一个宽大的圆环扫过身体，留下十二色的光谱轨迹。 | 较长的 `Colors` 色板 |
| `Nebula-Storm` | `SCATTER` | 末地传送门的微粒在您周围的空气中翻涌。 | 忽略 `Color` 的粒子 |
| `Arcane-Sphere` | `SPHERE` | 两个旋转的圆环构成陀螺仪般的笼子。 | 单一固定的 `Color` |
| `Seraph-Aegis` | 多层 | 镀金之翼、头顶转动的光环以及飘散的附魔微粒。 | 三个使用不同模式和粒子的层 |
</div>

## 设计出色的形状

内置的翼形披风使用 15 宽 × 9 高的网格，`Spacing: 0.2`，大约相当于 3 个方块宽，足以在远处辨认。有三点可以让一个形状看起来是精心设计的，而不是一块扁平的粒子板。

**让中间那一列保持空白。** 内置形状中每一行的第 7 列都是 `0`，这样形状会从玩家身体两侧分开，而不是从身体中间穿过。

**让底部边缘参差不齐。** 倒数第二行交替使用填充和空白单元，营造出破损羽毛的感觉，而不是一个规整的矩形。

```
#.............#
##...........##
###...#.#...###
####.##.##.####
#######.#######
.######.######.
..#####.#####..
.#.#.##.##.#.#.
......#.#......
```

**让颜色由内向外渐变。** Phoenix Wings 的形状从身体向翼尖依次使用 `#FFF7D6`、`#FFE07A`、`#FFB020`、`#FF6A0D`、`#E02D00`、`#8E1600`，让热度的衰减清晰可见。同样的形状若使用单一纯色，看起来会明显廉价许多。

```
-.............-
-:...........:-
-:*...@.@...*:-      @  #FFF7D6  white hot
-:*+.%@.@%.+*:-      %  #FFE07A
-:*+%@@.@@%+*:-      +  #FFB020
.-:*+%@.@%+*:-.      *  #FF6A0D
..-:*+%.%+*:-..      :  #E02D00
.-.-.:*.*:.-.-.      -  #8E1600  ember
......:.:......
```

## 从 COLOR_GRID 迁移

`COLOR_GRID` 已被**移除**。它与 `PICTURE` 绘制的是同一种东西，但参数更难用，同时保留两者只会让模式列表变得混乱。

仍然设置为 `COLOR_GRID` 的层会被**跳过**，控制台会告诉您是哪一件披风的哪一层。披风的其他部分不受影响，其余各层仍会正常渲染。

转换只需要改四处：

| 旧键 | 新键 | 说明 |
| ---- | ---- | ---- |
| `Animation-Mode: COLOR_GRID` | `Animation-Mode: PICTURE` | |
| `Spacing` | `Space` | 含义相同：单元格之间的距离。 |
| `Y-Start` | `Bottom-Height` | **定位基准变了。** `Y-Start` 量到的是*顶*行，`Bottom-Height` 量到的是*底*行。请减去网格的高度：`Bottom-Height ≈ Y-Start -（行数 - 1）× Space`。 |
| `Angle-Distance` | `Tilt` | 不再是行除数。请使用 `Tilt: 20.0`，这也是所有内置图案披风使用的值。 |

然后重写 `Shape`。`PICTURE` 读取的是**基于 `Palette` 的字符图案**，而不是逗号分隔的十六进制，因此请为用到的每种颜色取一个单字符名称：

```yaml
# 修改前
Animation-Mode: COLOR_GRID
Spacing: 0.2
Y-Start: 2.1
Angle-Distance: 22
Shape:
- '#8E1600,0,0,0,#8E1600'
- '#8E1600,#E02D00,0,#E02D00,#8E1600'

# 修改后
Animation-Mode: PICTURE
Palette:
  e: '#8E1600'
  r: '#E02D00'
Space: 0.2
Tilt: 20.0
Bottom-Height: 0.35
Shape:
- 'e...e'
- 'erere'
```

在 `PICTURE` 下 `Particle-Count` 的默认值是 `1` 而不是 `3`，因此转换后的披风只需三分之一的粒子。若想恢复原来的密度，请显式设置该值。

## 校验与错误处理

配置有误的披风绝不会让服务器崩溃，也不会禁用整个披风分类。披风加载时会检查每一个值，并在使用安全的回退值之前，向控制台输出一条包含披风名称和确切配置路径的警告。
<div class="md-table-max-content md-table-no-bg-color">

| 情形 | 处理方式 |
| --------- | ------------ |
| 披风名称已被另一件披风占用 | 跳过该披风并输出警告。 |
| 加载某件披风时出现其他任何失败 | 跳过该披风，其余披风仍会正常加载。 |
| 未知的 `Animation-Mode` | 回退为 `GRID`。 |
| 披风上使用了未知的 `Particle` | 回退为 `REDSTONE`。 |
| 某一层上使用了未知的 `Particle` | 回退为披风的 `Particle`。 |
| 未知的 `Rarity` | 回退为 `Legendary`。 |
| `Color`、`Colors` 或 `Palette` 条目中的十六进制值无效 | 回退为该层的颜色，默认为 `#FF0000`。 |
| `GRID` 或 `PICTURE` 未设置 `Shape` | 输出一条警告，该层不绘制任何内容。 |
| 使用了已被移除的 `Animation-Mode: COLOR_GRID` | 警告中会列出需要修改的键，该层被跳过。 |
| `Shape` 中出现不在 `Palette` 里的字符 | 警告中会逐一列出这些未知字符，对应单元格留空。 |
| `Palette` 的键超过一个字符 | 输出警告并忽略该项，因为它永远无法匹配到任何单元格。 |
| `Palette` 的键为 `.`、空格或 `0` | 输出警告并忽略该项，因为这些字符始终表示留空。 |
| `Palette` 某一项的十六进制值无效 | 输出警告并丢弃该项。 |
| `Shape` 各行长度不一致 | 输出警告并把较短的行补齐，使图案保持对齐。 |
| 某个形状每次更新绘制超过 320 个粒子 | 警告中会给出具体数量，提示开销较大，披风仍可正常使用。 |
| `Repeat-Delay`、`Orbit-Arms`、`Sphere-Points`、`Spiral-Ring-Points`、`Spiral-Particle-Count`、`Particle-Count`、`Angle-Distance` 或 `Color-Cycle-Speed` 低于 `1` | 提升为 `1`。 |
| `Scatter-Count` 或 `Scatter-Radius-X` / `Y` / `Z` 为负数 | 取其正值。 |
</div>

粒子名称在匹配时不区分大小写，并且短横线和空格都视作下划线，因此 `snow-shovel`、`Snow Shovel` 和 `SNOW_SHOVEL` 都会解析为同一种粒子。

## 提示

- **只要形状有明确的轮廓，就用 `PICTURE` 搭配 `Palette`。** 这是唯一能让您在配置文件里直接看出图案的模式，内置的图案披风也全都使用它。
- **图案的粒子开销请控制在每次更新约 320 个以内。** 内置图案披风的用量从 155（Easter Egg）到 321（Clover）不等，超出时插件会在控制台发出警告。描边的开销很高：Clover 的深色描边约占全部粒子的三分之一，而且图案缩小时它并不会跟着变便宜。
- **切勿在 `REDSTONE` 上使用纯黑（`#000000`）。** 红色通道为 0 的尘埃颜色会被游戏当作“默认值”处理，请改用 `#12140C` 之类的近黑色。
- **`Repeat-Delay` 是您主要的性能控制手段。** 一件披风的开销大致等于每层的 `已填充单元数 × Particle-Count`，每 `Repeat-Delay` 刻计算一次，并且对每位穿戴它的玩家都要计算。网格类披风在延迟为 `3` 到 `5` 时看起来完全一样，因为形状本身并不移动，所以请先提高延迟，再考虑缩减图案。环绕、螺旋和散射类披风需要 `1` 或 `2` 才能保持流畅。
- **`Particle-Count` 控制密度。** 对于 `FLAME` 等轻量效果使用 `1`，对于密实的 `REDSTONE` 形状使用 `2` 或 `3`。
- **`Angle-Distance` 控制弯曲程度。** 值越小，网格越往玩家身后包裹；值越大则越平整。
- **`Y-Start` 决定网格顶部的位置。** `1.3` 是胸部高度，`1.8` 位于头顶上方，`2.5` 则明显高于头顶。
- **网格尺寸决定披风大小。** 5 × 7 是标准斗篷，15 × 9 则是大型翼展。
- **只有 `REDSTONE` 支持颜色。** 其他所有粒子都使用自身内置的颜色，因此 `Color`、`Colors` 和 `Color-Cycle` 对它们无效。
- 所有内置披风都是 `Enabled: false`。将其设置为 `true` 并重启服务器，即可在披风菜单中看到它。

## 相关内容
<div class="md-relevant-content">

- [粒子效果](../wiki/others/particle-effects)
- [材料语法](../wiki/others/material-syntax)
- [头颅材质](../wiki/others/texture-head)
- [权限](../wiki/getting-started/permissions)
</div>
