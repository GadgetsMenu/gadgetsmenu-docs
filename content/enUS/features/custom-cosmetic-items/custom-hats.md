---
title: Custom Hats
description: 
group: custom-cosmetic-items
keywords: custom hats, custom cosmetic item
topics:
 - custom hats
 - custom cosmetic item
---

You are able to create your own hats in 'custom hats.yml' file.

>[Warning] {{title: Warning}} Make sure you have read the whole page before creating your own hats.

## Configuration
```yaml
# Please do not change this.
Custom-Hats:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the hat is 'gadgetsmenu.hats.steve'.
  Steve:

    # The name of hat.
    Name: '&aSteve Hat'

    # The price of hat.
    Mystery Dust: 12

    # The rarity of the hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common

    # This is the texture of the head that are stored in Mojang's database.
    # Simply paste the url right here.
    Texture: http://textures.minecraft.net/texture/eb7af9e4411217c7de9c60acbd3c3fd6519783332a1b3bc56fbfce90721ef35

    # Set to true will able player to equip it.
    Enabled: false

    # Can this hat found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of hat.
    Lore:
      Locked: ''
      Unlocked: ''

  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the hat is 'gadgetsmenu.hats.sponge'.
  Sponge:

    # The name of hat.
    Name: '&aSponge Hat'

    # The price of hat.
    Mystery Dust: 12

    # The rarity of the hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common

    # The material of hat.
    # https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html
    # Material Format: [Material]:[Material Data]
    Material: SPONGE

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this hat found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of hat.
    Lore: 
      Locked: ''
      Unlocked: ''
```

## Further reading
<div class="md-further-reading">

- [Texture Head](../wiki/others/texture-head)
</div>
