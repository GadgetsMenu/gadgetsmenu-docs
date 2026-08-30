---
title: 自定义微缩模型
description: 厌倦了 GadgetsMenu 内置的微缩模型？现在您可以制作自己的微缩模型，让它陪伴您的 Minecraft 旅程。
group: custom-cosmetic-items
keywords: 自定义微缩模型, 自定义化妆品
topics:
 - 自定义微缩模型
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom-miniatures.yml` 文件中创建自己的微缩模型。

>[Warning] {{title: 警告}} 在设置自定义微缩模型之前，请确保您已阅读完整个页面。

## 配置
```yaml
# Please do not change this.
Custom-Miniatures:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the following miniature is 'gadgetsmenu.miniatures.fisherman'.
  Fisherman:

    # The name of the miniature.
    Name: '&9Fisherman Miniature'

    # The material of the miniature.
    Material: head:528da0e5b26eac1c4fbc562cd7a41bc7a644be00231cd2c23dd278f3c6861ca6

    # The price of the miniature.
    Mystery Dust: 32

    # The rarity of the miniature.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Rare

    # Set to true to show this miniature to player.
    Enabled: false

    # Can this miniature be found in mystery boxes?
    CanBeFound: true

    # Can player get this miniature by purchasing it using mystery dust?
    Purchasable: true

    # The lore of the miniature.
    Lore:
      Locked:
      - '&7Select a Fisherman Miniature'
      - '&7to follow you.'
      Unlocked:
      - '&7Select a Fisherman Miniature'
      - '&7to follow you.'

    # Set to true to hide the armor stand
    Invisible: false

    # Should this miniature be rotated?
    Rotate: false

    # Armor stand equipments.
    Equipments:
      Main-Hand:
        Enabled: true
        Material: FISHING_ROD
      Helmet:
        Enabled: true
        Material: head:528da0e5b26eac1c4fbc562cd7a41bc7a644be00231cd2c23dd278f3c6861ca6
      Chestplate:
        Enabled: true
        Material: LEATHER_CHESTPLATE:#455B93
      Leggings:
        Enabled: true
        Material: LEATHER_LEGGINGS:#455B93
      Boots:
        Enabled: true
        Material: LEATHER_BOOTS:#455B93

  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the following miniature is 'gadgetsmenu.miniatures.soul-o-lantern'.
  Soul-O-Lantern:

    # The name of the miniature.
    Name: '&5Soul Jack O''Lantern Miniature'

    # The material of the miniature.
    Material: head:b81c14a4df2a65135673211dd55dc9c577b8500143ec1293eda8e05009c851a8

    # The price of the miniature.
    Mystery Dust: 58

    # The rarity of the miniature.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Epic

    # Set to true to show this miniature to player.
    Enabled: false

    # Can this miniature be found in mystery boxes?
    CanBeFound: true

    # Can player get this miniature by purchasing it using mystery dust?
    Purchasable: true

    # The lore of the miniature.
    Lore:
      Locked:
      - '&7Select a Soul Jack O''Lantern'
      - '&7Miniature to follow you.'
      Unlocked:
      - '&7Select a Soul Jack O''Lantern'
      - '&7Miniature to follow you.'

    # Set to true to hide the armor stand
    Invisible: true

    # Should this miniature be rotated?
    Rotate: true

    # Armor stand equipments.
    Equipments:
      Helmet:
        Enabled: true
        Material: head:b81c14a4df2a65135673211dd55dc9c577b8500143ec1293eda8e05009c851a8
```

## 相关内容
<div class="md-relevant-content">

- [头颅材质](../wiki/others/texture-head)
- [材料语法](../wiki/others/material-syntax)
</div>
