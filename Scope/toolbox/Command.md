# Command

The `Command` class allows you to create commands that players can use.

#### Constructing

```javascript
const { Command } = toolbox;

let cmd = new Command(
	"help", // Command Name
	[
		{
			argument: "string", // Argument Name
			required: "boolean", // Argument Required
			type: "string" | "number" | "json" | "array" // Argument Type
		}
	], // Command Arguments
	["h", "helpmenu", "menu"] // Command Aliases
);
```

#### Handling

```javascript
cmd.onTriggered = (
	text, // Command Sent (String)
	args // Command Arguments (Array<String>)
) => {
	console.log(
		text, // "help" | "h" | "helpmenu" | "menu"
		args // ["Argument1Value"]
	);
};
```

#### Registering

!> **WARNING**: You must register the command or it won't do anything

```javascript
registerCommand(cmd);
```

#### Extra Data

```javascript
cmd.player; // The player for the module (should be same as the player scope object)

cmd.name; // The One You Set
cmd.syntax; // (aka arguments) The Ones You Set
cmd.aliases; // The Ones You Set
```
