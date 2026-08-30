---
title: 自定义旗帜
description: 对旗帜有一些很棒的想法，但 GadgetsMenu 中还没有？不用担心，您可以创建自己的旗帜。
group: custom-cosmetic-items
keywords: 自定义旗帜, 自定义化妆品
topics:
 - 自定义旗帜
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom banners.yml` 文件中创建自己的旗帜。

>[Warning] {{title: 警告}} 在设置自定义旗帜之前，请确保您已阅读完整个页面。

## 配置
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

## 相关内容
<div class="md-relevant-content">

- [颜色](../wiki/others/banner-patterns#color)
- [旗帜图案](../wiki/others/banner-patterns)
</div>
