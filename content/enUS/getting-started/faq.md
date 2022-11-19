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