---
title: 主菜单自定义物品
description: 您可以在主菜单中创建自定义物品，将玩家引导至您自己的 GUI 菜单。
group: features
keywords: 主菜单自定义物品, 自定义物品
topics:
 - 主菜单自定义物品
 - 自定义物品
---

>**注意：** 此功能目前仅在 GadgetsMenu 高级版中提供。

自定义物品可以在 `categories/mainmenu.yml` 文件的 `Custom-Items` 部分中进行配置。
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

## 属性

### Name
```yaml
# Item display name.
Name: '&eCustom Item 1'
```

### Material
```yaml
# Refer material syntax page for more details.
Material: BOOK
```

### Enabled
```yaml
# Boolean value: true/false
Enabled: true
```

### Slot
```yaml
Slot: #
```

#### 多个槽位
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
```yaml
# Command Type: CONSOLE, PLAYER
# CONSOLE: Command will be executed from console side.
# PLAYER: Command will be executed from player side. Player need to have the permission in order to execute the command.

# Placeholder: {PLAYER} or any placeholders supported by PlaceholderAPI

# Syntax: <command type>:<command|player action>
Commands:
- CONSOLE:say {PLAYER} is clicking Custom Item 1.
- PLAYER:say I'm clicking Custom Item 1.
```

### Lore

## 命令类型
共有两种命令类型，可用于以不同的身份执行命令。
 - CONSOLE：命令由控制台执行。玩家无需任何权限。
 - PLAYER：命令由玩家执行。玩家需要拥有相应的权限才能执行该命令。


## 玩家动作
除了常规命令之外，还有一些**玩家动作**可用于执行那些无法通过命令实现的自定义操作。

 - `CLOSE_INVENTORY`：关闭玩家的物品栏菜单。

未来还会加入更多动作。如果您有任何建议，欢迎告诉我们。

### 示例
下面的示例演示了玩家点击该物品时将要执行的命令。该物品设置了两条命令，首先会执行 `rewards claim daily` 命令来领取每日奖励。然后，会执行玩家动作 `CLOSE_INVENTORY` 来关闭玩家当前打开的 GUI 菜单。

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

## 相关内容
<div class="md-relevant-content">

- [材料语法](../wiki/others/material-syntax)
- [头颅材质](../wiki/others/texture-head)
</div>
