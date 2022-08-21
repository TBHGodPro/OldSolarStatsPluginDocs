# Command

The `Inventory` class allows you to create inventories that can be opened for players which they can interact with.

> Uses the [Item](Scope/toolbox/Item.md) Class

#### Constructing

```typescript
enum InventoryType {
	ANVIL = "minecraft:anvil",
	BEACON = "minecraft:beacon",
	BREWING = "minecraft:brewing_stand",
	CHEST = "minecraft:chest",
	CONTAINER = "minecraft:container",
	CRAFTING = "minecraft:crafting_table",
	DISPENSER = "minecraft:dispenser",
	DROPPER = "minecraft:dropper",
	ENCHANTING_TABLE = "minecraft:enchanting_table",
	FURNACE = "minecraft:furnace",
	HOPPER = "minecraft:hopper",
	VILLAGER = "minecraft:villager"
}
```

```javascript
const { Inventory, Item, InventoryType } = toolbox;

let inv = new Inventory(
	InventoryType.SOMEVALUE, // The Inventory Type (Container is a default chest),
	"Inventory Title", // The Inventory Title
	54 // The Inventory Slots (27 = Single Chest | 54 = Double Chest) (You can pick any value)
);
```

#### Adding Items

```javascript
const item1 = new Item(/* Item Params */)
const item2 = new Item(/* Item Params */)
const item3 = new Item(/* Item Params */)

inv.addItem(
    item1, // The Item
    7 // The 0-Based Item Position In The Inventory
)

inv.addItems([
    {
        item1, // The Item
        7 // The 0-Based Item Position In The Inventory
    },
    {
        item2, // The Item
        21 // The 0-Based Item Position In The Inventory
    },
    {
        item3, // The Item
        15 // The 0-Based Item Position In The Inventory
    }
])
```

#### Handling

```javascript
inv.incomingPacketHandler = (data, meta) => {
	// Code Here
};
inv.outgoingPacketHandle = (data, meta, toClient, toServer) => {
	// Code Here
};

inv.on("close", () => {
	// Code Here
});
inv.on(
	"click",
	(
		event // The Inventory Click Event
		/*
        {
            slot: number;
            button: number;
            mode: number;
            raw: unknown;
            toServer: Server;
            cancel: (client: player.client) => void;
        }
        */
	) => {
		// Code Here
	}
);
```

#### Functions

```javascript
inv.removeItem(
    "number", // Position of the Item you're Removing
) // Removes a specific Item in the Inventory

inv.clear() // Clears the Inventory

inv.display(
    player // The Player to open the Inventory for
) // Opens the Inventory for someone

inv.close(
    player // The Player to close the Inventory for
) // Closes the Inventory for someone

inv.markAsClosed(
    proxy // The Proxy (player.proxy) to mark as closed for
) // Mark an Inventory as closed without closing it

inv.setSlot(
    client, // The Client (player.client) to set the Inventory slot for,
    item, // The Item to put in the Slot,
    slot // The Slot to put the Item in
) // Set a slot in the Inventory (When it's open)

inv.removeListener("click" | "close", function) // Remove a listener on the Inventory
```

#### Extra Data

```javascript
inv.incomingPacketHandler; // The Incoming Packet Handler For The Inventory
inv.outgoingPacketHandler; // The Outgoing Packet Handler For The Inventory

inv.items; // The Items in the Inventory
inv.type; // The InventoryType of the Inventory
inv.title; // The Inventory Title
inv.slotCount; // The Amount of Slots in the Inventory
inv.opened; // If the Inventory is Opened
```
