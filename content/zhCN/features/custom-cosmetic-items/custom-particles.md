---
title: 自定义粒子效果
description: 想使用 GadgetsMenu 尚未添加的粒子效果？不用担心，您可以创建自己的粒子效果。
group: custom-cosmetic-items
keywords: 自定义粒子效果, 自定义化妆品
topics:
 - 自定义粒子效果
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom particles.yml` 文件中创建自己的粒子效果。

>[Warning] {{title: 警告}} 在设置自定义粒子效果之前，请确保您已阅读完整个页面。

## 配置
```yaml
# Please do not change this.
Custom-Particles:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the particle is 'gadgetsmenu.particles.endrod'.
  End Rod:

    # The name of particle.
    Name: '&5End Rod Particle'
    
    # The material of particle that will show in gui menu.
    # Material Format: [Material]:[Material Data]
    Material: END_ROD

    # The price of particle.
    Mystery Dust: 32

    # The rarity of the particle.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Epic

    # The name of the particle effect.
    Effect: END_ROD

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this particle found in mystery boxes?
    CanBeFound: true

    # Can player get this hat by purchasing it using mystery dust?
    Purchasable: true

    # The lore of particle.
    Lore:
      Locked: ''
      Unlocked: ''
```

## 相关内容
<div class="md-relevant-content">

- [粒子效果](../wiki/others/particle-effects)
- [材料语法](../wiki/others/material-syntax)
</div>
