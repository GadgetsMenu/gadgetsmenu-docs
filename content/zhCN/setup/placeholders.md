---
title: 占位符
description: 您可以使用这些占位符来显示玩家信息，包括 Mystery Dust 数量、神秘箱数量、已解锁化妆品数量以及已装备的化妆品等。
group: setup
keywords: 占位符
topics:
 - 占位符
---

GadgetsMenu 为支持 [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) 的插件提供了一些占位符。计分板和排行榜等支持 PlaceholderAPI 占位符的插件，可以使用这些占位符来显示 GadgetsMenu 的信息。

您无需从 ecloud 下载任何扩展，只要您的服务器安装了 GadgetsMenu 插件，就可以直接使用这些占位符。

> **注意：** 这些占位符同样可以在 GadgetsMenu 中使用。您可以在 GadgetsMenu 的配置文件中使用这些占位符。

## PlaceholderAPI

- 要使用占位符，您需要遵循 `%gadgetsmenu_<placeholder>%` 的语法。

**示例：** `%gadgetsmenu_mystery_dust%`、`%gadgetsmenu_mystery_boxes%`

### FeatherBoard
如果您使用的是 FeatherBoard，其配置中的占位符语法有所不同，如下所示。

```
{placeholderapi_*} - (* = placeholder without %%)
ex: {placeholderapi_gadgetsmenu_mystery_dust}
```

## 占位符

### 通用
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_mystery_dust%` | | 获取玩家的 Mystery Dust。 | |
| `%gadgetsmenu_mystery_boxes%` | | 获取玩家的神秘箱。 | |
| `%gadgetsmenu_<type>_pet_name%` | `<type>` | 获取宠物的名字。（已弃用） | 注意：将在 5.20.0 版本中移除 |
| `%gadgetsmenu_pet_name%` | | 获取宠物的名字。（已弃用） | 注意：将在 5.20.0 版本中移除 |
</div>

### 宠物信息
这些占位符将返回宠物的信息。您可以使用 `当前已召唤的宠物` 专用占位符来显示当前已召唤宠物的信息；或者使用 `指定宠物类型` 占位符来指定您想要显示的宠物数据。

> **注意：** 这些占位符仅在高级版中可用。

#### 当前已召唤的宠物

<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符 | 说明 |
| - | - |
| `%gadgetsmenu_current_pet_name%` | 返回当前已召唤宠物的名字。 |
| `%gadgetsmenu_current_pet_level%` | 返回当前已召唤宠物的等级。 |
| `%gadgetsmenu_current_pet_exp_obtained%` | 返回当前已召唤宠物在当前等级已获得的经验。 |
| `%gadgetsmenu_current_pet_exp_max%` | 返回当前已召唤宠物在当前等级所需的最大经验。 |
| `%gadgetsmenu_current_pet_attribute_hunger%` | 返回当前宠物的饥饿度等级。 |
| `%gadgetsmenu_current_pet_attribute_thirst%` | 返回当前宠物的口渴度等级。 |
| `%gadgetsmenu_current_pet_attribute_exercise%` | 返回当前宠物的运动量等级。 |
| `%gadgetsmenu_current_pet_attribute_happiness%` | 返回当前宠物的快乐度状态。 |
</div>

#### 指定宠物类型
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符 | 参数 | 说明 | 示例 |
| - |:-:| - | -- |
| `%gadgetsmenu_pet_name_<type>%` | `<type>` | 返回该宠物的名字。 | `%gadgetsmenu_pet_name_baby_pig%`、`%gadgetsmenu_pet_name_wolf%`、`%gadgetsmenu_pet_name_angry_bee%` |
| `%gadgetsmenu_pet_level_<type>%` | `<type>` | 返回该宠物的当前等级。 | `%gadgetsmenu_pet_level_wolf%` |
| `%gadgetsmenu_pet_exp_obtained_<type>%` | `<type>` | 返回该宠物在当前等级已获得的经验。 | `%gadgetsmenu_pet_exp_obtained_wolf%` |
| `%gadgetsmenu_pet_exp_max_<type>%` | `<type>` | 返回该宠物在当前等级所需的最大经验。 | `%gadgetsmenu_pet_exp_max_wolf%` |
| `%gadgetsmenu_pet_attribute_hunger_<type>%` | `<type>` | 返回该宠物的饥饿度等级。 | `%gadgetsmenu_pet_attribute_hunger_wolf%` |
| `%gadgetsmenu_pet_attribute_thirst_<type>%` | `<type>` | 返回该宠物的口渴度等级。 | `%gadgetsmenu_pet_attribute_thirst_wolf%` |
| `%gadgetsmenu_pet_attribute_exercise_<type>%` | `<type>` | 返回该宠物的运动量等级。 | `%gadgetsmenu_pet_attribute_exercise_wolf%` |
| `%gadgetsmenu_pet_attribute_happiness_<type>%` | `<type>` | 返回该宠物的快乐度状态。 | `%gadgetsmenu_pet_attribute_happiness_wolf%` |
</div>

### 宠物物品
- 参考：[宠物物品列表](wiki/features/cosmetic-items/pets#pet-items)
- `<pet_item>` 语法：宠物物品名称全部小写，并将空格替换为 `_` 下划线。（例如：sparring_sword、pumpkin_pie）

<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符 | 参数 | 说明 | 示例 |
| - |:-:| - | -- |
| `%gadgetsmenu_pet_items_<pet_item>%` | `<pet_item>` | 返回玩家当前拥有的该宠物物品数量。 | `%gadgetsmenu_pet_items_apple%`、`%gadgetsmenu_pet_items_water%`、`%gadgetsmenu_pet_items_sparring_sword%` |
</div>

### 设置
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 说明               |
| ------------------------------------ | ------------------------- |
| `%gadgetsmenu_settings_bypasscooldown%` | 获取“绕过冷却时间”设置的状态。 |
| `%gadgetsmenu_settings_selfmorphview%` | 获取“自身伪装视角”设置的状态。 |
</div>

### 已解锁的化妆品
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_unlocked_total%` | | 获取玩家已解锁的化妆品总数。 | |
| `%gadgetsmenu_unlocked_<cosmetic>%` | `<cosmetic>` | 获取玩家已解锁的指定化妆品数量。 | `%gadgetsmenu_unlocked_hats%`、`%gadgetsmenu_unlocked_animated_hats%`、`%gadgetsmenu_unlocked_particles%`、`%gadgetsmenu_unlocked_suits%`、`%gadgetsmenu_unlocked_gadgets%`、`%gadgetsmenu_unlocked_pets%`、`%gadgetsmenu_unlocked_miniatures%`、`%gadgetsmenu_unlocked_morphs%`、`%gadgetsmenu_unlocked_banners%`、`%gadgetsmenu_unlocked_emotes%`、`%gadgetsmenu_unlocked_cloaks%` |
</div>

