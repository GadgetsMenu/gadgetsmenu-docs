---
title: 神秘箱
description: 玩家可以从神秘箱中获得化妆品、Mystery Dust 和自定义奖励。
group: features
keywords: 神秘箱
topics:
 - 神秘箱
---

GadgetsMenu 拥有内置的神秘箱系统。玩家可以通过开启神秘箱来获得化妆品。

目前只有三种类型的神秘箱：

 1. **合成神秘箱** - 使用 Mystery Dust 合成的神秘箱。
 2. **赠送神秘箱** - 只能从好友处获得。玩家会获得礼包，用于向他人赠送神秘箱。工作人员可以使用命令 `/gmysteryboxes gift` 向玩家发放礼包。
 3. **神秘箱** - 普通的神秘箱，可以通过在服务器中游玩获得，或通过命令 `/gmysteryboxes give` 获得。


化妆品被分为 4 种稀有度，分别是 `Common`（普通）、`Rare`（稀有）、`Epic`（史诗）和 `Legendary`（传说）。

每个神秘箱中包含 7 件不同稀有度的战利品。品质越高的神秘箱，里面包含的物品越稀有。开启一个神秘箱将从这 7 件战利品中随机获得一件，而获得更稀有物品的几率取决于神秘箱的品质。当您获得已经拥有的物品时，您将获得 Mystery Dust 作为交换。您获得的 Mystery Dust 数量将取决于所获物品的稀有程度。

<div class="md-table-max-content">

| 品质 |	普通 | 稀有 | 史诗 | 传说 |
|:-------:|:------:|:----:|:----:|:---------:|
| ⭐ | 4 | 1 | 1 | 1 |
| ⭐⭐ | 3 | 2 | 1 | 1 |
| ⭐⭐⭐ |	2 | 2 | 2 | 1 |
| ⭐⭐⭐⭐ | 1 | 1 | 2 | 3 |
| ⭐⭐⭐⭐⭐ | 0 | 1 | 2 | 4 |
</div>

## 如何设置神秘宝库？
要开启神秘箱，您需要找到一个神秘宝库。神秘宝库可以使用 `/gmysteryboxes mode add-vault` 命令创建。

创建神秘宝库之后，还需要在 mysteryboxes.yml 文件中完成一些[设置](wiki/getting-started/faq#i-have-purchased-a-cosmetic-item-via-mystery-dust-or-found-a-cosmetic-item-from-opening-mystery-box-but-they-still-can-t-access-that-cosmetic-item)，以便将已解锁的化妆品保存到权限插件中。如果您使用的是免费版，已解锁的化妆品将保存在权限插件中，而不是内置数据库中。

现在您可以通过神秘宝库来开启神秘箱了。

## 相关内容
<div class="md-relevant-content">

- [我该如何更改神秘宝库动画的方向？](../wiki/getting-started/faq#how-can-i-change-the-orientation-of-mystery-vaults-animation)
- [我该如何移除神秘宝库？](../wiki/getting-started/faq#how-can-i-remove-a-mystery-vault)
- [如何向玩家发放神秘箱？](../wiki/getting-started/faq#how-to-give-the-player-the-mystery-box)
- [如何向玩家发放随机品质的神秘箱？](../wiki/getting-started/faq#how-to-give-the-player-a-random-quality-mystery-box)
- [如何向玩家发放神秘礼物？](../wiki/getting-started/faq#how-to-give-player-mystery-gifts)
- [为什么有些玩家无法打开神秘宝库？](../wiki/getting-started/faq#why-some-players-cannot-open-the-mystery-vault)
- [为什么玩家无法开启神秘箱？](../wiki/getting-started/faq#why-players-cant-open-the-mystery-boxes)
- [为什么玩家偶尔会获得神秘箱？](../wiki/getting-started/faq#why-do-player-get-mystery-box-occasionally)
</div>
