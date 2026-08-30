---
title: 宠物
description: 感到孤单？召唤宠物来陪伴您，为您带来温暖，提升您的游戏体验。
group: cosmetic-items
keywords: 化妆品, 宠物
topics:
 - 化妆品
 - 宠物
---

宠物系统经过重新设计，加入了更多功能，让宠物变得更加实用。您可以用宠物物品喂养您的宠物，以提升它们的属性等级并让它们更加快乐。您可以骑乘宠物前往各处，也可以为每一只宠物设置专属的名字。

## 宠物属性

无论宠物是在移动还是在睡觉，宠物的属性等级每 **5 分钟**都会下降 **1** 点。您可以通过喂食、喂水或用玩具陪它玩耍来提升宠物的属性。您可以通过开启神秘箱获得宠物物品。每当您开启一个神秘箱，就会随机获得宠物物品。每只宠物都有自己最喜欢、比较喜欢或讨厌的物品。当它们吃到最喜欢的食物时，属性等级的提升会比平常更多。

<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th colspan="5" class="text-center">宠物属性</td>
  </tr>
  <tr>
    <td></td>
    <td><strong>讨厌</strong></td>
    <td><strong>喜欢</strong></td>
    <td><strong>非常喜欢</strong></td>
    <td><strong>最喜欢</strong></td>
  </tr>
  <tr>
    <td><strong>饥饿度</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
  <tr>
    <td><strong>口渴度</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
  <tr>
    <td><strong>运动量</strong></td>
    <td>+30</td>
    <td>+35</td>
    <td>+40</td>
    <td>+50</td>
  </tr>
</table>
</div>
</div>

## 宠物物品

以下是可用的宠物物品。每只宠物对宠物物品的喜好各不相同，可以在 `pets.yml` 文件中进行配置。狼宠物可能喜欢吃**骨头**而讨厌**干草**。牛宠物可能喜欢喝**牛奶**而讨厌**岩浆**。您可以使用 [/gmenu petitems](../wiki/getting-started/commands/general#gmenu-petitems) 命令向玩家发放宠物物品，玩家也可以从神秘箱中获得。大部分设置可以在 `pet system.yml` 文件中修改。

<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th colspan="7" class="text-center">宠物物品</td>
  </tr>
  <tr>
    <td rowspan="3"><strong>食物</strong></td>
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
    <td><strong>水</strong></td>
    <td colspan="2" class="text-center">Water</td>
    <td colspan="2" class="text-center">Milk</td>
    <td colspan="2" class="text-center">Lava</td>
  </tr>
  <tr>
    <td><strong>玩具</strong></td>
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


![宠物物品](/assets/gadgetsmenu-docs/images/features/pets_pet-items.png "[Wrapper] Pet Items")

## 宠物等级

此外，您还可以通过派宠物执行宠物任务来提升它的等级。当您的宠物至少达到**快乐**状态时，它就可以外出执行任务以赚取经验。宠物越快乐，获得的经验就越多。每只宠物的等级从**等级 1** 开始，最高可以升到**等级 100**。默认情况下，您每 **60 分钟**只能派宠物执行一次任务。


<div class="md-table-max-content">
<div class="overflow-auto">
<table>
  <tr>
    <th class="text-center">宠物快乐度</td>
    <th class="text-center">要求</td>
    <th class="text-center">经验</td>
  </tr>
  <tr>
    <td class="text-center">超级快乐</td>
    <td>所有属性等级大于或等于 75</td>
    <td class="text-center">800 EXP</td>
  </tr>
  <tr>
    <td class="text-center">非常快乐</td>
    <td>两项属性等级大于或等于 75</td>
    <td class="text-center">600 EXP</td>
  </tr>
  <tr>
    <td class="text-center">快乐</td>
    <td>两项属性等级大于或等于 25<br>其中任意一项属性等级大于或等于 75</td>
    <td class="text-center">400 EXP</td>
  </tr>
  <tr>
    <td class="text-center">一般</td>
    <td>所有属性等级低于 25</td>
    <td class="text-center">0 EXP</td>
  </tr>
</table>
</div>
</div>

<br>

宠物等级有什么用？
目前宠物等级还不会带来任何效果。我们稍后会加入一些奖励。这些奖励可能是粒子效果、投掷物品或动画。
