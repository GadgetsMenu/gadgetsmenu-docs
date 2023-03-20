---
title: Frequently Asked Questions
description: You can find answers to whatever you come across. Your question may have been asked and answered in this page.
group: getting-started
keywords: frequently asked questions,faq
topics:
 - frequently asked questions
 - faq
---

These are some of the common questions where user frequently ask. Please check if your question has been answered here before asking for help.

If your issue still persist after went through this page, you may join our [Discord](https://discord.gadgetsmenu.net/) server for support.

## Why is GadgetsMenu not working on my server?

### I received "`You don't have permission to do that in this world!`" message when I execute GadgetsMenu's command.

What you need to do is just to setup the worlds where you want to enable GadgetsMenu usage.

Look for `Enabled-Worlds` in `config.yml` file and add in the world's name in the listing.

**`'*'`** symbol indicates all worlds. This means GadgetsMenu will be entirely available in all worlds.

```yaml
# List of the worlds where cosmetics are enabled!
Enabled-Worlds:
- '*'
- world
- world_nether
- world_the_end
```

## Why my GadgetsMenu does not have Morphs?

GadgetsMenu does not come with built-in Morphs feature, it requires a mob disguise plugin to to provide morphing support.

Therefore, you need to download one of these mob disguise plugins so that GadgetsMenu will have Morph feature.
- Lib's Disguise
- iDisguise

## Why I didn't receive any menu selector to access GadgetsMenu menu?

Player is requires a permission `gadgetsmenu.menuselector` to get the menu selector when they join the server.
Simply assign this permission to the player or permission group in your permissions plugin.

If you don't know what other permissions you need to include, you may look for [Permission for Beginners](wiki/getting-started/permissions#permission-for-beginners).

## How can I sync GadgetsMenu's data between servers?

GadgetsMenu provides several ways to store the data, which are `sqlite` and `MySQL` storage. To share data between each minecraft server, you can use `MySQL` storage to store GadgetsMenu data.

To achieve this, simply change the `Storage` value to `mysql` and setup MySQL infos in `config.yml` file. You can get your MySQL credential from your database server provider.

```yaml
# This option allows you to set where
# player's data do you want to save.
# 
# Storages: 'sqlite' or 'mysql'.
# 
# If you enable mysql, you need to setup MySQL infos.
Player-Data:
  Storage: mysql
  MySQL:
    hostname: localhost
    username: root
    database: minecraft
    port: '3306'
    password: password
    useSSL: false
```

Once done, restart your server and you should be able see the below message stating that GadgetsMenu has succesfully connected to MySQL database.

![MySQL Success Message](/assets/gadgetsmenu-docs/images/getting-started/faq-mysql-connect-success.PNG "[Wrapper] MySQL Success Message")

>**Note:** Make sure your proxy server and minecraft server is setup correctly. Especially in `spigot.yml` file, `bungeecord` setting is set to true. Otherwise, GadgetsMenu will not be able to sync data properly.

## How can I use GadgetsMenu's placeholders in a scoreboard, leaderboard or xxx plugin?

GadgetsMenu use one of the popular placeholders plugin - [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/), to support placeholders in 3rd party plugins.

To use [GadgetsMenu placeholders](wiki/setup/placeholders), you're not required to download any expansion from eCloud. You can straight away use the placeholder as long as the 3rd party plugin supports PlaceholderAPI.

>**Note:** Make sure the plugin you use support PlaceholderAPI and has enabled PlaceholderAPI usage.

## I have purchased a cosmetic item via Mystery Dust or found a cosmetic item by opening Mystery Box, but they still can’t access that cosmetic item?

#### Free version

GadgetsMenu Free version does not save unlocked cosmetic items in it’s database. When player purchase a cosmetic item or found a cosmetic item by opening Mystery Box, GadgetsMenu executes a command to grant the player a permission to access the cosmetic item.

Therefore, you need to have a permissions plugin to handle player's permissions. Depending on the permission plugin you use, you need to set the command so that GadgetsMenu plugin will execute the correct command for granting the permissions.

There are two files allocated in `/plugins/GadgetsMenu` folder you need to make changes. You need to replace the following section to the respective command based on which permissions plugin you use.

You can refer to the table below to find the commands for the permission plugin you are using.

- `config.yml`
```yaml
Cosmetic-Item-Purchase:
  # This is the command when player purchase cosmetic items.
  # This command is depends on your permission plugin.
  Execute-Command: pex user {PLAYER} add {PERMISSION}
```

- `mystery boxes/mystery boxes.yml`
```yaml
Mystery-Boxes:
  Execute-Command: pex user {PLAYER} add {PERMISSION}
```

| Permission Plugin | Command                                            |
| ----------------- | -------------------------------------------------- |
| LuckPerms         | `lp user {PLAYER} permission set {PERMISSION}`     |
| PowerfulPerms     | `pp user {PLAYER} add {PERMISSION}`                |
| PowerRanks        | `pr addplayerperm {PLAYER} {PERMISSION}`           |
| CloudNet          | `cperms user {PLAYER} add permission {PERMISSION}` |
| PermissionsEx     | `pex user {PLAYER} add {PERMISSION}`               |
| GroupManager      | `manuaddp {PLAYER} {PERMISSION}`                   |

#### Premium version

If you’re using premium version, you may not face the above issue. However, if you found out that your problem has the similar scenario, do reach to our [Discord](https://discord.gadgetsmenu.net/) support staff for assistance.

## How can I change Mystery Dust storage to other economy storage?

GadgetsMenu supports several economy plugin for Mystery Dust replacement. Simply change the value of `Mystery-Dust-Storage` which can be found in `config.yml` file to any available storages mentioned in the list.

```yaml
Cosmetic-Item-Purchase:
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
```

Apart from that, GadgetsMenu also provides an API to implement your custom economy storage for Mystery Dust. If your server is using self-made economic system, you can hook GadgetsMenu Mystery Dust with your custom economy storage. Click the link for more information about [GadgetsMenu Custom Economy Storage](wiki/developers/custom-economy-storage).

## How to create a Mystery Vault that used to open Mystery Boxes?

Mystery Boxes can only be opened through Mystery Vault. Therefore, create Mystery Vault is a must if you want to use Mystery Box feature.

You can create Mystery Vault through the following steps:
1. Place a block (e.g. Ender Chest) at the location where you want to create Mystery Vault.
2. Orient your user view to the newly added block.
3. Execute the command `/gmysteryboxes mode add-vault <vaultName>` by replacing `<vaultName>` with a unique name that represents your Mystery Vault.
4. You should be able to see holograms shown on top of your Mystery Vault like the image below, if your steps were correct.
5. You're done! Now you may try to open Mystery Box via the newly created Mystery Vault.

![Mystery Vault](/assets/gadgetsmenu-docs/images/getting-started/faq-create-mystery-vault.jpg "[Wrapper] Mystery Vault")

Click on the [link](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-add-vault-vaultname) to see more details about the command.

## How can I change the orientation of Mystery Vault's animation?

![Mystery Vault's animation orientation](/assets/gadgetsmenu-docs/images/getting-started/faq-change-mystery-vault-orientation.jpg "[Wrapper] Mystery Vault's animation orientation")
Your Mystery Vault's animation is facing the wrong way similar to the above image? No worries, you can redefine the Mystery Vault location and its facing direction via a command `/gmysteryboxes mode redefine <vaultName>`. ([Click here for more info](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-redefine-vaultname))

Stand in front of the Mystery Vault, navigate your user view to the opposite direction and execute the above command.

> **Tips:**
> - If you don't remember the name of your Mystery Vault, execute this command `/gmysteryboxes mode near <radius>` to get the info of nearby Mystery Vaults.
> - [Click here for more info](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-near-radius)

## How can I remove a Mystery Vault?

You can remove Mystery Vault by looking at the Mystery Vault block and execute the following command.
- `/gmysteryboxes mode remove-vault`

If you wish to remove a Mystery Vault by its name or your nearby Mystery Vault by radius. Simply add this parameter at the end of the command `[vaultName|r:{radius}]`.

**Example:**
- `/gmysteryboxes mode remove-vault vault_1` - Remove specific Mystery Vault by name.
- `/gmysteryboxes mode remove-vault r:3` - Remove nearby Mystery Vault by radius.

## How to give the player the Mystery Box?

You can give player Mystery Box via the below command:
```
/gmysteryboxes give <player> <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false] c:(<quality>:<chances>)
```

You can view the full usage and description of this command by clicking [this link](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-give-player-amount-quality-ex-7h-7d-7m-false-reqperm-false-c-quality-chances).

## How to give the player a random quality Mystery Box?

You can give player random quality Mystery Box via the below command:
```
/gmysteryboxes give <player> <amount> c:(<quality>:<chances>)
```

With this command, you don't need to specify the quality of the Mystery Box in the command param. Instead, you specify the chances of each Mystery Box quality with the following syntax.

**Syntax:**
 - `c:(<quality>:<chances>)` - Custom chances quality of mystery boxes when the quality argument is not specified.

**Description:**
 - The quality of the Mystery Box followed by the chances to get it.
 - Please note that you must fill in all available qualities (1 - 5). Missing one will throw an error.
 - The total chances among all qualities can be greater than 100 or less than 100.

**Example:**
 - `/gmysteryboxes give <player> <amount> c:(1:40,2:30,3:25,4:15,5:10)` - 40% chance to get 1-star Mystery Box, 30% chance to get 2-star Mystery Box...and so on.
 - `/gmysteryboxes give <player> <amount> c:(1:80,2:70,3:65,4:5,5:3)` - 80% chance to get 1-star Mystery Box, 70% chance to get 2-star Mystery Box...and so on.

 [Click here for more info about the command](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-give-player-amount-quality-ex-7h-7d-7m-false-reqperm-false-c-quality-chances)

## How to give player Mystery Gifts?

You can give player Mystery Gifts via this command:
 - `/gmysteryboxes gift <player> <pack>`

 [Click here for more info about the command](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-gift-player-pack)

> **Note:** Please noted that each Mystery Gift contains 5 Mystery Boxes. Currently the amount of the Mystery Boxes can’t be changed.

## Why some players cannot open the Mystery Vault?

If you create a Mystery Vault nearby the spawn point, you may not be able to open the Mystery Vault menu by right-clicking on the Mystery Vault.

What you need to do is set the value of `Spawn-Protection` property to `0` in your server `server.properties` file.

## Why  players can't open the Mystery Boxes?

Mystery Box requires permission to be opened. Also, Mystery Box opening animation requires another permission.

Click on the link below for a list of permissions required to open Mystery Box:
- [Mystery Boxes](wiki/getting-started/permissions#mystery-boxes)
- [Mystery Vault Animations](wiki/getting-started/permissions#mystery-vault-animations)

If you do not know how to setup permissions for "default" rank player, you can refer [Permission for begineers](wiki/getting-started/permissions#permission-for-beginners).

## Why do player get Mystery Box occasionally?

GadgetsMenu offers a feature called Mystery Box Reward, which gives player Mystery Box when they reach certain amount of play time in the server.

You can disable or change the reward setting in `mystery boxes.yml` file.

- `mystery boxes/mystery boxes.yml`
```yaml
Mystery-Boxes-Reward:
  Enabled: true
  Allow-AFK: false
  Chance-To-Get-Mystery-Box: 75
  Chance:
    One-Star: 5
    Two-Star: 10
    Three-Star: 60
    Four-Star: 20
    Five-Star: 5
  Expiry-Date-In-Days: 7
  Play-Time:
    Hours: 0
    Minutes: 40
    Seconds: 0
  Enabled-Worlds:
  - '*'
  Message:
    One-Star: '&fYou found a &e✰&7✰✰✰✰ &fMystery Box!'
    Two-Star: '&fYou found a &e✰✰&7✰✰✰ &fMystery Box!'
    Three-Star: '&fYou found a &e✰✰✰&7✰✰ &fMystery Box!'
    Four-Star: '&fYou found a &e✰✰✰✰&7✰ &fMystery Box!'
    Five-Star: '&fYou found a &e✰✰✰✰✰ &fMystery Box!'
```

> **Note:** With GadgetsMenu (Premium), it saves player's play time in the database and provide an option to toggle play time counting while player is AFK.

## How to give player pet items?

You can give player Mystery Gifts via this command:
 - `/gmenu petitems`

Execute the above command will list out all the available sub commands. You can use `TAB` key to help you to auto-fill the required value. 

**Sub Commands:**
- `/gmenu petitems add <item> <player> <amount>` - Add pet items to player.
- `/gmenu petitems check <player>` - Check player's pet items.
- `/gmenu petitems remove <item> <player> <amount>` - Remove pet items from player.
- `/gmenu petitems set <player> <amount>` - Set player's pet items.

**Example:**
- `/gmenu petitems add Apple Notch 10`
- `/gmenu petitems check Notch`
- `/gmenu petitems remove Water Notch 3`
- `/gmenu petitems set Stick Notch 25`

[Click here for more info about the command](wiki/getting-started/commands/general#gmenu-petitems)

## What are the ways for players to obtain pet items?

Currently, there are two ways for players to obtain pet items:
1. By opening Mystery Boxes, player would gain certain amount of pet items varies from the quality of Mystery Box.
2. Give player pet items by command `/gmenu petitems`.

## Why does my Mystery Vault only show two lines of holograms instead of three?

![Mystery Vault holograms](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-show-solution.jpg "[Wrapper] Mystery Vault holograms")

In general, Mystery Vault should have 3 lines of holograms display on top of it. If you facing an issue where your Mystery Vault only show two lines of holograms as what you see in the below image:

![Mystery Vault hologram not showing](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-show.jpg "[Wrapper] Mystery Vault hologram not showing")

What you need to do is add [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) plugin into your server. The additional hologram requires ProtocolLib plugin to activate. Once you have that plugin, the hologram will show up automatically unless you have an incompatible version of ProtocolLib plugin that not supports your server version.

## Why is my Mystery Vault hologram not working properly?

![Mystery Vault hologram not working properly](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-working-properly.png "[Wrapper] Mystery Vault hologram not working properly")

Your Mystery Vault hologram isn't working and directly show the placeholder, similar to the image above?

No worries! This issue occurred when you are using the outdated version of ProtocolLib plugin. You have to update your [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) plugin to the latest build and make sure that it supports your server version.