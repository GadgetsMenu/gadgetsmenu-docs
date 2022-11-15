---
title: General Commands
description: In this page, you will find out the General commands available in the plugin.
group: commands
keywords: Commands,General,gmenu
topics:
 - Commands
 - General
 - gmenu
---

Simply type **`/gmenu help`** command in-game or in the console will print out a list of general commands.

The argument syntax to be used in the command:
- **`<required>`** - indicates the argument is required to fill in.
- **`[optional]`** - indicates the argument is optional, not mandatory to fill in.

<br>

> **Tips:**
> 1. Point your cursor at in-game command description will display more details about the command.
> 2. You can use **Tab** key to automatic fill in the missing arguments.

## `/gmenu about`

**Description:** Display information about the plugin.

**Permission:** `gadgetsmenu.commands.about`

**Aliases:** `info` `information` `version`

**Usable in Console:** Yes

## `/gmenu addperm <cosmetic> <type> <player>`

**Description:** Give player's permission to access cosmetic items.

**Permission:** `gadgetsmenu.commands.addpermission`

**Aliases:** `addpermission` `info` `ap`

**Usable in Console:** Yes

**Example:**
- `/gmenu addperm Gadget MobGun Notch`

## `/gmenu checkupdate`

**Description:** Check latest released version of the plugin.

**Permission:** `gadgetsmenu.commands.checkupdate`

**Aliases:** `cupdate` `cu`

**Usable in Console:** Yes

## `/gmenu equip <cosmetic> <type> [player]`

**Description:** Equip the cosmetic specified for the player.

**Permission:** `gadgetsmenu.commands.equip`

**Aliases:** -

**Usable in Console:** Yes

**Example:**
- `/gmenu equip Gadget MobGun`
- `/gmenu equip Gadget MobGun Notch`

## `/gmenu help [page]`

**Description:** Prints GadgetsMenu help message.

**Permission:** `gadgetsmenu.commands.help`

**Aliases:** `h`

**Usable in Console:** Yes

## `/gmenu main`

**Description:** Bring up main menu.

**Permission:** - (No permission is required)

**Aliases:** -

**Usable in Console:** No

## `/gmenu menu <cosmetic> [page]`

**Description:** Bring up specified menu.

**Permission:** - (No permission is required)

**Aliases:** `gui`

**Usable in Console:** No

**Example:**
- `/gmenu menu Hats`
- `/gmenu menu Hats 3`
- `/gmenu menu Particles 1`

## `/gmenu menuitem [player]`

**Description:** Give a player menu selector.

**Permission:** `gadgetsmenu.commands.menuitem`

**Aliases:** `menuselector` `mi`

**Usable in Console:** Yes

**Example:**
- `/gmenu menuitem Notch`

## `/gmenu migrate <confirm>`

**Description:** Migrate SQLite data to the current connected MySQL database.

**Permission:** `gadgetsmenu.commands.migrate`

**Usable in Console:** Yes

## `/gmenu namepet <name>`

**Description:** Name your current summoned pet.

**Permission:** `gadgetsmenu.commands.namepet`

**Aliases:** `renamepet`

**Usable in Console:** Yes

**Example:**
- `/gmenu namepet &cWosh`
- `/gmenu namepet &eMy &cPet &bName`

## `/gmenu permission <cosmetic|commands> [page]`

**Description:** Provide a list of all permissions.

**Permission:** `gadgetsmenu.commands.permission`

**Aliases:** `permissions` `perm`

**Usable in Console:** Yes

**Example:**
- `/gmenu permission commands`
- `/gmenu permission Hats`
- `/gmenu permission Hats 2`
- `/gmenu permission Particles`

## `/gmenu petitems`

**Description:** Manage player’s pet items.

**Permission:** `gadgetsmenu.commands.petitems`

**Aliases:** `petitems` `pi`

**Usable in Console:** Yes

**Sub Commands:**
- `/gmenu petitems add <item> <player> <amount>`
- `/gmenu petitems check <player>`
- `/gmenu petitems remove <item> <player> <amount>`
- `/gmenu petitems set <player> <amount>`

**Example:**
- `/gmenu petitems add Apple Notch 10`
- `/gmenu petitems check Notch`
- `/gmenu petitems remove Water Notch 3`
- `/gmenu petitems set Stick Notch 25`

## `/gmenu reload <confirm>`

**Description:** Reload the plugin.

**Permission:** `gadgetsmenu.commands.reload`

**Aliases:** `rl`

**Usable in Console:** Yes

>[Warning] {{title: Warning}} Use this command in your own risk! It might cause bugs and memory leaks.

## `/gmenu removeperm <cosmetic> <type> <player>`

**Description:** Remove the permission to access cosmetic item from a player.

**Permission:** `gadgetsmenu.commands.removepermission`

**Aliases:** `removeperm` `rp`

**Usable in Console:** Yes

**Example:**
- `/gmenu removeperm Emote RIP Notch`

## `/gmenu reset <all|cosmetic> <all|player>`

**Description:** Reset active cosmetics.

**Permission:** `gadgetsmenu.commands.reset`

**Aliases:** `remove` `unequip`

**Usable in Console:** Yes

**Example:**
- `/gmenu reset all all` - Reset all cosmetics for all online players.
- `/gmenu reset Hat Notch` - Reset cosmetic Hat for player Notch.
- `/gmenu reset all Notch` - Reset all cosmetics for player Notch.

## `/gmenu settings <setting> <value>`

**Description:** Modify personal settings.

**Permission:** `gadgetsmenu.commands.settings`

**Aliases:** `settings`

**Usable in Console:** No

**Settings:** `bypasscooldown` `selfmorphview`

**Example:**
- `/gmenu settings bypasscooldown true`
- `/gmenu settings bypasscooldown false`
- `/gmenu settings selfmorphview true`
- `/gmenu settings selfmorphview false`

## `/gmenu status <player>`

**Description:** Check player's data.

**Permission:** `gadgetsmenu.commands.status`

**Aliases:** `check`

**Usable in Console:** Yes

**Example:**
- `/gmenu status Notch`