---
title: Custom Emotes
description: GadgetsMenu allows you to make your own emotes with any number of player head frames.
group: custom-cosmetic-items
keywords: custom emotes, custom cosmetic item
topics:
 - custom emotes
 - custom cosmetic item
---

You can create your own emotes in `custom cosmetics/custom emotes.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before setup the custom emotes.

## Configuration
```yaml
# Please do not change this.
Custom-Emotes:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the emote is 'gadgetsmenu.emotes.slimes'.
  Slimes:

    # The name of emote.
    Name: '&aSmiles Emote'

    # The price of emote.
    Mystery Dust: 10

    # The cooldown timer of using emote once.
    Cooldown: 10

    # The rarity of the emote.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common 

    # Shows a hologram on the top of the player.
    Hologram:
      Enabled: false
      Text: ''

    # The head texture which will show in the GUI menu.
    Texture: 60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this emote found in mystery boxes?
    CanBeFound: true

    # Can player get this emote by purchasing it using mystery dust?
    Purchasable: true

    # How many ticks should wait before shows the next frame?
    # 20 ticks = 1 second
    TicksPerFrame: 5

    # The frames of emote.
    # Frames syntax: '<The amount of the frames>:<texture>'
    Frames:
    - 5:264614ad4bb2eb61b06b1a8b5d57f02448a975a8217ec16571f87c49227cbd
    - 1:60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # The lore of emote.
    Lore:
      Locked: ''
      Unlocked: ''
```

## How are animations played?

Let's say we have 7 frames, TicksPerFrame = 5, each with a different amount, same as in the above example.
 1. `5:264614ad4bb2eb61b06b1a8b5d57f02448a975a8217ec16571f87c49227cbd`
 2. `1:60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa`
 3. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 4. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 5. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 6. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 7. `3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`

The value of ticks per frame will be `5 ticks` or `0.25 second`, where 20 ticks equals to 1 second.

The animation sequence will be: `1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7`. The animation ends when the last frame has played. The player needs to activate the emote again to start the animation.

The duration of each frame and one animation cycle will be:
<div class="md-table-max-content md-table-no-bg-color">

| Frame | Amount | Duration in seconds (amount x 0.25s) |
| ----- |:------:| ------------------- |
| Frame 1 | 5 | 1.25s |
| Frame 2 | 1 | 0.25s |
| Frame 3 | 11 | 2.75s |
| Frame 4 | 1 | 0.25s |
| Frame 5 | 11 | 2.75s |
| Frame 6 | 1 | 0.25s |
| Frame 7 | 3 | 0.75s |
| | **Total** | 8.25s |
</div>

## Relevant content
<div class="md-relevant-content">

- [Texture Head](../wiki/others/texture-head)
</div>