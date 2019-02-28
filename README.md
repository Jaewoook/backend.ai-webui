# backend.ai-console

Backend.AI GUI console. Supports both app / web mode.

 * Administration mode
 * User mode

 Each mode is chosen with keypair.

## Features
 * Key management
    * Allocate resource limitation for keys
 * Session management
    * Set default resources for runs
 * Experiments
 * Virtual Folder management
    * Upload  / download files
 * Manager settings
 * Proxy mode to support various app environments (with Electron)

## Develop and Test

### Running polymer-based web UI

```
$ npm install -g polymer-cli
$ npm install
$ polymer serve --npm
```


### Running websocket with node.js

This is only needed with pure ES6 dev. environment / browser. With `Electron`, websocket proxy automatically starts.

```
$ cd src/wsproxy
$ npm install
$ node ./local_proxy.js
```

### Running stand-alone web service

Will be prepared soon.

## Build (Web)

Default setup will build `es6-unbundled` version.

```
$ polymer build
```

## Build (Electron App)

### Using makefile

Prerequistics : electron, electron-packager

```
$ make all (build win/mac/linux app)
```

### Manual run (using local Electron)

Hard way:
```
$ polymer build
$ cd build/unbundled
$ npm install --only=prod
$ cd ../..
$ npm start
```

OR,

Easy way:

```
$ make test
$ electron .
```


## Package

```
$ make clean
$ make all
$ make pack # To create an zip-packed files (works on macOS)
```

## Serve (Web)

```
$ make dep
$ make web
```
