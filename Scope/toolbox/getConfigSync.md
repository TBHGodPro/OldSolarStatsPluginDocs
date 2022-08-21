# getConfigSync

Gets the config from the `config.json` file in the SolarStats directory.

!> This is a `sync` function, meaning it pauses the execution of the node.js process until it's done, it doesn't need to have an `await` before it and it doesn't need to be in an `async function`, but do note you should **ONLY USE THIS WHEN 100% NECESSARY** because it has a chance to crash the entire SolarStats process.

```javascript
const config = getConfigSync();
```
