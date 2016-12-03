# xfunction
## Node Red xfunction: "An extended function node"

## Installation
go on your user node-red root directory (~/.node-red)
```
npm install https://github.com/gbrault/xfunction
```

## Usage
Will add an xfunction node on Node-Red Editor palette
It is a clone of the core Node-Red function node with the following extensions
* **RED.red**: this is the RED object created at Node-Red startup as ```var RED = require("./red/red.js");```
* RED.red.version() provides Node-Red version
* **RED.fs**: Node file system handle  ```var fs = require('fs');```
* **RED.path**: ```var path = require('path');```
* **RED.express**: ```var express = require('express');```
* **RED.process**: the Node.js process variable
* ```RED.porcess.exit()``` will exit the current node-red server, used in conjunction of forever can restart Node-RED 'programatically'
