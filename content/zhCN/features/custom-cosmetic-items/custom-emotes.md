---
title: 自定义表情
description: GadgetsMenu 允许您使用任意数量的玩家头颅帧来制作自己的表情。
group: custom-cosmetic-items
keywords: 自定义表情, 自定义化妆品
topics:
 - 自定义表情
 - 自定义化妆品
---

您可以在 `custom cosmetics/custom emotes.yml` 文件中创建自己的表情。

>[Warning] {{title: 警告}} 在设置自定义表情之前，请确保您已阅读完整个页面。

## 配置
```yaml
# Please do not change this.
Custom-Emotes:
  # This name will store in GadgetsMenu cache and use for mystery boxes, 
  # so do not use the same name!
  # The permission of the emote is 'gadgetsmenu.emotes.slimes'.
  Slimes:

    # The name of emote.
    Name: '&aSmiles Emote'

    # The price of emote.
    Mystery Dust: 10

    # The cooldown timer of using emote once.
    Cooldown: 10

    # The rarity of the emote.
    # Rarity: Common, Rare, Epic, Legendary
    Rarity: Common 

    # Shows a hologram on the top of the player.
    Hologram:
      Enabled: false
      Text: ''

    # The head texture which will show in the GUI menu.
    Texture: 60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa

    # Set to true will able player's to equip it.
    Enabled: false

    # Can this emote found in mystery boxes?
    CanBeFound: true

    # Can player get this emote by purchasing it using mystery dust?
    Purchasable: true

    # How many ticks should wait before shows the next frame?
    # 20 ticks = 1 second
    TicksPerFrame: 5

    # The frames of emote.
    # Frames syntax: '<The amount of the frames>:<texture>'
    Frames:
    - 5:264614ad4bb2eb61b06b1a8b5d57f02448a975a8217ec16571f87c49227cbd
    - 1:60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235
    - 1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d
    - 3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235

    # The lore of emote.
    Lore:
      Locked: ''
      Unlocked: ''
```

## 动画是如何播放的？

假设我们有 7 个帧，TicksPerFrame = 5，每个帧的数量各不相同，与上面的示例相同。
 1. `5:264614ad4bb2eb61b06b1a8b5d57f02448a975a8217ec16571f87c49227cbd`
 2. `1:60c432cbc490a8af6e9dfeb28095c0a0ec79fff705fb184674d1e743bd05baa`
 3. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 4. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 5. `11:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`
 6. `1:4168b716281635ceafc3268dfa7d5f46466c8032e11c1cfb7db711a9f647d`
 7. `3:41ac21d93ce17f2b7ee2e0e07a983eeb4a539e341ce5c77c36c722f77a2235`

每帧的刻数值为 `5 ticks`，即 `0.25 second`，其中 20 ticks 等于 1 秒。

动画播放顺序为：`1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7`。当最后一帧播放完毕后，动画即结束。玩家需要再次激活该表情才能重新开始动画。

每一帧以及一个完整动画周期的时长如下：
<div class="md-table-max-content md-table-no-bg-color">

| 帧 | 数量 | 时长（秒）（数量 x 0.25s） |
| ----- |:------:| ------------------- |
| 第 1 帧 | 5 | 1.25s |
| 第 2 帧 | 1 | 0.25s |
| 第 3 帧 | 11 | 2.75s |
| 第 4 帧 | 1 | 0.25s |
| 第 5 帧 | 11 | 2.75s |
| 第 6 帧 | 1 | 0.25s |
| 第 7 帧 | 3 | 0.75s |
| | **总计** | 8.25s |
</div>

## 相关内容
<div class="md-relevant-content">

- [头颅材质](../wiki/others/texture-head)
</div>
