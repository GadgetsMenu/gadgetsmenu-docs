---
title: 化妆品购买
description: 每一件化妆品都可以使用 Mystery Dust 或其他常见的经济系统购买。您可以配置玩家是否能够按分类或类型购买化妆品。
group: features
keywords: 化妆品购买,购买化妆品
topics:
 - 化妆品购买
 - 购买化妆品
---

## 配置
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

## 购买化妆品的步骤

 - **第 1 步：**（选择您想要购买的化妆品）

![第 1 步](https://i.imgur.com/dYtJb65.png)


 - **第 2 步：**（点击 `Confirm` 确认或 `Cancel` 取消购买）

![第 2 步](https://imgur.com/222pTtY.png)
![第 2 步](https://imgur.com/gFngP8l.png)


 - **第 3 步：**（现在您可以装备这件化妆品了）

![第 3 步](https://imgur.com/D7YlFT1.png)


## 相关内容
<div class="md-relevant-content">

- [自定义经济存储](../wiki/developers/custom-economy-storage)
</div>
