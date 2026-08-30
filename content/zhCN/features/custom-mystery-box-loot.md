---
title: 自定义神秘箱战利品
description: 您可以创建任意数量的自定义神秘箱战利品，为玩家增添开启神秘箱的乐趣。
group: features
keywords: 神秘箱战利品, 战利品, 自定义奖励
topics:
 - 神秘箱战利品
 - 战利品
 - 自定义奖励
---

您可以在位于 `mystery boxes` 文件夹中的 `custom loots.yml` 文件里创建和配置自定义神秘箱战利品。您可以设置自定义战利品的分类和稀有度，最重要的是，您可以配置在玩家获得该战利品时执行的自定义命令。

>**注意：** 此功能目前仅在 GadgetsMenu 高级版中提供。

## 配置
```yaml
Custom-Loots:
  # The name that saved in database.
  10-Money:
    # The name of custom loot.
    Name: '&a10$'
    # The rarity of custom loot.
    Rarity: Common
    # The category of custom loot.
    Category: '&cMoney'
    # Can this item can be found in mystery boxes.
    CanBeFound: true
    Execute-Command:
      # Set to true will execute the command when player found loot.
      Enabled: true
      # The command that execute when player found loot.
      # Placeholder: {PLAYER}
      Commands:
      - eco give {PLAYER} 10
  Diamond-Suit:
    Name: '&6Diamond Armor'
    Rarity: Legendary
    Category: '&cArmor'
    CanBeFound: true
    Execute-Command:
      Enabled: true
      Commands:
      - give {PLAYER} minecraft:diamond_helmet 1
      - give {PLAYER} minecraft:diamond_chestplate 1
      - give {PLAYER} minecraft:diamond_leggings 1
      - give {PLAYER} minecraft:diamond_boots 1
```

## 如何创建自定义神秘箱战利品？
1. 为您的自定义战利品使用一个唯一的名称。例如 `Custom-Loot1`。
2. 请确保您复制了下方示例中的所有属性，否则它将无法正常工作。
3. 如果您想启用该自定义战利品，请将 `CanBeFound` 设置为 `true`。
4. 设置当玩家获得此战利品时您想要执行的命令。

### 示例
```yaml
Custom-Loot1:
    Name: '&aCustom Loot 1'
    Rarity: Common
    Category: '&cLoot'
    CanBeFound: true
    Execute-Command:
      Enabled: true
      Commands:
      - eco give {PLAYER} 10
```
