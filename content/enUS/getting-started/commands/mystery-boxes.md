---
title: Mystery Boxes Commands
description: In this page, you will find out the Mystery Boxes commands available in the plugin.
group: commands
keywords: Commands,Mystery Boxes,gmysterybox
topics:
 - Commands
 - Mystery Boxes
 - gmysterybox
---

Simply type **`/gmysterybox`** command in-game or in the console will print out a list of Mystery Boxes commands.

The argument syntax to be used in the command:
- **`<required>`** - indicates the argument is required to fill in.
- **`[optional]`** - indicates the argument is optional, not mandatory to fill in.

<br>

> **Tips:**
> 1. Point your cursor at in-game command description will display more details about the command.
> 2. You can use **Tab** key to automatic fill in the missing arguments.

## `/gmysteryboxes check [player]`

**Description:** Check player’s mystery boxes amount.

**Permission:** `gadgetsmenu.mysteryboxes.check`

**Aliases:** `lookup`

**Usable in Console:** Yes

## `/gmysteryboxes gift <player> <pack>`

**Description:** Give mystery gifts to a player. Each pack of mystery gift contains 5 mystery boxes.

**Permission:** `gadgetsmenu.mysteryboxes.gift`

**Aliases:** -

**Usable in Console:** Yes

**Arguments:**
- `msg=false` - Will not send message to the player when they receive mystery gifts.

**Examples:**
- `/gmysteryboxes gift Notch 1`
- `/gmysteryboxes gift Notch 1 msg=false` - Give mystery gifts to a player without sending any notification messages.

## `/gmysteryboxes give <player> <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false] c:(<quality>:<chances>)`

**Description:** Give mystery boxes to a player.

**Permission:** `gadgetsmenu.mysteryboxes.give`

**Aliases:** -

**Usable in Console:** Yes

**Arguments:**
- `<amount>` - Integer value.
- `[quality]` - Integer value between **1** to **5**.
- `[ex=7h/d/m/false]` - Indicates the expiry date of the Mystery Box.
   - **`h`** stands for hour(s).
   - **`d`** stands for day(s).
   - **`m`** stands for month(s).
   - **`false`** stands for no expiry date.
- `[reqperm=false]` - Boolean value(true/false). Set to true indicate player require permission before opening the Mystery Box. The default value is true if not specified.
- `c:(<quality>:<chances>)` - Custom chances quality of mystery boxes when the quality argument is not specified.

   **Description:**  
   - The quality of the Mystery Box followed by the chances to get it.
   - Please note that you must fill in all available qualities (1 - 5). Missing one will throw an error.
   - The total chances among all qualities can be greater than 100 or less than 100.

**Examples:**
- `/gmysteryboxes give Notch 1` - Give player 1 Mystery Box with random quality.
- `/gmysteryboxes give Notch 1 5` - Give player a 5-star Mystery Box.
- `/gmysteryboxes give Notch 1 5 ex=3d` - Give player a 5-star Mystery Box with 3 days expiration.
- `/gmysteryboxes give Notch 1 5 msg=false` - Give Mystery Box to a player without sending any notification messages.
- `/gmysteryboxes give Notch 1 c:(1:40,2:30,3:25,4:15,5:10)` - 40% chance to get 1-star Mystery Box, 30% chance to get 2-star Mystery Box...and so on.

## `/gmysteryboxes giveall <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false]`

**Description:** Give all online players mystery boxes.

**Permission:** `gadgetsmenu.mysteryboxes.giveall`

**Aliases:** `ga`

**Usable in Console:** Yes

**Arguments:**
- `<amount>` - Integer value.
- `[quality]` - Integer value between **1** to **5**.
- `[ex=7h/d/m/false]` - Indicates the expiry date of the Mystery Box.
   - **`h`** stands for hour(s).
   - **`d`** stands for day(s).
   - **`m`** stands for month(s).
   - **`false`** stands for no expiry date.
- `[reqperm=false]` - Boolean value(true/false). Set to true indicate player require permission before opening the Mystery Box. The default value is true if not specified.
- `c:(<quality>:<chances>)` - Custom chances quality of mystery boxes when the quality argument is not specified.

   **Description:** 
   - The quality of the Mystery Box followed by the chances to get it.
   - Please note that you must fill in all available qualities (1 - 5). Missing one will throw an error.
   - The total chances among all qualities can be greater than 100 or less than 100.

**Examples:**
- `/gmysteryboxes giveall 1` - Give all online players 1 Mystery Box with random quality.
- `/gmysteryboxes giveall 1 5` - Give all online players a 5-star Mystery Box.
- `/gmysteryboxes giveall 1 5 ex=3d` - Give all online players a 5-star Mystery Box with 3 days expiration.
- `/gmysteryboxes giveall 1 5 msg=false` - Give Mystery Box to all online players without sending any notification messages.
- `/gmysteryboxes giveall 1 c:(1:40,2:30,3:25,4:15,5:10)` - 40% chance to get 1-star Mystery Box, 30% chance to get 2-star Mystery Box...and so on.

## `/gmysteryboxes mode`

**Description:** Shows the commands to manipulate the mystery vault.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** `setup` `edit`

**Usable in Console:** No

## `/gmysteryboxes mode add-vault <vaultName>`

**Description:** Create a mystery vault by looking at a block.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** `create`

**Usable in Console:** No

## `/gmysteryboxes mode info <vaultName>`

**Description:** Show the info of the mystery vault.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** `information`

**Usable in Console:** No

## `/gmysteryboxes mode list`

**Description:** List all available mystery vaults.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** -

**Usable in Console:** No

## `/gmysteryboxes mode near <radius>`

**Description:** Get a list of nearby mystery vault.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** -

**Usable in Console:** No

## `/gmysteryboxes mode redefine <vaultName>`

**Description:** Redefine mystery vault location.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** `relocate`

**Usable in Console:** No

## `/gmysteryboxes mode remove-vault [vaultName|r:{radius}]`

**Description:** Remove a mystery vault by looking at the mystery vault or specifing the mystery vault name.

**Permission:** `gadgetsmenu.mysteryboxes.mode`

**Aliases:** `remove`

**Usable in Console:** No

## `/gmysteryboxes mode teleport <vaultName>`

**Description:** Teleport player to the given mystery vault.

**Permission:** gadgetsmenu.mysteryboxes.mode

**Aliases:** tp

**Usable in Console:** No