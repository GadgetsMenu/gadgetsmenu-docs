---
title: 头颅材质
description: 您可以在此处找到获取头颅材质 URL 的方法。
group: others
keywords: 头颅材质
topics:
 - 头颅材质
---

在 GadgetsMenu 中，您可以使用玩家头颅作为物品材料。您需要做的就是获取头颅材质 URL，并将获得的值设置到物品的材料部分中。

## 如何获取玩家的头颅材质？

### minecraft-heads.com

[minecraft-heads.com](https://minecraft-heads.com/custom-heads) 提供了超过 2,000 个玩家头颅和 50,000 个自定义头颅。您可以找到各式各样的头颅材质，并像下面的示例那样粘贴 Minecraft-URL。

**示例：**
```
Item:
  Material: head:d2ac1c51807e261c12c4f2adbad36b8b2c497c277f7223ec244cb4608c59c
```

**步骤：**
1) 找到您想要的头颅材质并点击它。
2) 向下滚动到页面底部，找到 `Minecraft-URL` 部分。
  ![从 minecraft-heads.com 获取材质 URL](/assets/gadgetsmenu-docs/images/others/texture-head-get-url-from-minecraft-heads.png "[Wrapper] Get texture URL from minecraft-heads.com")
3) 复制该值，并按照语法（`head:<textureURL>`）将其粘贴到 `Material` 部分中。
