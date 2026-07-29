---
title: Developer API
description: Use the official GadgetsMenu API, including cosmetic, mystery box, gadget, and emote events, in your plugin.
group: developers
keywords: developer api, api, events, bukkit events, cosmetics, mystery boxes, gadgets, emotes
topics:
 - developer api
 - api
 - events
---

Here is the official API that you can use. Please do not use the method that didn't list here, it may cause some unstable issue and may crash the plugin.

## API events

<div class="md-relevant-content">
The public API now provides Bukkit events for common cosmetic actions. The
events are located under `com.yapzhenyie.GadgetsMenu.api.event` and follow the
standard Bukkit event pattern, including `getHandlerList()` and
`@EventHandler`.

</div>

### Cosmetics

Package: `com.yapzhenyie.GadgetsMenu.api.event.cosmetics`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Event | Cancellable | Fired when |
| --- | :---: | --- |
| `ItemPurchaseEvent` | Yes | A player purchases a cosmetic with mystery dust. The event exposes a `PurchaseStatus` of `SUCCESS` or `FAILED`. A successful event fires after the dust is deducted but before the cosmetic is granted. Cancelling it automatically refunds the dust. |
| `CosmeticEquipEvent` | Yes | A player equips a cosmetic from any category. Cancel the event to prevent equipping in places such as arenas or during combat. |
| `CosmeticUnequipEvent` | No | A player unequips a cosmetic. This event is informational. |
| `CosmeticUnlockEvent` | No | A cosmetic becomes owned by a player through a mystery dust purchase, mystery box reward, or admin/API grant. |

</div>
</div>

> `CosmeticEquipEvent`, `CosmeticUnequipEvent`, and `CosmeticUnlockEvent`
> expose the cosmetic as a `CosmeticType` through `getCosmeticType()`. This
> provides its name, display name, permission, rarity, and mystery dust price.
> Suits fire one event for each armour piece.

### Mystery boxes

Package: `com.yapzhenyie.GadgetsMenu.api.event.mysteryboxes`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Event | Cancellable | Fired when |
| --- | :---: | --- |
| `MysteryBoxCraftEvent` | Yes | A player crafts a mystery box with mystery dust. |
| `MysteryBoxRewardEvent` | No | A player receives a reward after opening a mystery box. Use `isDuplicate()` to check whether the reward was already owned. |

</div>
</div>

### Gadgets and emotes

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Event | Package | Cancellable | Fired when |
| --- | --- | :---: | --- |
| `GadgetActivateEvent` | `api.event.gadgets` | Yes | A player activates a gadget. Use `isLeftClick()` to distinguish between left-click and right-click activation. |
| `EmoteActivateEvent` | `api.event.emotes` | Yes | A player activates an emote. |

</div>
</div>

### Listening for an event

Register these events in the same way as any other Bukkit event. For example,
the following listener prevents players from equipping cosmetics inside an
arena:

```java
@EventHandler
public void onEquip(CosmeticEquipEvent event) {
    if (isInArena(event.getPlayer())) {
        event.setCancelled(true); // Block cosmetics inside arenas.
    }
}
```

All of the new API classes include full Javadoc documentation.

## Event class reference

Every event extends Bukkit's `Event` class and exposes `getHandlers()` and the
static `getHandlerList()`. Events marked as cancellable also implement
`Cancellable` and expose `isCancelled()` and `setCancelled(boolean)`.

### Cosmetic event details

#### <span class="md-api-event-name">ItemPurchaseEvent</span>

- **Constructor:** `ItemPurchaseEvent(Player player, Category category, String cosmeticName, String displayName, ItemCostDiscount discount, int price, String permission, PurchaseStatus status)`
- **Convenience constructor:** `ItemPurchaseEvent(Player player, ItemPurchaseMetadata metadata, PurchaseStatus status)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getCategory(): Category`<br>
  `getCosmeticName(): String`<br>
  `getDisplayName(): String`<br>
  `getItemCostDiscount(): ItemCostDiscount`<br>
  `getPrice(): int`<br>
  `getPermission(): String`<br>
  `getStatus(): PurchaseStatus`<br>
  `isSuccessful(): boolean`
- **Enum:** `PurchaseStatus.SUCCESS`, `PurchaseStatus.FAILED`
- **Notes:** `getPrice()` is the final price after discounts. `getItemCostDiscount()` may return `null`. The metadata constructor copies the values; it does not expose the mutable `ItemPurchaseMetadata`.

