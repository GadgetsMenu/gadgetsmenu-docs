

With Premium version, you will be able to create custom mystery boxes loot in `custom loots.yml` file where the file located in `mystery boxes` folder.

Sample of `custom loots.yml` file:
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

Sample
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