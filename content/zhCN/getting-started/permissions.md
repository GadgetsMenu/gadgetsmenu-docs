---
title: 权限
description: 您可以在此处找到所有与 GadgetsMenu 相关的权限，以及面向新手的初始权限设置。
group: getting-started
keywords: 权限
topics:
 - 权限
---

下面列出了所有权限。

若想快速了解 GadgetsMenu 在您 Minecraft 服务器中的权限，可以在游戏内执行此命令来预览可用的权限。
- `/gmenu permissions <cosmetic|commands>` - [点击此处了解更多信息](wiki/getting-started/commands/general#gmenu-permission-cosmetic-commands-page)

## 面向新手的权限设置
如果您不知道该如何为“default”等级的玩家设置使用 GadgetsMenu 的权限，下面提供了一个设置示例。

玩家可能需要以下这些权限才能顺畅地使用 GadgetsMenu。
 - `gadgetsmenu.menuselector` - 加入服务器时获得菜单物品。
 - `gadgetsmenu.mysteryboxes.open.*` - 允许玩家开启所有类型的神秘箱。
 - `gadgetsmenu.animations.normal` - 允许玩家使用“normal”神秘宝库动画来开启神秘箱。

**可选：**
 - `gadgetsmenu.summonpet` - 允许玩家召唤宠物 **[注意：仅限高级版]**
 - `gadgetsmenu.discount.default` - 将玩家分配到“default”折扣组，在购买化妆品或合成神秘箱时可根据设置获得特别的折扣率。


>**注意：** 授予某个父权限后，将同时拥有其所有子权限。

## GadgetsMenu

**父权限：** `gadgetsmenu.*`

**子权限：**
- `gadgetsmenu.cosmetics.*` - 授予使用所有化妆品的权限。
- `gadgetsmenu.commands.*` - 授予使用所有命令的权限。
- `gadgetsmenu.menuselector` - 在玩家加入/重生/切换世界时向其发放菜单选择器。
- `gadgetsmenu.cooldown.bypass` - 允许切换“绕过冷却时间”选项。
- `gadgetsmenu.bypassregion` - 玩家可以绕过黑名单地区，并在黑名单地区内使用化妆品。（仅限高级版）
- `gadgetsmenu.ridepet` - 允许玩家骑乘自己的宠物。（仅限高级版）
- `gadgetsmenu.summonpet` - 允许玩家召唤宠物。（仅限高级版）
- `gadgetsmenu.discount.*` - 授予玩家最高的折扣率。

## 化妆品

**父权限：** `gadgetsmenu.cosmetics.*`

**子权限：**
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

## 命令

**父权限：** `gadgetsmenu.commands.*`

**子权限：**
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

## 自动装备化妆品

**父权限：** `gadgetsmenu.autoequip.*`

**子权限：**
- `gadgetsmenu.autoequip.purchase` - 自动装备已购买的化妆品。
- `gadgetsmenu.autoequip.foundloot` - 装备从神秘箱中获得的化妆品。

## 绕过持续时间

**父权限：** `gadgetsmenu.bypassduration.*`

**说明：** 此权限允许玩家绕过音乐小工具的默认激活时长。授予此权限后，音乐小工具将一直激活到歌曲结束。

**子权限：**
- `gadgetsmenu.bypassduration.discoball` - 绕过 Disco Ball 小工具的默认持续时间。
- `gadgetsmenu.bypassduration.djbooth` - 绕过 DJBooth 小工具的默认持续时间。

## 神秘箱

**父权限：** `gadgetsmenu.mysteryboxes.open.*`

**说明：** 允许玩家开启指定品质的神秘箱。
- (1-5) 代表神秘箱的品质。

>**注意：** 合成神秘箱不受这些权限的影响，因为它不需要其中任何一项权限。

**子权限：**
```
gadgetsmenu.mysteryboxes.open.1
gadgetsmenu.mysteryboxes.open.2
gadgetsmenu.mysteryboxes.open.3
gadgetsmenu.mysteryboxes.open.4
gadgetsmenu.mysteryboxes.open.5
```

## 神秘宝库动画

**父权限：** `gadgetsmenu.animations.*`

**说明：** 开启神秘箱时所用神秘宝库动画的权限。

**子权限：**
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

## 同时开启多个神秘箱

**父权限：** `gadgetsmenu.multipleboxes.*`

**说明：** 使用“同时开启多个神秘箱”选项的权限。

**子权限：**
```
gadgetsmenu.multipleboxes.type1
gadgetsmenu.multipleboxes.type2
gadgetsmenu.multipleboxes.type3
```

## 帽子

**父权限：** `gadgetsmenu.hats.*`

**子权限：**
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

## 动画帽子

**父权限：** `gadgetsmenu.animatedhats.*`

**子权限：**
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

## 粒子效果

**父权限：** `gadgetsmenu.particles.*`

**子权限：**
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

## 套装

**父权限：** `gadgetsmenu.suits.*`

**子权限：**
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

## 小工具

**父权限：** `gadgetsmenu.gadgets.*`

**按小工具类型划分的子权限：**
### 娱乐与游戏
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

### 生物与 NPC
```
gadgetsmenu.gadgets.piggybank
gadgetsmenu.gadgets.catapult
gadgetsmenu.gadgets.whenpigsfly
gadgetsmenu.gadgets.explodingsheep
gadgetsmenu.gadgets.creeperastronaut
gadgetsmenu.gadgets.batlauncher
gadgetsmenu.gadgets.scarecrow
```

### 移动
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

### 音乐
```
gadgetsmenu.gadgets.jukebox
gadgetsmenu.gadgets.radio
gadgetsmenu.gadgets.discoball
gadgetsmenu.gadgets.djbooth
```

### 投射物
```
gadgetsmenu.gadgets.mobgun
gadgetsmenu.gadgets.railgun
gadgetsmenu.gadgets.paintballgun
gadgetsmenu.gadgets.explosivebow
gadgetsmenu.gadgets.melonlauncher
```

### 视觉
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

## 宠物

**父权限：** `gadgetsmenu.pets.*`

**子权限：**
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

## 微缩模型

**父权限：** `gadgetsmenu.miniatures.*`

**子权限：**
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

**父权限：** `gadgetsmenu.morphs.*`

**子权限：**
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

## 旗帜

**父权限：** `gadgetsmenu.banners.*`

**子权限：**
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

## 表情

**父权限：** `gadgetsmenu.emotes.*`

**子权限：**
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

## 披风

**父权限：** `gadgetsmenu.cloaks.*`

**子权限：**
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