---
title: Texture Head
description: You can find the methods to get the head texture URL here.
group: others
keywords: texture head
topics:
 - texture head
---

You can use player head as item material in GadgetsMenu. What you need to do is to get the texture head URL and set the value obtained into item's material section.

## How to get the player's head texture?

### minecraft-heads.com

[minecraft-heads.com](https://minecraft-heads.com/custom-heads) offers more than 2,000 player heads and 50,000 custom heads. You can find variety of texture head and paste Minecraft-URL in the item material section like in the example below.

**Example:**
```
Item:
  Material: head:d2ac1c51807e261c12c4f2adbad36b8b2c497c277f7223ec244cb4608c59c
```

**Steps:**
1) Find the texture head you're looking for and click on it.
2) Scroll down to the bottom and look for `Minecraft-URL`section.
  ![Get texture URL from minecraft-heads.com](/assets/gadgetsmenu-docs/images/others/texture-head-get-url-from-minecraft-heads.png "[Wrapper] Get texture URL from minecraft-heads.com")
3) Copy the value and paste it in the `Material` section by following the syntax(`head:<textureURL>`).