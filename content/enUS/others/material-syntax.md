---
title: Material Syntax
description: You can find all supported material syntax for GadgetsMenu menu item. You can use block, player head, potion, colored leather armor and custom model data as item material.
group: others
keywords: material syntax
topics:
 - material syntax
---

Regardless of your server version, you must follow the material syntax when configuring item materials. Otherwise, you may encounter some errors or the item may not display correctly.

## Material

**Relevant Link:**
- [Material List](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
  - Only the material types shown in the list can be used.
  - You can only use materials without the `LEGACY` prefix.

**Format:**
```yaml
# Material Format: [Material]:[Material Data]
Material: RED_STAINED_GLASS_PANE
```

## Player Head

- Relevant Link: [Texture Head](../wiki/others/texture-head)

**Format:**
```yaml
# Material Format: [head]:[texture]
Material: 'head:292009a4925b58f02c77dadc3ecef07ea4c7472f64e0fdc32ce5522489362680'
```

## Potion

- Relevant Link: [Potions](../wiki/others/potions)

**Format:**
```yaml
# Material Format: [Material]:[ID]
# Material: LINGERING_POTION, POTION, SPLASH_POTION
Material: 'POTION:8193'
```

## Colored Leather Armor

- Relevant Link: [Hex Color Format](https://htmlcolorcodes.com/)

**Format:**
```yaml
# Material Format: [Leather Armor]:[Hex Color Code]
# Available Material: LEATHER_HELMET, LEATHER_CHESTPLATE, LEATHER_LEGGINGS, LEATHER_BOOTS
Material: 'LEATHER_HELMET:#FF0000'
```

## Custom Model Data

**Format:**
```yaml
# Material Format: [custommodeldata]:<material>:<modeldata>
Material: 'custommodeldata:IRON_INGOT:123456'
```
