---
title: Configuration
description: You can find all configuration settings for GadgetsMenu in this page.
group: getting-started
keywords: configuration,setup
topics:
 - configuration
 - setup
---

## Properties (config.yml)
The following section contains all the properties in config.yml file.

### Player Data Storage
```yaml
# This option allows you to set where
# player's data do you want to save.
# 
# Storages: 'sqlite' or 'mysql'.
# 
# If you enable mysql, you need to setup MySQL infos.
Player-Data:
  Storage: sqlite
  MySQL:
    hostname: localhost
    username: root
    database: minecraft
    port: '3306'
    password: password
    useSSL: false
```

### Cosmetic Purchase
```yaml
Cosmetic-Item-Purchase:
  # Set to true allows player to purchase cosmetic items.
  Enabled: true
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault', 'tokenmanager'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
  # Set to true will allows player to purchase specified cosmetic.
  Enabled-Cosmetics:
    Hats: true
    Animated Hats: true
    Particles: true
    Suits: true
    Gadgets: true
    Pets: true
    Miniatures: true
    Morphs: true
    Banners: true
    Emotes: true
    Cloaks: true
  # Reopen GUI menu after player purchase item.
  Reopen-GUI-Menu-After-Purchase: true
  Execute-Command:
    # Set to true will use 3rd party plugin to store purchased cosmetic items,
    # otherwise will saved in built-in storage.
    Enabled: false
    Command: pex user {PLAYER} add {PERMISSION}
```

### General Settings
```yaml
# General settings.
Settings:
  # The mystery dust amount of the player who join the server first time.
  Starting-Mystery-Dust: 0
  # The maximum characters that player can set the pet name.
  Max-Pet-Name-Characters: 20
  # The slot when player equip gadget, emote or morph.
  Gadget-Slot: 5
  # Set how items are sorted in the menus.
  # Sorting Types: DEFAULT, RARITY, NAME
  Inventory-Sorting: DEFAULT
  # The default value of Mystery Vault animation.
  # The animation for the player who join the server first time.
  # Animation: None, Normal, CountDown, Star, Crafting, Summer, Halloween, Holiday
  Default-Mystery-Vault-Animation: NORMAL
  # The timezone of the crafting date of Crafted Mystery Box.
  Crafted-Mystery-Box-Date-Timezone: EST5EDT
  # The default self morph view setting.
  Default-Self-Morph-View: true
  # Do you want to enable self morph view?
  Enabled-Self-Morph-View: true
  # Display player name above the mob disguise.
  Show-Name-For-Mob-Disguise: true
  # Do you want to enable mob disguise damage?
  # Set to false will disable damage if disguised.
  Enabled-Mob-Disguise-Damage: false
  # Auto equip cosmetic after player purchased.
  Auto-Equip-After-Purchase: true
  # Auto equip cosmetic when player found loot from mystery box.
  Auto-Equip-On-Loot-Found: true
  # Set to true will shows particle effect to everyone,
  # otherwise will only show to the player itself.
  Show-Particle-Effect-To-Everyone: true
  # Set to true will shows cloak effect to everyone,
  # otherwise will only show to the player itself.
  Show-Cloak-Effect-To-Everyone: true
  # Set to true will hide particle effect for vanished player.
  Hide-Particle-Effect-For-Vanished-Player: true
  # Set to true will hide cloak effect for vanished player.
  Hide-Cloak-Effect-For-Vanished-Player: true
  # Do action when player equip cosmetic.
  # Equip Type: REPLACE, WARN, DROP
  # Replace: Replace the old item with equipped cosmetic.
  # Warn: Send a warning message to the player and reject to equip cosmetic.
  # Drop: Drop the old item on the ground and equip cosmetic.
  Equip-Cosmetic-Item-To-Slot: WARN
  # Sync player's selected cosmetics when they join the server.
  Sync-Cosmetics-On-Join: true
```

### Enabled Worlds
To configure which world can enable GadgetsMenu usage.
 - **`*`** to indicates all worlds

```yaml
# List of the worlds where cosmetics are enabled!
Enabled-Worlds:
- '*'
- world
- world_nether
- world_the_end
```

