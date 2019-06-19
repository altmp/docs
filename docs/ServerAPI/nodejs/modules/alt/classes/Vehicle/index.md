# Class "Vehicle"

## Constructor

```js
new Vehicle(model: string, x: number, y: number, z: number, rx: number, ry: number, rz: number);
```

### Properties

| Property name | Type | Access | Inherited from | Description |
| -------------- | ----------- | -------- | -------- | ----------- |
| activeRadioStation | number | set, get |  |  |
| all | Array | get |  | Replace <span style="color:orange">alt.vehicles</span> since build 569 |
| bodyAdditionalHealth | number | set, get |  |  |
| bodyHealth | number | set, get |  |  |
| customPrimaryColor | object | set, get |  |  |
| customSecondaryColor | object | set, get |  |  |
| customTires | boolean | set, get |  |  |
| darkness | number | set, get |  |  |
| dashboardColor | number | set, get |  |  |
| daylightOn | boolean | get |  |  |
| dirtLevel | number | set, get |  |  |
| driver | Player | get |  |  |
| engineHealth | number | set, get |  |  |
| engineOn | boolean | set, get |  |  |
| flamethrowerActive | boolean | get |  |  |
| handbrakeActive | boolean | get |  |  |
| hasArmoredWindows | number | get |  |  |
| headlightColor | number | set, get |  |  |
| interiorColor | number | set, get |  |  |
| lockState | number | set, get |  |  |
| manualEngineControl | boolean | set, get |  |  |
| modKit | number | set, get |  |  |
| modKitsCount | number | get |  |  |
| neon | object | set, get |  |  |
| neonColor | object | set, get |  |  |
| nightlightOn | boolean | get |  |  |
| numberPlateIndex | number | set, get |  |  |
| numberPlateText | string | set, get |  |  |
| pearlColor | number | set, get |  |  |
| petrolTankHealth | number | set, get |  |  |
| primaryColor | number | set, get |  |  |
| repairsCount | number | get |  |  |
| roofOpened | boolean | set, get |  |  |
| secondaryColor | number | set, get |  |  |
| sirenActive | boolean | set, get |  |  |
| tireSmokeColor | object | set, get |  |  |
| wheelColor | number | set, get |  |  |
| wheelsCount | number | get |  |  |
| windowTint | number | set, get |  |  |
| id | number | get | Entity |  |
| model | number | set, get | Entity |  |
| rot | object | set, get | Entity |  |
| dimension | number | set, get | WorldObject |  |
| pos | Value | set, get | WorldObject |  |
| type | number | get | BaseObject |  |


## Methods

