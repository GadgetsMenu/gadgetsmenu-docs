---
title: 开发者 API
description: 在您的插件中使用官方的 GadgetsMenu API，包括化妆品、神秘箱、小工具和表情事件。
group: developers
keywords: 开发者 api, api, 事件, bukkit 事件, 化妆品, 神秘箱, 小工具, 表情
topics:
 - 开发者 api
 - api
 - 事件
---

以下是您可以使用的官方 API。请勿使用未在此处列出的方法，否则可能引发不稳定问题，甚至导致插件崩溃。

## API 事件

<div class="md-relevant-content">
公共 API 现已为常见的化妆品操作提供 Bukkit 事件。这些
事件位于 `com.yapzhenyie.GadgetsMenu.api.event` 之下，并遵循
标准的 Bukkit 事件模式，包括 `getHandlerList()` 和
`@EventHandler`。

</div>

### 化妆品

包：`com.yapzhenyie.GadgetsMenu.api.event.cosmetics`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 事件 | 可取消 | 触发时机 |
| --- | :---: | --- |
| `ItemPurchaseEvent` | 是 | 玩家使用 Mystery Dust 购买化妆品时触发。该事件会提供值为 `SUCCESS` 或 `FAILED` 的 `PurchaseStatus`。成功的事件在扣除 Mystery Dust 之后、授予化妆品之前触发。取消该事件会自动退还 Mystery Dust。 |
| `CosmeticEquipEvent` | 是 | 玩家装备任意分类的化妆品时触发。取消该事件即可阻止在竞技场等场所或战斗期间装备化妆品。 |
| `CosmeticUnequipEvent` | 否 | 玩家卸下化妆品时触发。该事件仅用于通知。 |
| `CosmeticUnlockEvent` | 否 | 玩家通过 Mystery Dust 购买、神秘箱奖励或管理员/API 授予而获得某件化妆品时触发。 |

</div>
</div>

> `CosmeticEquipEvent`、`CosmeticUnequipEvent` 和 `CosmeticUnlockEvent`
> 通过 `getCosmeticType()` 以 `CosmeticType` 的形式提供该化妆品。它
> 提供化妆品的名称、显示名称、权限、稀有度以及 Mystery Dust 价格。
> 套装会为每一件盔甲部件分别触发一次事件。

### 神秘箱

包：`com.yapzhenyie.GadgetsMenu.api.event.mysteryboxes`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 事件 | 可取消 | 触发时机 |
| --- | :---: | --- |
| `MysteryBoxCraftEvent` | 是 | 玩家使用 Mystery Dust 合成神秘箱时触发。 |
| `MysteryBoxRewardEvent` | 否 | 玩家开启神秘箱后获得奖励时触发。使用 `isDuplicate()` 可以检查该奖励是否已经拥有。 |

</div>
</div>

### 小工具与表情

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 事件 | 包 | 可取消 | 触发时机 |
| --- | --- | :---: | --- |
| `GadgetActivateEvent` | `api.event.gadgets` | 是 | 玩家激活小工具时触发。使用 `isLeftClick()` 可以区分是左键还是右键激活。 |
| `EmoteActivateEvent` | `api.event.emotes` | 是 | 玩家激活表情时触发。 |

</div>
</div>

### 监听事件

注册这些事件的方式与其他任何 Bukkit 事件相同。例如，
下面的监听器会阻止玩家在竞技场内
装备化妆品：

```java
@EventHandler
public void onEquip(CosmeticEquipEvent event) {
    if (isInArena(event.getPlayer())) {
        event.setCancelled(true); // Block cosmetics inside arenas.
    }
}
```

所有新的 API 类都包含完整的 Javadoc 文档。

## 事件类参考

每个事件都继承自 Bukkit 的 `Event` 类，并提供 `getHandlers()` 和
静态的 `getHandlerList()`。标记为可取消的事件还会实现
`Cancellable`，并提供 `isCancelled()` 和 `setCancelled(boolean)`。

### 化妆品事件详情

#### <span class="md-api-event-name">ItemPurchaseEvent</span>

- **构造函数：** `ItemPurchaseEvent(Player player, Category category, String cosmeticName, String displayName, ItemCostDiscount discount, int price, String permission, PurchaseStatus status)`
- **便捷构造函数：** `ItemPurchaseEvent(Player player, ItemPurchaseMetadata metadata, PurchaseStatus status)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getCategory(): Category`<br>
  `getCosmeticName(): String`<br>
  `getDisplayName(): String`<br>
  `getItemCostDiscount(): ItemCostDiscount`<br>
  `getPrice(): int`<br>
  `getPermission(): String`<br>
  `getStatus(): PurchaseStatus`<br>
  `isSuccessful(): boolean`
