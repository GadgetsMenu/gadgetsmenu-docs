---
title: Custom Animated Hats
description: GadgetsMenu allows you to make your own animated hats.
group: custom-cosmetic-items
keywords: custom animated hats, custom cosmetic item
topics:
 - custom animated hats
 - custom cosmetic item
---

You are able to create your own animated hats in `custom cosmetics/custom animated hats.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before making the custom animated hats.

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
Let's say we have 5 frames: frame 1, 2, 3, 4, and 5.  
The animation will be played as:  
`1 -> 2 -> 3 -> 4 -> 5 -> 1 -> 2 -> 3 -> 4 -> 5`  
The animation will repeat after completion follow by a sequence. 

## Relevant content
<div class="md-relevant-content">

- [Texture Head](../wiki/others/texture-head)
</div>
