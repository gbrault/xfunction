# xfunction
## Node Red xfunction: "An extended function node"
It is a clone of the core Node-Red function node with some relaxation of the sandbox script execution context

## Why do I need that?
Node-Red Nodes "function node" have quite a restrictive sandbox, I wanted to relax it a bit to benefit from Node-Red Editor while writing nodes and flows which could have more interaction with Node-Red global context.

Used in conjunction of the functionGlobalContext in the settings.js file, one can virtually access any resources on the target computer. [See](https://nodered.org/docs/configuration) the last paragraph: Node Configuration.

## Installation
go on your user node-red root directory (~/.node-red)
```
npm install https://github.com/gbrault/xfunction
```

## Usage
Will add an xfunction node on Node-Red Editor palette.
It is a clone of the core Node-Red function node with the following extensions.
* **RED.red**: this is the RED object created at Node-Red startup as ```var RED = require("./red/red.js");```
* for example RED.red.version() provides Node-Red version. for more Node-Red Run-time API features [see](http://nodered.org/docs/api/runtime/api)
* **RED.fs**: Node file system handle  ```var fs = require('fs');```
* **RED.path**: ```var path = require('path');```
* **RED.express**: ```var express = require('express');```
* **RED.process**: the Node.js process variable
* ```RED.process.exit()``` will exit the current node-red server, used in conjunction of forever can restart Node-RED 'programatically'