- **枚举：** `PurchaseStatus.SUCCESS`, `PurchaseStatus.FAILED`
- **备注：** `getPrice()` 是折扣后的最终价格。`getItemCostDiscount()` 可能返回 `null`。元数据构造函数会复制这些值，不会暴露可变的 `ItemPurchaseMetadata`。

#### <span class="md-api-event-name">CosmeticEquipEvent</span>

- **构造函数：** `CosmeticEquipEvent(Player player, CosmeticType cosmeticType)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`
- **备注：** 在化妆品生效之前触发。包括菜单装备、自动装备以及恢复的化妆品。取消该事件会阻止装备。

#### <span class="md-api-event-name">CosmeticUnequipEvent</span>

- **构造函数：** `CosmeticUnequipEvent(Player player, CosmeticType cosmeticType)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`
- **备注：** 仅用于通知。只有当已激活的化妆品确实被移除时才会触发。

#### <span class="md-api-event-name">CosmeticUnlockEvent</span>

- **构造函数：** `CosmeticUnlockEvent(Player player, CosmeticType cosmeticType, Timestamp expiryTime)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`<br>
  `getExpiryTime(): Timestamp`<br>
  `isPermanent(): boolean`
- **备注：** 对于永久解锁，`getExpiryTime()` 返回 `null`，`isPermanent()` 返回 `true`。

`CosmeticType` 可用于获取化妆品的名称、显示名称、权限、
稀有度、Mystery Dust 价格、分类以及其他元数据。

### 神秘箱事件详情

#### <span class="md-api-event-name">MysteryBoxCraftEvent</span>

- **构造函数：** `MysteryBoxCraftEvent(Player player, CraftMysteryBoxType craftMysteryBoxType, int price)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getCraftMysteryBoxType(): CraftMysteryBoxType`<br>
  `getPrice(): int`
- **备注：** 在扣除 Mystery Dust 之前以及发放神秘箱之前触发。`getPrice()` 是折扣后的最终价格。取消该事件会阻止这两项操作。

#### <span class="md-api-event-name">MysteryBoxRewardEvent</span>

- **构造函数：** `MysteryBoxRewardEvent(Player player, MysteryBoxes mysteryBox, MysteryBoxesLoot loot, boolean duplicate)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getMysteryBox(): MysteryBoxes`<br>
  `getLoot(): MysteryBoxesLoot`<br>
  `isDuplicate(): boolean`
- **备注：** 仅用于通知，在奖励抽取完成后触发。`MysteryBoxesLoot` 包含化妆品的分类、名称、稀有度和显示名称。

#### <span class="md-api-event-name">OpenMysteryBoxEvent</span>

- **可取消：** 是
- **构造函数：** `OpenMysteryBoxEvent(Player player, MysteryBoxes mysteryBox)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getSelectedMysteryBox(): MysteryBoxes`
- **备注：** 取消该事件可阻止所选的神秘箱被开启。

#### <span class="md-api-event-name">PlayerSendMysteryGiftEvent</span>

- **可取消：** 否
- **构造函数：** `PlayerSendMysteryGiftEvent(Player sender, Player receiver)`
- **方法：**<br>
  `getSender(): Player`<br>
  `getReceiver(): Player`
- **备注：** 提供神秘礼物转赠中涉及的双方玩家。

### 小工具与表情事件详情

#### <span class="md-api-event-name">GadgetActivateEvent</span>

- **包：** `com.yapzhenyie.GadgetsMenu.api.event.gadgets`
- **构造函数：** `GadgetActivateEvent(Player player, GadgetType gadgetType, boolean leftClick)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getGadgetType(): GadgetType`<br>
  `isLeftClick(): boolean`
- **备注：** 可取消，在激活之前触发。右键激活时 `isLeftClick()` 为 `false`。

#### <span class="md-api-event-name">EmoteActivateEvent</span>

- **包：** `com.yapzhenyie.GadgetsMenu.api.event.emotes`
- **构造函数：** `EmoteActivateEvent(Player player, EmoteType emoteType)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getEmoteType(): EmoteType`
- **备注：** 可取消，在激活之前触发。

### Mystery Dust 事件

包：`com.yapzhenyie.GadgetsMenu.api.event.mysterydust`

#### <span class="md-api-event-name">AssignMysteryDustEvent</span>

