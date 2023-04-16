---
title: Pets
description: Feeling alone? Summon pets to accompany you, provide you with warmth, and increase your gaming experience.
group: cosmetic-items
keywords: cosmetic items, pets
topics:
 - cosmetic items
 - pets
---

Pet system has been redesigned with adding more features to make the pet become more functional. You can feed your pet with pet items to increase their attribute level and make them Happier. You will be able to ride your pet to go everywhere, set a special name for your every pet.

## Pet Attributes

Pet attribute level will decrease by **1** every **5 minutes** no matter it's moving or sleeping. You can increase your pet's attribute by feeding them with food, drinking water or playing with toys. You can gain pet items by opening Mystery Boxes. You will receive random pet items once you open a Mystery Box. Every pet has their favourite, most liked or disliked item. When they ate their favourite food, their attribute level will increase even more than normal.

<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th colspan="5" class="text-center">Pet Attributes</td>
  </tr>
  <tr>
    <td></td>
    <td><strong>Dislike</strong></td>
    <td><strong>Like</strong></td>
    <td><strong>Very Like</strong></td>
    <td><strong>Favourite</strong></td>
  </tr>
  <tr>
    <td><strong>Hunger</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
  <tr>
    <td><strong>Thirst</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
  <tr>
    <td><strong>Exercise</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
</table>
</div>
</div>

## Pet Items

These're the pet items available. Pet items interest are different for each pet and it can be configure in `pets.yml` file. A Wolf pet might likes to eat **Bone** and dislike **Hay**. A Cow pet might likes to drink **Milk** and dislike **Lava**. You can give player pet items by using [/gmenu petitems](../wiki/getting-started/commands/general#gmenu-petitems) command or they can gain it from Mystery Box. Most settings can be changed in `pet system.yml` file.

<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th colspan="7" class="text-center">Pet Items</td>
  </tr>
  <tr>
    <td rowspan="3"><strong>Food</strong></td>
    <td>Apple</td>
    <td>Melon</td>
    <td>Pumpkin Pie</td>
    <td>Carrot</td>
    <td>Baked Potato</td>
    <td>Mushroom Soup</td>
  </tr>
  <tr>
    <td>Flower</td>
    <td>Hay</td>
    <td>Wheat</td>
    <td>Bread</td>
    <td>Cookie</td>
    <td>Cake</td>
  </tr>
  <tr>
    <td>Raw Fish</td>
    <td>Raw Porkchop</td>
    <td>Angus Steak</td>
    <td>Bone</td>
    <td>Rotten Flesh</td>
    <td>Magma Cream</td>
  </tr>
  <tr>
    <td><strong>Water</strong></td>
    <td colspan="2" class="text-center">Water</td>
    <td colspan="2" class="text-center">Milk</td>
    <td colspan="2" class="text-center">Lava</td>
  </tr>
  <tr>
    <td><strong>Toy</strong></td>
    <td>Stick</td>
    <td>Ball</td>
    <td>Leash</td>
    <td>Feather</td>
    <td>Frisbee</td>
    <td>Sparring Sword</td>
  </tr>
</table>
</div>
</div>


![Pet Items](/assets/gadgetsmenu-docs/images/features/pets_pet-items.png "[Wrapper] Pet Items")

## Pet Level

Moreover, you can level up your pet by sending them on pet mission. When your pet has at least **Happy** status, it will be able to go for a mission to earn experiences. The Happier your pet is, the higher experiences your pet will get. Each pet's level starts from **level 1** and able to level up to **level 100 MAX**. You can only send your pets on a mission once **every 60 minutes** by default.


<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th class="text-center">Pet Happiness</td>
    <th class="text-center">Requirement</td>
    <th class="text-center">Experiences</td>
  </tr>
  <tr>
    <td class="text-center">Super Happy</td>
    <td>All attributes level greater than or equal to 75</td>
    <td class="text-center">800 EXP</td>
  </tr>
  <tr>
    <td class="text-center">Very Happy</td>
    <td>Two attributes level greater than or equal to 75</td>
    <td class="text-center">600 EXP</td>
  </tr>
  <tr>
    <td class="text-center">Happy</td>
    <td>Two attributes level greater than or equal to 25<br>Either One attributes level greater than or equal to 75</td>
    <td class="text-center">400 EXP</td>
  </tr>
  <tr>
    <td class="text-center">Okay</td>
    <td>All attributes level less than 25</td>
    <td class="text-center">0 EXP</td>
  </tr>
</table>
</div>
</div>

<br>

What you can do with pet level?
Currently pet level doesn't give anything. We will add some rewards later on. The rewards might be particle effects, throwing items or animations.