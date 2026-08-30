---
title: 自定义动画帽子
description: GadgetsMenu 允许您使用任意数量的玩家头颅帧来制作自己的动画帽子。
group: custom-cosmetic-items
keywords: 自定义动画帽子, 自定义化妆品
topics:
 - 自定义动画帽子
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom animated hats.yml` 文件中创建自己的动画帽子。

>[Warning] {{title: 警告}} 在设置自定义动画帽子之前，请确保您已阅读完整个页面。

## 配置
```yaml
# Please do not change this.
Custom-Animated-Hats:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the emote is 'gadgetsmenu.animatedhats.slimes'.
  Slimes:

    # The name of animated hat.
    Name: '&aSmiles Animated Hat'

    # The price of animated hat.
    Mystery Dust: 12

    # The rarity of the animated hat.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common 

    # This is the texture of the head that are stored in Mojang's database.
    # Simply paste the url right here.
    Texture: 41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # Set to true will able player to equip it.
    Enabled: false

    # Can this animated hat found in mystery boxes?
    CanBeFound: true

    # Can player get this animated hat by purchasing it using mystery dust?
    Purchasable: true

    # How many ticks should wait before shows the next frame?
    # 20 ticks = 1 second
    TicksPerFrame: 5

    # The frames of animated hat.
    # Frames syntax: '<The amount of the frames>:<texture>'
    Frames:
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # The lore of animated hat.
    Lore: 
      Locked: ''
      Unlocked: ''
```

## 动画是如何播放的？

假设我们有 5 个帧，每个帧的数量各不相同，与上面的示例相同。
 1. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 2. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 3. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 4. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 5. `3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`

每帧的刻数值为 `5 ticks`，即 `0.25 second`，其中 20 ticks 等于 1 秒。

动画播放顺序为：`1 -> 2 -> 3 -> 4 -> 5`。当最后一帧播放完毕后，将返回到第 1 帧并重复相同的顺序。

每一帧以及一个完整动画周期的时长如下：
<div class="md-table-max-content md-table-no-bg-color">

| 帧 | 数量 | 时长（秒）（数量 x 0.25s） |
| ----- |:------:| ------------------- |
| 第 1 帧 | 11 | 2.75s |
| 第 2 帧 | 1 | 0.25s |
| 第 3 帧 | 11 | 2.75s |
| 第 4 帧 | 1 | 0.25s |
| 第 5 帧 | 3 | 0.75s |
| | **总计** | 6.75s |
</div>

## 相关内容
<div class="md-relevant-content">

- [头颅材质](../wiki/others/texture-head)
</div>
