# PlayerModule

The `PlayerModule` class allows you to create modules that players can enable or disable to tell you whether or not they want your plugin to be active.

> Uses:

> -   [Item](Scope/toolbox/Item.md)
> -   [getConfigSync](Scope/toolbox/getConfigSync)

#### Constructing

```javascript
const { PlayerModule, Item, getConfigSync } = toolbox;

const settingItem = new Item(166, 7); // Creates a Barrier (Item ID 166) with quantity of 7
settingItem.displayName = "Module Name Herre";
settingItem.lore = ["", "§7Some description", "§7with more lines", "§7and more too", "§7and even more", "", `§7Current: §${getConfigSync().modules.myModule ? "aEnabled" : "cDisabled"}`]; // Recommended to start each line with §7

const module = new PlayerModule(
	"My Module Name", // Module Name
	"Some one line description", // Module Description (User \n for new lines)
	settingItem, // OPTIONAL Module settingItem
	"myModule"
); // OPTIONAL (But required if there is a settingItem) Module configKey
```

#### Handling

```javascript
module.customCode = () => {
	// Run when module is loaded
	// Code Here
};

module.onConfigChange = enabled => {
	// Run when the module is toggled on/off
	// Code Here
};

module.onLocationUpdate = status => {
	// Run when the player switches servers (As long as they are still on hypixel)
	// Code Here
};

module.onDisconnect = () => {
	// Run when the player leaves the proxy (aka leaves hypixel)
	// Code Here
};
```

#### Registering

!> **WARNING**: You must register the module or it won't do anything

```javascript
registerPlayerModule(module);
```

#### Extra Data

```javascript
module.enabled; // Whether the module is enabled or not
module.player; // The player for the module (should be same as the player scope object)

module.name; // The One You Set
module.description; // The One You Set
module.settingItem; // The One You Set
module.configKey; // The One You Set
```
