---
title: 化妆品购买价格优惠
description: 您可以为不同等级的玩家授予不同的折扣率，用于购买化妆品和合成神秘箱。
group: features
keywords: 化妆品购买价格优惠, 折扣组, 物品折扣
topics:
 - 化妆品购买价格优惠, 
 - 折扣组
 - 物品折扣
---

物品折扣会为拥有相应权限的玩家降低合成神秘箱与化妆品的价格。
下面是配置中可以修改这些折扣的部分。

## 配置
```yaml
# Discount the cost of an item when player purchase.
Item-Cost-Discount:
  # Set to true will enable item cost discount.
  Enabled: true
  # Which item do you want to enable item cost discount?
  Discount:
    Cosmetic-Item: true
    Crafting-Mystery-Box: true
  # You can add more discount rate by reference example.
  Discount-Rates:
    # The name of the discount group.
    # The name is use for placeholder to get the cost after discount.
    # Placeholder Syntax: {<name>_COST}
    # Get the cost of that discount rate.
    VIP:
      # Higher numbers override.
      Priority: 1
      # The permission to granted discount.
      Permission: gadgetsmenu.discount.VIP
      # Discount rates.
      Rate: 20
      Lore:
        Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - "&aVIP&7: &a{VIP_COST} &7Mystery Dust (&a20% &7OFF!) &e\u25C0"
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &a{VIP_COST} &7Mystery Dust'
        - '&eClick to craft!'
        Not-Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - "&aVIP&7: &a{VIP_COST} &7Mystery Dust (&a20% &7OFF!) &e\u25C0"
        - '&cMVP: {MVP_COST} Mystery Dust (40% OFF!)'
        - ''
        - '&7Your Cost: &c{VIP_COST} &7Mystery Dust'
        - '&cYou need &b{COST_LEFT} &cmore mystery dust!'
    MVP:
      Priority: 2
      Permission: gadgetsmenu.discount.MVP
      Rate: 40
      Lore:
        Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - '&8&mVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - "&bMVP&7: &a{MVP_COST} &7Mystery Dust (&a40% &7OFF!) &e\u25C0"
        - ''
        - '&7Your Cost: &a{MVP_COST} &7Mystery Dust'
        - '&eClick to craft!'
        Not-Enough-Mystery-Dust:
        - ''
        - '&8&mRegular: {COST} Mystery Dust!'
        - '&8&mVIP: {VIP_COST} Mystery Dust (20% OFF!)'
        - "&bMVP&7: &a{MVP_COST} &7Mystery Dust (&a40% &7OFF!) &e\u25C0"
        - ''
        - '&7Your Cost: &a{MVP_COST} &7Mystery Dust'
        - '&cYou need &b{COST_LEFT} &cmore mystery dust!'
```

`Priority` 的值越高，所应用的折扣率优先级就越高。例如，如果一位玩家同时拥有两个权限，`priority 2` 的折扣将覆盖 `priority 1` 的折扣。

- `{COST}` 值代表原价。
- `{COST_LEFT}` 值代表玩家为了购买该物品还需要获得的金额。