#### <span class="md-api-event-name">CosmeticEquipEvent</span>

- **Constructor:** `CosmeticEquipEvent(Player player, CosmeticType cosmeticType)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`
- **Notes:** Fires before the cosmetic is applied. It includes menu equips, automatic equips, and restored cosmetics. Cancelling blocks the equip.

#### <span class="md-api-event-name">CosmeticUnequipEvent</span>

- **Constructor:** `CosmeticUnequipEvent(Player player, CosmeticType cosmeticType)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`
- **Notes:** Informational. It fires only when an active cosmetic is actually removed.

#### <span class="md-api-event-name">CosmeticUnlockEvent</span>

- **Constructor:** `CosmeticUnlockEvent(Player player, CosmeticType cosmeticType, Timestamp expiryTime)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getCosmeticType(): CosmeticType`<br>
  `getCategory(): Category`<br>
  `getExpiryTime(): Timestamp`<br>
  `isPermanent(): boolean`
- **Notes:** `getExpiryTime()` returns `null` and `isPermanent()` returns `true` for a permanent unlock.

`CosmeticType` gives access to the cosmetic name, display name, permission,
rarity, mystery dust price, category, and other metadata.

### Mystery box event details

#### <span class="md-api-event-name">MysteryBoxCraftEvent</span>

- **Constructor:** `MysteryBoxCraftEvent(Player player, CraftMysteryBoxType craftMysteryBoxType, int price)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getCraftMysteryBoxType(): CraftMysteryBoxType`<br>
  `getPrice(): int`
- **Notes:** Fires before dust is deducted and before the box is awarded. `getPrice()` is the final price after discounts. Cancelling prevents both operations.

#### <span class="md-api-event-name">MysteryBoxRewardEvent</span>

- **Constructor:** `MysteryBoxRewardEvent(Player player, MysteryBoxes mysteryBox, MysteryBoxesLoot loot, boolean duplicate)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getMysteryBox(): MysteryBoxes`<br>
  `getLoot(): MysteryBoxesLoot`<br>
  `isDuplicate(): boolean`
- **Notes:** Informational and fired after the reward is rolled. `MysteryBoxesLoot` contains the cosmetic category, name, rarity, and display name.

#### <span class="md-api-event-name">OpenMysteryBoxEvent</span>

- **Cancellable:** Yes
- **Constructor:** `OpenMysteryBoxEvent(Player player, MysteryBoxes mysteryBox)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getSelectedMysteryBox(): MysteryBoxes`
- **Notes:** Cancel the event to prevent the selected mystery box from opening.

#### <span class="md-api-event-name">PlayerSendMysteryGiftEvent</span>

- **Cancellable:** No
- **Constructor:** `PlayerSendMysteryGiftEvent(Player sender, Player receiver)`
- **Methods:**<br>
  `getSender(): Player`<br>
  `getReceiver(): Player`
- **Notes:** Exposes both players involved in a mystery gift transfer.

### Gadget and emote event details

#### <span class="md-api-event-name">GadgetActivateEvent</span>

- **Package:** `com.yapzhenyie.GadgetsMenu.api.event.gadgets`
- **Constructor:** `GadgetActivateEvent(Player player, GadgetType gadgetType, boolean leftClick)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getGadgetType(): GadgetType`<br>
  `isLeftClick(): boolean`
- **Notes:** Cancellable and fired before activation. `isLeftClick()` is `false` for a right-click activation.

#### <span class="md-api-event-name">EmoteActivateEvent</span>

- **Package:** `com.yapzhenyie.GadgetsMenu.api.event.emotes`
- **Constructor:** `EmoteActivateEvent(Player player, EmoteType emoteType)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getEmoteType(): EmoteType`
- **Notes:** Cancellable and fired before activation.

### Mystery dust events

Package: `com.yapzhenyie.GadgetsMenu.api.event.mysterydust`

#### <span class="md-api-event-name">AssignMysteryDustEvent</span>

- **Cancellable:** Yes
- **Constructor:** `AssignMysteryDustEvent(Player player, int amount)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **Notes:** Represents assigning or setting a player's mystery dust amount. Cancelling prevents the balance change.

#### <span class="md-api-event-name">GainMysteryDustEvent</span>

- **Cancellable:** Yes
- **Constructor:** `GainMysteryDustEvent(Player player, int amount)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **Notes:** Represents mystery dust being added to a player. Cancelling prevents the balance change.

