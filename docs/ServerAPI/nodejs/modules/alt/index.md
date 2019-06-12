# Module "alt"

## Classes

* [Player](docs/ServerAPI/nodejs/modules/alt/classes/Player/index.md)
* [Vehicle](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/index.md)
* [Blip](docs/ServerAPI/nodejs/modules/alt/classes/Blip/index.md)
* [Checkpoint](docs/ServerAPI/nodejs/modules/alt/classes/Checkpoint/index.md)
* [VoiceChannel](docs/ServerAPI/nodejs/modules/alt/classes/VoiceChannel/index.md)

## Properties

| Property name | Type | Access | Description |
| -------------- | ----------- | -------- | ----------- |
| currentResource | string | get |  |
| players | Array | get |  |
| rootDir | string | get |  |
| vehicles | Array | get |  |


## Methods

* [createBlipForCoords](docs/ServerAPI/nodejs/modules/alt/method_createBlipForCoords.md)
```js
function createBlipForCoords(type: number, x: number, y: number, z: number);
```
* [createCheckpoint](docs/ServerAPI/nodejs/modules/alt/method_createCheckpoint.md)
```js
function createCheckpoint(type: number, x: number, y: number, z: number, radius: number, height: number, r: number, g: number, b: number, a: number);
```
* [createVehicle](docs/ServerAPI/nodejs/modules/alt/method_createVehicle.md)
```js
var vehicle = new alt.Vehicle(model: string, posX: number, posY: number, posZ: number, roll: number, pitch: number, yaw: number);
```
* [createVoiceChannel](docs/ServerAPI/nodejs/modules/alt/method_createVoiceChannel.md)
```js
function createVoiceChannel(isSpatial: boolean, maxDistance: number);
```
* [emit](docs/ServerAPI/nodejs/modules/alt/method_emit.md)
```js
function emit(evName: string, args: any);
```
* [emitClient](docs/ServerAPI/nodejs/modules/alt/method_emitClient.md)
```js
function emitClient(v8Player: Object, evName: string, args: any);
```
* [getPlayersByName](docs/ServerAPI/nodejs/modules/alt/method_getPlayersByName.md)
```js
function getPlayersByName(name: string);
```
* [getResourceExports](docs/ServerAPI/nodejs/modules/alt/method_getResourceExports.md)
```js
function getResourceExports(name: string);
```
* [getResourceMain](docs/ServerAPI/nodejs/modules/alt/method_getResourceMain.md)
```js
function getResourceMain(name: string);
```
* [getResourcePath](docs/ServerAPI/nodejs/modules/alt/method_getResourcePath.md)
```js
function getResourcePath(name: string);
```
* [hasResource](docs/ServerAPI/nodejs/modules/alt/method_hasResource.md)
```js
function hasResource(name: string);
```
* [log](docs/ServerAPI/nodejs/modules/alt/method_log.md)
```js
function log(str: string);
```
* [logError](docs/ServerAPI/nodejs/modules/alt/method_logError.md)
```js
function logError(str: string);
```
* [logWarning](docs/ServerAPI/nodejs/modules/alt/method_logWarning.md)
```js
function logWarning(str: string);
```
* [on](docs/ServerAPI/nodejs/modules/alt/method_on.md)
```js
function on(evName: string, p1: Function);
```
* [onClient](docs/ServerAPI/nodejs/modules/alt/method_onClient.md)
```js
function onClient(evName: string, p1: Function);
```
* [removeEntity](docs/ServerAPI/nodejs/modules/alt/method_removeEntity.md)
```js
function removeEntity(_this: Object);
```
* [removeVoiceChannel](docs/ServerAPI/nodejs/modules/alt/method_removeVoiceChannel.md)
```js
function removeVoiceChannel(_this: Object);
```
* [resourceLoaded](docs/ServerAPI/nodejs/modules/alt/method_resourceLoaded.md)
```js
function resourceLoaded(name: string, p1: any);
```


