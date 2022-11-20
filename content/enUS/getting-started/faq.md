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

## I have purchased a cosmetic item via Mystery Dust or found a cosmetic item from opening Mystery Box, but they still can’t access that cosmetic item?

#### Free version

GadgetsMenu Free version does not save unlocked cosmetic items in it’s database. When player purchase a cosmetic item or found a cosmetic item from opening Mystery Box, GadgetsMenu executes a command to grant the player a permission to access the cosmetic item.

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

```yaml
Cosmetic-Item-Purchase:
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
```