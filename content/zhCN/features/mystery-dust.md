---
title: Mystery Dust
description: GadgetsMenu 的货币，用于交易、购买化妆品、合成神秘箱等。
group: features
keywords: Mystery Dust
topics:
 - Mystery Dust
 - 经济
 - 货币
---

## 什么是 Mystery Dust？
Mystery Dust 是 GadgetsMenu 的内置交易货币。玩家可以使用 Mystery Dust 购买化妆品、合成神秘箱以及与其他玩家交易。

获得 Mystery Dust 有两种方式，其中最简单的方式是开启神秘箱。当玩家从神秘箱中获得重复的化妆品时，将会根据该化妆品的稀有度，随机给予玩家一定数量的 Mystery Dust 作为补偿。

另一种获得 Mystery Dust 的方式是通过[命令](../wiki/getting-started/commands/mystery-dust)将其发放给玩家。服务器管理员可以设置多种途径来向玩家发放 Mystery Dust，例如出售 Mystery Dust 礼包商店、每日奖励、游戏奖励以及在线时长奖励等。


## Mystery Dust 存储

除了使用 GadgetsMenu 内置的存储来保存 Mystery Dust 数据之外，您也可以将 Mystery Dust 存储挂钩到其他经济插件，例如 Vault、PlayerPoints 和 CoinsAPI。

您需要做的只是将 `Mystery-Dust-Storage` 的值替换为您想要使用的、受支持的经济插件。该选项可以在 `config.yml` 文件中找到。
```yaml
Cosmetic-Item-Purchase:
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault', 'tokenmanager', 'coinsengine:<currency>'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
```

>**注意：** 想要使用自定义经济存储？请查看[自定义经济存储](../wiki/developers/custom-economy-storage) API。

## 延伸阅读
<div class="md-relevant-content">

- [化妆品购买](../wiki/features/cosmetic-purchase)
- [化妆品购买价格优惠](../wiki/features/cosmetic-purchase-price-discount)
</div>
