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
 - First, you need to open `plugin.yml` file in your plugin and add `depend` or `softdepend` entry so the server knows that your plugin depends on GadgetsMenu.

```yaml
name: CustomEconomy
main: com.yapzhenyie.customeconomy.CustomEconomyMain
version: 1.0.0
author: yapzhenyie
softdepend: [GadgetsMenu]
```

## Custom Economy File
 - Then, create a new class which extends GEconomyProvider.
 - Create a constructor and add unimplemented methods.

```java
import com.yapzhenyie.GadgetsMenu.economy.GEconomyProvider;
import com.yapzhenyie.GadgetsMenu.economy.GStorage;
import com.yapzhenyie.GadgetsMenu.player.OfflinePlayerManager;

public class Economy_CustomEconomy extends GEconomyProvider {

	public Economy_CustomEconomy(CustomEconomyMain yourPlugin) {
                //Plugin plugin, your storage name
		super(yourPlugin, "Custom-Storage");
	}

	@Override
	public int getMysteryDust(OfflinePlayerManager pManager) {
		return 0;
	}

	@Override
	public boolean addMysteryDust(OfflinePlayerManager pManager, int amount) {
               // Add your code here.
               return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean setMysteryDust(OfflinePlayerManager pManager, int amount) {
               // Add your code here.
               return true; // Return true when the transaction is successful, otherwise return false.
	}

	@Override
	public boolean removeMysteryDust(OfflinePlayerManager pManager, int amount) {
               // Add your code here.
               return true; // Return true when the transaction is successful, otherwise return false.
	}
}
```

## Startup File
 - Lastly, set mystery dust storage if GadgetsMenu is found.

```java
import com.yapzhenyie.GadgetsMenu.economy.GEconomyProvider;

public class CustomEconomyMain extends JavaPlugin {
	@Override
	public void onEnable() {
              if(Bukkit.getPluginManager().isPluginEnabled("GadgetsMenu")) {
                    // Set Mystery Dust Storage.
                    GEconomyProvider.setMysteryDustStorage(new Economy_CustomEconomy(this));
              }
        }
}
```


