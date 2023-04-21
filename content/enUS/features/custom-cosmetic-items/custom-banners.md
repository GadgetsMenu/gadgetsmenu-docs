---
title: Custom Banners
description: Has some cool ideas on banners but it does not available in GadgetsMenu yet? No worries, you can create your own banners.
group: custom-cosmetic-items
keywords: custom banners, custom cosmetic item
topics:
 - custom banners
 - custom cosmetic item
---

You can create your own banners in `custom cosmetics/custom banners.yml` file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before setup the custom banners.

## Configuration
```yaml
# Please do not change this.
Custom-Banners:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the banner is 'gadgetsmenu.banners.wolf'.
  Wolf:

    # The name of banner.
    Name: '&5Wolf Banner'

    # The price of banner.
    Mystery Dust: 15

    # The rarity of the banner.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Epic

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this banner found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The base color of banner.
    Base-Color: WHITE

    # The patterns of banner.
    # Pattern syntax: <color>:<pattern>
    Patterns:
    - BLACK:RHOMBUS_MIDDLE
    - BLACK:RHOMBUS_MIDDLE
    - LIGHT_BLUE:CURLY_BORDER
    - LIGHT_BLUE:CIRCLE_MIDDLE
    - LIGHT_BLUE:CREEPER
    - LIGHT_BLUE:TRIANGLE_TOP

    # The lore of banner.
    Lore:
      Locked: ''
      Unlocked: ''
```

## Relevant content
<div class="md-relevant-content">

- [Colors](../wiki/others/banner-patterns#color)
- [Banner Patterns](../wiki/others/banner-patterns)
</div>