- **可取消：** 是
- **构造函数：** `AssignMysteryDustEvent(Player player, int amount)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **备注：** 表示分配或设置玩家的 Mystery Dust 数量。取消该事件会阻止余额变动。

#### <span class="md-api-event-name">GainMysteryDustEvent</span>

- **可取消：** 是
- **构造函数：** `GainMysteryDustEvent(Player player, int amount)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **备注：** 表示向玩家添加 Mystery Dust。取消该事件会阻止余额变动。

#### <span class="md-api-event-name">RemoveMysteryDustEvent</span>

- **可取消：** 是
- **构造函数：** `RemoveMysteryDustEvent(Player player, int amount)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **备注：** 表示从玩家处移除 Mystery Dust。取消该事件会阻止余额变动。

### 宠物事件

包：`com.yapzhenyie.GadgetsMenu.api.event.pets`

#### 宠物生命周期

##### <span class="md-api-event-name">PetPreSpawnEvent</span>

- **可取消：** 否
- **构造函数：** `PetPreSpawnEvent(Player player, Location spawnLocation, PetType type)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getSpawnLocation(): Location`<br>
  `getPetType(): PetType`
- **备注：** 在宠物生成之前，提供玩家、预定的生成位置以及宠物类型。

##### <span class="md-api-event-name">PetRemoveEvent</span>

- **可取消：** 是
- **构造函数：** `PetRemoveEvent(Pet pet)`
- **方法：**<br>
  `getPet(): Pet`
- **备注：** 当已生成的宠物即将被移除时触发。取消该事件会阻止移除。

##### <span class="md-api-event-name">PetRenameEvent</span>

- **可取消：** 是
- **构造函数：** `PetRenameEvent(Player owner, GPet pet, String petName)`
- **方法：**<br>
  `getOwner(): Player`<br>
  `getPet(): GPet`<br>
  `getPetName(): String`
- **备注：** 提供主人、已存储的宠物数据以及请求的名称。取消该事件会阻止重命名。

> **当前实现：** 构造函数接受一个 `GPet`，但并未将其
> 赋值给事件字段，因此 `getPet()` 目前返回 `null`。

##### <span class="md-api-event-name">SendPetForMissionEvent</span>

- **可取消：** 否
- **构造函数：** `SendPetForMissionEvent(Player owner, GPet pet, int expObtained)`
- **方法：**<br>
  `getOwner(): Player`<br>
  `getGPet(): GPet`<br>
  `getEXPObtained(): int`
- **备注：** 提供主人、已存储的宠物数据以及从任务中获得的经验。

#### 宠物互动

##### <span class="md-api-event-name">PetHatEvent</span>

- **可取消：** 是
- **构造函数：** `PetHatEvent(Pet pet, Type type)`
- **方法：**<br>
  `getPet(): Pet`<br>
  `getEventType(): Type`
- **枚举：** `Type.SET`, `Type.REMOVE`
- **备注：** 控制将宠物设为帽子或将其取下。

##### <span class="md-api-event-name">PetRideEvent</span>

- **可取消：** 是
- **构造函数：** `PetRideEvent(Pet pet, Type type)`
- **方法：**<br>
  `getPet(): Pet`<br>
  `getEventType(): Type`
- **枚举：** `Type.MOUNT`, `Type.DISMOUNT`
- **备注：** 控制骑上或离开可骑乘的宠物。

#### <span class="md-api-event-name">PetMoveEvent</span>

- **可取消：** 否
- **构造函数：** `PetMoveEvent(IEntityPet entity, Cause cause)`
- **异步构造函数：** `PetMoveEvent(IEntityPet entity, Cause cause, boolean async)`
- **方法：**<br>
  `getEntity(): IEntityPet`<br>
  `getTargetLocation(): Location`<br>
  `getCause(): Cause`
- **枚举：** `Cause.RIDE`, `Cause.WALK`
- **目标位置：** 对于 `RIDE` 为该实体的当前位置，对于 `WALK` 为宠物主人的当前位置。
- **异步支持：** 三参数的构造函数会将 `async` 传递给 Bukkit 的 `Event` 构造函数。

> **当前实现：** 两参数的构造函数不会将其
> `cause` 参数赋值给事件字段。使用它构造的事件可能会从
> `getCause()` 返回 `null`。

### 神秘宝库事件

包：`com.yapzhenyie.GadgetsMenu.api.event.mysteryvault`

#### <span class="md-api-event-name">MysteryVaultPreviewEvent</span>

- **可取消：** 是
- **构造函数：** `MysteryVaultPreviewEvent(Player player, MysteryVault mysteryVault)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getClickedMysteryVault(): MysteryVault`
- **备注：** 提供玩家以及被点击的神秘宝库。取消该事件会阻止预览操作。

### 黑名单地区事件

包：`com.yapzhenyie.GadgetsMenu.api.event.blacklistedregion`

这些 WorldGuard 集成事件会在玩家跨越已配置的
化妆品限制边界时进行上报。

#### <span class="md-api-event-name">EnterBlacklistedRegionEvent</span>

- **可取消：** 否
- **构造函数：** `EnterBlacklistedRegionEvent(Player player, boolean isReverseWhitelist, BlacklistedRegionType regionType)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getRegionType(): BlacklistedRegionType`
- **备注：** 在玩家进入已配置的化妆品限制边界时上报。

#### <span class="md-api-event-name">ExitBlacklistedRegionEvent</span>

- **可取消：** 否
- **构造函数：** `ExitBlacklistedRegionEvent(Player player, boolean isReverseWhitelist, BlacklistedRegionType regionType)`
- **方法：**<br>
  `getPlayer(): Player`<br>
  `getRegionType(): BlacklistedRegionType`
- **备注：** 在玩家离开已配置的化妆品限制边界时上报。

> 两个构造函数都接受 `isReverseWhitelist`，但当前的公共类
> 并未为该值提供 getter 方法。

### 完整的监听器示例

```java
import com.yapzhenyie.GadgetsMenu.api.event.cosmetics.CosmeticEquipEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public final class CosmeticListener implements Listener {

    @EventHandler
    public void onEquip(CosmeticEquipEvent event) {
        if (isInArena(event.getPlayer())) {
            event.setCancelled(true);
        }
    }
}
```

在您插件的 `onEnable()` 方法中注册该监听器：

```java
getServer().getPluginManager().registerEvents(new CosmeticListener(), this);
```

## 使用开发者 API

下面各节介绍可直接读取或修改玩家
GadgetsMenu 数据的方法。它们与上面的事件 API 相互独立：事件用于在某个操作发生时通知您的
插件，而 `PlayerManager` 则让您的插件能够执行某项
操作或获取玩家数据。

### 获取玩家的 API 管理器

大多数开发者 API 方法都可以通过 `PlayerManager` 使用。将
在线的 Bukkit `Player` 传给 `GadgetsMenuAPI.getPlayerManager(Player)`，并将
返回的管理器保存在局部变量中，以便执行您想要的操作。

```java
import org.bukkit.entity.Player;