### 未解锁的化妆品
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_locked_total%` | | 获取玩家尚未解锁的化妆品总数。 | |
| `%gadgetsmenu_locked_<cosmetic>%` | `<cosmetic>` | 获取玩家尚未解锁的指定化妆品数量。 | `%gadgetsmenu_locked_hats%`、`%gadgetsmenu_locked_animated_hats%`、`%gadgetsmenu_locked_particles%`、`%gadgetsmenu_locked_suits%`、`%gadgetsmenu_locked_gadgets%`、`%gadgetsmenu_locked_pets%`、`%gadgetsmenu_locked_miniatures%`、`%gadgetsmenu_locked_morphs%`、`%gadgetsmenu_locked_banners%`、`%gadgetsmenu_locked_emotes%`、`%gadgetsmenu_locked_cloaks%` |
</div>

### 化妆品总数
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_total_size%` | | 获取可用化妆品的总数。 | |
| `%gadgetsmenu_<cosmetic>_size%` | `<cosmetic>` | 获取指定化妆品的可用总数。 | `%gadgetsmenu_hats_size%`、`%gadgetsmenu_animated_hats_size%`、`%gadgetsmenu_particles_size%`、`%gadgetsmenu_suits_size%`、`%gadgetsmenu_gadgets_size%`、`%gadgetsmenu_pets_size%`、`%gadgetsmenu_miniatures_size%`、`%gadgetsmenu_morphs_size%`、`%gadgetsmenu_banners_size%`、`%gadgetsmenu_emotes_size%`、`%gadgetsmenu_cloaks_size%` |
</div>