* [doesWheelHasTire](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_doesWheelHasTire.md)
```js
function doesWheelHasTire(wheelId: number);
```
* [getAppearanceDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getAppearanceDataBase64.md)
```js
function getAppearanceDataBase64();
```
* [getArmoredWindowHealth](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getArmoredWindowHealth.md)
```js
function getArmoredWindowHealth(windowId: number);
```
* [getArmoredWindowShootCount](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getArmoredWindowShootCount.md)
```js
function getArmoredWindowShootCount(windowId: number);
```
* [getBumperDamageLevel](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getBumperDamageLevel.md)
```js
function getBumperDamageLevel(part: number);
```
* [getDamageStatusBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getDamageStatusBase64.md)
```js
function getDamageStatusBase64();
```
* [getDoorState](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getDoorState.md)
```js
function getDoorState(doorId: number);
```
* [getGamestateDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getGamestateDataBase64.md)
```js
function getGamestateDataBase64();
```
* [getHealthDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getHealthDataBase64.md)
```js
function getHealthDataBase64();
```
* [getModsCount](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getModsCount.md)
```js
function getModsCount(category: number);
```
* [getPartBulletHoles](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getPartBulletHoles.md)
```js
function getPartBulletHoles(part: number);
```
* [getPartDamageLevel](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getPartDamageLevel.md)
```js
function getPartDamageLevel(part: number);
```
* [getScriptDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getScriptDataBase64.md)
```js
function getScriptDataBase64();
```
* [getWheelHealth](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_getWheelHealth.md)
```js
function getWheelHealth(wheelId: number);
```
* [isLightDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_isLightDamaged.md)
```js
function isLightDamaged(lightId: number);
```
* [isSpecialLightDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_isSpecialLightDamaged.md)
```js
function isSpecialLightDamaged(specialLightId: number);
```
* [isWheelBurst](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_isWheelBurst.md)
```js
function isWheelBurst(wheelId: number);
```
* [isWindowDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_isWindowDamaged.md)
```js
function isWindowDamaged(windowId: number);
```
* [isWindowOpened](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_isWindowOpened.md)
```js
function isWindowOpened(windowId: number);
```
* [setAppearanceDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setAppearanceDataBase64.md)
```js
function setAppearanceDataBase64(appearanceData: string);
```
* [setArmoredWindowHealth](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setArmoredWindowHealth.md)
```js
function setArmoredWindowHealth(p0: number, p1: number);
```
* [setArmoredWindowShootCount](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setArmoredWindowShootCount.md)
```js
function setArmoredWindowShootCount(p0: number, p1: number);
```
* [setBumperDamageLevel](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setBumperDamageLevel.md)
```js
function setBumperDamageLevel(p0: number, p1: number);
```
* [setDamageStatusBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setDamageStatusBase64.md)
```js
function setDamageStatusBase64(damageStatus: string);
```
* [setDoorState](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setDoorState.md)
```js
function setDoorState(p0: number, p1: number);
```
* [setExtra](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setExtra.md)
```js
function setExtra(category: number, state: boolean);
```
* [setGamestateDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setGamestateDataBase64.md)
```js
function setGamestateDataBase64(gamestateData: string);
```
* [setHealthDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setHealthDataBase64.md)
```js
function setHealthDataBase64(healthData: string);
```
* [setLightDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setLightDamaged.md)
```js
function setLightDamaged(p0: number, p1: boolean);
```
* [setMod](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setMod.md)
```js
function setMod(category: number, id: number);
```
* [setPartBulletHoles](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setPartBulletHoles.md)
```js
function setPartBulletHoles(p0: number, p1: number);
```
* [setPartDamageLevel](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setPartDamageLevel.md)
```js
function setPartDamageLevel(p0: number, p1: number);
```
* [setScriptDataBase64](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setScriptDataBase64.md)
```js
function setScriptDataBase64(scriptData: string);
```
* [setSpecialLightDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setSpecialLightDamaged.md)
```js
function setSpecialLightDamaged(p0: number, p1: boolean);
```
* [setWheelBurst](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWheelBurst.md)
```js
function setWheelBurst(p0: number, p1: boolean);
```
* [setWheelHasTire](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWheelHasTire.md)
```js
function setWheelHasTire(p0: number, p1: boolean);
```
* [setWheelHealth](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWheelHealth.md)
```js
function setWheelHealth(wheelId: number, health: number);
```
* [setWheels](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWheels.md)
```js
function setWheels(p0: number, p1: number);
```
* [setWindowDamaged](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWindowDamaged.md)
```js
function setWindowDamaged(p0: number, p1: boolean);
```
* [setWindowOpened](docs/ServerAPI/nodejs/modules/alt/classes/Vehicle/method_setWindowOpened.md)
```js
function setWindowOpened(p0: number, p1: boolean);
```
* [getSyncedMeta](docs/ServerAPI/nodejs/modules/alt/classes/Entity/method_getSyncedMeta.md)
```js
function getSyncedMeta(key: string);
```
* [setSyncedMeta](docs/ServerAPI/nodejs/modules/alt/classes/Entity/method_setSyncedMeta.md)
```js
function setSyncedMeta(key: string, p1: any);
```
* [destroy](docs/ServerAPI/nodejs/modules/alt/classes/BaseObject/method_destroy.md)
```js
function destroy();
```
* [getMeta](docs/ServerAPI/nodejs/modules/alt/classes/BaseObject/method_getMeta.md)
```js
function getMeta(key: string);
```
* [setMeta](docs/ServerAPI/nodejs/modules/alt/classes/BaseObject/method_setMeta.md)
```js
function setMeta(key: string, p1: any);
```


