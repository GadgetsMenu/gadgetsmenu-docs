---
title: Custom Economy Storage
description: You can use the custom economy storage API to store Mystery Dust in your own economy system.
group: developers
keywords: custom economy storage,economy provider,mystery dust,api
topics:
 - custom economy storage
 - api
---

The custom economy storage API lets your plugin store Mystery Dust in your own economy system. GadgetsMenu then reads and changes every player's Mystery Dust through your code.

GadgetsMenu keeps Mystery Dust in one **active economy storage** at a time. The built-in storages are chosen with `Mystery-Dust-Storage` in `config.yml` (see [Mystery Dust Storage](../wiki/features/mystery-dust#mystery-dust-storage)). A custom storage is registered and activated by your plugin when it starts.

## plugin.yml File
 - First, open the `plugin.yml` file in your plugin and add GadgetsMenu to the `depend` or `softdepend` entry. The server then enables GadgetsMenu before your plugin, so the API is ready when your plugin starts.

```yaml
name: PluginEconomy
main: com.developer.plugineconomy.CustomEconomyMain
version: 1.0.0
author: yapzhenyie
softdepend: [GadgetsMenu]
```

## Custom Economy File
 - Then, create a new class which extends `EconomyProvider`.
 - Copy the constructor and the methods below.
 - Implement your own economy code.

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

The storage identifier (`custom-storage` above) must be unique, and it is not case-sensitive. Do not use the identifier of a built-in storage: `default`, `vault`, `playerpoints`, `coinsapi`, `tokenmanager`, `coinsengine` or `ultraeconomy`.

GadgetsMenu calls the methods as follows:

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Method | Called when | Return |
| --- | --- | --- |
| `hookDependency()` | Once, when the storage is registered. | `true` when your economy is ready. `false` stops the registration with an `EconomyStorageHookException`. |
| `getBalance(pManager)` | GadgetsMenu needs a player's Mystery Dust, such as when the player joins or a menu shows it. An online player's balance is kept for 1 second, so it is asked at most once a second per player. | The player's Mystery Dust. |
| `addBalance(pManager, amount)` | Mystery Dust is given to the player. | `true` if the change succeeded. |
| `setBalance(pManager, amount)` | The player's Mystery Dust is set. `amount` is never negative. | `true` if the change succeeded. |
| `removeBalance(pManager, amount)` | Mystery Dust is taken from the player, such as for a purchase. GadgetsMenu checks that the player has enough first. | `true` if the change succeeded. |
| `getBalances(players)` | Optional, see [Reading Many Balances at Once](#reading-many-balances-at-once). | The Mystery Dust of each player, by UUID. |

</div>
</div>

 - Identify the player with `pManager.getUUID()`. `pManager.getPlayer()` returns an `OfflinePlayer`, and the player may be offline, for example when Mystery Dust is given to an offline player with a command.
 - For online players, GadgetsMenu fires `GainMysteryDustEvent`, `AssignMysteryDustEvent` and `RemoveMysteryDustEvent` before it calls `addBalance`, `setBalance` and `removeBalance`. When another plugin cancels the event, your method is not called.
 - Return `false` when a change fails. The code that made the change is told it failed, and GadgetsMenu asks your provider for the balance again the next time it needs it.
 - Changes made directly in your economy show in GadgetsMenu the next time it reads the player's balance.

>**Warning:** GadgetsMenu calls your provider from the main server thread and from async threads. `getBalance` is called from both, for example when a menu opens and when a player's data loads. `getBalances` is called from an async thread. `addBalance`, `setBalance` and `removeBalance` run on the thread of the code that changes the balance, usually the main thread. Make your methods thread-safe and quick: a slow read on the main thread lags the server. If your economy reads from a database, keep the online players' balances in a cache.

## Reading Many Balances at Once
Every 10 minutes, GadgetsMenu refreshes the Mystery Dust of all online players with one `getBalances` call. By default, `getBalances` calls `getBalance` once for each player. If your economy can read many players at once, such as with one database query, override `getBalances` in your class:

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

 - Return the Mystery Dust of each player by UUID.
 - Leave out a player whose balance could not be read. That player keeps their current balance instead of being reset to 0. If `getBalances` throws an exception, every player keeps their balance.
 - Players whose balance was read in the last second are not included.
 - If a player's Mystery Dust changes while `getBalances` runs, GadgetsMenu keeps the new amount.

## Startup File
 - Lastly, register and activate the economy storage if GadgetsMenu is found when enabling your plugin.

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

 - `register(true)` registers the storage and makes it the active economy storage, so all Mystery Dust is stored in it.
 - `register()` registers the storage without activating it. Call `setAsActiveEconomyStorage()` later to activate it.
 - `register` throws an `EconomyStorageHookException` when `hookDependency()` returns `false` or your plugin is not enabled. It returns `false` when a storage with the same identifier is already registered.
 - Do not set `Mystery-Dust-Storage` in `config.yml` to your identifier. GadgetsMenu reads `config.yml` before your plugin registers the storage, so it does not know the identifier yet and falls back to the `default` storage. Your plugin activates the storage with `register(true)` instead.
 - If your provider class also implements `org.bukkit.event.Listener`, GadgetsMenu registers its event handlers when the storage is registered, and removes them when it is unregistered.

## Unregister the Storage
 - `unregister()` removes the storage. If it is the active economy storage, GadgetsMenu first switches back to the `default` storage. If the `default` storage is not registered, `unregister()` returns `false` and your storage stays active.
 - Call `unregister()` while your plugin is still enabled. Bukkit marks a plugin as disabled before it calls `onDisable()`, so `unregister()` fails inside `onDisable()`.

## API Reference

### EconomyProvider
Package: `com.yapzhenyie.GadgetsMenu.economy`

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Method | Description |
| --- | --- |
| `EconomyProvider(Plugin plugin, String storageIdentifier)` | Creates a custom storage owned by your plugin. |
| `boolean hookDependency()` | Abstract. Prepares your economy when the storage is registered. |
| `int getBalance(OfflinePlayerManager pManager)` | Abstract. Gets a player's Mystery Dust. |
| `boolean addBalance(OfflinePlayerManager pManager, int amount)` | Abstract. Adds Mystery Dust to a player. |
| `boolean setBalance(OfflinePlayerManager pManager, int amount)` | Abstract. Sets a player's Mystery Dust. |
| `boolean removeBalance(OfflinePlayerManager pManager, int amount)` | Abstract. Takes Mystery Dust from a player. |
| `Map<UUID, Integer> getBalances(Collection<? extends OfflinePlayerManager> players)` | Gets the Mystery Dust of several players. Override it to read them together. Since 5.34.5. |
| `boolean register()` | Registers the storage. |
| `boolean register(boolean setAsActiveEconomyStorage)` | Registers the storage, and with `true` also makes it the active economy storage. |
| `boolean setAsActiveEconomyStorage()` | Makes the registered storage the active economy storage. Returns `false` if it is not registered or already active. |
| `boolean unregister()` | Unregisters the storage. See [Unregister the Storage](#unregister-the-storage). |
| `boolean isRegistered()` | Whether the storage is registered. |
| `boolean isDependencyEnabled()` | Whether the plugin that owns the storage is enabled. |
| `boolean canRegister()` | Whether the storage can be registered, that is, the plugin that owns it is enabled. |
| `EconomyStorage getEconomyStorage()` | The storage details: `getStorageIdentifier()` (in lower case), `getPluginName()`, `isCustomStorage()`, `isDefaultStorage()` and `getAdditionalParams()`. |

</div>
</div>

### EconomyStorageManager
Get it with `GadgetsMenu.getInstance().getEconomyStorageManager()`.

<div class="md-table-max-content md-table-width-100">
<div class="overflow-auto">

| Method | Description |
| --- | --- |
| `EconomyProvider getActiveEconomyProvider()` | The provider of the active economy storage. |
| `EconomyProvider getEconomyProviderByIdentifier(String storageIdentifier)` | The registered provider with this identifier, or `null`. |
| `Collection<String> getStorageIdentifiers()` | The identifiers of all registered storages. |
| `Collection<EconomyProvider> getEconomyProviders()` | All registered providers. |

</div>
</div>

## Relevant content
<div class="md-relevant-content">

- [Mystery Dust](../wiki/features/mystery-dust)
- [Developer API](../wiki/developers/developer-api)
</div>
