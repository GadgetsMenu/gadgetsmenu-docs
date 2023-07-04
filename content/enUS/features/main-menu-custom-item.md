---
title: Main Menu Custom Item
description: -
group: features
keywords: main menu custom item, custom item
topics:
 - main menu custom item
 - custom item
---



```yaml
Custom-Items:
  # You can add as many custom items as you like.
  Item-1:
    Name: '&eCustom Item 1'
    Material: BOOK
    Enabled: true
    Slot: 4
    # Command Type: CONSOLE, PLAYER
    # CONSOLE: Command will be executed from console side.
    # PLAYER: Command will be executed from player side. Player need to have the permission in order to execute the command.
    # Placeholder: {PLAYER}
    Commands:
    - CONSOLE:say {PLAYER} is clicking Custom Item 1.
    - PLAYER:say I'm clicking Custom Item 1.
    Lore:
    - '&7This is the custom item lore.'
```

## Commands

CONSOLE, PLAYER

### Player Action
- `CLOSE_INVENTORY`

```yaml
Custom-Items:
  Item-1:
    Name: '&eCustom Item 1'
    Material: BOOK
    Enabled: true
    Slot: 2
    Commands:
    - PLAYER:gmenu menu emotes
    - PLAYER:CLOSE_INVENTORY
```