---
title: Changelog
description: You can view the GadgetsMenu plugin changelog in the list below.
group: project-info
keywords: changelog
topics:
 - changelog
---

## GadgetsMenu Changelog
  - 4.3.1
    - Fixed ISSUES-634 - Item purchase system broken if no discount.
  - 4.3.0
    - Added Animated Hats. YEAHHH!!:LOL:
    - Added 4 Animated Hats.
    - Added new placeholders.
    - Added 13 Hats.
    - Added an option to hide particle effect & cloak effect for vanished player.
    - 'CUSTOM_MATERIAL2' has been removed from the plugin and main menu file.
    - Modified Cowboy gadget.
    - Change the way to access MySQL data. (Please inform me if you have lag issue)
    - You can now modify cosmetics item material.
    - You can now rename Scarecrow Jack o Lantern display name in config.
    - Updated Metrics.
    - Crafting Mystery Boxes lore has been reset due to format changes.
    - Purchasing cosmetic items and crafting mystery box is now able to discount the cost with 'item cost discount' in config.yml file.
    - You can now give offline player mystery boxes.
    - Fixed ISSUES-619 - SQLException occur every 8 minutes.
    - Fixed ISSUES-624 - Halloween animation mini block facing the wrong direction.
    - Fixed ISSUES-626 - Tic Tac Toc Gadget stopped when more than 2 groups of players playing.
    - Fixed ISSUES-627 - "Go back" button and "Previous Page" button collide in 1.8 server caused both buttons not function correctly.
    - Fixed ISSUES-629 - Players able to pass through the worldborder with Teleport Stick Gadget.
    - Fixed ISSUES-630 - The first recent loot shows nothing instead of shows 'none' while using MySQL.
    - Fixed bug - Unable to remove flower(Flower Giver Gadget) under some condition.
    - Fixed bug - 'Normal' & 'Crafting' mystery vault animation sounds weird.
    - Fixed bug - Server timezone being changed when player craft mystery box.
    - Fixed bug - Flower Giver Gadget and Tic Tac Toe Gadget no longer need to pointing target player head to send request.
  - 4.2.3
    - Display 'none' instead of display nothing when player no recent loot has found.
    - Fixed ISSUES-614 - Cowboy gadget able to ride vanished player.
    - Fixed ISSUES-616 - MobGun gadget items does not according to the launched mob.
    - Fixed ISSUES-617 - Mystery Vault holograms shows the same amount of the mystery boxes to players.
    - Fixed bug - Occur NoSuchFieldError: entityList when using paper server.
    - Fixed some minor bugs.
  - 4.2.2
    - Fixed some minor bugs.
  - 4.2.1
    - Fixed bug - Occur MySQLSyntaxErrorException while enabling MySQL.
  - 4.2.0
    - Added 1.13 support. (BETA)
    - ISSUES-547 - Added Akarin support.
    - ISSUES-588 - Custom hats are now supported normal material block.
    - Added an option to set Teleport Stick gadget range.
    - "/gmenu namepet" command are now able to execute from console.
    - Material format has changed, you need to follow the new format no matter what version you're using.
    - Command block are now available to execute "/gmenu" commands.
    - Mystery Boxes broadcast messages only send to worlds that are enabled in config instead of all worlds.
    - Fixed ISSUES-568 - Memory leaks while using MySQL.
    - Fixed ISSUES-584 - Player glitch in the wool block while Trampoline gadget activated nearby the player.
    - Fixed ISSUES-586 - MobGun Gadget occur error while spawning witch.
    - Fixed ISSUES-587 - Some gadget items shown lore in player's inventory when selected.
    - Fixed ISSUES-589 - Display banner lore in player's inventory when selected.
    - Fixed ISSUES-597 - When "Able-To-Move" set to true, player still unable to move menu selector.
    - Fixed ISSUES-602 - Gadget categories item does not unlock when player had one of the gadget.
    - Fixed ISSUES-603 - Player able to open any type of Mystery Box when open multiple boxes at once.
    - Fixed ISSUES-605 - Cooldown with suits not working.
    - Fixed ISSUES-610 - Custom mob name in MobGun gadget does not appear in action bar.
    - Fixed ISSUES-611 - Occur IllegalStateException while resetting gadget.
    - Fixed a bunch of minor bugs.
  - 4.1.23
    - Fixed ISSUES-573 - Occur error when player switching world.
    - Fixed ISSUES-596 - "/gmb giveall 1 c:(1:40,2:30,3:25,4:15,5:10)" command not working.
  - 4.1.22
    - Added an option to execute custom command when player found a loot that he already have.
    - Added an option to modify mystery vault menu items slot.
    - Fixed ISSUES-560 - More than one player can open boxes at the same time.
    - Fixed bug - Occur IllegalStateException when unequip gadget.
  - 4.1.21
    - Added an option to disable sync selected cosmetics on player join.
    - Fixed ISSUES-555 - Items can be duplicated while in Creative mode.
    - Fixed bug - Plugin doesn't load on startup. (Only affect the servers who using Turkish.)
  - 4.1.20
    - Fixed ISSUES-548 - JSON message not working on spigot 1.11 and 1.12.
    - Fixed bug - Occur error when some mystery vault animations disabled in config.
  - 4.1.19
    - Fixed bug - mysterybox give command not working. (since version 4.1.17)
  - 4.1.18
    - No longer support old mystery box format.
    - Modified mystery vault animations.
    - Added 6 new mystery vault animations.
    - Added an option to select random mystery vault animation.
    - Added JSON message which able player get more information by hover that message.(found mystery box and found loot messages)
    - Added an option to reopen gui menu after purchase.
    - Fixed ISSUES-536 - Same gadget(Sand Castle, Diving Board, DJBooth, Pocket Beach) activate in the same area causes the block can't be recover.
    - Fixed some minor bug(446, 463, 545).
  - 4.1.17
    - Able to set the chances between different quality in command "/gmysteryboxes give" & "/gmysteryboxes giveall".
    - DJBooth gadget and DiscoBall gadget cannot activate in the same area.
    - Fixed ISSUES-480, 518 - Citizens NPC become invisible.
  - 4.1.16
    - Fixed ISSUES-528 - Occur SQL error if player join the server for the first time.
    - Fixed bug - Occur IllegalStateException when player unequipped vampire suit.
  - 4.1.15
    - Display "Error" when player doesn't have any gift packs.
    - Fixed ISSUES-521 - Some of the SQL result sets does not close.
  - 4.1.14
    - Fixed bug - Occur error while crafting items.
  - 4.1.13
    - Fixed ISSUES-515 - Unable to reset equipped gadget.
  - 4.1.12
    - Fixed ISSUES-513 - Occur error on startup.
  - 4.1.11
    - Use NBTTag to determine cosmetic item instead of using display name.
    - Added REPLACE/DROP/WARN option when equip cosmetic item.
    - 472 - Display "No Box Available" instead of display "0 Available" (done)
    - Fixed bug - Gifted Mystery Boxes sometimes doesn't give to the receiver.
  - 4.1.10
    - Added an option to open multiple mystery boxes at the same time.
    - 477 - Added command "/gmenu settings" to modify personal settings such as (self morph view, cooldown bypass)
    - Fixed ISSUES-491 - Let It Snow gadget able to freeze Diving Board water.
  - 4.1.9
    - Added Australia hat.
    - Fixed bug - Player able to get multiple flower.
    - Fixed bug - Mystery Vault animation still working even disabled.
    - Fixed bug - Gadget doesn't remove when server restart/reload.
    - Fixed some minor bug.
  - 4.1.8
    - Fixed bug - "/gmenu menu main" command not working.
    - Fixed bug - Occurred error while using suit.
    - Fixed bug - Thor hammer sometimes doesn't remove.
    - Fixed bug - Unable to change settings menu name.
  - 4.1.7
    - Fixed bug - Mystery Vault holograms doesn't load on startup.
    - Fixed bug - Piano sound doesn't work on NBT song.
  - 4.1.6
    - Added "/gmenu purge" command to delete old player data.
    - Added 1.12 sounds.
    - Fixed bug - Mystery Vault doesn't load on startup.
    - Fixed bug - Occur error while updating plugin from version 4.0.22
    - Fixed bug - "mini enderchest" still appear after server restarted.
  - 4.1.5
    - Fixed bug ISSUES-454 - Able to ride players with gamemode spectator using Cowboy Gadget.
  - 4.1.4
    - Added 7 emotes. (Sun Tan Emote, Heart Eyes Emote, Dizzy Emote, RIP Emote, Relax Emote, Spicy Emote, Deal With It Emote)
    - Added cooldown for suit.(Default value is 0)
    - config.yml is now supported UTF-8 format.
    - Optimize code.
  - 4.1.3
    - Added 19 pets (Snowman, 2 Polar Bear, 8 Llama, 2 Husk, 2 Zombie Villager, Evoker, Vindicator, Illusioner, Stray Skeleton).
    - Added slime particle.
    - Added an option to disable Mystery Box Crafting.
    - Added an option to disable particle/cloak effect shows to everyone.
    - Fixed bug ISSUES-440 - Occurred error on startup while server has SilkSpawners plugin installed.
    - Fixed bug - 1.8 horse doesn't work.
    - Fixed bug - kick player while using Rocket Gadget.
  - 4.1.2
    - Fixed bug - Occur error while using teleport stick gadget.
    - Fixed bug - MySQL issue.
  - 4.1.1
    - Added Frosty Cloak.
    - Fixed bug ISSUES-428 - Scarecrow gadget occur error.
  - 4.1.0
    - Added Coins-JasperJH support.
    - Added "/gmysteryboxes check [player]" command to check player's mystery boxes amount.
    - Added "/gmysteryboxes mode redefine <vaultname>" command to redefine mystery vault location and blockface.
    - Added a hologram above the player when they activate emote. (BETA)
    - Added an option to auto equip cosmetic when player purchase cosmetic item or found loot in mystery box. (Permissions)
    - Added a new faster mystery vault animation named 'none'.
    - Mystery Vault is now required a permission to use each animation. (Permissions)
    - Added 10 gadgets (Diving board Gadget, Teleporter Gadget, Flower Giver Gadget, DJ Booth Gadget, BBQ Grill Gadget, Sand Castle Gadget, Pocket Beach Gadget, Scarecrow Gadget, Ice Cream Stand gadget, Tic Tac Toe Gadget)
    - Added 9 placeholders to get equipped cosmetic.
    - Now has four holograms above each Mystery Vault.
    - New economy system. Developers can hook custom economy plugin using API.
    - Fixed bug ISSUES-420 - Cosmetics doesn't sync while connect between servers.
    - Fixed a bunch of minor bugs.
  - 4.0.22
    - Cosmetic item still can be found even disabled in mystery boxes.yml
    - Fixed bug - unable to change pet name via rename pet name button.
    - Fixed bug ISSUES-413, 415 - Fixed MySQL issue.
    - Fixed bug ISSUES-416 - Occur NullPointerException when initialize player data.
  - 4.0.21
    - Fixed bug - Mystery Dust unable to hook into other plugin. (Only occur in version 4.0.20)
  - 4.0.20
    - Fixed bug ISSUES-407 - NoClassDefFoundError occur when updating plugin.
    - Fixed bug - cosmetics doesn't sync when player changing world.
    - Fixed bug - Individual hologram didn't remove while removing mystery vault.
  - 4.0.19
    - Fixed bug ISSUES-405 - mystery box requires "gadgetsmenu.animations.normal" permission to open.
  - 4.0.18
    - Added frown emote and cheeky emote.
    - Fixed gadget lore shows wrongly.
    - Fixed mysql connection problem.
  - 4.0.17
    - You're able to create own emote now.
    - Fixed bug ISSUES-403 - Failed to get the displayName of loot.
    - Fixed item lore shows wrongly.
    - Fixed angry villager particle display in every emote instead of only rage emote.
  - 4.0.16
    - Fixed bug - Individual hologram will not disable itself when ProtocolLib didn't installed.
  - 4.0.15
    - Added "Available Mystery Boxes" individual hologram. (Required ProtocolLib installed)
    - Added Rage emote.
    - Added Scanner cloak.
    - Fixed bug ISSUES-375 - DiscoBall effect still activate when the song is finished.
    - Fixed bug ISSUES-380 - Doesn't play sound when player do not have permission to rename pet.
    - Fixed bug ISSUES-382 - Occur errors when player moving item with cursor.
    - Fixed bug ISSUES-391 - Unable to rename pet with capital letters or use color codes.
    - Fixed bug ISSUES-394 - Occur errors when player changing worlds.
    - Fixed bug ISSUES-255754 - NoSuchMethodError when using 1.11 spigot.
    - Fixed bug ISSUES-1552 - Gadgets unable to be found in Mystery Boxes.
    - Fixed banners menu unable to view page 3 and so on.
    - Fixed a bunch of minor bugs.
  - 4.0.14
    - Pet's name is now supported for other languages.
    - Menu selector will be removed when player do not have permission.
    - Fixed bug - Mystery boxes reward did not disable even when Mystery Boxes disabled.
    - Fixed a bunch of minor bugs.
  - 4.0.13
    - Fixed bug - A problem occurred When updating config.
  - 4.0.12
    - Re-added Mystery Boxes Reward.
    - Fixed bug - Banner and morph can't be disabled.
    - Fixed bug ISSUES-330, ISSUES-362 - Pet doesn't despawn when player leave the server.
  - 4.0.11
    - Modified Cowboy Gadget.
    - Added support mysteryboxes & mysterydust command for all command sender. 
    - Fixed bug - Cowboy gadget not working.
    - Fixed bug ISSUES-358 - Player are not able to see their disguise.
    - Fixed bug ISSUES-359 - Disabled cosmetic items can be found in mystery boxes.
  - 4.0.10
    - Added an option to disable gift inventory.
  - 4.0.9
    - Re-added reload command.
    - Added '/mysteryboxes give' support for offline player. (case sensitive)
    - Added mysteryboxes command support for command block.
    - Added an option disable required permission to open mystery boxes.
    - Added an option to disable self morph view in config.
    - Use '/gmysteryboxes give <player> <amount> reqperm=false', player do not need permission to open mystery boxes.
    - You're not able to equip a cosmetic before remove the item from the specified slot or armors.
    - Updated CoinsAPI to version 1.4
    - Modified Cowboy gadget.
    - Fixed bug - back to main menu custom commands doesn't working.
    - Fixed bug ISSUES-303 - Fixed equipping morph will pass over the floor.
    - Fixed bug ISSUES-344 - Fixed 'mysterydust pay' command placeholder not work when player doesn't have 0 mystery dust.
    - Fixed bug ISSUES-355 - Mystery Vault animation doesn't stop and remove 'mini enderchest' when player leave the server.
    - Fixed a bunch of minor bugs.
  - 4.0.8
    - Added sound for thor suit when the anvil touch the ground.
    - Added an option to turn off bumblebee song by left clicking again with an empty hand.
    - Added an option to disable suit ability(Ninja,Baker, Plumber, Spooderman, Bumblebee, Thor, Warrior) while holding an item on main hand.
    - Fixed bug - Player's activated cosmetics will be synced even the world was disabled.
    - Fixed bug ISSUES-171 - Menu selector "mystery dust" and "mystery boxes" doesn't sync.
    - Fixed bug ISSUES-337 - "Previous Page" button doesn't work.
  - 4.0.7
    - Fixed bug ISSUES-312 - 'Red little helper' and 'Green little helper' item show undyed hat when permission is not given.
    - Fixed bug ISSUES-316 - Mysql reconnect error.
    - Fixed bug ISSUES-321,313 - Mystery vault holograms spawn every 0.5 second.
  - 4.0.6
    - Fixed bug ISSUES-304 - Ignore Cooldown & Morph Self View settings using the same permission.
    - Fixed bug ISSUES-305 - Occurring error activate discoball gadget.
    - Fixed bug ISSUES-306 - Give player's menu selector even disabled.
    - Fixed bug - Occurring error while equipping morph.
    - Fixed a bunch of minor bugs.
  - 4.0.5
    - Fixed bug - wither skeleton and horse spawn wrong type on 1.11/1.12 spigot.
    - Fixed bug ISSUES-295 - Some gadgets doesn't working due checking worldguard plugin.
    - Fixed bug ISSUES-296 - Occurring error while equipping morph.
  - 4.0.4
    - Fixed bug - gift packs, gift sent and gift received count wrongly while using MySQL database.
    - Fixed bug ISSUES-269 - Morph self view unable to disable.
    - Fixed bug ISSUES-272,274,276 - Reset button doesn't work.
    - Fixed bug ISSUES-278 - Some item doesn't show the original material while custom item was disabled.
    - Fixed bug ISSUES-279 - Ignore cooldown option able to toggle when player doesn't have permission.
    - Fixed bug - '/gmenu reset' command doesn't work.
  - 4.0.3
    - Modified auto updater, now won't restart the server when update completed.
  - 4.0.2
    - Fixed bug ISSUES-272 - Fixed Teleport Stick Gadget, Paint Trail Gadget, Fire Trail Gadget, Let It Snow Gadget, Cowboy Gadget, Paintball Gun Gadget doesn't working because of WorldGuard plugin checking.
  - 4.0.1
    - Remove worldguard support for some issue when when worldguard version is below than 6.2.
    - Fixed bug ISSUES-260 - Fixed 'mysterydust pay' command placeholder not work.
    - Fixed bug ISSUES-262 - Fixed '/gmysteryboxes giveall' command not working.
    - Fixed bug ISSUES-266 - Fixed reset button doesn't work in gadget type GUI menu.
    - Fixed a bunch of minor bugs.
  - 4.0.0
    - Made some optimisations.
    - Fully supported minecraft 1.12.
    - Does not support 3.7.11 and older version anymore.
    - Updated to the latest method of getting the plugin version.
    - Added an option to create your own hats, particles and banners.
    - Added permission for menu selector(gadgetsmenu.menuselector). Now player's required permission of giving them a menu selector.
    - Added custom flags to disable unique cosmetic in region. (Required WorldGuard installed)
    - Added iDisguise support for morphs. plugin can now work with either of iDisguise or Lib's Disguise, if the two are      installed, priority is given to Lib's Disguise.
    - Added an option to disable commands while player equipped a cosmetic. ("Disabled-Commands")
    - Added an option that will execute custom commands when back to main menu.
    - Added gift mystery boxes.
    - Added Mystery Boxes support for MySQL.
    - Mystery Boxes is now have a expiry date.
    - Crafted Mystery Boxes, Gifted Mystery Boxes and Normal Mystery Boxes can have different names.
    - Added new placeholders.
    - Normal Mystery Boxes are now require permission to open it. (permissions)
    - Renamed cosmetics folder to categories folder.
    - Renamed Broadcast Radio Gadget to Radio Gadget.
    - Modified Radio Gadget, make it only play song to the player who activate it.
    - Renamed permission gadgetsmenu.mysterybox to gadgetsmenu.mysteryboxes.
    - Exploding Sheep Gadget will now shows explode countdown timer.
    - Modified KawarimiNoJutsu Gadget.
    - Modified Parachute Gadget.
    - Modified Discoball Gadget.
    - Removed '/gmenu reload' command due some unstable issue.
    - Fixed bug (Reported by AnimalMaceYT #1179) - Tetherball Gadget unable to activate while the current location Y + 150 is higher than 256.
    - Fixed a bunch of bugs.
  - 3.7.11
    - Fixed bug (ISSUES-242, ISSUES-243) - Failed to check update while using spigot 1.12.1.
  - 3.7.10
    - Fixed bug ISSUES-218 - JsonSyntaxException while using actionbar for gadget cooldown on 1.8.8 spigot.
    - Fixed bug ISSUES-218 - Occur errors when player left-click with an empty item while using mobgun gadget to change mob.
  - 3.7.9
    - Fixed bug ISSUES-190 - Occur errors when player first join to the server.
    - Fixed bug ISSUES-208 - Cooldown bar count wrongly.
    - Fixed bug ISSUES-209 - Gadget Items able to use number key to modify.
  - 3.7.8
    - Fixed bug (Reported by FunnyCraft_) - Tetherball gadget not working on minecraft 1.12.
    - Fixed bug ISSUES-206 - Gadgets can not be found in mystery boxes.
    - Fixed bug ISSUES-207 - Suits able to purchase even if disabled.
  - 3.7.7
    - Fixed bug (Reported by FunnyCraft_) - CooldownBar not working on minecraft 1.12.
  - 3.7.6
    - Added 1.12 support.
  - 3.7.5
    - Fixed bug ISSUES-P1000 - Should fix pet spawn duplicate.
    - Fixed bug ISSUES-185 - java.lang.IllegalStateException issue.
  - 3.7.4
    - Fixed bug - SQL syntax error.
  - 3.7.3
    - Fixed bug ISSUES-135 - when pet's name contains " ' ".
    - Fixed bug ISSUES-158 - mystery dust sync error while using database.
  - 3.7.2
    - "Date Modified" in GadgetsMenu Information written wrong.
    - Fixed bug ISSUES-153 - NullPointerException when player leave game.
  - 3.7.1
    - Remove Jukebox Gadget on 1.8 server for some unfixable bug.
    - Remove Tetherball Gadget on 1.8 server for some unfixable bug.
    - Fixed bug ISSUES-122 - CryoTube Gadget will change the default block on ground.
    - Fixed bug ISSUES-130 - When player craft item using 2 x 2 crafting grid.
    - Fixed bug ISSUES-136 - GUI will break when disabled all gadgets in 1 category.
    - Fixed bug ISSUES-136 - Paintball Gun Gadget blacklist and radius doesn't working.
    - Fixed bug ISSUES-146 - Mobgun Gadget error when spawning horse.
    - Fixed bug ISSUES-147 - Spawning pets will get NoSuchMethodError on 1.8 server.
  - 3.7.0
    - Added 9 new gadgets.
    - Added 8 new suits.
    - Added CoinsAPI support for mystery dust.
    - Added an option to disable morph ability.
    - Renamed mystery box command. (/gmysteryboxes)
    - Mystery Boxes can now be crafted with Mystery Dust.
    - Guardian morph can now shoot lasers.
    - Able to sneak to deactivate When Pigs Fly gadget.
    - Able to change Disco Ball gadget song duration time.
    - Recoded Morph Watcher.
    - Recoded Gadgets and grouped it well.
    - Fixed main menu inventory will break when enabled cosmetics less than 5.
    - Fixed item lore show errors.
    - Fixed Happy Villager Particles permission named wrong.
    - Fixed material format. New material format ('1' or '1:0')
    - Fixed Bat Launcher doesn't working when Affect-Player set to false.
    - Fixed player able to use anvil to rename gadgets or selector items.
    - Removed MCStats metrics and added bStats metrics. (https://bstats.org/plugin/bukkit/GadgetsMenu)
    - You can add your own song track.
    - Updated gadgets file. Old gadgets file will be rename to 'oldgadgets.yml'.
  - 3.6.17
    - Fixed mermaid suit will get errors if Lib's Disguise didn't installed.
    - Fixed melons unable to pick up.
    - Fixed minor bugs.
  - 3.6.16
    - Fixed pet spawn duplicate.
  - 3.6.15
    - Added Ninja suits (Click to throw a Ninja Shuriken)
    - Added Mermaid suits (Transform into a beautiful Squid when under water)
    - Added Baker suits (Click to deliver baked goods around the lobby)
    - Added Sleepy emote.
    - Fixed 1.11 skeleton pets and Horse pets not working.
    - Fixed lag issues.
    - Fixed mystery vault unable to click "Next Page".
  - 3.6.14
    - Added an option will execute commands when player click "go back" arrow.
    - Disable player to use shortcut key to move item.
    - Bug fixes.
  - 3.6.13
     - Fixed data will load duplicate when player join the server.
    - Fixed 1.8 Cowboy not working.
  - 3.6.12
    - Fixed Sheep morph and Witch morph not working on 1.8 server.
  - 3.6.11
    - Added 1.8 Morphs support.
  - 3.6.10
    - Bug Fixes
  - 3.6.9
    - Fixed lag issue.
    - Fixed player can rename pet without required any permission.
  - 3.6.8
    - Change package name. (If you using GadgetsMenu API, you must update package name.)
    - Bug fixes.
  - 3.6.7
    - Added new placeholders.
    - Added option to give player mystery box reward every single hours by default, that depends you setted how many hours.
    - Fixed helmet will be replace when activate emote.
    - Fixed MySQL.
    - Fixed v1_8_R1 JsonWriter.
  - 3.6.6
    - Added 2 gadgets (Kawarimi No Jutsu Gadget, When Pigs Fly Gadget)
    - Added command /gmenu equip <cosmetic> <type> <player>
    - PaintBall Gun gadget will now fill 20% of radius.
    - Corrected spelling mistakes.
    - Fixed selector "Able to move" doesn't worked.
    - Fixed holograms.
    - Fixed minor bugs.
    - Fixed MySQL error.
  - 3.6.5
    - Added Spain hat.
    - Remove banner patterns of the BannerMeta.
    - Fixed holograms.
    - Fixed reload command not working.
  - 3.6.4
    - Fixed Speedster suit Cloud particle will not remove when player leave the server.
    - Fixed failed to get player data.
    - Fixed MySQL error.
    - Fixed Disco Ball Gadget play songs error in 1.8 server.
  - 3.6.3
    - Added command '/mysterybox mode info <vaultName>'.
    - Added command '/mysterybox mode list'.
    - Added command '/mysterybox mode near <radius>'.
    - Added command '/mysterybox mode remove-vault r={radius}'.
    - Added command 'mysterybox mode teleport <vaultName>'.
    - Updated holograms.
    - Removed message "How to setup GadgetsMenu? Click-Here".
    - Fixed PlaceholderAPI error.
    - Fixed morph ability bug.
  - 3.6.2
    - Fixed Parachute Gadget.
    - Fixed GUI bug.
  - 3.6.1
    - Added broadcast option when player open mystery box and player found loot.
    - Able to change Mystery Boxes name, material.
    - Able to change Mystery Vault GUI name.
    - Fixed Purchase item error.
    - Fixed holograms errors when the world is not exist.
    - Fixed open Mystery Vault error.
    - Fixed command /gmenu reload.
  - 3.6.0
    - Added Vault and PlayerPoints support.
    - Added Suits and Cloaks.
    - Added an option to disable bat launcher will affect the player.
    - Added an option that you can unleash the player that riding on you.
    - Added ActionBar support for cooldown timer.
    - Added an option to change pet move-speed.
    - Added an option to disable morphs self view and bypass cooldown.
    - Added command block able to access mystery dust command.
    - Added cosmetic items rarity.
    - Added Mystery Boxes, Mystery Vault.
    - Added Settings menu.
    - Added 1.11 sounds and 1.11 particles.
    - Added placeholders, requested PlaceholderAPI plugin.
    - Added an option to let player rename pet in chat.
    - Added Morph skills.
    - Added songs supported, play songs when activated Disco Ball Gadget.
    - Removed /menu givemenu command.
    - Removed Wardrobe and Disco Armor.
    - Removed Clown Hat.
    - Renamed Disabled-Worlds to Enabled-Worlds in config.yml.
    - Renamed Credits to Mystery Dust.
    - Updated Paintball Gun Gadget will only fill 10% of radius.
    - Updated ParticleEffect.
    - Updated GadgetsMenu storage data.
    - Updated Metrics.
    - Updated Pet speed, now will able to change pet speed in pet file.
    - Updated all commands.
    - Updated cosmetic items display name.
    - Updated /gmenu reload, will reload the plugin.
    - Updated guitar banner pattern.
    - Fixed command /menu namepet.
    - Fixed command /menu reset.
    - Fixed Chicken pet will spawn eggs.
    - Fixed Paintball Gun block able to break.
    - Fixed Fire Trail Gadget.
    - Fixed pet will spawn wrongly when changing worlds.
    - Fixed mystery dust can be negative amount.
    - Fixed player can put off the fire.(Fire Trail Gadget)
    - Fixed Miner hat texture same as white wizard hat.
    - Fixed Cowboy Gadget not working when using 1.9 spigot and above.
    - Fixed Explosive Bow Gadget able to pick up arrow.
  - 3.5.19
    - Fixed MySQL problem.
  - 3.5.18
    - Fixed 1.11 glow item not working.
    - Fixed 1.11 Spawn Egg not working.
  - 3.5.17
    - Fixed 1.11 sounds.
  - 3.5.16
    - Added 1.11 support.
  - 3.5.15
    - Fixed listeners when it's not the same world.
  - 3.5.14
    - Fixed melon(Melon Launcher Gadget) able to pick up.
    - Fixed database cannot be enable.
  - 3.5.13
    - Fixed 1.8 Pet.
    - Fixed player cannot tame horse and wear item on horse.
  - 3.5.12
    - Fixed Cowboy Gadget Circular entity riding.
  - 3.5.11
    - Fixed Paintball Gun Gadget and Paint Trail Gadget.
  - 3.5.10
    - Fixed block gadget will no longer change the lit redstone lamp.
    - Fixed duplicated give player items.
    - Fixed emotes bug.
    - Fixed Gadget would not remove when player leave the server/server reload.