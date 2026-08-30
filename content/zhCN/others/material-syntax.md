---
title: 材料语法
description: 您可以在此处找到 GadgetsMenu 菜单物品所支持的全部材料语法。您可以使用方块、玩家头颅、药水、染色皮革盔甲以及自定义模型数据作为物品材料。
group: others
keywords: 材料语法
topics:
 - 材料语法
---

无论您的服务器版本如何，在配置物品材料时都必须遵循材料语法。否则，您可能会遇到一些错误，或者物品无法正确显示。

## 材料

**相关链接：**
- [材料列表](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
  - 只能使用列表中显示的材料类型。
  - 您只能使用不带 `LEGACY` 前缀的材料。

**格式：**
```yaml
# Material Format: [Material]:[Material Data]
Material: RED_STAINED_GLASS_PANE
```

## 玩家头颅

- 相关链接：[头颅材质](../wiki/others/texture-head)

**格式：**
```yaml
# Material Format: [head]:[texture]
Material: 'head:292009a4925b58f02c77dadc3ecef07ea4c7472f64e0fdc32ce5522489362680'
```

### 拥有者头颅
用于显示当前玩家的头颅。

> 起始版本：5.10.0 [Premium]

**格式：**
```yaml
# Material Format: [head]:[OWNER_HEAD]
Material: 'head:OWNER_HEAD
```

## 药水

- 相关链接：[药水](../wiki/others/potions)

**格式：**
```yaml
# Material Format: [Material]:[ID]
# Material: LINGERING_POTION, POTION, SPLASH_POTION
Material: 'POTION:8193'
```

## 染色皮革盔甲

- 相关链接：[十六进制颜色格式](https://htmlcolorcodes.com/)

**格式：**
```yaml
# Material Format: [Leather Armor]:[Hex Color Code]
# Available Material: LEATHER_HELMET, LEATHER_CHESTPLATE, LEATHER_LEGGINGS, LEATHER_BOOTS
Material: 'LEATHER_HELMET:#FF0000'
```

## 自定义模型数据

### 常规材料

**格式：**
```yaml
# Material Format: [custommodeldata]:[material]:[model data]
Material: 'custommodeldata:IRON_INGOT:123456'
```

### 皮革盔甲 / 药水

**格式：**
```yaml
# Material Format: [custommodeldata]:[material]:[model data]:[Hex Color Code|Potion ID]
Material: 'custommodeldata:LEATHER_HELMET:123456:#FFFFFF'
```
