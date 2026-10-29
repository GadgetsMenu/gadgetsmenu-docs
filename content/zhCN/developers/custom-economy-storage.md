---
title: 自定义经济存储
description: 您可以使用自定义经济存储 API，将 Mystery Dust 存储到您自己的经济系统中。
group: developers
keywords: 自定义经济存储,经济提供者,mystery dust,api
topics:
 - 自定义经济存储
 - api
---

自定义经济存储 API 让您的插件可以把 Mystery Dust 存储到您自己的经济系统中。之后，GadgetsMenu 会通过您的代码读取和修改每位玩家的 Mystery Dust。

GadgetsMenu 同一时间只会使用一个**已激活的经济存储**来保存 Mystery Dust。内置的经济存储通过 `config.yml` 中的 `Mystery-Dust-Storage` 选择（请参阅 [Mystery Dust 存储](../wiki/features/mystery-dust#mystery-dust)）。自定义经济存储则由您的插件在启动时注册并激活。

## plugin.yml 文件 ${plugin-yml-file}
 - 首先，打开您插件中的 `plugin.yml` 文件，并在 `depend` 或 `softdepend` 条目中添加 GadgetsMenu。这样服务器会先启用 GadgetsMenu，再启用您的插件，确保您的插件启动时 API 已经可用。

```yaml
name: PluginEconomy
main: com.developer.plugineconomy.CustomEconomyMain
version: 1.0.0
author: yapzhenyie
softdepend: [GadgetsMenu]
```

## 自定义经济文件 ${custom-economy-file}
 - 接着，创建一个继承 `EconomyProvider` 的新类。
 - 复制下面的构造函数和方法。
 - 实现您自己的经济逻辑代码。

```java
import com.yapzhenyie.GadgetsMenu.economy.EconomyProvider;
import com.yapzhenyie.GadgetsMenu.player.OfflinePlayerManager;

public class Economy_CustomEconomy extends EconomyProvider {

	public Economy_CustomEconomy(CustomEconomyMain yourPlugin) {
		// Your plugin, and a unique identifier for your storage.
		super(yourPlugin, "custom-storage");
	}

	@Override
	public boolean hookDependency() {
		// Connect to your economy here. Return false if it is not available,
		// then the storage is not registered.
		return true;
	}

	@Override
	public int getBalance(OfflinePlayerManager pManager) {
		// Return the player's Mystery Dust.
		return 0;
	}

	@Override
	public boolean addBalance(OfflinePlayerManager pManager, int amount) {
		// Add the amount to the player's Mystery Dust.
		return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean setBalance(OfflinePlayerManager pManager, int amount) {
		// Set the player's Mystery Dust to the amount.
		return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean removeBalance(OfflinePlayerManager pManager, int amount) {
		// Take the amount from the player's Mystery Dust.
		return true; // Return true when the transaction is successful, otherwise return false.
	}
}
```

存储标识符（上例中的 `custom-storage`）必须唯一，且不区分大小写。请勿使用内置经济存储的标识符：`default`、`vault`、`playerpoints`、`coinsapi`、`tokenmanager`、`coinsengine` 或 `ultraeconomy`。

GadgetsMenu 调用这些方法的时机如下：

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 方法 | 调用时机 | 返回值 |
| --- | --- | --- |
| `hookDependency()` | 注册经济存储时调用一次。 | 您的经济系统已就绪时返回 `true`。返回 `false` 会中止注册，并抛出 `EconomyStorageHookException`。 |
| `getBalance(pManager)` | GadgetsMenu 需要玩家的 Mystery Dust 时，例如玩家加入服务器或菜单显示余额时。在线玩家的余额会保留 1 秒，因此每位玩家每秒最多查询一次。 | 玩家的 Mystery Dust。 |
| `addBalance(pManager, amount)` | 给予玩家 Mystery Dust 时。 | 修改成功时返回 `true`。 |
| `setBalance(pManager, amount)` | 设置玩家的 Mystery Dust 时。`amount` 永远不会是负数。 | 修改成功时返回 `true`。 |
| `removeBalance(pManager, amount)` | 扣除玩家的 Mystery Dust 时，例如购买化妆品。GadgetsMenu 会先检查玩家的余额是否足够。 | 修改成功时返回 `true`。 |
| `getBalances(players)` | 可选，请参阅[一次读取多个余额](#reading-many-balances-at-once)。 | 每位玩家的 Mystery Dust，以 UUID 为键。 |

</div>
</div>

 - 请使用 `pManager.getUUID()` 识别玩家。`pManager.getPlayer()` 返回的是 `OfflinePlayer`，玩家可能不在线，例如通过命令给离线玩家 Mystery Dust 时。
 - 对于在线玩家，GadgetsMenu 会在调用 `addBalance`、`setBalance` 和 `removeBalance` 之前触发 `GainMysteryDustEvent`、`AssignMysteryDustEvent` 和 `RemoveMysteryDustEvent`。如果其他插件取消了该事件，您的方法就不会被调用。
 - 修改失败时请返回 `false`。发起修改的代码会得知修改失败，GadgetsMenu 下次需要余额时也会重新向您的经济提供者查询。
 - 直接在您的经济系统中所做的修改，会在 GadgetsMenu 下次读取该玩家余额时显示出来。

>**警告：** GadgetsMenu 会在服务器主线程和异步线程中调用您的经济提供者。`getBalance` 在两者中都会被调用，例如打开菜单时和加载玩家数据时。`getBalances` 在异步线程中调用。`addBalance`、`setBalance` 和 `removeBalance` 则在修改余额的代码所在的线程中运行，通常是主线程。请确保您的方法线程安全且执行迅速：在主线程中进行缓慢的读取会导致服务器卡顿。如果您的经济系统从数据库读取数据，请将在线玩家的余额缓存起来。

## 一次读取多个余额 ${reading-many-balances-at-once}
GadgetsMenu 每 10 分钟会通过一次 `getBalances` 调用刷新所有在线玩家的 Mystery Dust。默认情况下，`getBalances` 会为每位玩家各调用一次 `getBalance`。如果您的经济系统可以一次读取多位玩家，例如使用一条数据库查询，请在您的类中重写 `getBalances`：

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.UUID;

	// Add this method to your Economy_CustomEconomy class.
	@Override
	public Map<UUID, Integer> getBalances(Collection<? extends OfflinePlayerManager> players) {
		List<UUID> uuids = new ArrayList<>();
		for (OfflinePlayerManager pManager : players) {
			uuids.add(pManager.getUUID());
		}
		Map<UUID, Integer> balances = new HashMap<>();
		// Read the Mystery Dust of all the UUIDs at once, and put each balance in the map.
		return balances;
	}
```

 - 以 UUID 为键，返回每位玩家的 Mystery Dust。
 - 无法读取余额的玩家请不要放入结果中。该玩家会保留当前的余额，而不会被重置为 0。如果 `getBalances` 抛出异常，所有玩家都会保留各自的余额。
 - 在过去 1 秒内已读取过余额的玩家不会包含在内。
 - 如果玩家的 Mystery Dust 在 `getBalances` 运行期间发生变化，GadgetsMenu 会保留新的数值。

## 启动文件 ${startup-file}
 - 最后，在启用您的插件时，如果检测到 GadgetsMenu，则注册并激活该经济存储。

```java
import com.yapzhenyie.GadgetsMenu.economy.EconomyProvider;
import com.yapzhenyie.GadgetsMenu.exception.EconomyStorageHookException;
import org.bukkit.Bukkit;
import org.bukkit.plugin.java.JavaPlugin;

public class CustomEconomyMain extends JavaPlugin {

	@Override
	public void onEnable() {
		if (Bukkit.getPluginManager().isPluginEnabled("GadgetsMenu")) {
			// Register the economy storage and set it as the active economy storage.
			try {
				EconomyProvider economyProvider = new Economy_CustomEconomy(this);
				economyProvider.register(true);
			} catch (EconomyStorageHookException e) {
				// hookDependency() returned false, or this plugin is not enabled.
				e.printStackTrace();
			}
		}
	}
}
```

 - `register(true)` 会注册该经济存储并将其设为已激活的经济存储，之后所有 Mystery Dust 都会存储在其中。
 - `register()` 只注册经济存储而不激活它。之后可调用 `setAsActiveEconomyStorage()` 将其激活。
 - 当 `hookDependency()` 返回 `false` 或您的插件未启用时，`register` 会抛出 `EconomyStorageHookException`。如果已注册了相同标识符的经济存储，则返回 `false`。
 - 请勿将 `config.yml` 中的 `Mystery-Dust-Storage` 设为您的标识符。GadgetsMenu 会在您的插件注册经济存储之前读取 `config.yml`，此时它还不认识该标识符，因此会改用 `default` 经济存储。请改由您的插件通过 `register(true)` 激活该经济存储。
 - 如果您的经济提供者类同时实现了 `org.bukkit.event.Listener`，GadgetsMenu 会在注册经济存储时注册其事件处理器，并在注销时将其移除。

## 注销经济存储 ${unregister-the-storage}
 - `unregister()` 会移除该经济存储。如果它是已激活的经济存储，GadgetsMenu 会先切换回 `default` 经济存储。如果 `default` 经济存储尚未注册，`unregister()` 会返回 `false`，您的经济存储仍保持激活。
 - 请在您的插件仍处于启用状态时调用 `unregister()`。Bukkit 会在调用 `onDisable()` 之前将插件标记为已禁用，因此在 `onDisable()` 中调用 `unregister()` 会失败。

## API 参考 ${api-reference}

### EconomyProvider ${economyprovider}
包：`com.yapzhenyie.GadgetsMenu.economy`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 方法 | 说明 |
| --- | --- |
| `EconomyProvider(Plugin plugin, String storageIdentifier)` | 创建一个属于您插件的自定义经济存储。 |
| `boolean hookDependency()` | 抽象方法。在注册经济存储时准备您的经济系统。 |
| `int getBalance(OfflinePlayerManager pManager)` | 抽象方法。获取玩家的 Mystery Dust。 |
| `boolean addBalance(OfflinePlayerManager pManager, int amount)` | 抽象方法。给予玩家 Mystery Dust。 |
| `boolean setBalance(OfflinePlayerManager pManager, int amount)` | 抽象方法。设置玩家的 Mystery Dust。 |
| `boolean removeBalance(OfflinePlayerManager pManager, int amount)` | 抽象方法。扣除玩家的 Mystery Dust。 |
| `Map<UUID, Integer> getBalances(Collection<? extends OfflinePlayerManager> players)` | 获取多位玩家的 Mystery Dust。重写它即可一次读取。自 5.34.5 起可用。 |
| `boolean register()` | 注册经济存储。 |
| `boolean register(boolean setAsActiveEconomyStorage)` | 注册经济存储，传入 `true` 时同时将其设为已激活的经济存储。 |
| `boolean setAsActiveEconomyStorage()` | 将已注册的经济存储设为已激活的经济存储。如果它尚未注册或已经处于激活状态，则返回 `false`。 |
| `boolean unregister()` | 注销经济存储。请参阅[注销经济存储](#unregister-the-storage)。 |
| `boolean isRegistered()` | 该经济存储是否已注册。 |
| `boolean isDependencyEnabled()` | 拥有该经济存储的插件是否已启用。 |
| `boolean canRegister()` | 该经济存储是否可以注册，即拥有它的插件已启用。 |
| `EconomyStorage getEconomyStorage()` | 经济存储的详细信息：`getStorageIdentifier()`（小写）、`getPluginName()`、`isCustomStorage()`、`isDefaultStorage()` 和 `getAdditionalParams()`。 |

</div>
</div>

### EconomyStorageManager ${economystoragemanager}
通过 `GadgetsMenu.getInstance().getEconomyStorageManager()` 获取。

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| 方法 | 说明 |
| --- | --- |
| `EconomyProvider getActiveEconomyProvider()` | 已激活经济存储的经济提供者。 |
| `EconomyProvider getEconomyProviderByIdentifier(String storageIdentifier)` | 使用该标识符注册的经济提供者，未找到时返回 `null`。 |
| `Collection<String> getStorageIdentifiers()` | 所有已注册经济存储的标识符。 |
| `Collection<EconomyProvider> getEconomyProviders()` | 所有已注册的经济提供者。 |

</div>
</div>

## 相关内容 ${relevant-content}
<div class="md-relevant-content">

- [Mystery Dust](../wiki/features/mystery-dust)
- [开发者 API](../wiki/developers/developer-api)
</div>
