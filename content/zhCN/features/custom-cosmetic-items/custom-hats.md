---
title: 自定义帽子
description: GadgetsMenu 允许您使用玩家头颅或材料方块制作自己的帽子。
group: custom-cosmetic-items
keywords: 自定义帽子, 自定义化妆品
topics:
 - 自定义帽子
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom hats.yml` 文件中创建自己的帽子。

>[Warning] {{title: 警告}} 在设置自定义帽子之前，请确保您已阅读完整个页面。

## 配置
```yaml
# Please do not change this.
Custom-Hats:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the hat is 'gadgetsmenu.hats.steve'.
  Steve:

    # The name of hat.
    Name: '&aSteve Hat'

    # The price of hat.
    Mystery Dust: 12

    # The rarity of the hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common

    # This is the texture of the head that are stored in Mojang's database.
    # Simply paste the url right here.
    Texture: eb7af9e4411217c7de9c60acbd3c3fd6519783332a1b3bc56fbfce90721ef35

    # Set to true will able player to equip it.
    Enabled: false

    # Can this hat found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of hat.
    Lore:
      Locked: ''
      Unlocked: ''

  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the hat is 'gadgetsmenu.hats.sponge'.
  Sponge:

    # The name of hat.
    Name: '&aSponge Hat'

    # The price of hat.
    Mystery Dust: 12

    # The rarity of the hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common

    # The material of hat.
    # https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html
    # Material Format: [Material]:[Material Data]
    Material: SPONGE

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this hat found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of hat.
    Lore: 
      Locked: ''
      Unlocked: ''
```

## 相关内容
<div class="md-relevant-content">

- [头颅材质](../wiki/others/texture-head)
- [材料语法](../wiki/others/material-syntax)
</div>
