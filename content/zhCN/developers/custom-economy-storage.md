---
title: 自定义经济存储
description: 您可以使用自定义经济存储 API，将 Mystery Dust 挂钩到您自己的经济系统上。
group: developers
keywords: 自定义经济存储,api
topics:
 - 自定义经济存储
 - api
---

## plugin.yml 文件
 - 首先，打开您插件中的 `plugin.yml` 文件，并在 `depend` 或 `softdepend` 条目中添加 GadgetsMenu 的名称，让服务器知道您的插件依赖于 GadgetsMenu。

```yaml
name: PluginEconomy
main: com.developer.plugineconomy.CustomEconomyMain
version: 1.0.0
author: yapzhenyie
softdepend: [GadgetsMenu]
```

## 自定义经济文件
 - 接着，创建一个继承 EconomyProvider 的新类。
 - 复制下面的构造函数和方法。
 - 实现您自己的经济逻辑代码。

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

## 启动文件
 - 最后，在启用您的插件时，如果检测到 GadgetsMenu，则注册并激活该经济存储。

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
