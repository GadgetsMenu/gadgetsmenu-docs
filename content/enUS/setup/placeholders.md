---
title: Placeholders
description: 
group: setup
keywords: placeholders
topics:
 - placeholders
---

GadgetsMenu offers a few placeholders for those plugins who supported [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/). Plugins such as scoreboards and leaderboards that support PlaceholderAPI placeholders can use these placeholders to display GadgetsMenu's information. 

You're not required to download any expansion from ecloud, you can directly use these placeholders, as long as your server has GadgetsMenu plugin.

> **Note:** These placeholders are not available in GadgetsMenu itself.

## PlaceholderAPI

- To use the placeholder, you need to follow the syntax `%gadgetsmenu_<placeholder>%`.

**Example:** `%gadgetsmenu_mystery_dust%`, `%gadgetsmenu_mystery_boxes%`

### FeatherBoard
If you're using FeatherBoard, the placeholder syntax for its configuration is different, as shown below.

```
{placeholderapi_*} - (* = placeholder without %%)
ex: {placeholderapi_gadgetsmenu_mystery_dust}
```

## Placeholders

### General
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_mystery_dust%` | | Gets the player's mystery dust. | |
| `%gadgetsmenu_mystery_boxes%` | | Gets the player's mystery boxes. | |
| `%gadgetsmenu_<type>_pet_name%` | `<type>` | Gets the name of the pet. (Requires Premium version 4.5.0+) | `%gadgetsmenu_baby_pig_pet_name%`, `%gadgetsmenu_wolf_pet_name%` |
| `%gadgetsmenu_current_pet_name%` | | Gets the name of current spawned pet. (Requires Premium version 4.5.0+) | |
| `%gadgetsmenu_current_pet_level%` | | Gets the current level of the spawned pet. (Requires Premium version 4.5.0+) | |
| `%gadgetsmenu_current_pet_exp_obtained%` | | Gets the experience obtained of the current level of the spawned pet. (Requires Premium version 4.5.0+) | |
| `%gadgetsmenu_current_pet_exp_max%` | | Gets the maximum experience of the current level of the spawned pet. (Requires Premium version 5.2.0+) | |
| `%gadgetsmenu_pet_name%` | | Gets the name of the pet. (Deprecated) | |
</div>

### Settings
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Description               |
| ------------------------------------ | ------------------------- |
| `%gadgetsmenu_settings_bypasscooldown%` | Gets the status of bypass cooldown setting. |
| `%gadgetsmenu_settings_selfmorphview%` | Gets the status of self morph view setting. |
</div>

### Unlocked Cosmetic Items
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_unlocked_total%` | | Gets the total amount of cosmetics that player has unlocked. | |
| `%gadgetsmenu_unlocked_<cosmetic>%` | `<cosmetic>` | Gets the amount of specific cosmetic that player has unlocked. | `%gadgetsmenu_unlocked_hats%`, `%gadgetsmenu_unlocked_animated_hats%`, `%gadgetsmenu_unlocked_particles%`, `%gadgetsmenu_unlocked_suits%`, `%gadgetsmenu_unlocked_gadgets%`, `%gadgetsmenu_unlocked_pets%`, `%gadgetsmenu_unlocked_miniatures%`, `%gadgetsmenu_unlocked_morphs%`, `%gadgetsmenu_unlocked_banners%`, `%gadgetsmenu_unlocked_emotes%`, `%gadgetsmenu_unlocked_cloaks%` |
</div>

### Locked Cosmetic Items
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_locked_total%` | | Gets the total amount of cosmetics that player hasn't unlocked. | |
| `%gadgetsmenu_locked_<cosmetic>%` | `<cosmetic>` | Gets the amount of specific cosmetic that player hasn't unlocked. | `%gadgetsmenu_locked_hats%`, `%gadgetsmenu_locked_animated_hats%`, `%gadgetsmenu_locked_particles%`, `%gadgetsmenu_locked_suits%`, `%gadgetsmenu_locked_gadgets%`, `%gadgetsmenu_locked_pets%`, `%gadgetsmenu_locked_miniatures%`, `%gadgetsmenu_locked_morphs%`, `%gadgetsmenu_locked_banners%`, `%gadgetsmenu_locked_emotes%`, `%gadgetsmenu_locked_cloaks%` |
</div>

### Total Number of Cosmetic Items
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_total_size%` | | Get the total amount of cosmetic items available. | |
| `%gadgetsmenu_<cosmetic>_size%` | `<cosmetic>` | Get the total amount of specific cosmetic available. | `%gadgetsmenu_hats_size%`, `%gadgetsmenu_animated_hats_size%`, `%gadgetsmenu_particles_size%`, `%gadgetsmenu_suits_size%`, `%gadgetsmenu_gadgets_size%`, `%gadgetsmenu_pets_size%`, `%gadgetsmenu_miniatures_size%`, `%gadgetsmenu_morphs_size%`, `%gadgetsmenu_banners_size%`, `%gadgetsmenu_emotes_size%`, `%gadgetsmenu_cloaks_size%` |
</div>

### The Percentages of Unlocked Cosmetic Items
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_unlocked_total_percentages%` | | Get the percentages of cosmetics that player has unlocked. | |
| `%gadgetsmenu_unlocked_<cosmetic>_percentages%` | `<cosmetic>` | Get the percentages of specific cosmetic that player has unlocked. | `%gadgetsmenu_unlocked_hats_percentages%`, `%gadgetsmenu_unlocked_animated_hats_percentages%`, `%gadgetsmenu_unlocked_particles_percentages%`, `%gadgetsmenu_unlocked_suits_percentages%`, `%gadgetsmenu_unlocked_gadgets_percentages%`, `%gadgetsmenu_unlocked_pets_percentages%`, `%gadgetsmenu_unlocked_miniatures_percentages%`, `%gadgetsmenu_unlocked_morphs_percentages%`, `%gadgetsmenu_unlocked_banners_percentages%`, `%gadgetsmenu_unlocked_emotes_percentages%`, `%gadgetsmenu_unlocked_cloaks_percentages%` |
</div>

### Equipped Cosmetic Items
<div class="md-table-max-content md-table-no-bg-color md-table-width-100 md-table-column-4-width-25">

| Placeholder                          | Argument           | Description               | Example                       |
| ------------------------------------ |:------------------:| ------------------------- | ----------------------------- |
| `%gadgetsmenu_equipped_cosmetics%` | | Get the cosmetics that player equipped. | |
| `%gadgetsmenu_equipped_<cosmetic>%` | `<cosmetic>` | Get the specific cosmetic that player equipped. | `%gadgetsmenu_equipped_hat%`, `%gadgetsmenu_equipped_animated_hat%`, `%gadgetsmenu_equipped_particle%`, `%gadgetsmenu_equipped_suit_helmet%`, `%gadgetsmenu_equipped_suit_chestplate%`, `%gadgetsmenu_equipped_suit_leggings%`, `%gadgetsmenu_equipped_suit_boots%`, `%gadgetsmenu_equipped_gadget%`, `%gadgetsmenu_equipped_pet%`, `%gadgetsmenu_equipped_miniature%`, `%gadgetsmenu_equipped_morph%`, `%gadgetsmenu_equipped_banner%`, `%gadgetsmenu_equipped_emote%`, `%gadgetsmenu_equipped_cloak%` |
</div>