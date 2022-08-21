# requireModule

Require a Node.js Module

!> NOTE: This should only be used for packages that are included in SolarStats itself. Any other packages should be installed into the Plugin Template and imported using `require`

```javascript
const chalk = requireModule("chalk");
const hypixelapi = requireModule("hypixel-api-reborn");
const nodeCanvas = require("canvas"); // Use "npm install canvas" before
```