#### <span class="md-api-event-name">RemoveMysteryDustEvent</span>

- **Cancellable:** Yes
- **Constructor:** `RemoveMysteryDustEvent(Player player, int amount)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getAmount(): int`
- **Notes:** Represents mystery dust being removed from a player. Cancelling prevents the balance change.

### Pet events

Package: `com.yapzhenyie.GadgetsMenu.api.event.pets`

#### Pet lifecycle

##### <span class="md-api-event-name">PetPreSpawnEvent</span>

- **Cancellable:** No
- **Constructor:** `PetPreSpawnEvent(Player player, Location spawnLocation, PetType type)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getSpawnLocation(): Location`<br>
  `getPetType(): PetType`
- **Notes:** Exposes the player, intended spawn location, and pet type before the pet spawns.

##### <span class="md-api-event-name">PetRemoveEvent</span>

- **Cancellable:** Yes
- **Constructor:** `PetRemoveEvent(Pet pet)`
- **Methods:**<br>
  `getPet(): Pet`
- **Notes:** Fires when a spawned pet is being removed. Cancelling prevents removal.

##### <span class="md-api-event-name">PetRenameEvent</span>

- **Cancellable:** Yes
- **Constructor:** `PetRenameEvent(Player owner, GPet pet, String petName)`
- **Methods:**<br>
  `getOwner(): Player`<br>
  `getPet(): GPet`<br>
  `getPetName(): String`
- **Notes:** Exposes the owner, stored pet data, and requested name. Cancelling prevents renaming.

> **Current implementation:** the constructor accepts a `GPet` but does not
> assign it to the event field, so `getPet()` currently returns `null`.

##### <span class="md-api-event-name">SendPetForMissionEvent</span>

- **Cancellable:** No
- **Constructor:** `SendPetForMissionEvent(Player owner, GPet pet, int expObtained)`
- **Methods:**<br>
  `getOwner(): Player`<br>
  `getGPet(): GPet`<br>
  `getEXPObtained(): int`
- **Notes:** Exposes the owner, stored pet data, and experience obtained from the mission.

#### Pet interactions

##### <span class="md-api-event-name">PetHatEvent</span>

- **Cancellable:** Yes
- **Constructor:** `PetHatEvent(Pet pet, Type type)`
- **Methods:**<br>
  `getPet(): Pet`<br>
  `getEventType(): Type`
- **Enum:** `Type.SET`, `Type.REMOVE`
- **Notes:** Controls setting or removing a pet as a hat.

##### <span class="md-api-event-name">PetRideEvent</span>

- **Cancellable:** Yes
- **Constructor:** `PetRideEvent(Pet pet, Type type)`
- **Methods:**<br>
  `getPet(): Pet`<br>
  `getEventType(): Type`
- **Enum:** `Type.MOUNT`, `Type.DISMOUNT`
- **Notes:** Controls mounting or dismounting a rideable pet.

#### <span class="md-api-event-name">PetMoveEvent</span>

- **Cancellable:** No
- **Constructor:** `PetMoveEvent(IEntityPet entity, Cause cause)`
- **Async constructor:** `PetMoveEvent(IEntityPet entity, Cause cause, boolean async)`
- **Methods:**<br>
  `getEntity(): IEntityPet`<br>
  `getTargetLocation(): Location`<br>
  `getCause(): Cause`
- **Enum:** `Cause.RIDE`, `Cause.WALK`
- **Target location:** The entity's current location for `RIDE`, or the pet owner's current location for `WALK`.
- **Async support:** The three-argument constructor passes `async` to Bukkit's `Event` constructor.

> **Current implementation:** the two-argument constructor does not assign its
> `cause` parameter to the event field. Events constructed with it may return
> `null` from `getCause()`.

### Mystery vault events

Package: `com.yapzhenyie.GadgetsMenu.api.event.mysteryvault`

#### <span class="md-api-event-name">MysteryVaultPreviewEvent</span>

- **Cancellable:** Yes
- **Constructor:** `MysteryVaultPreviewEvent(Player player, MysteryVault mysteryVault)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getClickedMysteryVault(): MysteryVault`
- **Notes:** Exposes the player and clicked vault. Cancelling prevents the preview action.

### Blacklisted region events

Package: `com.yapzhenyie.GadgetsMenu.api.event.blacklistedregion`

These WorldGuard integration events report when players cross configured
cosmetic restriction boundaries.

