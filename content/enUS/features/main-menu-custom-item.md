---
title: Main Menu Custom Item
description: You can create custom items in the main menu to navigate the players to your custom GUI menus.
group: features
keywords: main menu custom item, custom item
topics:
 - main menu custom item
 - custom item
---

>**Note:** This feature is currently only available in GadgetsMenu Premium.

The custom items can be configured in `categories/mainmenu.yml` file at `Custom-Items` section.
```yaml
Custom-Items:
  # You can add as many custom items as you like.
  Item-1:
    # Item display name.
    Name: '&eCustom Item 1'

    # Refer material syntax page for more details.
    Material: BOOK

    # Boolean value: true/false
    Enabled: true

    # Available slots: 0 - 53
    Slot: 4

    # Command Type: CONSOLE, PLAYER
    # CONSOLE: Command will be executed from console side.
    # PLAYER: Command will be executed from player side. Player need to have the permission in order to execute the command.

    # Placeholder: {PLAYER} or any placeholders supported by PlaceholderAPI

    # Syntax: <command type>:<command|player action>
    Commands:
    - CONSOLE:say {PLAYER} is clicking Custom Item 1.
    - PLAYER:say I'm clicking Custom Item 1.

    # Item lore.
    Lore:
    - '&7This is the custom item lore.'
```

## Attributes

### Name

### Material

### Enabled

### Slot
```yaml
Slot: #
```

#### Multiple Slots
```yaml
Slots:
  - #
  - #
  - #

# or

Slots: 
  - #-#
  - #-#
  - #-#
```

### Commands

### Lore

## Type of Command
There are two types of commands that can be used to execute commands from different entities.
 - CONSOLE: The command is executed from the console. No permission is required from the player.
 - PLAYER: The command is executed by the player. The player is require to have the necessary permission in order to execute the command.


## Player Action
Apart from the general commands, there are some **Player Action** available to perform the custom actions which is not available through the commands.

 - `CLOSE_INVENTORY`: Close player's inventory menu.

More actions will be added in the future. Send us some suggestions if you have any.

### Example
The example below illustrate the commands to be executed when player click on that item. There are two commands setup for that item, first it will execute the `rewards claim daily` command to claim the daily rewards. Then, it will execute the player action `CLOSE_INVENTORY` to close the player's current opening GUI menu.

```yaml
Custom-Items:
  Item-1:
    Name: '&eCustom Item 1'
    Material: BOOK
    Enabled: true
    Slot: 2
    Commands:
    - PLAYER:rewards claim daily
    - PLAYER:CLOSE_INVENTORY
```

## Relevant content
<div class="md-relevant-content">

- [Material Syntax](../wiki/others/material-syntax)
- [Texture Head](../wiki/others/texture-head)
</div>
