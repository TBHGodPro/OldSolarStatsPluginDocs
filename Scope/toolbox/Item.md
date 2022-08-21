# Command

The `Item` class allows you to create items that can be used for [Inventories](Scope/toolbox/Inventory.md) or [PlayerModules](Scope/toolbox/PlayerModule.md).

#### Constructing

```javascript
const { Item } = toolbox;

let item = new Item(
	166, // Item ID (166 is Barrier Block)
	7 // Item Count
);
```

#### Changing Values

```javascript
item.id = 339; // Change the Item ID (339 is Paper)
item.amount = 9; // Change the Amount of the Item
item.meta = 3; // Change the Item Damage Value
item.displayName = "urmom"; // Change the Item Name
item.lore = ["", "some lore", "eeeee"]; // The stuff under the Name of the Item (Each item in the Array is a new Line)
```

#### Extra Data

```javascript
item.slotRepresentation = "object" // The Item Data for the Item
/*
{
  blockId: number;
  itemCount: number;
  itemDamage?: number;
  nbtData?: {
    type: 'compound';
    name: '';
    value: {
      display?: {
        type: 'compound';
        value: {
          Lore?: {
            type: 'list';
            value: {
              type: 'string';
              value: string[];
            };
          };
          Name?: {
            type: 'string';
            value: string;
          };
        };
      };
    };
  };
}
*/

item._id = "number" // The Item ID
item._amount = "number" // The Amount of the Item
item._meta = "number" // The Damage Value for the Item
item._displayName = "string" // The Item Name
item._lore = Array<"string"> // The Lore for the Item
```
