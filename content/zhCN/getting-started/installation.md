---
title: 安装
description: 从零开始，在您的服务器中使用此插件的完整安装步骤。
group: getting-started
keywords: 安装
topics:
 - 安装
 - 说明
---

## 初次安装步骤

### 第 1 步：下载插件

从 SpigotMC 下载 GadgetsMenu 的 jar 文件，并将其保存到您的本地设备中。

不确定在哪里下载插件？您随时可以在[下载](../download)页面找到下载或购买链接。

### 第 2 步：下载依赖插件（可选）

GadgetsMenu 不依赖任何其他插件即可运行，但部分特性与功能需要依赖插件才能启用。

您可以暂时跳过此步骤，等成功设置好 GadgetsMenu 插件之后再回来处理。

**依赖项列表**
 - [**[Lib's Disguise](https://www.spigotmc.org/resources/libs-disguises.81/)**、**[iDisguise](https://www.spigotmc.org/resources/idisguise.5509/)**]：用于启用 Morphs 化妆品。（点击链接查看关于 [Morphs](/wiki/features/cosmetic-items/morphs) 的更多详情）
 - [**[Vault](https://www.spigotmc.org/resources/vault.41918/)**、**[PlayerPoints](https://dev.bukkit.org/projects/playerpoints)**、**[CoinsAPI](https://www.spigotmc.org/resources/coinsapi.35150/)**]：用于使用其他经济插件来存储 Mystery Dust 数据。
 - [**[ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/)**]：用于在神秘宝库上方显示独立的全息图。
 - [**[WorldGuard](https://dev.bukkit.org/projects/worldguard)**]：通过配置黑名单地区，限制在特定地区使用化妆品。
 - [**[Placeholders](https://www.spigotmc.org/resources/placeholderapi.6245/)**]：用于在计分板、排行榜或每日奖励等第三方插件中显示 GadgetsMenu 的相关信息。

### 第 3 步：将 GadgetsMenu jar 文件和依赖项 jar 文件放入服务器的 `/plugins` 文件夹

现在，将您下载的 GadgetsMenu jar 文件上传到服务器的 `/plugins` 文件夹中。

请确保该文件夹中没有重复的 GadgetsMenu jar 文件。如果有，请删除较旧的 jar 文件。

### 第 4 步：重启您的服务器

上传完成后，您可以关闭或重启您的 Minecraft 服务器。

GadgetsMenu 将在服务器启动时生成默认的配置文件。

服务器启动时，如果加载成功，您应当能在控制台看到 GadgetsMenu 的加载消息。插件应当在没有任何错误的情况下加载完成。如果您发现任何与 GadgetsMenu 插件相关的错误，请联系我们的支持团队。

![安装 - 初始化插件](/assets/gadgetsmenu-docs/images/getting-started/installation_step-4.PNG "[Wrapper] Installation - Initialize plugin")

加载成功后，您现在可以根据需要配置文件和设置。请查阅我们的 Wiki 页面以了解更多详情。

### 第 5 步：根据需要配置设置

您可以在 `plugins/GadgetsMenu` 文件夹中找到 GadgetsMenu 的配置文件，并根据需要自定义各项设置。

![配置文件](/assets/gadgetsmenu-docs/images/getting-started/installation_step-5-configuration-files.PNG "[Wrapper] Configuration files")

这里有若干文件夹和文件，每一个都有不同的用途。
 - **`categories`** 文件夹：此文件夹中的文件用于配置每种化妆品与主菜单物品的设置。
 - **`custom cosmetics`** 文件夹：此文件夹中的文件用于配置自定义化妆品。
 - **`mystery boxes`** 文件夹：此文件夹中的文件用于配置神秘箱设置、神秘宝库动画设置以及自定义神秘箱战利品。
 - **`songs`** 文件夹：用于存放音乐小工具所使用的音乐文件。
 - **`config.yml`**：此文件存储插件的常规设置，包括数据库设置、菜单物品和化妆品分类。
 - **`messages.yml`**：此文件存储常规消息和 GUI 菜单物品设置。
 - **`mystery vaults.yml`**：此文件存储神秘宝库数据。（注意：除非您清楚自己在做什么，否则请勿编辑此文件。）
 - **`pet system.yml`**：此文件存储与宠物系统相关的设置，包括宠物物品、宠物属性和快乐度设置。

### 第 6 步：如有任何配置更改，请再次重启服务器

在完成修改并保存文件之后，您可以重启服务器，测试您的更改是否按预期生效。

作为替代方案，GadgetsMenu 提供了[重载命令](../wiki/getting-started/commands/general#gmenu-reload-confirm)，可以立即应用更改，而无需重启服务器。

不过请注意，您绝不能在正式服务器中使用此命令，因为它可能导致漏洞和内存泄漏问题。请谨慎使用此命令，风险自负。

## 延伸阅读
<div class="md-relevant-content">

- [配置](../wiki/getting-started/configuration)
- [命令](../wiki/getting-started/commands)
- [权限](../wiki/getting-started/permissions)
</div>
