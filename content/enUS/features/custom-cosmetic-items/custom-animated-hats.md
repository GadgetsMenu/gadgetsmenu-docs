---
title: Custom Animated Hats
description: GadgetsMenu allows you to make your own animated hats with any number of player head frames.
group: custom-cosmetic-items
keywords: custom animated hats, custom cosmetic item
topics:
 - custom animated hats
 - custom cosmetic item
---

You can create your own animated hats in `custom cosmetics/custom animated hats.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before setup the custom animated hats.

## Configuration
```yaml
# Please do not change this.
Custom-Animated-Hats:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the emote is 'gadgetsmenu.animatedhats.slimes'.
  Slimes:

    # The name of animated hat.
    Name: '&aSmiles Animated Hat'

    # The price of animated hat.
    Mystery Dust: 12

    # The rarity of the animated hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common 

    # This is the texture of the head that are stored in Mojang's database.
    # Simply paste the url right here.
    Texture: 41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # Set to true will able player to equip it.
    Enabled: false

    # Can this animated hat found in mystery boxes?
    CanBeFound: true

    # Can player get this animated hat by purchasing it using mystery dust?
    Purchasable: true

    # How many ticks should wait before shows the next frame?
    # 20 ticks = 1 second
    TicksPerFrame: 5

    # The frames of animated hat.
    # Frames syntax: '<The amount of the frames>:<texture>'
    Frames:
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # The lore of animated hat.
    Lore: 
      Locked: ''
      Unlocked: ''
```

## How are animations played?

Let's say we have 5 frames, each with a different amount, same as in the above example.
 1. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 2. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 3. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 4. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 5. `3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`

The value of ticks per frame will be `5 ticks` or `0.25 second`, where 20 ticks equals to 1 second.

The animation sequence will be: `1 -> 2 -> 3 -> 4 -> 5`. When the last frame is played, it will return back to frame 1 and repeat the same sequence.

The duration of each frame and one animation cycle will be:
<div class="md-table-max-content md-table-no-bg-color">

| Frame | Amount | Duration in seconds (amount x 0.25s) |
| ----- |:------:| ------------------- |
| Frame 1 | 11 | 2.75s |
| Frame 2 | 1 | 0.25s |
| Frame 3 | 11 | 2.75s |
| Frame 4 | 1 | 0.25s |
| Frame 5 | 3 | 0.75s |
| | **Total** | 6.75s |
</div>

## Relevant content
<div class="md-relevant-content">

- [Texture Head](../wiki/others/texture-head)
</div>