import com.yapzhenyie.GadgetsMenu.api.GadgetsMenuAPI;
import com.yapzhenyie.GadgetsMenu.player.PlayerManager;

public static void doSomeAction(Player player) {
    PlayerManager playerManager = GadgetsMenuAPI.getPlayerManager(player);

    // Use the Developer API for this player.
    int mysteryDust = playerManager.getMysteryDust();
}
```

以下各节中的示例均假设名为
`playerManager` 的变量已按上述方式获取。

> 请在服务器主线程上获取和使用 Bukkit 玩家数据，除非某个方法的
> 文档明确说明支持
> 异步使用。

## 常规玩家设置

#### 获取玩家的 Mystery Dust
```java
playerManager.getMysteryDust();
```

#### 增加玩家的 Mystery Dust
```java
playerManager.addMysteryDust(amount);
```

#### 设置玩家的 Mystery Dust
```java
playerManager.setMysteryDust(amount);
```

#### 移除玩家的 Mystery Dust
```java
playerManager.removeMysteryDust(amount);
```

#### 获取玩家的神秘箱
```java
playerManager.getMysteryBoxes();
```

#### 向玩家发放神秘箱
```java
/**
 * Give player mystery boxes.
 * 
 * @param MysteryBoxType
 *   The type of mystery boxes.
 * @param expiryDate
 *   The expiry date of mystery boxes.
 *   Set to null won't expire.
 * @param requirePerm
 *   Does player need to require permission to open it.
 * @param details
 *   The details of gifted mystery box(sender) and crafted mystery
 *   box(craft date).
 * @param amount
 *   The amount of the mystery boxes will give to player.
 */
playerManager.giveMysteryBoxes(MysteryBoxType mysteryBoxType, Long expiryDate, boolean requirePerm, String details, int amount);