#### <span class="md-api-event-name">EnterBlacklistedRegionEvent</span>

- **Cancellable:** No
- **Constructor:** `EnterBlacklistedRegionEvent(Player player, boolean isReverseWhitelist, BlacklistedRegionType regionType)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getRegionType(): BlacklistedRegionType`
- **Notes:** Reports when a player enters a configured cosmetic restriction boundary.

#### <span class="md-api-event-name">ExitBlacklistedRegionEvent</span>

- **Cancellable:** No
- **Constructor:** `ExitBlacklistedRegionEvent(Player player, boolean isReverseWhitelist, BlacklistedRegionType regionType)`
- **Methods:**<br>
  `getPlayer(): Player`<br>
  `getRegionType(): BlacklistedRegionType`
- **Notes:** Reports when a player exits a configured cosmetic restriction boundary.

> Both constructors accept `isReverseWhitelist`, but the current public classes
> do not expose a getter for that value.

### Complete listener example

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

Register the listener from your plugin's `onEnable()` method:

```java
getServer().getPluginManager().registerEvents(new CosmeticListener(), this);
```

## Using the Developer API

The sections below describe methods that directly read or change a player's
GadgetsMenu data. They are separate from the event API above: events notify your
plugin when an action occurs, while `PlayerManager` lets your plugin perform an
action or retrieve player data.

### Get a player's API manager

Most Developer API methods are available through `PlayerManager`. Pass the
online Bukkit `Player` to `GadgetsMenuAPI.getPlayerManager(Player)` and keep the
returned manager in a local variable for the operation you want to perform.

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

The examples in the following sections assume that a variable named
`playerManager` has already been obtained as shown above.

> Retrieve and use Bukkit player data on the server thread unless the
> documentation for a specific method explicitly states that asynchronous use
> is supported.

## General player settings

#### Get player's Mystery Dust
```java
playerManager.getMysteryDust();
```

#### Add player's Mystery Dust
```java
playerManager.addMysteryDust(amount);
```

#### Set player's Mystery Dust
```java
playerManager.setMysteryDust(amount);
```

#### Remove player's Mystery Dust
```java
playerManager.removeMysteryDust(amount);
```

#### Get player's Mystery Boxes
```java
playerManager.getMysteryBoxes();
```

#### Give player's Mystery Boxes
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

#### Get player's mystery gifts
```java
playerManager.getGiftPacks();
```

#### Give player's mystery gifts
```java
 /**
  * Give player's mystery gifts.
  * Each gift contains 5 mystery boxes.
  */
  playerManager.addGiftPacks(amount);
```
#### Give player's menu selector
```java
playerManager.giveMenuSelector();
```

## Open Specific menu

#### Open the main menu
```java
playerManager.goBackToMainMenu();
```

#### Open the hats menu
```java
playerManager.openHatsMenu(page);
```

#### Open the animated hats menu
```java
playerManager.openAnimatedHatsMenu(page);
```

#### Open the particles menu
```java
playerManager.openParticlesMenu(page);
```

#### Open the suits menu
```java
playerManager.openSuitsMenu();
```

#### Open the specific suit equipment menu
```java
 /**
  * @param type The SuitType.
  */
  playerManager.openSuitEquipmentMenu(type);
```

#### Open the category gadgets menu
```java
playerManager.openCategoryGadgetsMenu();
```

#### Open the specific gadget type menu
```java
 /**
  * @param type The GadgetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openGadgetTypesMenu(type, page);
```

#### Open the category pets menu
```java
playerManager.openCategoryPetsMenu();
```

#### Open the specific pet type menu
```java
 /**
  * @param type The PetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openPetTypesMenu(type, page);
```

#### Open the morphs menu
```java
playerManager.openMorphsMenu();
```

#### Open the banners menu
```java
playerManager.openBannersMenu(page);
```

#### Open the emotes menu
```java
playerManager.openMorphsMenu(page);
```

#### Open the cloaks menu
```java
playerManager.openCloaksMenu();
```

## Equip & Unequip cosmetic

#### Equip & Unequip hat
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

#### Equip & Unequip Animatedhat
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

#### Equip & Unequip particle
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

#### Equip & Unequip suit
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

#### Equip & Unequip gadget
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

#### Equip & Unequip pet
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

#### Equip & Unequip morph
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

#### Equip & Unequip banner
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

#### Equip & Unequip emote
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

#### Equip & Unequip cloak
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
