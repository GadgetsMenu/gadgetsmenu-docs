---
title: Custom Particles
description: Want to use particle effects that GadgetsMenu hasn't added yet? No worries, you can create your own particles.
group: custom-cosmetic-items
keywords: custom particles, custom cosmetic item
topics:
 - custom particles
 - custom cosmetic item
---

You can create your own particles in `custom cosmetics/custom particles.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before setup the custom particles.

## Configuration
```yaml
# Please do not change this.
Custom-Particles:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the particle is 'gadgetsmenu.particles.endrod'.
  End Rod:

    # The name of particle.
    Name: '&5End Rod Particle'
    
    # The material of particle that will show in gui menu.
    # Material Format: [Material]:[Material Data]
    Material: END_ROD

    # The price of particle.
    Mystery Dust: 32

    # The rarity of the particle.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Epic

    # The name of the particle effect.
    Effect: END_ROD

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this particle found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of particle.
    Lore:
      Locked: ''
      Unlocked: ''
```

## Relevant content
<div class="md-relevant-content">

- [Particle Effects](../wiki/others/particle-effects)
- [Material Syntax](../wiki/others/material-syntax)
</div>