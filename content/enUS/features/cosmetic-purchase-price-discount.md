---
title: Cosmetic Purchase Price Discount
description: You can grant your ranked player with different discount rate when purchase cosmetic item and craft Mystery Box.
group: features
keywords: cosmetic purchase price discount, discount group, item discount
topics:
 - cosmetic purchase price discount, 
 - discount group
 - item discount
---

An item discount reduces the price of crafted Mystery Boxes & cosmetic items for the players who have the permission.
Here is the part of the config in which you can change these discounts.

## Configuration
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

The higher the `Priority` value is, the higher discount rate will be placed. For example, a discount with `priority 2` will override a discount with `priority 1` if a player has both permissions.

- The `{COST}` value represents the regular cost.
- The `{COST_LEFT}` value represents the cost that the player still needs to get in order to buy the item.