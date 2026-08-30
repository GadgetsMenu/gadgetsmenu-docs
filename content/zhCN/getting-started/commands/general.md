---
title: 通用命令
description: 在本页中，您将了解插件中可用的通用命令。
group: commands
keywords: 命令,通用,gmenu
topics:
 - 命令
 - 通用
 - gmenu
---

只需在游戏内或控制台中输入 **`/gmenu help`** 命令，即可列出所有通用命令。

命令中所使用的参数语法：
- **`<required>`** - 表示该参数为必填项。
- **`[optional]`** - 表示该参数为可选项，并非必须填写。

<br>

> **提示：**
> 1. 将光标指向游戏内的命令说明，可以显示该命令的更多详情。
> 2. 您可以使用 **Tab** 键自动补全缺少的参数。

## `/gmenu about`

**说明：** 显示有关该插件的信息。

**权限：** `gadgetsmenu.commands.about`

**别名：** `info` `information` `version`

**可在控制台使用：** 是

## `/gmenu addperm <cosmetic> <type> <player>`

**说明：** 授予玩家使用化妆品的权限。

**权限：** `gadgetsmenu.commands.addpermission`

**别名：** `addpermission` `info` `ap`

**可在控制台使用：** 是

**示例：**
- `/gmenu addperm Gadget MobGun Notch`

## `/gmenu checkupdate`

**说明：** 检查该插件最新发布的版本。

**权限：** `gadgetsmenu.commands.checkupdate`

**别名：** `cupdate` `cu`

**可在控制台使用：** 是

## `/gmenu equip <cosmetic> <type> [player]`

**说明：** 为玩家装备指定的化妆品。

**权限：** `gadgetsmenu.commands.equip`

**别名：** -

**可在控制台使用：** 是

**示例：**
- `/gmenu equip Gadget MobGun`
- `/gmenu equip Gadget MobGun Notch`

## `/gmenu help [page]`

**说明：** 输出 GadgetsMenu 的帮助消息。

**权限：** `gadgetsmenu.commands.help`

**别名：** `h`

**可在控制台使用：** 是

## `/gmenu main`

**说明：** 打开主菜单。

**权限：** -（无需任何权限）

**别名：** -

**可在控制台使用：** 否

## `/gmenu menu <cosmetic> [page]`

**说明：** 打开指定的菜单。

**权限：** -（无需任何权限）

**别名：** `gui`

**可在控制台使用：** 否

**示例：**
- `/gmenu menu Hats`
- `/gmenu menu Hats 3`
- `/gmenu menu Particles 1`

## `/gmenu menuitem [player]`

**说明：** 向玩家发放菜单选择器。

**权限：** `gadgetsmenu.commands.menuitem`

**别名：** `menuselector` `mi`

**可在控制台使用：** 是

**示例：**
- `/gmenu menuitem Notch`

## `/gmenu migrate <confirm>`

**说明：** 将 SQLite 数据迁移到当前已连接的 MySQL 数据库。

**权限：** `gadgetsmenu.commands.migrate`

**可在控制台使用：** 是

## `/gmenu namepet <name>`

**说明：** 为您当前召唤的宠物命名。

**权限：** `gadgetsmenu.commands.namepet`

**别名：** `renamepet`

**可在控制台使用：** 是

**示例：**
- `/gmenu namepet &cWosh`
- `/gmenu namepet &eMy &cPet &bName`

## `/gmenu permission <cosmetic|commands> [page]`

**说明：** 提供所有权限的列表。

**权限：** `gadgetsmenu.commands.permission`

**别名：** `permissions` `perm`

**可在控制台使用：** 是

**示例：**
- `/gmenu permission commands`
- `/gmenu permission Hats`
- `/gmenu permission Hats 2`
- `/gmenu permission Particles`

## `/gmenu petitems`

**说明：** 管理玩家的宠物物品。

**权限：** `gadgetsmenu.commands.petitems`

**别名：** `petitems` `pi`

**可在控制台使用：** 是

**子命令：**
- `/gmenu petitems add <item> <player> <amount>`
- `/gmenu petitems check <player>`
- `/gmenu petitems remove <item> <player> <amount>`
- `/gmenu petitems set <player> <amount>`

**示例：**
- `/gmenu petitems add Apple Notch 10`
- `/gmenu petitems check Notch`
- `/gmenu petitems remove Water Notch 3`
- `/gmenu petitems set Stick Notch 25`

## `/gmenu reload <confirm>`

**说明：** 重载该插件。

**权限：** `gadgetsmenu.commands.reload`

**别名：** `rl`

**可在控制台使用：** 是

>[Warning] {{title: 警告}} 使用此命令风险自负！它可能导致漏洞和内存泄漏。

## `/gmenu removeperm <cosmetic> <type> <player>`

**说明：** 移除玩家使用化妆品的权限。

**权限：** `gadgetsmenu.commands.removepermission`

**别名：** `removeperm` `rp`

**可在控制台使用：** 是

**示例：**
- `/gmenu removeperm Emote RIP Notch`

## `/gmenu reset <all|cosmetic> <all|player>`

**说明：** 重置当前已激活的化妆品。

**权限：** `gadgetsmenu.commands.reset`

**别名：** `remove` `unequip`

**可在控制台使用：** 是

**示例：**
- `/gmenu reset all all` - 重置所有在线玩家的全部化妆品。
- `/gmenu reset Hat Notch` - 重置玩家 Notch 的帽子化妆品。
- `/gmenu reset all Notch` - 重置玩家 Notch 的全部化妆品。

## `/gmenu settings <setting> <value>`

**说明：** 修改个人设置。

**权限：** `gadgetsmenu.commands.settings`

**别名：** `settings`

**可在控制台使用：** 否

**设置项：** `bypasscooldown` `selfmorphview`

**示例：**
- `/gmenu settings bypasscooldown true`
- `/gmenu settings bypasscooldown false`
- `/gmenu settings selfmorphview true`
- `/gmenu settings selfmorphview false`

## `/gmenu status <player>`

**说明：** 查看玩家的数据。

**权限：** `gadgetsmenu.commands.status`

**别名：** `check`

**可在控制台使用：** 是

**示例：**
- `/gmenu status Notch`
