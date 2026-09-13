---
title: Custom Cloaks
description: GadgetsMenu allows you to build your own cloaks out of particles, using six animation modes that can be layered together on a single cloak.
group: custom-cosmetic-items
keywords: custom cloaks, custom cosmetic item
topics:
 - custom cloaks
 - custom cosmetic item
---

You can create your own cloaks in `custom cosmetics/custom-cloaks.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before setup the custom cloaks.

A custom cloak is built from one or more **animation layers**. Each layer picks an animation mode, a particle effect and its own settings, so a single cloak can show a cape on your back while particles orbit around you at the same time.

The cloak's config key (for example `Infernal-Wings`) is its internal name and **must be unique**. A custom cloak that reuses the name of a built-in cloak (`Superhero`, `Mystical`, `Firewings`, `Vampire Wings`, `Frosty`, `Icewings`, `Shaman`, `Firerings`, `Scanner`, `Archangel`, `Yin and Yang`, `Flame of the Titans`) is skipped with a console warning, because two cloaks sharing a name would break menu clicks and equipped cloak lookups.

>[Warning] {{title: Warning}} `custom-cloaks.yml` is only read when the server starts. Restart the server after editing the file.

## Configuration
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

## Basic Properties

These properties apply to every cloak, no matter which animation mode it uses.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Description |
| -------- |:----:| ----------- |
| `Name` | String | The display name of the cloak. |
| `Material` | String | The menu item material, or `head:<texture>` for a player head. |
| `Permission` | String | The permission node required to equip the cloak. Omit it and GadgetsMenu writes back `gadgetsmenu.cloaks.<name>`, lowercased with spaces and dashes removed. |
| `Mystery Dust` | Integer | The price of the cloak. |
| `Rarity` | String | `Common`, `Rare`, `Epic` or `Legendary`. |
| `Enabled` | Boolean | Set to true to show this cloak to players. |
| `CanBeFound` | Boolean | Can this cloak be found in mystery boxes? |
| `Purchasable` | Boolean | Can players buy this cloak with mystery dust? |
| `Lore.Locked` | String List | The lore shown while the cloak is locked. |
| `Lore.Unlocked` | String List | The lore shown once the cloak is unlocked. |
| `Particle` | String | The particle effect of the cloak, and the default for every layer that does not set its own. |
| `Repeat-Delay` | Integer | Ticks between animation updates. `1` is every tick, `20` is once per second. Values below `1` are raised to `1`. |
</div>

## Shape Formats

Two modes read a `Shape`: `GRID` and `PICTURE`. There are two ways to write one.

### Palette, the readable way

Define a `Palette` that maps **one character to one colour**, then draw the shape as art. One character is one cell, and `.` (or a space) is empty.

```yaml
Palette:
  k: '#3C0C14'   # outline
  r: '#D6283C'   # body
  w: '#FFF0F2'   # highlight
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

The shape in the config looks like the shape in the world, so you can edit it by eye. **Defining a `Palette` is the only thing that switches a layer to character mode.**

- `.`, a space and `0` always mean empty, in every mode. You cannot use them as palette keys.
- `#`, `x`, `X` and `1` mean "fill with the layer's `Color`" when they are not in the palette, so a plain single colour shape needs no palette entry.
- Any other character that is not in the palette is left empty and named in a console warning, so a typo tells you about itself instead of vanishing silently.
- In `GRID`, which is a single colour, any character that is not empty counts as filled.
- Quote palette keys that mean something in YAML. `'#'` needs quotes, letters and digits do not.
- Rows do not have to be the same length. Short rows are padded and a warning tells you which shape it happened in, but keeping them even is what makes the art readable.

>[Tip] {{title: Why this matters}} The built-in Clover cloak is a 21 by 25 grid. Written as comma separated hex that is about 4,200 characters of YAML across 25 lines. As character art it is 525 characters, and you can see the clover in it.

### Comma separated, the original way

Without a `Palette`, `GRID` keeps reading the original format, where every cell is separated by a comma. `PICTURE` always reads character art, so it always needs a `Palette`.

```yaml
Shape:
- '0,#FF3366,#FF3366,0'
- '#FF3366,#FF6699,#FF3366,#FF3366'
```

## Animation Modes

The animation mode is set with `Animation-Mode`. There are **6 modes**.

### 1. GRID

