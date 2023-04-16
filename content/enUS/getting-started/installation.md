---
title: Installation
description: Complete installation steps to use this plugin in your server from scratch.
group: getting-started
keywords: Installation
topics:
 - Installation
 - Instruction
---

## Initial Installation Steps

### Step 1: Download the plugin

Download the GadgetsMenu jar file from SpigotMC and save it in your local device.

Not sure where to download the plugin? You can always find the download or purchase link at [Download](../download).

### Step 2: Download dependencies plugin (Optional)

GadgetsMenu does not depends on any other plugin to make it work, but some features & functions are require plugin dependencies to activate.

You can skip this step for now and come back after successfully setting up the Gadgets Menu plugin.

**Dependency List**
 - [**[Lib's Disguise](https://www.spigotmc.org/resources/libs-disguises.81/)**, **[iDisguise](https://www.spigotmc.org/resources/idisguise.5509/)**]: To enable Morphs cosmetic. (Click on the link to see more details about [Morphs](/wiki/features/cosmetic-items/morphs))
 - [**[Vault](https://www.spigotmc.org/resources/vault.41918/)**, **[PlayerPoints](https://dev.bukkit.org/projects/playerpoints)**, **[CoinsAPI](https://www.spigotmc.org/resources/coinsapi.35150/)**]: To use other economy plugins to store Mystery Dust data.
 - [**[ProtocolLib](https://www.spigotmc.org/resources/protocollib.1997/)**]: To display the individual hologram on top of Mystery Vault.
 - [**[WorldGuard](https://dev.bukkit.org/projects/worldguard)**]: Restrict cosmetic usage in certain regions by configuring blacklisted regions.
 - [**[Placeholders](https://www.spigotmc.org/resources/placeholderapi.6245/)**]: To show information about GadgetsMenu in 3rd party plugins such as scoreboard, leaderboards or daily rewards plugin.

### Step 3: Place GadgetsMenu jar file and dependencies jar files into your server `/plugins` folder

Now, upload the GadgetsMenu jar file you have downloaded into your server `/plugins` folder. 

Make sure there isn't any duplicate GadgetsMenu jar file in that folder. If yes, delete the older jar file.

### Step 4: Restart your server

Once uploaded, you may shutdown or restart your minecraft server.

GadgetsMenu will generates the default configuration files on server startup.

As the server starts up, you should be able to see the GadgetsMenu loading message at the console when it is successfully loaded. The plugin should loaded without any errors. Please contact our support team when you notice there is any errors related to GadgetsMenu plugin.

![Installation - Initialize plugin](/assets/gadgetsmenu-docs/images/getting-started/installation_step-4.PNG "[Wrapper] Installation - Initialize plugin")

Once successful loaded, you can now configure the files and settings as your need. Check out our Wiki pages for more details.

### Step 5: Configure settings as needed

To configure GadgetsMenu files, 

![Configuration files](/assets/gadgetsmenu-docs/images/getting-started/installation_step-5-configuration-files.PNG "[Wrapper] Configuration files")


### Step 6: Restart your server again if any configuration changes are made


## Further reading
<div class="md-relevant-content">

- [Configuration](../wiki/getting-started/configuration)
- [Commands](../wiki/getting-started/commands)
- [Permissions](../wiki/getting-started/permissions)
</div>