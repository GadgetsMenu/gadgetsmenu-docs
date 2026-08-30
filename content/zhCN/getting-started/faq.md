---
title: 常见问题
description: 您可以在此处找到所遇问题的答案。您的问题也许已经在本页中被提出并解答。
group: getting-started
keywords: 常见问题,faq
topics:
 - 常见问题
 - faq
---

以下是用户经常提出的一些常见问题。在寻求帮助之前，请先查看您的问题是否已经在此处得到解答。

如果您在浏览完本页后问题仍未解决，可以加入我们的 [Discord](https://discord.gadgetsmenu.net/) 服务器寻求支持。

## 为什么 GadgetsMenu 在我的服务器上无法运行？

### 我执行 GadgetsMenu 的命令时收到了“`You don't have permission to do that in this world!`”消息。

您只需要设置想要启用 GadgetsMenu 的世界即可。

在 `config.yml` 文件中找到 `Enabled-Worlds`，并将世界名称添加到列表中。

**`'*'`** 符号表示所有世界。这意味着 GadgetsMenu 将在所有世界中完全可用。

```yaml
# List of the worlds where cosmetics are enabled!
Enabled-Worlds:
- '*'
- world
- world_nether
- world_the_end
```

## 为什么我的 GadgetsMenu 中没有 Morphs？

GadgetsMenu 本身不内置 Morphs 功能，它需要一个生物伪装插件来提供变身支持。

因此，您需要下载以下其中一个生物伪装插件，GadgetsMenu 才会具备 Morphs 功能。
- Lib's Disguise
- iDisguise

## 为什么我没有收到用于打开 GadgetsMenu 菜单的菜单选择器？

玩家需要拥有 `gadgetsmenu.menuselector` 权限，才能在加入服务器时获得菜单选择器。
只需在您的权限插件中，将该权限分配给相应的玩家或权限组即可。

如果您不清楚还需要包含哪些其他权限，可以查看[面向新手的权限设置](wiki/getting-started/permissions#permission-for-beginners)。

## 我该如何在多台服务器之间同步 GadgetsMenu 的数据？

GadgetsMenu 提供了多种数据存储方式，即 `sqlite` 和 `MySQL` 存储。若要在各个 Minecraft 服务器之间共享数据，您可以使用 `MySQL` 存储来保存 GadgetsMenu 的数据。

为此，只需将 `Storage` 的值改为 `mysql`，并在 `config.yml` 文件中配置 MySQL 信息。您可以从数据库服务提供商处获取 MySQL 凭据。

```yaml
# This option allows you to set where
# player's data do you want to save.
# 
# Storages: 'sqlite' or 'mysql'.
# 
# If you enable mysql, you need to setup MySQL infos.
Player-Data:
  Storage: mysql
  MySQL:
    hostname: localhost
    username: root
    database: minecraft
    port: '3306'
    password: password
    useSSL: false
```

完成后，重启您的服务器，您应当能看到下面这条消息，表明 GadgetsMenu 已成功连接到 MySQL 数据库。

![MySQL 成功消息](/assets/gadgetsmenu-docs/images/getting-started/faq-mysql-connect-success.PNG "[Wrapper] MySQL Success Message")

>**注意：** 请确保您的代理服务器和 Minecraft 服务器配置正确。尤其是 `spigot.yml` 文件中的 `bungeecord` 设置要设为 true。否则 GadgetsMenu 将无法正常同步数据。

## 我该如何在计分板、排行榜或其他插件中使用 GadgetsMenu 的占位符？

GadgetsMenu 使用了流行的占位符插件之一 —— [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/)，以支持在第三方插件中使用占位符。

要使用 [GadgetsMenu 占位符](wiki/setup/placeholders)，您无需从 eCloud 下载任何扩展。只要第三方插件支持 PlaceholderAPI，您就可以直接使用这些占位符。

>**注意：** 请确保您使用的插件支持 PlaceholderAPI，并且已启用 PlaceholderAPI。

## 我已经通过 Mystery Dust 购买了化妆品，或通过开启神秘箱获得了化妆品，但仍然无法使用该化妆品？

#### 免费版

GadgetsMenu 免费版不会将已解锁的化妆品保存在自己的数据库中。当玩家购买化妆品或通过开启神秘箱获得化妆品时，GadgetsMenu 会执行一条命令，授予玩家使用该化妆品的权限。

因此，您需要一个权限插件来管理玩家的权限。根据您所使用的权限插件，您需要设置相应的命令，以便 GadgetsMenu 插件执行正确的授权命令。

您需要修改 `/plugins/GadgetsMenu` 文件夹中的两个文件。请根据您使用的权限插件，将下面的部分替换为相应的命令。

您可以参考下表，找到您所使用的权限插件对应的命令。

- `config.yml`
```yaml
Cosmetic-Item-Purchase:
  # This is the command when player purchase cosmetic items.
  # This command is depends on your permission plugin.
  Execute-Command: pex user {PLAYER} add {PERMISSION}
```

- `mystery boxes/mystery boxes.yml`
```yaml
Mystery-Boxes:
  Execute-Command: pex user {PLAYER} add {PERMISSION}
```

| 权限插件 | 命令                                            |
| ----------------- | -------------------------------------------------- |
| LuckPerms         | `lp user {PLAYER} permission set {PERMISSION}`     |
| PowerfulPerms     | `pp user {PLAYER} add {PERMISSION}`                |
| PowerRanks        | `pr addplayerperm {PLAYER} {PERMISSION}`           |
| CloudNet          | `cperms user {PLAYER} add permission {PERMISSION}` |
| PermissionsEx     | `pex user {PLAYER} add {PERMISSION}`               |
| GroupManager      | `manuaddp {PLAYER} {PERMISSION}`                   |

#### 高级版

如果您使用的是高级版，通常不会遇到上述问题。不过，如果您发现自己的问题与此类似，请联系我们的 [Discord](https://discord.gadgetsmenu.net/) 支持人员寻求协助。

## 我该如何将 Mystery Dust 存储切换为其他经济存储？

GadgetsMenu 支持多款经济插件来替代 Mystery Dust 存储。只需将 `config.yml` 文件中的 `Mystery-Dust-Storage` 的值改为列表中提到的任一可用存储即可。

```yaml
Cosmetic-Item-Purchase:
  # Set the storage where do you want to save mystery dust.
  # Available storages: 'default', 'coinsapi', 'playerpoints', 'vault'.
  # 'default' represent follow player data storage.
  Mystery-Dust-Storage: default
```

除此之外，GadgetsMenu 还提供了一个 API，用于为 Mystery Dust 实现您自己的自定义经济存储。如果您的服务器使用自制的经济系统，可以将 GadgetsMenu 的 Mystery Dust 挂钩到您的自定义经济存储上。点击链接了解更多关于 [GadgetsMenu 自定义经济存储](wiki/developers/custom-economy-storage)的信息。

## 如何创建用于开启神秘箱的神秘宝库？

神秘箱只能通过神秘宝库开启。因此，如果您想使用神秘箱功能，就必须创建神秘宝库。

您可以通过以下步骤创建神秘宝库：
1. 在您想要创建神秘宝库的位置放置一个方块（例如末影箱）。
2. 将您的视角对准刚放置的方块。
3. 执行命令 `/gmysteryboxes mode add-vault <vaultName>`，将 `<vaultName>` 替换为代表您神秘宝库的唯一名称。
4. 如果步骤正确，您应当能像下图那样，在神秘宝库上方看到全息图。
5. 完成！现在您可以尝试通过刚创建的神秘宝库来开启神秘箱了。

![神秘宝库](/assets/gadgetsmenu-docs/images/getting-started/faq-create-mystery-vault.jpg "[Wrapper] Mystery Vault")

点击[链接](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-add-vault-vaultname)查看该命令的更多详情。

## 我该如何更改神秘宝库动画的方向？

![神秘宝库动画的方向](/assets/gadgetsmenu-docs/images/getting-started/faq-change-mystery-vault-orientation.jpg "[Wrapper] Mystery Vault's animation orientation")
您的神秘宝库动画方向不对，和上图类似？不用担心，您可以通过命令 `/gmysteryboxes mode redefine <vaultName>` 重新定义神秘宝库的位置和朝向。（[点击此处了解更多信息](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-redefine-vaultname)）

站在神秘宝库前方，将视角转向相反方向，然后执行上述命令。

> **提示：**
> - 如果您不记得神秘宝库的名称，可以执行命令 `/gmysteryboxes mode near <radius>` 来获取附近神秘宝库的信息。
> - [点击此处了解更多信息](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-mode-near-radius)

## 我该如何移除神秘宝库？

您可以注视神秘宝库方块并执行以下命令来移除它。
- `/gmysteryboxes mode remove-vault`

如果您希望按名称移除某个神秘宝库，或按半径移除附近的神秘宝库，只需在命令末尾添加参数 `[vaultName|r:{radius}]` 即可。

**示例：**
- `/gmysteryboxes mode remove-vault vault_1` - 按名称移除指定的神秘宝库。
- `/gmysteryboxes mode remove-vault r:3` - 按半径移除附近的神秘宝库。

## 如何向玩家发放神秘箱？

您可以通过以下命令向玩家发放神秘箱：
```
/gmysteryboxes give <player> <amount> [quality] [ex=7h/7d/7m/false] [reqperm=false] c:(<quality>:<chances>)
```

您可以点击[此链接](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-give-player-amount-quality-ex-7h-7d-7m-false-reqperm-false-c-quality-chances)查看该命令的完整用法和说明。

## 如何向玩家发放随机品质的神秘箱？

您可以通过以下命令向玩家发放随机品质的神秘箱：
```
/gmysteryboxes give <player> <amount> c:(<quality>:<chances>)
```

使用此命令时，您无需在命令参数中指定神秘箱的品质，而是通过以下语法指定每种神秘箱品质的几率。

**语法：**
 - `c:(<quality>:<chances>)` - 当未指定 quality 参数时，神秘箱品质的自定义几率。

**说明：**
 - 神秘箱的品质，后面跟着获得该品质的几率。
 - 请注意，您必须填写所有可用的品质（1 - 5）。缺少任何一项都会引发错误。
 - 所有品质的几率总和可以大于 100，也可以小于 100。

**示例：**
 - `/gmysteryboxes give <player> <amount> c:(1:40,2:30,3:25,4:15,5:10)` - 40% 的几率获得 1 星神秘箱，30% 的几率获得 2 星神秘箱……以此类推。
 - `/gmysteryboxes give <player> <amount> c:(1:80,2:70,3:65,4:5,5:3)` - 80% 的几率获得 1 星神秘箱，70% 的几率获得 2 星神秘箱……以此类推。

 [点击此处了解该命令的更多信息](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-give-player-amount-quality-ex-7h-7d-7m-false-reqperm-false-c-quality-chances)

## 如何向玩家发放神秘礼物？

您可以通过以下命令向玩家发放神秘礼物：
 - `/gmysteryboxes gift <player> <pack>`

 [点击此处了解该命令的更多信息](wiki/getting-started/commands/mystery-boxes#gmysteryboxes-gift-player-pack)

> **注意：** 请注意，每份神秘礼物包含 5 个神秘箱。目前神秘箱的数量无法更改。

## 为什么有些玩家无法打开神秘宝库？

如果您在出生点附近创建了神秘宝库，可能无法通过右键点击神秘宝库来打开其菜单。

您需要在服务器的 `server.properties` 文件中，将 `Spawn-Protection` 属性的值设置为 `0`。

## 为什么玩家无法开启神秘箱？

开启神秘箱需要相应的权限。此外，神秘箱的开启动画还需要另一项权限。

点击下方链接查看开启神秘箱所需的权限列表：
- [神秘箱](wiki/getting-started/permissions#mystery-boxes)
- [神秘宝库动画](wiki/getting-started/permissions#mystery-vault-animations)

如果您不知道该如何为“default”等级的玩家设置权限，可以参阅[面向新手的权限设置](wiki/getting-started/permissions#permission-for-beginners)。

## 为什么玩家偶尔会获得神秘箱？

GadgetsMenu 提供了一项名为“神秘箱奖励”的功能，当玩家在服务器中的游玩时长达到一定数值时，就会获得神秘箱。

您可以在 `mystery boxes.yml` 文件中禁用或修改该奖励设置。

- `mystery boxes/mystery boxes.yml`
```yaml
Mystery-Boxes-Reward:
  Enabled: true
  Allow-AFK: false
  Chance-To-Get-Mystery-Box: 75
  Chance:
    One-Star: 5
    Two-Star: 10
    Three-Star: 60
    Four-Star: 20
    Five-Star: 5
  Expiry-Date-In-Days: 7
  Play-Time:
    Hours: 0
    Minutes: 40
    Seconds: 0
  Enabled-Worlds:
  - '*'
  Message:
    One-Star: '&fYou found a &e✰&7✰✰✰✰ &fMystery Box!'
    Two-Star: '&fYou found a &e✰✰&7✰✰✰ &fMystery Box!'
    Three-Star: '&fYou found a &e✰✰✰&7✰✰ &fMystery Box!'
    Four-Star: '&fYou found a &e✰✰✰✰&7✰ &fMystery Box!'
    Five-Star: '&fYou found a &e✰✰✰✰✰ &fMystery Box!'
```

> **注意：** 使用 GadgetsMenu（高级版）时，玩家的游玩时长会保存在数据库中，并提供一个选项来控制玩家挂机时是否继续计时。

## 如何向玩家发放宠物物品？

您可以通过以下命令向玩家发放神秘礼物：
 - `/gmenu petitems`

执行上述命令将列出所有可用的子命令。您可以使用 `TAB` 键帮助自动补全所需的值。 

**子命令：**
- `/gmenu petitems add <item> <player> <amount>` - 向玩家添加宠物物品。
- `/gmenu petitems check <player>` - 查看玩家的宠物物品。
- `/gmenu petitems remove <item> <player> <amount>` - 从玩家处移除宠物物品。
- `/gmenu petitems set <player> <amount>` - 设置玩家的宠物物品。

**示例：**
- `/gmenu petitems add Apple Notch 10`
- `/gmenu petitems check Notch`
- `/gmenu petitems remove Water Notch 3`
- `/gmenu petitems set Stick Notch 25`

[点击此处了解该命令的更多信息](wiki/getting-started/commands/general#gmenu-petitems)

## 玩家可以通过哪些方式获得宠物物品？

目前，玩家有两种方式获得宠物物品：
1. 通过开启神秘箱，玩家会获得一定数量的宠物物品，数量取决于神秘箱的品质。
2. 通过命令 `/gmenu petitems` 向玩家发放宠物物品。

## 为什么我的神秘宝库只显示两行全息图而不是三行？

![神秘宝库全息图](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-show-solution.jpg "[Wrapper] Mystery Vault holograms")

一般来说，神秘宝库上方应当显示 3 行全息图。如果您遇到神秘宝库只显示两行全息图的问题，如下图所示：

![神秘宝库全息图未显示](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-show.jpg "[Wrapper] Mystery Vault hologram not showing")

您需要在服务器中添加 [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) 插件。额外的那行全息图需要 ProtocolLib 插件才能启用。安装该插件后，全息图会自动显示，除非您使用的 ProtocolLib 版本与您的服务器版本不兼容。

## 为什么我的神秘宝库全息图无法正常工作？

![神秘宝库全息图无法正常工作](/assets/gadgetsmenu-docs/images/getting-started/faq-mystery-vault-hologram-not-working-properly.png "[Wrapper] Mystery Vault hologram not working properly")

您的神秘宝库全息图无法正常工作，直接显示了占位符，和上图类似？

不用担心！该问题是由于您使用了过旧版本的 ProtocolLib 插件所致。请将您的 [ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/) 插件更新到最新构建版本，并确保它支持您的服务器版本。

## 为什么即使启用了自身伪装视角，有些 Morphs 我仍然看不到？

如果您的 Morphs 没有显示，请确保 LibsDisguises 文件夹中的 `players.yml` 文件里，以下属性已设置为 `true`。

**LibsDisguises/configs/players.yml**
```yaml
TallSelfDisguises: true
```