/**
 * MysteryBox Types: NORMAL_MYSTERY_BOX_1, NORMAL_MYSTERY_BOX_2, NORMAL_MYSTERY_BOX_3, NORMAL_MYSTERY_BOX_4, 
 *                   NORMAL_MYSTERY_BOX_5
 * expiryDate: System.currentTimeMillis() + (24 * 3600 * 1000) // 1 day; Set to null, the mystery box won't expire.
 * requirePerm: true or false
 * details: always set to null
 * amount: How many mystery boxes should be given.
Ex: playerManager.giveMysteryBoxes(MysteryBoxType.NORMAL_MYSTERY_BOX_3, (System.currentTimeMillis() + (24 * 3600 * 1000)), true, null, 1);

```

#### 获取玩家的神秘礼物
```java
playerManager.getGiftPacks();
```

#### 向玩家发放神秘礼物
```java
 /**
  * Give player's mystery gifts.
  * Each gift contains 5 mystery boxes.
  */
  playerManager.addGiftPacks(amount);
```
#### 向玩家发放菜单选择器
```java
playerManager.giveMenuSelector();
```

## 打开特定菜单

#### 打开主菜单
```java
playerManager.goBackToMainMenu();
```

#### 打开帽子菜单
```java
playerManager.openHatsMenu(page);
```

#### 打开动画帽子菜单
```java
playerManager.openAnimatedHatsMenu(page);
```

#### 打开粒子效果菜单
```java
playerManager.openParticlesMenu(page);
```

#### 打开套装菜单
```java
playerManager.openSuitsMenu();
```

#### 打开特定套装部件菜单
```java
 /**
  * @param type The SuitType.
  */
  playerManager.openSuitEquipmentMenu(type);
```

#### 打开小工具分类菜单
```java
playerManager.openCategoryGadgetsMenu();
```

#### 打开特定小工具类型菜单
```java
 /**
  * @param type The GadgetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openGadgetTypesMenu(type, page);
```

#### 打开宠物分类菜单
```java
playerManager.openCategoryPetsMenu();
```

#### 打开特定宠物类型菜单
```java
 /**
  * @param type The PetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openPetTypesMenu(type, page);
```

#### 打开 Morphs 菜单
```java
playerManager.openMorphsMenu();
```

#### 打开旗帜菜单
```java
playerManager.openBannersMenu(page);
```

#### 打开表情菜单
```java
playerManager.openMorphsMenu(page);
```

#### 打开披风菜单
```java
playerManager.openCloaksMenu();
```

## 装备与卸下化妆品

#### 装备与卸下帽子
```java
/**
 * Equip hat.
 * @param type The HatType.
 */
 playerManager.equipHat(type);

/**
 * Unequip hat.
 */
 playerManager.unequipHat();
```

#### 装备与卸下动画帽子
```java
/**
 * Equip animated hat.
 * @param type The AnimatedHatType.
 */
 playerManager.equipAnimatedHat(type);

/**
 * Unequip animatedhat.
 */
 playerManager.unequipAnimatedHat();
```

#### 装备与卸下粒子效果
```java
/**
 * Equip particle.
 * @param type The ParticleType.
 */
 playerManager.equipParticle(type);

/**
 * Unequip particle.
 */
 playerManager.unequipParticle();
```

#### 装备与卸下套装
```java
/**
 * Equip suit.
 * @param type The SuitType.
 */
 playerManager.equipSuit(type);

/**
 * Unequip suit.
 */
 playerManager.unequipSuit();
```

#### 装备与卸下小工具
```java
/**
 * Equip gadget.
 * @param type The GadgetType.
 */
 playerManager.equipGadget(type);

/**
 * Unequip gadget.
 */
 playerManager.unequipGadget();
```

#### 装备与卸下宠物
```java
/**
 * Equip pet.
 * @param type The PetType.
 */
 playerManager.equipPet(type);

/**
 * Unequip pet.
 */
 playerManager.unequipPet();
```

#### 装备与卸下 Morph
```java
/**
 * Equip morph.
 * @param type The MorphType.
 */
 playerManager.equipMorph(type);

/**
 * Unequip morph.
 */
 playerManager.unequipMorph();
```

#### 装备与卸下旗帜
```java
/**
 * Equip banner.
 * @param type The BannerType.
 */
 playerManager.equipBanner(type);

/**
 * Unequip banner.
 */
 playerManager.unequipBanner();
```

#### 装备与卸下表情
```java
/**
 * Equip emote.
 * @param type The EmoteType.
 */
 playerManager.equipEmote(type);

/**
 * Unequip emote.
 */
 playerManager.unequipEmote();
```

#### 装备与卸下披风
```java
/**
 * Equip cloak.
 * @param type The CloakType.
 */
 playerManager.equipCloak(type);

/**
 * Unequip cloak.
 */
 playerManager.unequipCloak();
```
