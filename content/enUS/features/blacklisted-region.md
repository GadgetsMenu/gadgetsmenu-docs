---
title: Blacklisted Region
description: Wants to disable cosmetic usage or only enable cosmetic usage in certain regions?
group: features
keywords: blacklisted region, whitelisted region, worldguard
topics:
 - blacklisted region
 - whitelisted region
 - worldguard
supportedVersion: 5.10.0
supportedPlan: premium
---

> **Dependency:**
> WorldGuard

Blacklisted region allows you to configure the regions which will disallow players to use cosmetics inside that area. When player is inside the region, cosmetic will be automatically unequip and no longer allow to equip until the player leave the region.

Apart from that, by setting the value of `Reverse-Whitelist` to `true` will convert the blacklisted region as whitelisted region. In such, players are only allowed to equip/activate cosmetics when they are inside the configured regions.

## Configuration
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
You can configure the region only perform checking for a specific world, or use asterisk ("*") for all worlds.
For more details about region format, please refer [Region Format](../wiki/features/blacklisted-region#region-format).

## Whitelisted Region
You can reverse the blacklisted region into whitelisted region. Which means players are only able to equip cosmetics when they are inside the regions which specified in the `Blacklisted-Region` section.

Simply set `Reverse-Whitelist` as `true` to reverse blacklisted region into whitelisted region.

## Region Format

```yaml
# Format: [region_id]:[world_name|*], [__global__]:[world_name|*]
Example: 
 - 'regionA:world'
 - 'regionB:world_nether'
 - 'regionC:*'
```

>**Note:** Region id and world name is case sensitive.

### Global Region
You can use `__global__` to specify the `overworld region`/`wilderness region`/`global region` which covers the entire world.

```yaml
Example:
 - '__global__:world1'
```

#### Scenario 1: I want to enable all cosmetics except Gadget in survival & skyblock world.
In this case, you just need to specify `__global__` region under `Gadget` blacklisted region section.
```yaml
Blacklisted-Region:
  Enabled: true
  Reverse-Whitelist: false
  Region:
    Gadgets:
    - '__global__:survival'
    - '__global__:skyblock'
```