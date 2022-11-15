---
title: Mystery Dust Commands
description: In this page, you will find out the Mystery Dust commands available in the plugin.
group: commands
keywords: Commands,Mystery Dust,mysterydust
topics:
 - Commands
 - Mystery Dust
 - mysterydust
---

Simply type **`/mysterydust`** command in-game or in the console will print out a list of Mystery Dust commands.

The argument syntax to be used in the command:
- **`<required>`** - indicates the argument is required to fill in.
- **`[optional]`** - indicates the argument is optional, not mandatory to fill in.

<br>

> **Tips:**
> 1. Point your cursor at in-game command description will display more details about the command.
> 2. You can use **Tab** key to automatic fill in the missing arguments.

## `/mysterydust add <player|all> <amount>`

**Description:** Add mystery dust to a player.

**Permission:** `gadgetsmenu.mysterydust.add`

**Aliases:** `give`

**Usable in Console:** Yes

**Arguments:**
- `msg=false` - Will not send message to the player when they receive mystery dust.

**Example:**
- `/mysterydust add Notch 100`
- `/mysterydust add all 100` - Add mystery dust to all online players.
- `/mysterydust add Notch 100 msg=false` - Add mystery dust to a player without sending any notification messages.

## `/mysterydust check [player]`

**Description:** Check current mystery dust of a player.

**Permission:** `gadgetsmenu.mysterydust.check`

**Aliases:** -

**Usable in Console:** Yes

**Example:**
- `/mysterydust check Notch`

## `/mysterydust pay <player> <amount>`

**Description:** Transfer mystery dust to a player.

**Permission:** `gadgetsmenu.mysterydust.pay`

**Aliases:** `transfer`

**Usable in Console:** No

**Arguments:**
- `msg=false` - Will not send message to the player when they receive mystery dust.

**Example:**
- `/mysterydust pay Notch 100`
- `/mysterydust pay Notch 100 msg=false` - Transfer mystery dust to a player without sending any notification messages.

## `/mysterydust remove <player> <amount>`

**Description:** Remove mystery dust from a player.

**Permission:** `gadgetsmenu.mysterydust.remove`

**Aliases:** -

**Usable in Console:** Yes

**Arguments:**
- `msg=false` - Will not send message to the player when their mystery dust has been removed.

**Example:**
- `/mysterydust remove Notch 100`
- `/mysterydust remove Notch 100 msg=false` - Remove mystery dust from a player without sending any notification messages.

## `/mysterydust set <player> <amount>`

**Description**: Sets a player’s mystery dust.

**Permission**: `gadgetsmenu.mysterydust.set`

**Aliases**: -

**Usable in Console**: Yes

**Arguments:**
- `msg=false` - Will not send message to the player when their mystery dust has been changed.

**Example:**
- `/mysterydust set Notch 100`
- `/mysterydust set Notch 100 msg=false` - Sets a player’s mystery dust without sending any notification messages.