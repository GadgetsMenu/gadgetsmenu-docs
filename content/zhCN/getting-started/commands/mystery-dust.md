---
title: Mystery Dust 命令
description: 在本页中，您将了解插件中可用的 Mystery Dust 命令。
group: commands
keywords: 命令,Mystery Dust,mysterydust
topics:
 - 命令
 - Mystery Dust
 - mysterydust
---

只需在游戏内或控制台中输入 **`/mysterydust`** 命令，即可列出所有 Mystery Dust 命令。

命令中所使用的参数语法：
- **`<required>`** - 表示该参数为必填项。
- **`[optional]`** - 表示该参数为可选项，并非必须填写。

<br>

> **提示：**
> 1. 将光标指向游戏内的命令说明，可以显示该命令的更多详情。
> 2. 您可以使用 **Tab** 键自动补全缺少的参数。

## `/mysterydust add <player|all> <amount>`

**说明：** 向玩家添加 Mystery Dust。

**权限：** `gadgetsmenu.mysterydust.add`

**别名：** `give`

**可在控制台使用：** 是

**参数：**
- `msg=false` - 玩家获得 Mystery Dust 时不会向其发送消息。

**示例：**
- `/mysterydust add Notch 100`
- `/mysterydust add all 100` - 向所有在线玩家添加 Mystery Dust。
- `/mysterydust add Notch 100 msg=false` - 向玩家添加 Mystery Dust，且不发送任何提示消息。

## `/mysterydust check [player]`

**说明：** 查看玩家当前的 Mystery Dust。

**权限：** `gadgetsmenu.mysterydust.check`

**别名：** -

**可在控制台使用：** 是

**示例：**
- `/mysterydust check Notch`

## `/mysterydust pay <player> <amount>`

**说明：** 将 Mystery Dust 转账给玩家。

**权限：** `gadgetsmenu.mysterydust.pay`

**别名：** `transfer`

**可在控制台使用：** 否

**参数：**
- `msg=false` - 玩家获得 Mystery Dust 时不会向其发送消息。

**示例：**
- `/mysterydust pay Notch 100`
- `/mysterydust pay Notch 100 msg=false` - 将 Mystery Dust 转账给玩家，且不发送任何提示消息。

## `/mysterydust remove <player> <amount>`

**说明：** 从玩家处移除 Mystery Dust。

**权限：** `gadgetsmenu.mysterydust.remove`

**别名：** -

**可在控制台使用：** 是

**参数：**
- `msg=false` - 玩家的 Mystery Dust 被移除时不会向其发送消息。

**示例：**
- `/mysterydust remove Notch 100`
- `/mysterydust remove Notch 100 msg=false` - 从玩家处移除 Mystery Dust，且不发送任何提示消息。

## `/mysterydust set <player> <amount>`

**说明**：设置玩家的 Mystery Dust。

**权限**：`gadgetsmenu.mysterydust.set`

**别名**：-

**可在控制台使用**：是

**参数：**
- `msg=false` - 玩家的 Mystery Dust 被更改时不会向其发送消息。

**示例：**
- `/mysterydust set Notch 100`
- `/mysterydust set Notch 100 msg=false` - 设置玩家的 Mystery Dust，且不发送任何提示消息。
