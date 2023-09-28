---
title: Custom Economy Storage
description: You can use the custom economy storage API to hook Mystery Dust with your own economy system.
group: developers
keywords: custom economy storage,api
topics:
 - custom economy storage
 - api
---

## plugin.yml File
 - First, open the `plugin.yml` file in your plugin and add GadgetsMenu name in `depend` or `softdepend` entry so the server knows that your plugin depends on GadgetsMenu.

```yaml
name: PluginEconomy
main: com.developer.plugineconomy.CustomEconomyMain
version: 1.0.0
author: yapzhenyie
softdepend: [GadgetsMenu]
```

## Custom Economy File
 - Then, create a new class which extends EconomyProvider.
 - Copy the constructor and the methods below.
 - Implement your own economy code.

```java
import com.yapzhenyie.GadgetsMenu.economy.EconomyProvider;
import com.yapzhenyie.GadgetsMenu.player.OfflinePlayerManager;

public class Economy_CustomEconomy extends EconomyProvider {

	public Economy_CustomEconomy(CustomEconomyMain yourPlugin) {
        //Plugin plugin, your storage name
		super(yourPlugin, "custom-storage");
	}

    @Override
    public boolean hookDependency() {
		// Any pre-checking or pre-hook code if required
        return true;
    }

	@Override
	public int getBalance(OfflinePlayerManager pManager) {
		return 0;
	}

	@Override
	public boolean addBalance(OfflinePlayerManager pManager, int amount) {
		// Add your code here.
		return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean setBalance(OfflinePlayerManager pManager, int amount) {
		// Add your code here.
		return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean removeBalance(OfflinePlayerManager pManager, int amount) {
		// Add your code here.
		return true; // Return true when the transaction is successful, otherwise return false.
	}
}
```

## Startup File
 - Lastly, register and activate the economy storage if GadgetsMenu is found when enabling your plugin.

```java
import com.yapzhenyie.GadgetsMenu.economy.EconomyProvider;
import com.yapzhenyie.GadgetsMenu.exception.EconomyStorageHookException;

public class CustomEconomyMain extends JavaPlugin {
	
	@Override
	public void onEnable() {
		if (Bukkit.getPluginManager().isPluginEnabled("GadgetsMenu")) {
			// Register and activate the economy storage.
			try {
				EconomyProvider economyProvider = new Economy_CustomEconomy(this);
				economyProvider.register(true);
			} catch (EconomyStorageHookException e) {
				e.printStackTrace();
			}
		}
	}
}
```