A flat particle grid behind the player drawn in one colour, like the built-in Superhero Cloak. The whole shape can be animated with [Color Cycling](#color-cycling).
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Color` | Hex String | `#FF0000` | The particle colour. Only works with the `REDSTONE` particle. |
| `Spacing` | Double | `0.2` | The distance between particles, in blocks. |
| `Y-Start` | Double | `1.3` | The Y offset of the top row from the player's feet. |
| `Angle-Distance` | Integer | `20` | How much the lower rows curve behind the player. Lower = more curve. |
| `Particle-Count` | Integer | `3` | Particles per grid cell. Controls how solid the shape looks. |
| `Shape` | String List | — | The grid rows, top row first. Each cell is `1` (filled) or `0` (empty). |
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

`x` and `true` are accepted in place of `1`, and `false` in place of `0`.

### 2. PICTURE

**This is the mode to use for a picture.** It draws pixel art flat on the player's back, and it is the renderer behind the built-in Melon, Clover, Strawberry, Snow Globe, Popcorn and Bubble Tea cloaks, so a custom cloak using it hangs and turns exactly the way those do.

This mode replaced the old `COLOR_GRID`, which did the same job with clumsier controls. If you still have a config using it, see [Moving from COLOR_GRID](#moving-from-color_grid).

<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Palette` | Section | — | One character per colour. See [Shape Formats](#shape-formats). |
| `Shape` | String List | — | The grid rows, top row first, one character per cell. |
| `Space` | Double | `0.13` | The distance between neighbouring cells, in blocks. This is what sets the size. |
| `Tilt` | Double | `20.0` | How many degrees the picture leans back, so it faces up at the sky. |
| `Bottom-Height` | Double | `0.15` | How high off the feet the **bottom** row hangs. |
| `Top-Back` | Double | `0.25` | How far behind the shoulders the top row hangs. |
| `Rotation` | Double | `0.0` | Degrees to turn the picture in its own plane. Positive is clockwise as a viewer sees it. The built-in Clover uses `30`, the Bubble Tea `-30`. |
| `Particle-Count` | Integer | `1` | Particles per cell. Leave this at `1`. |
</div>

```yaml
Animation-Mode: PICTURE
Palette:
  g: '#50C341'   # rind
  y: '#F0EB78'
  p: '#F5A5BE'
  e: '#E12D37'   # flesh
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

**Sizing it.** The picture ends up `(columns - 1) × Space` blocks wide. At the default `Space: 0.13`, a 21 column shape is about 2.6 blocks across, which is roughly shoulder to shoulder plus a margin.

- `Space` of **0.12 to 0.14** reads as a solid surface at full size.
- `Space` of **0.09 to 0.10** suits a small emblem. If you go finer than that, keep the cell count up. Shrinking the grid to match is what turns a picture to mush.
- Wider than `0.14` and it goes dotty.

**Orientation.** The shape is written the way somebody standing behind the player sees it, so what you type is what an onlooker reads. Left in your config is left on screen.

>[Warning] {{title: Warning}} `PICTURE` paints every cell individually, so `Color-Cycle` has no effect in this mode. Use `GRID` if you want a whole shape to cycle colours.

### 3. ORBIT

Particles orbit the player in circular arms, like the built-in Firerings and Dark Energy cloaks. Turning on `Orbit-Y-Oscillation` makes the arms rise and fall while they turn, which traces a helix.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Orbit-Radius` | Double | `1.2` | The radius of the orbit, in blocks. |
| `Orbit-Arms` | Integer | `2` | How many arms orbit at once. Raised to `1` if lower. |
| `Orbit-Speed` | Integer | `3` | The rotation speed. Higher is faster. |
| `Orbit-Y-Base` | Double | `1.0` | The base height offset of the orbit. |
| `Orbit-Y-Oscillation` | Boolean | `false` | Makes the arms rise and fall. |
| `Orbit-Y-Min` | Double | `0.0` | The lowest point of the rise and fall. |
| `Orbit-Y-Max` | Double | `1.5` | The highest point. If it is below `Orbit-Y-Min`, the two are swapped automatically. |
| `Orbit-Y-Step` | Double | `0.05` | How far the arms move vertically each update. Must be greater than `0`. |
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

A ring of particles that sweeps up and down the player, like the built-in Scanner and Candy Spiral cloaks.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Spiral-Radius` | Double | `0.6` | The radius of the ring, in blocks. |
| `Spiral-Ring-Points` | Integer | `9` | How many particles make up the ring. Higher looks more solid. |
| `Spiral-Particle-Count` | Integer | `25` | How tightly the ring winds. Must be at least `1`. |
</div>

```yaml
Animation-Mode: SPIRAL
Spiral-Radius: 0.85
Spiral-Ring-Points: 14
Spiral-Particle-Count: 45
```

### 5. SCATTER

Particles are randomly placed in a box around the player every update, like the built-in Blizzard and Swarm cloaks.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Scatter-Count` | Integer | `20` | How many particles to spawn per update. |
| `Scatter-Radius-X` | Double | `2.0` | The horizontal spread on the X axis. |
| `Scatter-Radius-Y` | Double | `3.0` | The vertical spread, measured upward from the player's feet. |
| `Scatter-Radius-Z` | Double | `2.0` | The horizontal spread on the Z axis. |
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

Two rotating rings, one around the waist and one over the head, which together form a turning cage around the player. Like the built-in Snowball cloak.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Sphere-Radius` | Double | `1.0` | The radius of the rings, in blocks. |
| `Sphere-Points` | Integer | `12` | How many particles make up each ring. |
| `Sphere-Speed` | Double | `0.15` | The rotation speed per update. |
</div>

```yaml
Animation-Mode: SPHERE
Color: '#B14BFF'
Sphere-Radius: 1.15
Sphere-Points: 20
Sphere-Speed: 0.11
```

## Color Cycling

Colour cycling animates the cloak through a list of colours over time. It works in `GRID`, `ORBIT`, `SPIRAL`, `SCATTER` and `SPHERE`, and only with the `REDSTONE` particle. It has no effect in `PICTURE`, which colours every cell individually.
<div class="md-table-max-content md-table-no-bg-color">

| Property | Type | Default | Description |
| -------- |:----:|:-------:| ----------- |
| `Color-Cycle` | Boolean | `false` | Turns colour cycling on. |
| `Color-Cycle-Speed` | Integer | `1` | How many animation updates between each colour change. Higher is slower. Raised to `1` if lower. |
| `Colors` | String List | — | The colours to cycle through. If every entry is invalid, the layer falls back to `Color`. |
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

The list wraps around from the last colour straight back to the first. If you want the colour to ease back instead of snapping, walk the palette down again at the end, for example `red, orange, gold, orange` rather than `red, orange, gold`.

## Multi-Layer Cloaks

A single cloak can run several animations at once by listing them under `Layers`. Each layer has its own `Animation-Mode`, its own `Particle`, and its own mode settings. A layer that omits `Particle` inherits the cloak's root `Particle`.

Without layers, the animation settings sit at the top level of the cloak. With layers, they move under `Layers.<Layer Name>`. Layer names are only labels, so you can call them anything.

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

## Bundled Examples

The first time GadgetsMenu generates `custom-cloaks.yml`, it writes **one showcase cloak per animation type**. Each one is a finished effect you can turn on as it is, so you can look at a working cloak before writing your own. They all ship with `Enabled: false`.
<div class="md-table-max-content md-table-no-bg-color">

| Cloak | Mode | Effect | Also shows |
| ----- |:----:| ------ | ---------- |
| `Infernal-Wings` | `GRID` | A tattered demon wing silhouette that breathes through ember colours. | `Color-Cycle` on a `1`/`0` shape |
| `Phoenix-Wings` | `PICTURE` | The same wingspan with a white hot core fading to dark ember at the tips. | A six colour `Palette` gradient |
| `Pixel-Heart` | `PICTURE` | A 15 by 13 pixel heart with an outline and a highlight, 122 particles. | A `Palette` with a character art `Shape` |
| `Astral-Helix` | `ORBIT` | Six arms circling while sweeping from ankle to head, tracing a rising helix. | `Orbit-Y-Oscillation` with `Color-Cycle` |
| `Aurora-Scanner` | `SPIRAL` | A wide ring sweeping the body, leaving a twelve colour spectrum trail. | A long `Colors` palette |
| `Nebula-Storm` | `SCATTER` | Ender portal motes churning in the air around you. | A particle that ignores `Color` |
| `Arcane-Sphere` | `SPHERE` | Two rotating rings forming a gyroscope cage. | A single fixed `Color` |
| `Seraph-Aegis` | Multi-layer | Gilded wings, a halo turning overhead and drifting enchantment motes. | Three layers with different modes and particles |
</div>

## Designing a Good Shape

The bundled wing cloaks use a 15 wide by 9 tall grid at `Spacing: 0.2`, which is roughly 3 blocks across and large enough to read from a distance. Three things separate a shape that looks designed from a flat slab of particles.

**Leave the centre column empty.** Column 7 of every row in the bundled shapes is `0`, so the shape parts around the player's body instead of cutting through it.

**Ragged the bottom edge.** The second to last row alternates filled and empty cells, which suggests torn feathers instead of a rectangle.

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

**Run a gradient outward.** The Phoenix Wings shape steps `#FFF7D6` to `#FFE07A` to `#FFB020` to `#FF6A0D` to `#E02D00` to `#8E1600` from the body out to the wing tip, so the heat visibly falls off. The same shape in one flat colour looks noticeably cheaper.

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

## Validation and Error Handling

A misconfigured cloak never crashes the server and never disables the whole cloak category. Every value is checked when the cloak loads, and a warning naming the cloak and the exact config path is printed to console before a safe fallback is used.
<div class="md-table-max-content md-table-no-bg-color">

| Situation | What happens |
| --------- | ------------ |
| The cloak name is already used by another cloak | That cloak is skipped with a warning. |
| Any other failure while loading one cloak | That cloak is skipped, and the rest still load. |
| Unknown `Animation-Mode` | Falls back to `GRID`. |
| Unknown `Particle` on the cloak | Falls back to `REDSTONE`. |
| Unknown `Particle` on a layer | Falls back to the cloak's `Particle`. |
| Unknown `Rarity` | Falls back to `Legendary`. |
| Invalid hex in `Color`, `Colors` or a `Palette` entry | Falls back to the layer colour, `#FF0000` by default. |
| `GRID` or `PICTURE` with no `Shape` | A warning is printed and that layer draws nothing. |
| `Animation-Mode: COLOR_GRID`, which was removed | A warning names the keys to change, and that layer is skipped. |
| A `Shape` character that is not in the `Palette` | A warning names every unknown character, and those cells are left empty. |
| A `Palette` key longer than one character | A warning is printed and the entry is ignored, because it could never match a cell. |
| A `Palette` key of `.`, a space or `0` | A warning is printed and the entry is ignored, because those always mean empty. |
| Invalid hex in a `Palette` entry | A warning is printed and that entry is dropped. |
| `Shape` rows of different lengths | A warning is printed and short rows are padded, so the picture stays lined up. |
| A shape drawing more than 320 particles per update | A warning names the count so you know it is expensive. The cloak still works. |
| `Repeat-Delay`, `Orbit-Arms`, `Sphere-Points`, `Spiral-Ring-Points`, `Spiral-Particle-Count`, `Particle-Count`, `Angle-Distance` or `Color-Cycle-Speed` below `1` | Raised to `1`. |
| Negative `Scatter-Count` or `Scatter-Radius-X` / `Y` / `Z` | Made positive. |
</div>

Particle names are matched without case, and dashes and spaces count as underscores, so `snow-shovel`, `Snow Shovel` and `SNOW_SHOVEL` all resolve to the same particle.

## Tips

- **Use `PICTURE` with a `Palette` for anything with a recognisable shape.** It is the only mode where you can see the picture in the config, and it is what every built-in picture cloak uses.
- **Budget roughly 320 particles per update for a picture.** The built-in ones run from 155 (Easter Egg) to 321 (Clover), and the plugin warns you in console when a shape goes over. An outline is expensive: on the Clover the dark border alone is about a third of all the particles, and it does not get cheaper when you shrink the picture.
- **Never use pure black (`#000000`) with `REDSTONE`.** A dust colour with a red channel of zero is treated as "default" by the game. Use a near black such as `#12140C` instead.
- **`Repeat-Delay` is your main performance control.** The cost of a cloak is roughly `filled cells x Particle-Count` per layer, per `Repeat-Delay` ticks, for every player wearing it. Grid cloaks look identical at a delay of `3` to `5` because the shape does not move, so raise the delay before you shrink the artwork. Orbit, spiral and scatter cloaks need `1` or `2` to look smooth.
- **`Particle-Count` controls density.** Use `1` for light effects such as `FLAME`, and `2` or `3` for solid `REDSTONE` shapes.
- **`Angle-Distance` controls the curve.** Lower values wrap the grid further behind the player, higher values flatten it.
- **`Y-Start` positions the top of the grid.** `1.3` is chest height, `1.8` is above the head, and `2.5` is well above it.
- **Grid dimensions set the cloak size.** 5 by 7 is a standard cape, and 15 by 9 is a large wingspan.
- **Only `REDSTONE` takes a colour.** Every other particle uses its own built-in colour, so `Color`, `Colors` and `Color-Cycle` are ignored for them.
- Every bundled cloak is `Enabled: false`. Set it to `true` and restart the server to see it in the Cloaks menu.

## Relevant content
<div class="md-relevant-content">

- [Particle Effects](../wiki/others/particle-effects)
- [Material Syntax](../wiki/others/material-syntax)
- [Texture Head](../wiki/others/texture-head)
- [Permissions](../wiki/getting-started/permissions)
</div>
