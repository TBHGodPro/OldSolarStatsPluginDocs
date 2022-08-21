# parseNBTData

Parses passed in NBT Data

```javascript
parseNBTData(
	data, // (Buffer | String) The Data To Parse
	nbtType // OPTIONAL ("big" | "little" | "littleVarint") The NBT Data Type
);
```

```javascript
import { parse as parseNBT } from "prismarine-nbt";

function parseNBTData(
	data: Buffer | string,
	nbtType?: "big" | "little" | "littleVarint"
): Promise<{
	parsed: {
		type: "compound",
		value: any
	} & {
		name: string
	},
	type: "big" | "little" | "littleVarint",
	metadata: {
		// The decompressed buffer
		buffer: Buffer,
		// The length of bytes read from the buffer
		size: number
	}
}> {
	if (!Buffer.isBuffer(data)) {
		data = Buffer.from(data, "base64");
	}
	return parseNBT(data, nbtType);
}
```
