---
title: 神秘箱命令
description: 在本页中，您将了解插件中可用的神秘箱命令。
group: commands
keywords: 命令,神秘箱,gmysterybox
topics:
 - 命令
 - 神秘箱
 - gmysterybox
---

只需在游戏内或控制台中输入 **`/gmysterybox`** 命令，即可列出所有神秘箱命令。

命令中所使用的参数语法：
- **`<required>`** - 表示该参数为必填项。
- **`[optional]`** - 表示该参数为可选项，并非必须填写。

<br>

> **提示：**
> 1. 将光标指向游戏内的命令说明，可以显示该命令的更多详情。
> 2. 您可以使用 **Tab** 键自动补全缺少的参数。

## `/gmysteryboxes check [player]`

**说明：** 查看玩家的神秘箱数量。

**权限：** `gadgetsmenu.mysteryboxes.check`

**别名：** `lookup`

**可在控制台使用：** 是

## `/gmysteryboxes gift <player> <pack>`

**说明：** 向玩家赠送神秘礼物。每份神秘礼物礼包中包含 5 个神秘箱。

**权限：** `gadgetsmenu.mysteryboxes.gift`

**别名：** -

**可在控制台使用：** 是

**参数：**
- `msg=false` - 玩家获得神秘礼物时不会向其发送消息。

**示例：**
- `/gmysteryboxes gift Notch 1`
- `/gmysteryboxes gift Notch 1 msg=false` - 向玩家赠送神秘礼物，且不发送任何提示消息。

## `/gmysteryboxes give <player> <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false] c:(<quality>:<chances>)`

**说明：** 向玩家发放神秘箱。

**权限：** `gadgetsmenu.mysteryboxes.give`

**别名：** -

**可在控制台使用：** 是

**参数：**
- `<amount>` - 整数值。
- `[quality]` - **1** 到 **5** 之间的整数值。
- `[ex=7h/d/m/false]` - 表示神秘箱的过期时间。
   - **`h`** 代表小时。
   - **`d`** 代表天。
   - **`m`** 代表月。
   - **`false`** 代表没有过期时间。
- `[reqperm=false]` - 布尔值（true/false）。设置为 true 表示玩家在开启神秘箱之前需要拥有相应权限。如果未指定，默认值为 true。
- `c:(<quality>:<chances>)` - 当未指定 quality 参数时，神秘箱品质的自定义几率。

   **说明：**  
   - 神秘箱的品质，后面跟着获得该品质的几率。
   - 请注意，您必须填写所有可用的品质（1 - 5）。缺少任何一项都会引发错误。
   - 所有品质的几率总和可以大于 100，也可以小于 100。

**示例：**
- `/gmysteryboxes give Notch 1` - 向玩家发放 1 个随机品质的神秘箱。
- `/gmysteryboxes give Notch 1 5` - 向玩家发放 1 个 5 星神秘箱。
- `/gmysteryboxes give Notch 1 5 ex=3d` - 向玩家发放 1 个 3 天后过期的 5 星神秘箱。
- `/gmysteryboxes give Notch 1 5 msg=false` - 向玩家发放神秘箱，且不发送任何提示消息。
- `/gmysteryboxes give Notch 1 c:(1:40,2:30,3:25,4:15,5:10)` - 40% 的几率获得 1 星神秘箱，30% 的几率获得 2 星神秘箱……以此类推。

## `/gmysteryboxes giveall <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false]`

**说明：** 向所有在线玩家发放神秘箱。

**权限：** `gadgetsmenu.mysteryboxes.giveall`

**别名：** `ga`

**可在控制台使用：** 是

**参数：**
- `<amount>` - 整数值。
- `[quality]` - **1** 到 **5** 之间的整数值。
- `[ex=7h/d/m/false]` - 表示神秘箱的过期时间。
   - **`h`** 代表小时。
   - **`d`** 代表天。
   - **`m`** 代表月。
   - **`false`** 代表没有过期时间。
- `[reqperm=false]` - 布尔值（true/false）。设置为 true 表示玩家在开启神秘箱之前需要拥有相应权限。如果未指定，默认值为 true。
- `c:(<quality>:<chances>)` - 当未指定 quality 参数时，神秘箱品质的自定义几率。

   **说明：** 
   - 神秘箱的品质，后面跟着获得该品质的几率。
   - 请注意，您必须填写所有可用的品质（1 - 5）。缺少任何一项都会引发错误。
   - 所有品质的几率总和可以大于 100，也可以小于 100。

**示例：**
- `/gmysteryboxes giveall 1` - 向所有在线玩家发放 1 个随机品质的神秘箱。
- `/gmysteryboxes giveall 1 5` - 向所有在线玩家发放 1 个 5 星神秘箱。
- `/gmysteryboxes giveall 1 5 ex=3d` - 向所有在线玩家发放 1 个 3 天后过期的 5 星神秘箱。
- `/gmysteryboxes giveall 1 5 msg=false` - 向所有在线玩家发放神秘箱，且不发送任何提示消息。
- `/gmysteryboxes giveall 1 c:(1:40,2:30,3:25,4:15,5:10)` - 40% 的几率获得 1 星神秘箱，30% 的几率获得 2 星神秘箱……以此类推。

## `/gmysteryboxes mode`

**说明：** 显示用于管理神秘宝库的命令。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** `setup` `edit`

**可在控制台使用：** 否

## `/gmysteryboxes mode add-vault <vaultName>`

**说明：** 通过注视某个方块来创建神秘宝库。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** `create`

**可在控制台使用：** 否

## `/gmysteryboxes mode info <vaultName>`

**说明：** 显示该神秘宝库的信息。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** `information`

**可在控制台使用：** 否

## `/gmysteryboxes mode list`

**说明：** 列出所有可用的神秘宝库。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** -

**可在控制台使用：** 否

## `/gmysteryboxes mode near <radius>`

**说明：** 获取附近神秘宝库的列表。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** -

**可在控制台使用：** 否

## `/gmysteryboxes mode redefine <vaultName>`

**说明：** 重新定义神秘宝库的位置。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** `relocate`

**可在控制台使用：** 否

## `/gmysteryboxes mode remove-vault [vaultName|r:{radius}]`

**说明：** 通过注视神秘宝库或指定神秘宝库名称来移除神秘宝库。

**权限：** `gadgetsmenu.mysteryboxes.mode`

**别名：** `remove`

**可在控制台使用：** 否

**示例：**
- `/gmysteryboxes mode remove-vault` - 通过注视神秘宝库来移除它。
- `/gmysteryboxes mode remove-vault vault_1` - 按名称移除指定的神秘宝库。
- `/gmysteryboxes mode remove-vault r:3` - 按半径移除附近的神秘宝库。

## `/gmysteryboxes mode teleport <vaultName>`

**说明：** 将玩家传送到指定的神秘宝库。

**权限：** gadgetsmenu.mysteryboxes.mode

**别名：** tp

**可在控制台使用：** 否
