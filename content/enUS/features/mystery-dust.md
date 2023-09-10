---
title: Mystery Dust
description: GadgetsMenu currency that used for transactions, purchase cosmetic items, craft Mystery Box and more.
group: features
keywords: Mystery Dust
topics:
 - Mystery Dust
 - Economy
 - Money
---

## What is Mystery Dust?
Mystery Dust is GadgetsMenu's built-in transaction currency. Player can use Mystery Dust to purchase cosmetic items, craft Mystery Box and trade with players.

There are two ways to obtain Mystery Dust, the easiest of which is by opening Mystery Boxes. When player found duplicate cosmetic item from Mystery Box, a random amount of mystery dust will be given to the player as compensation depending on the cosmetic item rarity.

Another way to obtain Mystery Dust is to grant it to the player through [commands](../wiki/getting-started/commands/mystery-dust). Server owner could setup several approach including selling Mystery Dust bundle store, daily rewards, game rewards and play time rewards etc to give player Mystery Dust.


## Mystery Dust Storage

Apart from using GadgetsMenu built-in storage to store Mystery Dust data, you also can hook Mystery Dust storage into another economy plugin such as Vault, PlayerPoints and CoinsAPI.

What you need to do is simply replace the value of `Mystery-Dust-Storage` with the supported economy plugin you wanted to use. This option can be found in `config.yml` file.
```yaml
Cosmetic-Item-Purchase:
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault', 'tokenmanager'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
```

>**Note:** Want to use custom economy storage? Look for [Custom Economy Storage](../wiki/developers/custom-economy-storage) API.

## Further reading
<div class="md-relevant-content">

- [Cosmetic Purchase](../wiki/features/cosmetic-purchase)
- [Cosmetic Purchase Price Discount](../wiki/features/cosmetic-purchase-price-discount)
</div>