### Sample config.yml
```yaml
# This option allows you to set where
# player's data do you want to save.
# 
# Storages: 'sqlite' or 'mysql'.
# 
# If you enable mysql, you need to setup MySQL infos.
Player-Data:
  Storage: sqlite
  MySQL:
    hostname: localhost
    username: root
    database: minecraft
    port: '3306'
    password: password
    useSSL: false

Cosmetic-Item-Purchase:
  # Set to true allows player to purchase cosmetic items.
  Enabled: true
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault', 'tokenmanager'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
  # Set to true will allows player to purchase specified cosmetic.
  Enabled-Cosmetics:
    Hats: true
    Animated Hats: true
    Particles: true
    Suits: true
    Gadgets: true
    Pets: true
    Miniatures: true
    Morphs: true
    Banners: true
    Emotes: true
    Cloaks: true
  # Reopen GUI menu after player purchase item.
  Reopen-GUI-Menu-After-Purchase: true
  Execute-Command:
    # Set to true will use 3rd party plugin to store purchased cosmetic items,
    # otherwise will saved in built-in storage.
    Enabled: false
    Command: pex user {PLAYER} add {PERMISSION}

# General settings.
Settings:
  # The mystery dust amount of the player who join the server first time.
  Starting-Mystery-Dust: 0
  # The maximum characters that player can set the pet name.
  Max-Pet-Name-Characters: 20
  # The slot when player equip gadget, emote or morph.
  Gadget-Slot: 5
  # Set how items are sorted in the menus.
  # Sorting Types: DEFAULT, RARITY, NAME
  Inventory-Sorting: DEFAULT
  # The default value of Mystery Vault animation.
  # The animation for the player who join the server first time.
  # Animation: None, Normal, CountDown, Star, Crafting, Summer, Halloween, Holiday
  Default-Mystery-Vault-Animation: NORMAL
  # The timezone of the crafting date of Crafted Mystery Box.
  Crafted-Mystery-Box-Date-Timezone: EST5EDT
  # The default self morph view setting.
  Default-Self-Morph-View: true
  # Do you want to enable self morph view?
  Enabled-Self-Morph-View: true
  # Display player name above the mob disguise.
  Show-Name-For-Mob-Disguise: true
  # Do you want to enable mob disguise damage?
  # Set to false will disable damage if disguised.
  Enabled-Mob-Disguise-Damage: false
  # Auto equip cosmetic after player purchased.
  Auto-Equip-After-Purchase: true
  # Auto equip cosmetic when player found loot from mystery box.
  Auto-Equip-On-Loot-Found: true
  # Set to true will shows particle effect to everyone,
  # otherwise will only show to the player itself.
  Show-Particle-Effect-To-Everyone: true
  # Set to true will shows cloak effect to everyone,
  # otherwise will only show to the player itself.
  Show-Cloak-Effect-To-Everyone: true
  # Set to true will hide particle effect for vanished player.
  Hide-Particle-Effect-For-Vanished-Player: true
  # Set to true will hide cloak effect for vanished player.
  Hide-Cloak-Effect-For-Vanished-Player: true
  # Do action when player equip cosmetic.
  # Equip Type: REPLACE, WARN, DROP
  # Replace: Replace the old item with equipped cosmetic.
  # Warn: Send a warning message to the player and reject to equip cosmetic.
  # Drop: Drop the old item on the ground and equip cosmetic.
  Equip-Cosmetic-Item-To-Slot: WARN
  # Sync player's selected cosmetics when they join the server.
  Sync-Cosmetics-On-Join: true

# The menu selector settings.
Menu-Item:
  # The name of the selector.
  Name: '&aGadgetsMenu'
  # The material of the selector.
  # Material: https://gadgetsmenu.net/wiki/others/material-syntax
  Material: NETHER_STAR
  # Slot: 0-8
  Slot: 4
  # Should give player menu selector when they join the server.
  Give-On-Join: true
  # The way to open menu selector.
  # Click Type: LEFT, RIGHT, LEFT_AND_RIGHT
  Click-Type: LEFT_AND_RIGHT
  # Set to true allows player to move menu selector to another slot.
  Able-To-Move: false
  Lore:
  - '&7Mystery Dust: &b{MYSTERY_DUST}'
  - ''
  - '&7Enjoy fun cosmetic features!'
  - '&7More stuff will be added over time,'
  - '&7make sure to check our update forums!'
  - '&7Thanks you for supporting our server.'

# List of the worlds where cosmetics are enabled!
Enabled-Worlds:
- '*'
- world
- world_nether
- world_the_end

# List of the disabled cosmetics.
# Set to true to disable it.
Disabled-Cosmetics:
  Hats: false
  Animated Hats: false
  Particles: false
  Suits: false
  Gadgets: false
  Pets: false
  Miniatures: false
  Morphs: false
  Banners: false
  Emotes: false
  Cloaks: false

# Sync the last equipped cosmetics when player join the server.
Cosmetics-Sync-On-Join:
  Hats: true
  Animated Hats: true
  Particles: true
  Suits: true
  Gadgets: true
  Pets: true
  Miniatures: true
  Morphs: true
  Banners: true
  Emotes: true
  Cloaks: true

Permission:
  # When player doesn't have the permission of that item.
  No-Permission:
    # Set to true will show the lore.
    Show-In-Lore: false
    # Should close GUI menu when player selected 
    # an item which he doesn't have the permission.
    Close-GUI-Menu-After-Select: true
    Lore:
    - ''
    - '&7Status: &c&lLOCKED'
    # Set to true, will play sound 
    # when player select the item.
    #
    # Sounds: https://gadgetsmenu.net/wiki/others/sounds
    Play-Sound:
      Enabled: true
      Sound: ENTITY_ENDERMAN_TELEPORT
    Show-Custom-Item:
      Enabled: true
      Material: GRAY_DYE
 # When player have the permission of that item.
  Has-Permission:
    # Set to true will show the lore.
    Show-In-Lore: false
    Close-GUI-Menu-After-Select: true
    Lore:
    - ''
    - '&7Status: &a&lUNLOCKED'
    # Set to true, will play sound 
    # when player select the item.
    #
    # Sounds: https://gadgetsmenu.net/wiki/others/sounds
    Play-Sound:
      Enabled: true
      Sound: ENTITY_EXPERIENCE_ORB_PICKUP

# Discount the cost of an item when player purchase.
Item-Cost-Discount:
  # Set to true will enable item cost discount.
  Enabled: true
  # Which item do you want to enable item cost discount?
  Discount:
    Cosmetic-Item: true
    Crafting-Mystery-Box: true
  # You can add more discount rate by reference example.
  Discount-Rates:
    # The name of the discount group.
    # This name is use for placeholder to get the cost after discount.
    # Placeholder Syntax: {<name>_COST}
    # Example: The placeholder for 'Default' is {DEFAULT_COST}.
    # {COST}: Get the original price.
    # {COST_LEFT}: How many cost left you need.
    Default:
      # Higher numbers override lower number groups.
      Priority: 1
      # The permission to grant cost discount.
      Permission: gadgetsmenu.discount.default
      # Discount rates.
      # Range: 0 - 100
      # If you purchase an item with 100 cost and 20% off,
      # your final price will be 80.
      Rate: 0
      Lore:
        Enough-Mystery-Dust:
        - ''
        - "&aRegular&7: &a{COST} &7Mystery Dust! &e\u25C0"
        - '&cVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &a{DEFAULT_COST} &7Mystery Dust'
        - '&eClick to craft!'
        Not-Enough-Mystery-Dust:
        - ''
        - "&aRegular: {COST} Mystery Dust! &e\u25C0"
        - '&cVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &c{DEFAULT_COST} &7Mystery Dust'
        - '&cYou need &b{COST_LEFT} &cmore mystery dust!'
    VIP:
      Priority: 2
      Permission: gadgetsmenu.discount.VIP
      Rate: 20
      Lore:
        Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - "&aVIP&7: &a{VIP_COST} &7Mystery Dust (&a20% &7OFF!) &e\u25C0"
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &a{VIP_COST} &7Mystery Dust'
        - '&eClick to craft!'
        Not-Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - "&aVIP&7: &a{VIP_COST} &7Mystery Dust (&a20% &7OFF!) &e\u25C0"
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &c{VIP_COST} &7Mystery Dust'
        - '&cYou need &b{COST_LEFT} &cmore mystery dust!'
    MVP:
      Priority: 3
      Permission: gadgetsmenu.discount.MVP
      Rate: 40
      Lore:
        Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - '&8&mVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - "&bMVP&7: &a{MVP_COST} &7Mystery Dust (&a40% &7OFF!) &e\u25C0"
        - ''
        - '&7Your Cost: &a{MVP_COST} &7Mystery Dust'
        - '&eClick to craft!'
        Not-Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - '&8&mVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - "&bMVP&7: &a{MVP_COST} &7Mystery Dust (&a40% &7OFF!) &e\u25C0"
        - ''
        - '&7Your Cost: &a{MVP_COST} &7Mystery Dust'
        - '&cYou need &b{COST_LEFT} &cmore mystery dust!'

# When player clicks 'Go Back' button will execute these commands.
# If you enabled this option, it won't open the main menu of GadgetsMenu.
# Placeholders: {PLAYER}
Back-To-Main-Menu:
  Execute-Commands:
    Enabled: false
    Commands:
    - cc open menu.yml {PLAYER}

# Set to true will fill the blank slots of inventories with the item you set.
Fill-Empty-Slot-With-Item:
  Enabled: false
  Material: BLACK_STAINED_GLASS_PANE

# List of commands that won't work when equip a cosmetic.
# Type commands in lowercase without slashes.
Disabled-Commands:
- hat
- ah sell
- cmi hat
- 'cmi:cmi hat'

# Anti Lag System.
# Activate these actions if server TPS is below the minimum TPS.
Anti-Lag:
  Enabled: true
  Minimum-TPS: 17
  Action:
    # Unequip online players cosmetics.
    Clear-Cosmetics: true
    # Disable the usage of cosmetics.
    Disable-Usage: true

# Blacklisted region
# Disable cosmetic usage in the configured regions.
# Require WorldGuard plugin.
Blacklisted-Region:
  Enabled: true
  # Set 'Reverse-Whitelist' as true will change to whitelisted region.
  # Whitelisted region: Enable cosmetic usage only in the configured regions.
  Reverse-Whitelist: false
  # Format: [region_id]:[world_name|*]
  # Example: region:world1
  Region:
    All-Cosmetics:
    - region1:*
    - region2:world1
    - region3:world2
    Hats: ''
    Animated-Hats: ''
    Particles: ''
    Suits: ''
    Gadgets: ''
    Pets: ''
    Miniatures: ''
    Morphs: ''
    Banners: ''
    Emotes: ''
    Cloaks: ''
    Pet-Riding: ''

# Check for updates if you set to true.
Check-Update: true

# Do not edit this.
Config-Version: 2.0.8
```

