---
title: Permissions
description: You can find all GadgetsMenu related permissions here and initial permission setup for beginners.
group: getting-started
keywords: Permissions
topics:
 - Permissions
---

All permissions are listed below.

To quickly get to know GadgetsMenu's permissions in your minecraft server, you may execute this command in-game to preview the available permissions.
- `/gmenu permissions <cosmetic|commands>` - [Click here for more info](wiki/getting-started/commands/general#gmenu-permission-cosmetic-commands-page)

## Permission for Beginners
If you do not know how to setup permissions for "default" rank player to use GadgetsMenu, a sample setup is provided below.

A player might need these permissions to use GadgetsMenu smoothly.
 - `gadgetsmenu.menuselector` - To get the menu item on join.
 - `gadgetsmenu.mysteryboxes.open.*` - Allows the player to open all types of Mystery Box.
 - `gadgetsmenu.animations.normal` - Allows the player to access the Mystery Vault animation "normal" to open the Mystery Box.

**Optional:**
 - `gadgetsmenu.summonpet` - Allows the player summon pet **[Note: for premium version only]**
 - `gadgetsmenu.discount.default` - Assign players to "default" discount group where purchase cosmetic items or craft Mystery Box could get a special discount rate based on settings.


>**Note:** Granting access to a parent permission will have all access to its child permissions.

## GadgetsMenu

**Parent Permission:** `gadgetsmenu.*`

**Child Permissions:**
- `gadgetsmenu.cosmetics.*` - Granted permission to access to all cosmetics items.
- `gadgetsmenu.commands.*` - Granted permission to access to all commands.
- `gadgetsmenu.menuselector` - Give player a menu selector when they join/respawn/switching world.
- `gadgetsmenu.cooldown.bypass` - Allows to toggle cooldown timer bypass option.
- `gadgetsmenu.bypassregion` - Player can bypass blacklisted regions and able to access cosmetic items in blacklisted regions. (Premium Only)
- `gadgetsmenu.ridepet` - Allows the player to ride its pet. (Premium Only)
- `gadgetsmenu.summonpet` - Allows the player to summon pet. (Premium Only)
- `gadgetsmenu.discount.*` - Granted player to have the highest discount rate.

## Cosmetics

**Parent Permission:** `gadgetsmenu.cosmetics.*`

**Child Permissions:**
```
gadgetsmenu.hats.*
gadgetsmenu.animatedhats.*
gadgetsmenu.particles.*
gadgetsmenu.suits.*
gadgetsmenu.gadgets.*
gadgetsmenu.pets.*
gadgetsmenu.miniatures.*
gadgetsmenu.morphs.*
gadgetsmenu.banners.*
gadgetsmenu.emotes.*
gadgetsmenu.cloaks.*
```

## Commands

**Parent Permission:** `gadgetsmenu.commands.*`

**Child Permissions:**
```
gadgetsmenu.commands.about
gadgetsmenu.commands.addpermission
gadgetsmenu.commands.admin
gadgetsmenu.commands.checkupdate
gadgetsmenu.commands.equip
gadgetsmenu.commands.help
gadgetsmenu.commands.namepet
gadgetsmenu.commands.migrate
gadgetsmenu.commands.permission
gadgetsmenu.commands.purge
gadgetsmenu.commands.reload
gadgetsmenu.commands.removepermission
gadgetsmenu.commands.reset
gadgetsmenu.commands.settings
gadgetsmenu.commands.status
gadgetsmenu.mysterydust.add
gadgetsmenu.mysterydust.check
gadgetsmenu.mysterydust.pay
gadgetsmenu.mysterydust.remove
gadgetsmenu.mysterydust.set
gadgetsmenu.mysteryboxes.check
gadgetsmenu.mysteryboxes.gift
gadgetsmenu.mysteryboxes.give
gadgetsmenu.mysteryboxes.giveall
gadgetsmenu.mysteryboxes.mode
```

## Auto Equip Cosmetic

**Parent Permission:** `gadgetsmenu.autoequip.*`

**Child Permissions:**
- `gadgetsmenu.autoequip.purchase` - Equip purchased cosmetic item automatically.
- `gadgetsmenu.autoequip.foundloot` - Equip cosmetic item found from mystery boxes.

## Bypass Duration

**Parent Permission:** `gadgetsmenu.bypassduration.*`

**Description:** This permission allows the player to bypass the default activation duration of a music gadget. Granting this permission will activate the music gadget until the song ends.

**Child Permissions:**
- `gadgetsmenu.bypassduration.discoball` - Bypass the default duration of Disco Ball Gadget.
- `gadgetsmenu.bypassduration.djbooth` - Bypass the default duration of DJBooth Gadget.

## Mystery Boxes

**Parent Permission:** `gadgetsmenu.mysteryboxes.open.*`

**Description:** Allows a player to open specified quality of Mystery Boxes.
- (1-5) is the quality of the Mystery Box.

>**Note:** Crafted Mystery Box will not be affected by these permissions as it does not require any of these permissions.

**Child Permissions:**
```
gadgetsmenu.mysteryboxes.open.1
gadgetsmenu.mysteryboxes.open.2
gadgetsmenu.mysteryboxes.open.3
gadgetsmenu.mysteryboxes.open.4
gadgetsmenu.mysteryboxes.open.5
```

## Mystery Vault Animations

**Parent Permission:** `gadgetsmenu.animations.*`

**Description:** Permissions for the Mystery Vault animation when opening the Mystery Box.

**Child Permissions:**
```
gadgetsmenu.animations.random
gadgetsmenu.animations.none
gadgetsmenu.animations.normal
gadgetsmenu.animations.countdown
gadgetsmenu.animations.star
gadgetsmenu.animations.crafting
gadgetsmenu.animations.summer
gadgetsmenu.animations.halloween
gadgetsmenu.animations.holiday
```

## Open Multiple Mystery Boxes

**Parent Permission:** `gadgetsmenu.multipleboxes.*`

**Description:** The permission to access Open Multiple Mystery Boxes option.

**Child Permissions:**
```
gadgetsmenu.multipleboxes.type1
gadgetsmenu.multipleboxes.type2
gadgetsmenu.multipleboxes.type3
```

## Hats

**Parent Permission:** `gadgetsmenu.hats.*`

**Child Permissions:**
```
gadgetsmenu.hats.hamburger
gadgetsmenu.hats.chocolatedonut
gadgetsmenu.hats.sandwich
gadgetsmenu.hats.blackchocolatebar
gadgetsmenu.hats.whitechocolatebar
gadgetsmenu.hats.candycane
gadgetsmenu.hats.computer
gadgetsmenu.hats.goldstevehead
gadgetsmenu.hats.diamondstevehead
gadgetsmenu.hats.emeraldstevehead
gadgetsmenu.hats.goldblock
gadgetsmenu.hats.diamondblock
gadgetsmenu.hats.scared
gadgetsmenu.hats.angel
gadgetsmenu.hats.embarrassed
gadgetsmenu.hats.sad
gadgetsmenu.hats.cool
gadgetsmenu.hats.surprised
gadgetsmenu.hats.dead
gadgetsmenu.hats.cry
gadgetsmenu.hats.grin
gadgetsmenu.hats.wink
gadgetsmenu.hats.derp
gadgetsmenu.hats.mustache
gadgetsmenu.hats.bigsmile
gadgetsmenu.hats.smile
gadgetsmenu.hats.neutral
gadgetsmenu.hats.fallinlove
gadgetsmenu.hats.netherlands
gadgetsmenu.hats.norway
gadgetsmenu.hats.sweden
gadgetsmenu.hats.chile
gadgetsmenu.hats.monaco
gadgetsmenu.hats.canada
gadgetsmenu.hats.unitedstates
gadgetsmenu.hats.italy
gadgetsmenu.hats.england
gadgetsmenu.hats.germany
gadgetsmenu.hats.singapore
gadgetsmenu.hats.france
gadgetsmenu.hats.spain
gadgetsmenu.hats.australia
gadgetsmenu.hats.china
gadgetsmenu.hats.letter_a
gadgetsmenu.hats.letter_b
gadgetsmenu.hats.letter_c
gadgetsmenu.hats.letter_d
gadgetsmenu.hats.letter_e
gadgetsmenu.hats.letter_f
gadgetsmenu.hats.letter_g
gadgetsmenu.hats.letter_h
gadgetsmenu.hats.letter_i
gadgetsmenu.hats.letter_j
gadgetsmenu.hats.letter_k
gadgetsmenu.hats.letter_l
gadgetsmenu.hats.letter_m
gadgetsmenu.hats.letter_n
gadgetsmenu.hats.letter_o
gadgetsmenu.hats.letter_p
gadgetsmenu.hats.letter_q
gadgetsmenu.hats.letter_r
gadgetsmenu.hats.letter_s
gadgetsmenu.hats.letter_t
gadgetsmenu.hats.letter_u
gadgetsmenu.hats.letter_v
gadgetsmenu.hats.letter_w
gadgetsmenu.hats.letter_x
gadgetsmenu.hats.letter_y
gadgetsmenu.hats.letter_z
gadgetsmenu.hats.rainbowletter_a
gadgetsmenu.hats.rainbowletter_b
gadgetsmenu.hats.rainbowletter_c
gadgetsmenu.hats.rainbowletter_d
gadgetsmenu.hats.rainbowletter_e
gadgetsmenu.hats.rainbowletter_f
gadgetsmenu.hats.rainbowletter_g
gadgetsmenu.hats.rainbowletter_h
gadgetsmenu.hats.rainbowletter_i
gadgetsmenu.hats.rainbowletter_j
gadgetsmenu.hats.rainbowletter_k
gadgetsmenu.hats.rainbowletter_l
gadgetsmenu.hats.rainbowletter_m
gadgetsmenu.hats.rainbowletter_n
gadgetsmenu.hats.rainbowletter_o
gadgetsmenu.hats.rainbowletter_p
gadgetsmenu.hats.rainbowletter_q
gadgetsmenu.hats.rainbowletter_r
gadgetsmenu.hats.rainbowletter_s
gadgetsmenu.hats.rainbowletter_t
gadgetsmenu.hats.rainbowletter_u
gadgetsmenu.hats.rainbowletter_v
gadgetsmenu.hats.rainbowletter_w
gadgetsmenu.hats.rainbowletter_x
gadgetsmenu.hats.rainbowletter_y
gadgetsmenu.hats.rainbowletter_z
gadgetsmenu.hats.number_0
gadgetsmenu.hats.number_1
gadgetsmenu.hats.number_2
gadgetsmenu.hats.number_3
gadgetsmenu.hats.number_4
gadgetsmenu.hats.number_5
gadgetsmenu.hats.number_6
gadgetsmenu.hats.number_7
gadgetsmenu.hats.number_8
gadgetsmenu.hats.number_9
gadgetsmenu.hats.symbol_plus
gadgetsmenu.hats.symbol_poundkey
gadgetsmenu.hats.symbol_question
gadgetsmenu.hats.symbol_exclamation
gadgetsmenu.hats.aquarius
gadgetsmenu.hats.pisces
gadgetsmenu.hats.aries
gadgetsmenu.hats.taurus
gadgetsmenu.hats.gemini
gadgetsmenu.hats.cancer
gadgetsmenu.hats.leo
gadgetsmenu.hats.virgo
gadgetsmenu.hats.libra
gadgetsmenu.hats.scorpio
gadgetsmenu.hats.sagittarius
gadgetsmenu.hats.capricorn
gadgetsmenu.hats.blaze
gadgetsmenu.hats.enderman
gadgetsmenu.hats.slime
gadgetsmenu.hats.magmacube
gadgetsmenu.hats.ocelot
gadgetsmenu.hats.enderdragon
gadgetsmenu.hats.cavespider
gadgetsmenu.hats.ghast
gadgetsmenu.hats.pigzombie
gadgetsmenu.hats.chicken
gadgetsmenu.hats.pig
gadgetsmenu.hats.cow
gadgetsmenu.hats.mushroomcow
gadgetsmenu.hats.squid
gadgetsmenu.hats.irongolem
gadgetsmenu.hats.horse
gadgetsmenu.hats.herobine
gadgetsmenu.hats.bird
gadgetsmenu.hats.pokeball
gadgetsmenu.hats.mario
gadgetsmenu.hats.nurse
gadgetsmenu.hats.freddyfazbear
gadgetsmenu.hats.bonnie
gadgetsmenu.hats.jake
gadgetsmenu.hats.doge
gadgetsmenu.hats.cooldoge
gadgetsmenu.hats.polarbear
gadgetsmenu.hats.rabbit
gadgetsmenu.hats.koala
gadgetsmenu.hats.bee
gadgetsmenu.hats.clownfish
gadgetsmenu.hats.ferret
gadgetsmenu.hats.walrus
gadgetsmenu.hats.tiger
gadgetsmenu.hats.monkey
gadgetsmenu.hats.cactus
gadgetsmenu.hats.duck
gadgetsmenu.hats.earth
gadgetsmenu.hats.beachball
gadgetsmenu.hats.snowglobe
gadgetsmenu.hats.toaster
gadgetsmenu.hats.cheese
gadgetsmenu.hats.mars
gadgetsmenu.hats.penguin
gadgetsmenu.hats.elephant
gadgetsmenu.hats.astronaut
gadgetsmenu.hats.otter
gadgetsmenu.hats.mummy
gadgetsmenu.hats.orc
gadgetsmenu.hats.minotaur
gadgetsmenu.hats.demonknight
gadgetsmenu.hats.whitewizard
gadgetsmenu.hats.miner
gadgetsmenu.hats.monk
gadgetsmenu.hats.woodelf
gadgetsmenu.hats.pirate
gadgetsmenu.hats.odin
gadgetsmenu.hats.ghost
gadgetsmenu.hats.skull
gadgetsmenu.hats.pumpkin
gadgetsmenu.hats.scarecrow
gadgetsmenu.hats.fox
gadgetsmenu.hats.pug
gadgetsmenu.hats.owl
gadgetsmenu.hats.panda
gadgetsmenu.hats.sloth
gadgetsmenu.hats.gorilla
gadgetsmenu.hats.snowman
gadgetsmenu.hats.reindeer
gadgetsmenu.hats.shulker
gadgetsmenu.hats.turtle
gadgetsmenu.hats.solvedrubikscube
gadgetsmenu.hats.scrambledrubikscube
gadgetsmenu.hats.rainbowglitch
gadgetsmenu.hats.pacman
```

## Animated Hats

**Parent Permission:** `gadgetsmenu.animatedhats.*`

**Child Permissions:**
```
gadgetsmenu.animatedhats.siren
gadgetsmenu.animatedhats.trafficlight
gadgetsmenu.animatedhats.sammythecookie
gadgetsmenu.animatedhats.chromaslime
gadgetsmenu.animatedhats.colorblock
gadgetsmenu.animatedhats.joethepenguin
gadgetsmenu.animatedhats.cometthereindeer
gadgetsmenu.animatedhats.brokentv
```

## Particles

**Parent Permission:** `gadgetsmenu.particles.*`

**Child Permissions:**
```
gadgetsmenu.particles.watersplash
gadgetsmenu.particles.dripwater
gadgetsmenu.particles.driplava
gadgetsmenu.particles.crit
gadgetsmenu.particles.magiccrit
gadgetsmenu.particles.spell
gadgetsmenu.particles.instantspell
gadgetsmenu.particles.mobspell
gadgetsmenu.particles.witchspell
gadgetsmenu.particles.angryvillager
gadgetsmenu.particles.happyvillager
gadgetsmenu.particles.townaura
gadgetsmenu.particles.note
gadgetsmenu.particles.portal
gadgetsmenu.particles.enchantment
gadgetsmenu.particles.flame
gadgetsmenu.particles.redstone
gadgetsmenu.particles.heart
gadgetsmenu.particles.fireworkspark
gadgetsmenu.particles.smoke
```

## Suits

**Parent Permission:** `gadgetsmenu.suits.*`

**Child Permissions:**
```
gadgetsmenu.suits.frog.*
  gadgetsmenu.suits.frog.helmet
  gadgetsmenu.suits.frog.chestplate
  gadgetsmenu.suits.frog.leggings
  gadgetsmenu.suits.frog.boots

gadgetsmenu.suits.ninja.*
  gadgetsmenu.suits.ninja.helmet
  gadgetsmenu.suits.ninja.chestplate
  gadgetsmenu.suits.ninja.leggings
  gadgetsmenu.suits.ninja.boots

gadgetsmenu.suits.speedster.*
  gadgetsmenu.suits.speedster.helmet
  gadgetsmenu.suits.speedster.chestplate
  gadgetsmenu.suits.speedster.leggings
  gadgetsmenu.suits.speedster.boots

gadgetsmenu.suits.ghostly.*
  gadgetsmenu.suits.ghostly.helmet
  gadgetsmenu.suits.ghostly.chestplate
  gadgetsmenu.suits.ghostly.leggings
  gadgetsmenu.suits.ghostly.boots

gadgetsmenu.suits.disco.*
  gadgetsmenu.suits.disco.helmet
  gadgetsmenu.suits.disco.chestplate
  gadgetsmenu.suits.disco.leggings
  gadgetsmenu.suits.disco.boots

gadgetsmenu.suits.mermaid.*
  gadgetsmenu.suits.mermaid.helmet
  gadgetsmenu.suits.mermaid.chestplate
  gadgetsmenu.suits.mermaid.leggings
  gadgetsmenu.suits.mermaid.boots

gadgetsmenu.suits.spooderman.*
  gadgetsmenu.suits.spooderman.helmet
  gadgetsmenu.suits.spooderman.chestplate
  gadgetsmenu.suits.spooderman.leggings
  gadgetsmenu.suits.spooderman.boots

gadgetsmenu.suits.warrior.*
  gadgetsmenu.suits.warrior.helmet
  gadgetsmenu.suits.warrior.chestplate
  gadgetsmenu.suits.warrior.leggings
  gadgetsmenu.suits.warrior.boots

gadgetsmenu.suits.necromancer.*
  gadgetsmenu.suits.necromancer.helmet
  gadgetsmenu.suits.necromancer.chestplate
  gadgetsmenu.suits.necromancer.leggings
  gadgetsmenu.suits.necromancer.boots

gadgetsmenu.suits.thor.*
  gadgetsmenu.suits.thor.helmet
  gadgetsmenu.suits.thor.chestplate
  gadgetsmenu.suits.thor.leggings
  gadgetsmenu.suits.thor.boots

gadgetsmenu.suits.baker.*
  gadgetsmenu.suits.baker.helmet
  gadgetsmenu.suits.baker.chestplate
  gadgetsmenu.suits.baker.leggings
  gadgetsmenu.suits.baker.boots

gadgetsmenu.suits.bumblebee.*
  gadgetsmenu.suits.bumblebee.helmet
  gadgetsmenu.suits.bumblebee.chestplate
  gadgetsmenu.suits.bumblebee.leggings
  gadgetsmenu.suits.bumblebee.boots

gadgetsmenu.suits.firefighter.*
  gadgetsmenu.suits.firefighter.helmet
  gadgetsmenu.suits.firefighter.chestplate
  gadgetsmenu.suits.firefighter.leggings
  gadgetsmenu.suits.firefighter.boots

gadgetsmenu.suits.plumber.*
  gadgetsmenu.suits.plumber.helmet
  gadgetsmenu.suits.plumber.chestplate
  gadgetsmenu.suits.plumber.leggings
  gadgetsmenu.suits.plumber.boots

gadgetsmenu.suits.icewalker.*
  gadgetsmenu.suits.icewalker.helmet
  gadgetsmenu.suits.icewalker.chestplate
  gadgetsmenu.suits.icewalker.leggings
  gadgetsmenu.suits.icewalker.boots

gadgetsmenu.suits.vampire.*
  gadgetsmenu.suits.vampire.helmet
  gadgetsmenu.suits.vampire.chestplate
  gadgetsmenu.suits.vampire.leggings
  gadgetsmenu.suits.vampire.boots
```

## Gadgets

**Parent Permission:** `gadgetsmenu.gadgets.*`

**Child Permissions by gadget type:**
### Fun and games
```
gadgetsmenu.gadgets.magic9ball
gadgetsmenu.gadgets.fortunecookie
gadgetsmenu.gadgets.tetherball
gadgetsmenu.gadgets.divingboard
gadgetsmenu.gadgets.trampoline
gadgetsmenu.gadgets.flowergiver
gadgetsmenu.gadgets.sandcastle
gadgetsmenu.gadgets.bbqgrill
gadgetsmenu.gadgets.pocketbeach
gadgetsmenu.gadgets.icecreamstand
gadgetsmenu.gadgets.tictactoe
```

### Mobs and NPCs
```
gadgetsmenu.gadgets.piggybank
gadgetsmenu.gadgets.catapult
gadgetsmenu.gadgets.whenpigsfly
gadgetsmenu.gadgets.explodingsheep
gadgetsmenu.gadgets.creeperastronaut
gadgetsmenu.gadgets.batlauncher
gadgetsmenu.gadgets.scarecrow
```

### Movement
```
gadgetsmenu.gadgets.cowboy
gadgetsmenu.gadgets.teleportstick
gadgetsmenu.gadgets.firetrail
gadgetsmenu.gadgets.painttrail
gadgetsmenu.gadgets.grapplinghook
gadgetsmenu.gadgets.parachute
gadgetsmenu.gadgets.teleporter
gadgetsmenu.gadgets.rocket
gadgetsmenu.gadgets.letitsnow
```

### Musical
```
gadgetsmenu.gadgets.jukebox
gadgetsmenu.gadgets.radio
gadgetsmenu.gadgets.discoball
gadgetsmenu.gadgets.djbooth
```

### Projectile
```
gadgetsmenu.gadgets.mobgun
gadgetsmenu.gadgets.railgun
gadgetsmenu.gadgets.paintballgun
gadgetsmenu.gadgets.explosivebow
gadgetsmenu.gadgets.melonlauncher
```

### Visual
```
gadgetsmenu.gadgets.kookiefountain
gadgetsmenu.gadgets.pyromaniac
gadgetsmenu.gadgets.diamondshower
gadgetsmenu.gadgets.goldfountain
gadgetsmenu.gadgets.kawariminojutsu
gadgetsmenu.gadgets.crytube
gadgetsmenu.gadgets.ghosts
gadgetsmenu.gadgets.partypopper
gadgetsmenu.gadgets.poopbomb
gadgetsmenu.gadgets.tntfountain
gadgetsmenu.gadgets.dracula
```

## Pets

**Parent Permission:** `gadgetsmenu.pets.*`

**Child Permissions:**
```
gadgetsmenu.pets.silverfish.*
  gadgetsmenu.pets.silverfish

gadgetsmenu.pets.chicken.*
  gadgetsmenu.pets.chicken
  gadgetsmenu.pets.babychicken

gadgetsmenu.pets.wolf.*
  gadgetsmenu.pets.wolf
  gadgetsmenu.pets.babywolf

gadgetsmenu.pets.cat.*
  gadgetsmenu.pets.blackcat
  gadgetsmenu.pets.babyblackcat
  gadgetsmenu.pets.redcat
  gadgetsmenu.pets.babyredcat
  gadgetsmenu.pets.siamesecat
  gadgetsmenu.pets.babysiamesecat
  gadgetsmenu.pets.wildocelot
  gadgetsmenu.pets.babywildocelot
  gadgetsmenu.pets.tabbycat
  gadgetsmenu.pets.babytabbycat
  gadgetsmenu.pets.britishshorthaircat
  gadgetsmenu.pets.babybritishshorthaircat
  gadgetsmenu.pets.calicocat
  gadgetsmenu.pets.babycalicocat
  gadgetsmenu.pets.persiancat
  gadgetsmenu.pets.babypersiancat
  gadgetsmenu.pets.ragdollcat
  gadgetsmenu.pets.babyragdollcat
  gadgetsmenu.pets.whitecat
  gadgetsmenu.pets.babywhitecat
  gadgetsmenu.pets.jelliecat
  gadgetsmenu.pets.babyjelliecat
  gadgetsmenu.pets.allblackcat
  gadgetsmenu.pets.babyallblackcat

gadgetsmenu.pets.zombie.*
  gadgetsmenu.pets.zombie
  gadgetsmenu.pets.babyzombie
  gadgetsmenu.pets.husk
  gadgetsmenu.pets.babyhusk
  gadgetsmenu.pets.redlittlehelper
  gadgetsmenu.pets.greenlittlehelper

gadgetsmenu.pets.bat.*
  gadgetsmenu.pets.bat

gadgetsmenu.pets.spider.*
  gadgetsmenu.pets.spider
  gadgetsmenu.pets.cavespider

gadgetsmenu.pets.snowman.*
  gadgetsmenu.pets.snowman

gadgetsmenu.pets.rabbit.*
  gadgetsmenu.pets.blackrabbit
  gadgetsmenu.pets.babyblackrabbit
  gadgetsmenu.pets.blackandwhiterabbit
  gadgetsmenu.pets.babyblackandwhiterabbit
  gadgetsmenu.pets.brownrabbit
  gadgetsmenu.pets.babybrownrabbit
  gadgetsmenu.pets.goldrabbit
  gadgetsmenu.pets.babygoldrabbit
  gadgetsmenu.pets.saltandpepperrabbit
  gadgetsmenu.pets.babysaltandpepperrabbit
  gadgetsmenu.pets.whiterabbit
  gadgetsmenu.pets.babywhiterabbit

gadgetsmenu.pets.villager.*
  gadgetsmenu.pets.blacksmithvillager
  gadgetsmenu.pets.babyblacksmithvillager
  gadgetsmenu.pets.butchervillager
  gadgetsmenu.pets.babybutchervillager
  gadgetsmenu.pets.farmervillager
  gadgetsmenu.pets.babyfarmervillager
  gadgetsmenu.pets.librarianvillager
  gadgetsmenu.pets.babylibrarianvillager
  gadgetsmenu.pets.priestvillager
  gadgetsmenu.pets.babypriestvillager
  gadgetsmenu.pets.zombievillager
  gadgetsmenu.pets.babyzombievillager
  gadgetsmenu.pets.witch
  gadgetsmenu.pets.evoker
  gadgetsmenu.pets.vindicator
  gadgetsmenu.pets.illusioner

gadgetsmenu.pets.golem.*
  gadgetsmenu.pets.golem

gadgetsmenu.pets.enderman.*
  gadgetsmenu.pets.enderman

gadgetsmenu.pets.blaze.*
  gadgetsmenu.pets.blaze

gadgetsmenu.pets.endermite.*
  gadgetsmenu.pets.endermite

gadgetsmenu.pets.cow.*
  gadgetsmenu.pets.cow
  gadgetsmenu.pets.babycow
  gadgetsmenu.pets.mushroomcow
  gadgetsmenu.pets.babymushroomcow

gadgetsmenu.pets.creeper.*
  gadgetsmenu.pets.creeper
  gadgetsmenu.pets.poweredcreeper

gadgetsmenu.pets.horse.*
  gadgetsmenu.pets.blackhorse
  gadgetsmenu.pets.babyblackhorse
  gadgetsmenu.pets.brownhorse
  gadgetsmenu.pets.babybrownhorse
  gadgetsmenu.pets.chestnuthorse
  gadgetsmenu.pets.babychestnuthorse
  gadgetsmenu.pets.creamyhorse
  gadgetsmenu.pets.babycreamyhorse
  gadgetsmenu.pets.darkbrownhorse
  gadgetsmenu.pets.babydarkbrownhorse
  gadgetsmenu.pets.grayhorse
  gadgetsmenu.pets.babygrayhorse
  gadgetsmenu.pets.whitehorse
  gadgetsmenu.pets.babywhitehorse
  gadgetsmenu.pets.donkey
  gadgetsmenu.pets.babydonkey
  gadgetsmenu.pets.mule
  gadgetsmenu.pets.babymule
  gadgetsmenu.pets.skeletonhorse
  gadgetsmenu.pets.babyskeletonhorse
  gadgetsmenu.pets.undeadhorse
  gadgetsmenu.pets.babyundeadhorse

gadgetsmenu.pets.pig.*
  gadgetsmenu.pets.pig
  gadgetsmenu.pets.babypig
  gadgetsmenu.pets.pigzombie
  gadgetsmenu.pets.babypigzombie

gadgetsmenu.pets.sheep.*
  gadgetsmenu.pets.blacksheep
  gadgetsmenu.pets.babyblacksheep
  gadgetsmenu.pets.bluesheep
  gadgetsmenu.pets.babybluesheep
  gadgetsmenu.pets.brownsheep
  gadgetsmenu.pets.babybrownsheep
  gadgetsmenu.pets.cyansheep
  gadgetsmenu.pets.babycyansheep
  gadgetsmenu.pets.graysheep
  gadgetsmenu.pets.babygraysheep
  gadgetsmenu.pets.greensheep
  gadgetsmenu.pets.babygreensheep
  gadgetsmenu.pets.lightbluesheep
  gadgetsmenu.pets.babylightbluesheep
  gadgetsmenu.pets.limesheep
  gadgetsmenu.pets.babylimesheep
  gadgetsmenu.pets.magentasheep
  gadgetsmenu.pets.babymagentasheep
  gadgetsmenu.pets.orangesheep
  gadgetsmenu.pets.babyorangesheep
  gadgetsmenu.pets.pinksheep
  gadgetsmenu.pets.babypinksheep
  gadgetsmenu.pets.purplesheep
  gadgetsmenu.pets.babypurplesheep
  gadgetsmenu.pets.redsheep
  gadgetsmenu.pets.babyredsheep
  gadgetsmenu.pets.silversheep
  gadgetsmenu.pets.babysilversheep
  gadgetsmenu.pets.whitesheep
  gadgetsmenu.pets.babywhitesheep
  gadgetsmenu.pets.yellowsheep
  gadgetsmenu.pets.babyyellowsheep
  gadgetsmenu.pets.rainbowsheep
  
gadgetsmenu.pets.slime.*
  gadgetsmenu.pets.bigslime
  gadgetsmenu.pets.smallslime
  gadgetsmenu.pets.tinyslime

gadgetsmenu.pets.magmacube.*
  gadgetsmenu.pets.bigmagmacube
  gadgetsmenu.pets.smallmagmacube
  gadgetsmenu.pets.tinymagmacube

gadgetsmenu.pets.skeleton.*
  gadgetsmenu.pets.skeleton
  gadgetsmenu.pets.witherskeleton
  gadgetsmenu.pets.strayskeleton

gadgetsmenu.pets.polarbear.*
  gadgetsmenu.pets.polarbear
  gadgetsmenu.pets.babypolarbear

gadgetsmenu.pets.llama.*
  gadgetsmenu.pets.brownllama
  gadgetsmenu.pets.babybrownllama
  gadgetsmenu.pets.creamyllama
  gadgetsmenu.pets.babycreamyllama
  gadgetsmenu.pets.grayllama
  gadgetsmenu.pets.babygrayllama
  gadgetsmenu.pets.whitellama
  gadgetsmenu.pets.babywhitellama

gadgetsmenu.pets.panda.*
  gadgetsmenu.pets.normalpanda
  gadgetsmenu.pets.babynormalpanda
  gadgetsmenu.pets.lazypanda
  gadgetsmenu.pets.babylazypanda
  gadgetsmenu.pets.worriedpanda
  gadgetsmenu.pets.babyworriedpanda
  gadgetsmenu.pets.playfulpanda
  gadgetsmenu.pets.babyplayfulpanda
  gadgetsmenu.pets.brownpanda
  gadgetsmenu.pets.babybrownpanda
  gadgetsmenu.pets.weakpanda
  gadgetsmenu.pets.babyweakpanda
  gadgetsmenu.pets.aggressivepanda
  gadgetsmenu.pets.babyaggressivepanda

gadgetsmenu.pets.turtle.*
  gadgetsmenu.pets.turtle
  gadgetsmenu.pets.babyturtle
  
gadgetsmenu.pets.fox.*
  gadgetsmenu.pets.redfox
  gadgetsmenu.pets.babyredfox
  gadgetsmenu.pets.snowfox
  gadgetsmenu.pets.babysnowfox

gadgetsmenu.pets.axolotl.*
  gadgetsmenu.pets.lucyaxolotl
  gadgetsmenu.pets.babylucyaxolotl
  gadgetsmenu.pets.wildaxolotl
  gadgetsmenu.pets.babywildaxolotl
  gadgetsmenu.pets.goldaxolotl
  gadgetsmenu.pets.babygoldaxolotl
  gadgetsmenu.pets.cyanaxolotl
  gadgetsmenu.pets.babycyanaxolotl
  gadgetsmenu.pets.blueaxolotl
  gadgetsmenu.pets.babyblueaxolotl
  
gadgetsmenu.pets.goat.*
  gadgetsmenu.pets.goat
  gadgetsmenu.pets.babygoat

gadgetsmenu.pets.allay.*
  gadgetsmenu.pets.allay

gadgetsmenu.pets.frog.*
  gadgetsmenu.pets.temperatefrog
  gadgetsmenu.pets.warmfrog
  gadgetsmenu.pets.coldfrog

gadgetsmenu.pets.tadpole.*
  gadgetsmenu.pets.tadpole

gadgetsmenu.pets.warden.*
  gadgetsmenu.pets.warden

gadgetsmenu.pets.bee.*
  gadgetsmenu.pets.bee
  gadgetsmenu.pets.babybee
  gadgetsmenu.pets.angrybee
  gadgetsmenu.pets.babyangrybee
  gadgetsmenu.pets.rollingbee
  gadgetsmenu.pets.babyrollingbee

gadgetsmenu.pets.camel.*
  gadgetsmenu.pets.camel
  gadgetsmenu.pets.babycamel

gadgetsmenu.pets.sniffer.*
  gadgetsmenu.pets.sniffer
  gadgetsmenu.pets.babysniffer

gadgetsmenu.pets.vex.*
  gadgetsmenu.pets.vex
  gadgetsmenu.pets.angryvex
```

## Miniatures

**Parent Permission:** `gadgetsmenu.miniatures.*`

**Child Permissions:**
```
gadgetsmenu.miniatures.doge
gadgetsmenu.miniatures.mrsmiley
gadgetsmenu.miniatures.devil
gadgetsmenu.miniatures.astronaut
gadgetsmenu.miniatures.zombie
gadgetsmenu.miniatures.enderman
gadgetsmenu.miniatures.irongolem
gadgetsmenu.miniatures.witch
gadgetsmenu.miniatures.swampmonster
gadgetsmenu.miniatures.scarecrow
gadgetsmenu.miniatures.clown
gadgetsmenu.miniatures.ghost
gadgetsmenu.miniatures.grimreaper
gadgetsmenu.miniatures.miner
gadgetsmenu.miniatures.santa
gadgetsmenu.miniatures.snowman
gadgetsmenu.miniatures.reindeer
gadgetsmenu.miniatures.lantern
gadgetsmenu.miniatures.present
gadgetsmenu.miniatures.globe
gadgetsmenu.miniatures.mars
gadgetsmenu.miniatures.snowglobe
```

## Morphs

**Parent Permission:** `gadgetsmenu.morphs.*`

**Child Permissions:**
```
gadgetsmenu.morphs.pig
gadgetsmenu.morphs.cow
gadgetsmenu.morphs.enderman
gadgetsmenu.morphs.chicken
gadgetsmenu.morphs.spider
gadgetsmenu.morphs.sheep
gadgetsmenu.morphs.skeleton
gadgetsmenu.morphs.creeper
gadgetsmenu.morphs.blaze
gadgetsmenu.morphs.zombie
gadgetsmenu.morphs.irongolem
gadgetsmenu.morphs.witch
gadgetsmenu.morphs.snowman
gadgetsmenu.morphs.guardian
gadgetsmenu.morphs.cavespider
gadgetsmenu.morphs.witherskeleton
gadgetsmenu.morphs.rabbit
gadgetsmenu.morphs.wolf
gadgetsmenu.morphs.grinch
```

## Banners

**Parent Permission:** `gadgetsmenu.banners.*`

**Child Permissions:**
```
gadgetsmenu.banners.snowbunny
gadgetsmenu.banners.reindeer
gadgetsmenu.banners.holidaytree
gadgetsmenu.banners.santa
gadgetsmenu.banners.holidaywreath
gadgetsmenu.banners.heart
gadgetsmenu.banners.guitar
gadgetsmenu.banners.dino
gadgetsmenu.banners.redpool
gadgetsmenu.banners.pengu
gadgetsmenu.banners.pug
gadgetsmenu.banners.tryhard
gadgetsmenu.banners.pumpkin
gadgetsmenu.banners.crown
gadgetsmenu.banners.firecreeper
gadgetsmenu.banners.portal
gadgetsmenu.banners.rainbowwall
gadgetsmenu.banners.skullking
gadgetsmenu.banners.devourer
```

## Emotes

**Parent Permission:** `gadgetsmenu.emotes.*`

**Child Permissions:**
```
gadgetsmenu.emotes.smile
gadgetsmenu.emotes.cool
gadgetsmenu.emotes.wink
gadgetsmenu.emotes.grin
gadgetsmenu.emotes.surprised
gadgetsmenu.emotes.cry
gadgetsmenu.emotes.sleepy
gadgetsmenu.emotes.rage
gadgetsmenu.emotes.frown
gadgetsmenu.emotes.cheeky
gadgetsmenu.emotes.suntan
gadgetsmenu.emotes.hearteyes
gadgetsmenu.emotes.dizzy
gadgetsmenu.emotes.rip
gadgetsmenu.emotes.relax
gadgetsmenu.emotes.spicy
gadgetsmenu.emotes.dealwithit
```

## Cloaks

**Parent Permission:** `gadgetsmenu.cloaks.*`

**Child Permissions:**
```
gadgetsmenu.cloaks.superhero
gadgetsmenu.cloaks.mystical
gadgetsmenu.cloaks.firewings
gadgetsmenu.cloaks.vampirewings
gadgetsmenu.cloaks.frosty
gadgetsmenu.cloaks.icewings
gadgetsmenu.cloaks.shaman
gadgetsmenu.cloaks.firerings
gadgetsmenu.cloaks.scanner
gadgetsmenu.cloaks.archangel
gadgetsmenu.cloaks.yinandyang
gadgetsmenu.cloaks.flameofthetitans
```