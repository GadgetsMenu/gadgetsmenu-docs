 Developer API
===
Here is the official API that you can use. Please do not use the method that didn't list here, it may cause some unstable issue and may crash the plugin.

- [General Player Settings](#general-player-settings--top)
- [Open Specific Menu](#open-specific-menu--top)
- [Equip & Unequip Cosmetic](#equip--unequip-cosmetic--top)



## This is the first thing you need to add.
```
public static void doSomeAction(Player player) {
    PlayerManager playerManager = GadgetsMenuAPI.getPlayerManager(player);
    // Add some code here.
}

```



----



## General player settings.  ([top](#developer-api))

### Get player's Mystery Dust
```
playerManager.getMysteryDust();
```

### Add player's Mystery Dust
```
playerManager.addMysteryDust(amount);
```

### Set player's Mystery Dust
```
playerManager.setMysteryDust(amount);
```

### Remove player's Mystery Dust
```
playerManager.removeMysteryDust(amount);
```

### Get player's Mystery Boxes
```
playerManager.getMysteryBoxes();
```

### Give player's Mystery Boxes
```
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

### Get player's mystery gifts
```
playerManager.getGiftPacks();
```

### Give player's mystery gifts
```
 /**
  * Give player's mystery gifts.
  * Each gift contains 5 mystery boxes.
  */
  playerManager.addGiftPacks(amount);
```
### Give player's menu selector
```
playerManager.giveMenuSelector();
```




## Open Specific menu  ([top](#developer-api))

### Open the main menu
```
playerManager.goBackToMainMenu();
```

### Open the hats menu
```
playerManager.openHatsMenu(page);
```

### Open the animated hats menu
```
playerManager.openAnimatedHatsMenu(page);
```

### Open the particles menu
```
playerManager.openParticlesMenu(page);
```

### Open the suits menu
```
playerManager.openSuitsMenu();
```

### Open the specific suit equipment menu
```
 /**
  * @param type The SuitType.
  */
  playerManager.openSuitEquipmentMenu(type);
```

### Open the category gadgets menu
```
playerManager.openCategoryGadgetsMenu();
```

### Open the specific gadget type menu
```
 /**
  * @param type The GadgetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openGadgetTypesMenu(type, page);
```

### Open the category pets menu
```
playerManager.openCategoryPetsMenu();
```

### Open the specific pet type menu
```
 /**
  * @param type The PetCategoryType.
  * @param page The page of the menu.
  */
  playerManager.openPetTypesMenu(type, page);
```

### Open the morphs menu
```
playerManager.openMorphsMenu();
```

### Open the banners menu
```
playerManager.openBannersMenu(page);
```

### Open the emotes menu
```
playerManager.openMorphsMenu(page);
```

### Open the cloaks menu
```
playerManager.openCloaksMenu();
```




## Equip & Unequip cosmetic  ([top](#developer-api))

### Equip & Unequip hat
```
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

### Equip & Unequip Animatedhat
```
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

### Equip & Unequip particle
```
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

### Equip & Unequip suit
```
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

### Equip & Unequip gadget
```
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

### Equip & Unequip pet
```
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

### Equip & Unequip morph
```
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

### Equip & Unequip banner
```
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

### Equip & Unequip emote
```
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

### Equip & Unequip cloak
```
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

Go to the [top](#developer-api) of the page.