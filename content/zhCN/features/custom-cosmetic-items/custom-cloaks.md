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
    # Animation-Mode: GRID, COLOR_GRID, ORBIT, SPIRAL, SCATTER, SPHERE
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

### 2. COLOR_GRID

同样的网格，但每个单元都有自己的颜色。内置的 Easter Egg、Rose、Clover 和 Dragon Wings 披风就是这样绘制的。
<div class="md-table-max-content md-table-no-bg-color">

| 属性 | 类型 | 默认值 | 说明 |
| -------- |:----:|:-------:| ----------- |
| `Spacing` | 双精度 | `0.2` | 粒子之间的距离，单位为方块。 |
| `Y-Start` | 双精度 | `1.3` | 顶行相对于玩家脚部的 Y 轴偏移。 |
| `Angle-Distance` | 整数 | `20` | 下方各行在玩家身后弯曲的程度。 |
| `Particle-Count` | 整数 | `3` | 每个网格单元的粒子数量。 |
| `Shape` | 字符串列表 | — | 网格的各行。每个单元为一个十六进制颜色，或用 `0` 表示透明。 |
</div>

```yaml
Animation-Mode: COLOR_GRID
Shape:
- '0,#FF3366,#FF3366,0,0,0,#FF3366,#FF3366,0'
- '#FF3366,#FF6699,#FF3366,#FF3366,0,#FF3366,#FF6699,#FF3366,#FF3366'
- '#FF3366,#FF3366,#FF3366,#FF3366,#FF3366,#FF3366,#FF3366,#FF3366,#FF3366'
- '0,0,0,0,#CC0044,0,0,0,0'
```

- `0`、`false` 或空单元不绘制任何内容。
- `#RRGGBB` 设置该单元的颜色。开头的 `#` 可以省略，`#RGB` 简写形式同样有效。
- `1`、`x` 或 `true` 会使用该层的 `Color` 填充该单元，因此 `GRID` 形状可以直接粘贴到 `COLOR_GRID` 层中而无需重写。

>[Warning] {{title: 警告}} `COLOR_GRID` 会单独为每个单元上色，因此 `Color-Cycle` 在此模式下无效。如果您希望整个形状循环变色，请使用 `GRID`。

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

颜色循环会让披风随时间在一组颜色之间变化。它适用于 `GRID`、`ORBIT`、`SPIRAL`、`SCATTER` 和 `SPHERE`，并且只对 `REDSTONE` 粒子有效。它在 `COLOR_GRID` 中无效，因为该模式会单独为每个单元上色。
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
        Animation-Mode: COLOR_GRID
        Spacing: 0.2
        Y-Start: 2.1
        Angle-Distance: 22
        Particle-Count: 2
        Shape:
        - '#D9A62E,0,0,0,0,0,0,0,0,0,0,0,0,0,#D9A62E'
        - '#D9A62E,#F5C34B,0,0,0,0,0,0,0,0,0,0,0,#F5C34B,#D9A62E'
        - '#D9A62E,#F5C34B,#FFE08A,0,0,0,#FFFFFF,0,#FFFFFF,0,0,0,#FFE08A,#F5C34B,#D9A62E'
        - '#D9A62E,#F5C34B,#FFE08A,#FFF3C4,0,#FFFFFF,#FFFFFF,0,#FFFFFF,#FFFFFF,0,#FFF3C4,#FFE08A,#F5C34B,#D9A62E'
        - '#D9A62E,#F5C34B,#FFE08A,#FFF3C4,#FFFFFF,#FFFFFF,#FFFFFF,0,#FFFFFF,#FFFFFF,#FFFFFF,#FFF3C4,#FFE08A,#F5C34B,#D9A62E'
        - '0,#D9A62E,#F5C34B,#FFE08A,#FFF3C4,#FFFFFF,#FFFFFF,0,#FFFFFF,#FFFFFF,#FFF3C4,#FFE08A,#F5C34B,#D9A62E,0'
        - '0,0,#D9A62E,#F5C34B,#FFE08A,#FFF3C4,#FFFFFF,0,#FFFFFF,#FFF3C4,#FFE08A,#F5C34B,#D9A62E,0,0'
        - '0,#D9A62E,0,#D9A62E,0,#F5C34B,#FFE08A,0,#FFE08A,#F5C34B,0,#D9A62E,0,#D9A62E,0'
        - '0,0,0,0,0,0,#F5C34B,0,#F5C34B,0,0,0,0,0,0'

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
| `Phoenix-Wings` | `COLOR_GRID` | 同样的翼展，核心炽白，翼尖渐变为暗红余烬。 | 逐单元的十六进制渐变 |
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

**在 COLOR_GRID 中让颜色由内向外渐变。** Phoenix Wings 的形状从身体向翼尖依次使用 `#FFF7D6`、`#FFE07A`、`#FFB020`、`#FF6A0D`、`#E02D00`、`#8E1600`，让热度的衰减清晰可见。同样的形状若使用单一纯色，看起来会明显廉价许多。

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
| `Color`、`Colors` 或 `COLOR_GRID` 单元中的十六进制值无效 | 回退为该层的颜色，默认为 `#FF0000`。 |
| `GRID` 或 `COLOR_GRID` 未设置 `Shape` | 输出一条警告，该层不绘制任何内容。 |
| `Repeat-Delay`、`Orbit-Arms`、`Sphere-Points`、`Spiral-Ring-Points`、`Spiral-Particle-Count`、`Particle-Count`、`Angle-Distance` 或 `Color-Cycle-Speed` 低于 `1` | 提升为 `1`。 |
| `Scatter-Count` 或 `Scatter-Radius-X` / `Y` / `Z` 为负数 | 取其正值。 |
</div>

粒子名称在匹配时不区分大小写，并且短横线和空格都视作下划线，因此 `snow-shovel`、`Snow Shovel` 和 `SNOW_SHOVEL` 都会解析为同一种粒子。

## 提示

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