### 已解锁化妆品的百分比
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_unlocked_total_percentages%` | | 获取玩家已解锁化妆品的百分比。 | |
| `%gadgetsmenu_unlocked_<cosmetic>_percentages%` | `<cosmetic>` | 获取玩家已解锁的指定化妆品的百分比。 | `%gadgetsmenu_unlocked_hats_percentages%`、`%gadgetsmenu_unlocked_animated_hats_percentages%`、`%gadgetsmenu_unlocked_particles_percentages%`、`%gadgetsmenu_unlocked_suits_percentages%`、`%gadgetsmenu_unlocked_gadgets_percentages%`、`%gadgetsmenu_unlocked_pets_percentages%`、`%gadgetsmenu_unlocked_miniatures_percentages%`、`%gadgetsmenu_unlocked_morphs_percentages%`、`%gadgetsmenu_unlocked_banners_percentages%`、`%gadgetsmenu_unlocked_emotes_percentages%`、`%gadgetsmenu_unlocked_cloaks_percentages%` |
</div>

### 已装备的化妆品
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符                          | 参数           | 说明               | 示例                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_equipped_cosmetics%` | | 获取玩家已装备的化妆品。 | |
| `%gadgetsmenu_equipped_<cosmetic>%` | `<cosmetic>` | 获取玩家已装备的指定化妆品。 | `%gadgetsmenu_equipped_hat%`、`%gadgetsmenu_equipped_animated_hat%`、`%gadgetsmenu_equipped_particle%`、`%gadgetsmenu_equipped_suit_helmet%`、`%gadgetsmenu_equipped_suit_chestplate%`、`%gadgetsmenu_equipped_suit_leggings%`、`%gadgetsmenu_equipped_suit_boots%`、`%gadgetsmenu_equipped_gadget%`、`%gadgetsmenu_equipped_pet%`、`%gadgetsmenu_equipped_miniature%`、`%gadgetsmenu_equipped_morph%`、`%gadgetsmenu_equipped_banner%`、`%gadgetsmenu_equipped_emote%`、`%gadgetsmenu_equipped_cloak%` |
</div>

### 查看化妆品权限状态

<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| 占位符 | 参数 | 说明 | 示例 |
| - |:-:| - | -- |
| `%gadgetsmenu_has_permission_<cosmetic>_<permission>%` | `<cosmetic>`、`<permission>` | 获取某件化妆品的权限状态。 | `%gadgetsmenu_has_permission_banner_skullking%`、`%gadgetsmenu_has_permission_hat_hamburger%` |
</div>

#### 输出示例：
 - 拥有权限 -> `yes`
 - 没有权限 -> `no`

#### 参数：`<cosmetic>`

**可用值：** `hat`、`animated_hat`、`particle`、`suit`、`gadget`、`pet`、`miniature`、`morph`、`banner`、`emote`、`cloak`


#### 参数：`<permission>`

`<permission>` 的值来源于一份与化妆品效果相关的预定义权限列表。这些权限遵循以下格式：

```
gadgetsmenu.hats.hamburger
gadgetsmenu.animatedhats.siren
gadgetsmenu.particles.watersplash
gadgetsmenu.gadgets.divingboard
gadgetsmenu.pets.blackrabbit
gadgetsmenu.miniatures.doge
gadgetsmenu.morphs.pig
gadgetsmenu.banners.snowbunny
gadgetsmenu.emotes.smile
gadgetsmenu.cloaks.superhero
```
[完整权限列表](../wiki/getting-started/permissions)

**获取占位符中正确 `<permission>` 值的方法：**
 1. 从上方列表中取出完整的权限字符串。
 2. 从该字符串中移除前缀 `"gadgetsmenu.<cosmetic>."`。
 3. 将剩余部分用作 `<permission>` 的值。

**示例：**
`gadgetsmenu.hats.hamburger`
 - 移除 `"gadgetsmenu.hats."`
 - 得到的 `<permission>` 值为：`hamburger`
 - 最终的占位符为：`%gadgetsmenu_has_permission_hat_hamburger%`

**更多示例：** `%gadgetsmenu_has_permission_animated_hat_siren%`、`%gadgetsmenu_has_permission_particle_watersplash%`、`%gadgetsmenu_has_permission_gadget_divingboard%`、`%gadgetsmenu_has_permission_pet_blackrabbit%`、`%gadgetsmenu_has_permission_miniature_doge%`
