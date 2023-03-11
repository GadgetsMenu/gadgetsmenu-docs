---
title: Cosmetic Purchase
description: Each cosmetic item can be purchased using Mystery Dust or any other popular economy system. You can configure whether players can purchase cosmetic items by category or type.
group: features
keywords: cosmetic purchase,buy cosmetic item
topics:
 - cosmetic purchase
 - buy cosmetic item
---

## Configuration
```yaml
Cosmetic-Item-Purchase:

  # Set to true allows player to purchase cosmetic items.
  Enabled: true

  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default

  # Set to true will allows player to purchase specified cosmetic.
  Enabled-Cosmetics:
    Hats: true
    Animated Hats: true
    Particles: true
    Suits: true
    Gadgets: true
    Pets: true
    Miniatures: true
    Morphs: true
    Banners: true
    Emotes: true
    Cloaks: true

  # Reopen GUI menu after player purchase item.
  Reopen-GUI-Menu-After-Purchase: true

  Execute-Command:
    # Set to true will use 3rd party plugin to store purchased cosmetic items,
    # otherwise will saved in built-in storage.
    Enabled: false
    Command: pex user {PLAYER} add {PERMISSION}
```

## Steps to purchase cosmetic item

 - **Step 1:** (Choose a cosmetic item that you want to purchase)

![Step 1](https://i.imgur.com/dYtJb65.png)


 - **Step 2:** (Click `Confirm` or `Cancel` purchase)

![Step 2](https://imgur.com/222pTtY.png)
![Step 2](https://imgur.com/gFngP8l.png)


 - **Step 3:** (You can now equip this cosmetic item)

![Step 3](https://imgur.com/D7YlFT1.png)


## Relevant content
<div class="md-relevant-content">

- [Custom Economy Storage](../wiki/developers/custom-economy-storage)
</div>