## Frequently asked questions

### How can I disable a certain cosmetic item?
You can disable the cosmetic item in the corresponding files which located in `/GadgetsMenu/categories` folder.

In the following sample, will be using `hats.yml` file to demonstrate how to disable a certain cosmetic item. 

Simply set the `Enabled` property to `false` will disable the cosmetic item. Player will no longer be able to equip this cosmetic item and can't find this cosmetic item from Mystery Box.
```yaml
# Don't change this!
Hamburger:
  ...
  # Is it enabled?
  Enabled: true
  ...
```

### How can I disable specific cosmetic item to be found in Mystery Box?
You can disable finding specific cosmetic item in Mystery Box in the corresponding files which located in `/GadgetsMenu/categories` folder.

In the following sample, will be using `hats.yml` file to demonstrate how to disable specific cosmetic item to be found in Mystery Box. 

Simply set the `CanBeFound` property to `false` to disable the cosmetic from being found in the Mystery Box.
```yaml
# Don't change this!
Hamburger:
  ...
  # Can this item be found in mystery box?
  CanBeFound: true
  ...
```

### How can I configure hex color in item display name?
You can implement hex color for display names and holograms in minecraft versions 1.16 and later.
 - **Syntax: `{#<hex color>}`**


**Examples:**
 - `{#FFFFFF}`, `{#000000}`

```yaml
Name: '{#FC5383}GadgetsMenu'
```

### What are the supported sounds that I can configure in GadgetsMenu?

You can find a list of all sound names [here](../wiki/others/sounds).
```
Play-Sound:
  Enabled: true
  Sound: ENTITY_ENDERMAN_TELEPORT
```