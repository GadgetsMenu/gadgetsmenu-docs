---
title: 黑名单地区
description: 想要在特定地区禁用化妆品，或者只在特定地区启用化妆品？
group: features
keywords: 黑名单地区, 白名单地区, worldguard
topics:
 - 黑名单地区
 - 白名单地区
 - worldguard
supportedVersion: 5.10.0
supportedPlan: premium
---

> **依赖项：**
> WorldGuard

黑名单地区允许您配置一些地区，在这些区域内禁止玩家使用化妆品。当玩家进入该地区时，化妆品将被自动卸下，并且在玩家离开该地区之前无法再次装备。

除此之外，将 `Reverse-Whitelist` 的值设置为 `true`，即可将黑名单地区转换为白名单地区。这样一来，玩家只有在配置的地区内才被允许装备/激活化妆品。

## 配置
```yaml
# Blacklisted region
# Disable cosmetic usage in the configured regions.
# Require WorldGuard plugin.
Blacklisted-Region:
  Enabled: true
  # Set 'Reverse-Whitelist' as true will change to whitelisted region.
  # Whitelisted region: Enable cosmetic usage only in the configured regions.
  Reverse-Whitelist: false
  # Format: [region_id]:[world_name|*], [__global__]:[world_name|*]
  # Example: region:world1, __global__:world2
  Region:
    All-Cosmetics:
    - region1:*
    - region2:world1
    - region3:world2
    Hats: ''
    Animated-Hats: ''
    Particles: ''
    Suits: ''
    Gadgets: ''
    Pets: ''
    Miniatures: ''
    Morphs: ''
    Banners: ''
    Emotes: ''
    Cloaks: ''
    Pet-Riding: ''
```
您可以将地区配置为仅对特定世界进行检查，或使用星号（"*"）表示所有世界。
有关地区格式的更多详情，请参阅[地区格式](../wiki/features/blacklisted-region#region-format)。

## 白名单地区
您可以将黑名单地区反转为白名单地区。这意味着玩家只有身处 `Blacklisted-Region` 部分中所指定的地区内时，才能装备化妆品。

只需将 `Reverse-Whitelist` 设置为 `true`，即可将黑名单地区反转为白名单地区。

## 地区格式

```yaml
# Format: [region_id]:[world_name|*], [__global__]:[world_name|*]
Example: 
 - 'regionA:world'
 - 'regionB:world_nether'
 - 'regionC:*'
```

>**注意：** 地区 ID 和世界名称区分大小写。

### 全局地区
您可以使用 `__global__` 来指定覆盖整个世界的 `overworld region`/`wilderness region`/`global region`。

```yaml
Example:
 - '__global__:world1'
```

#### 场景 1：我想在生存和空岛世界中启用除小工具以外的所有化妆品。
在这种情况下，您只需在 `Gadget` 黑名单地区部分下指定 `__global__` 地区。
```yaml
Blacklisted-Region:
  Enabled: true
  Reverse-Whitelist: false
  Region:
    Gadgets:
    - '__global__:survival'
    - '__global__:skyblock'
```
