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
  # Format: [region_id]:[world_name|*]
  # Example: region:world1
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


## Region Format

```yaml
# Format: [region_id]:[world_name|*]
Example: 
 - 'regionA:world'
 - 'regionB:world_nether'
 - 'regionC:*'
```

>**Note:** Region id and world name is case sensitive.