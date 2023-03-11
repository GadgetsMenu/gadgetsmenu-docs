---
title: Custom Mystery Box Loot
description: You can create any number of custom mystery box loot to increase the player's fun with the mystery box.
group: features
keywords: mystery box loot, loot, custom reward
topics:
 - mystery box loot
 - loot
 - custom reward
---

You can create and configure custom Mystery Box loot in `custom loots.yml` file which located in `mystery boxes` folder. You can set the category and the rarity of the custom loot and most importantly you can configure custom commands which it will be executed when player found the loot.

>**Note:** This feature is currently only available in GadgetsMenu Premium.

## Configuration
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

## How to create custom mystery box loot?
1. Use an unique name for your custom loot. For example, `Custom-Loot1`.
2. Make sure you copy all the attribute from the below sample, otherwise it will not work properly.
3. Set `CanBeFound` to `true` if you want to enable the custom loot.
4. Set the commands you want to execute when player get this loot.

### Example
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