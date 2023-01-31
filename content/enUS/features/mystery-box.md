---
title: Mystery Box
description: G
group: features
keywords: mystery box, mystery boxes
topics:
 - mystery box
 - mystery boxes
---

GadgetsMenu has built-in Mystery Boxes System. Player can find cosmetic items by opening Mystery Boxes.

Currently, only three type of Mystery Box available:

 1. **Crafted Mystery Box** - Mystery Box that craft with Mystery Dust.
 2. **Gifted Mystery Box** - Only get from friends. Player gain Gift Packs that used to send Gifted Mystery Boxes to others. Staff can give player Gift Packs by using command `/gmysteryboxes gift`
 3. **Mystery Box** - Normal Mystery Box that can gain from playing in the server or get it by command `/gmysteryboxes give`


Cosmetic items were categorized into 4 type of rarity which are `Common`, `Rare`, `Epic` and `Legendary`.

Every Mystery Box contains 7 different loots with different rarity. The higher quality Mystery Box contains rarer items inside. Open a Mystery Box will gain a random loot from 7 loots and the chances getting a rarer items will depends on the quality of Mystery Box. When you get an item that you already have, you will receive Mystery Dust for exchange. You will get differ amount of Mystery Dust depending on how rare the item you received.

<div class="md-table-max-content">

| Quality |	Common | Rare | Epic | Legendary |
|:-------:|:------:|:----:|:----:|:---------:|
| ⭐ | 4 | 1 | 1 | 1 |
| ⭐⭐ | 3 | 2 | 1 | 1 |
| ⭐⭐⭐ |	2 | 2 | 2 | 1 |
| ⭐⭐⭐⭐ | 1 | 1 | 2 | 3 |
| ⭐⭐⭐⭐⭐ | 0 | 1 | 2 | 4 |
</div>

## How to setup Mystery Vault?
To open a Mystery Box, you need to find a Mystery Vault. Mystery Vault can be created by using `/gmysteryboxes mode add-vault` command.

After creating a Mystery Vault, there is some [setup](wiki/getting-started/faq#i-have-purchased-a-cosmetic-item-via-mystery-dust-or-found-a-cosmetic-item-from-opening-mystery-box-but-they-still-can-t-access-that-cosmetic-item) need to be done inside mysteryboxes.yml file in order to save unlocked cosmetic items in permission plugin. Unlocked cosmetic items were saved inside permission plugin instead of built-in database if you're using the Free version.

Now you can open Mystery Box thru a Mystery Vault. 