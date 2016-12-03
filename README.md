# xfunction
## Node Red xfunction: "An extended function node"
It is a clone of the core Node-Red function node ([see](https://github.com/node-red/node-red/blob/master/nodes/core/core/80-function.js)) with some relaxation of the sandbox script execution context

## Why do I need that?
Node-Red Nodes "function node" have quite a restrictive sandbox, I wanted to relax it a bit to benefit from Node-Red Editor while writing nodes and flows which could have more interaction with Node-Red global context.

For example, with this relaxation and using forever ([see](https://github.com/foreverjs/forever)), one can restart Node-Red programatically.[See](https://gist.github.com/gbrault/e87331911a79fdc7821c54f4991259d6) to learn how to start node-red from forever.

Another scenario is the capability to add routes to express in order to add some web ui resources to extend the existing dashboard framework or using some new framework.

Using nrcloudcmd ([see](https://github.com/gbrault/nrcloudcmd)) one can import, modify client html and scripts. We hence have a full web-based development tool build upon Node-Red corner stone tool.

Moreover,used in conjunction of the functionGlobalContext in the settings.js file, one can virtually access any resources on the target computer from an xfunction node. [See](https://nodered.org/docs/configuration) the last paragraph: Node Configuration to learn how to load some 'require' objects.

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
