About
=====
Interface to the Raspberry Pi Piface board using Node.js.  This addon shouldn't require any sudo or root privileges to run, as long as your user is in the "spi" group on your Pi.

Note: I've been playing a bit too much with the Pi, so these notes might be missing a few steps.

Installation
============

Get the Piface C libraries
--------------------------
First, you'll need the C libraries, available [here](https://github.com/thomasmacpherson/piface).  Follow the "C" library installation, naturally.

Get the NPM module
------------------
```bash
$ npm install piface-node
```

A note on running Node.js on the Raspberry Pi
---------------------------------------------
It's not quite as easy to install [Node.js](http://nodejs.org/) on a Raspberry Pi as it is on other platforms, so you might need to dig around to find the newest available version for the Pi's architecture.  At the time I write this, the latest available packaged build for Raspberry Pi is [v0.10.17](http://nodejs.org/dist/v0.10.17/node-v0.10.17-linux-arm-pi.tar.gz).  v0.10.17 is the only version I've tested this on, but if you have success on other versions, please let me know!

Using piface-node
=================
I've intended this to be used with the full awesome power of Node's EventEmitter.  You can easily wire up the physical I/O on the Piface with pretty much anything.

Here's a basic example of the usage, in lieu of actual documentation.  There are also a few examples in the examples folder.

```js
var pfio = require('piface-node');
pfio.init();
pfio.digital_write(0,1); // (pin, state)
var foo = pfio.digital_read(0); // (pin; returns state)
pfio.deinit();
```
