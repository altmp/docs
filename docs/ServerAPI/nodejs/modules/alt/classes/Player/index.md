# Class "Player"

`WARNING!` This class is abstract! Object can't be created!

### Properties

| Property name | Type | Access | Inherited from | Description |
| -------------- | ----------- | -------- | -------- | ----------- |
| all | Array | get |  | Replace <span style="color:orange">alt.players</span> since build 569 |
| health | number | get |  |  |
| name | string | set, get |  |  |
| ping | number | get |  |  |
| seat | number | get |  |  |
| vehicle | Vehicle | get |  |  |
| id | number | get | Entity |  |
| model | number | set, get | Entity |  |
| rot | object | set, get | Entity |  |
| dimension | number | set, get | WorldObject |  |
| pos | Value | set, get | WorldObject |  |
| type | number | get | BaseObject |  |


## Methods

* [giveWeapon](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_giveWeapon.md)
```js
function giveWeapon(weaponHash: number, ammo: number, equipNow: boolean);
```
* [kick](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_kick.md)
```js
function kick();
```
* [removeAllWeapons](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_removeAllWeapons.md)
```js
function removeAllWeapons();
```
* [removeWeapon](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_removeWeapon.md)
```js
function removeWeapon(weaponHash: number);
```
* [setDateTime](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_setDateTime.md)
```js
function setDateTime(day: number, month: number, year: number, hour: number, minute: number, second: number);
```
* [setWeather](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_setWeather.md)
```js
function setWeather(weather: number);
```
* [spawn](docs/ServerAPI/nodejs/modules/alt/classes/Player/method_spawn.md)
```js
function spawn(x: number, y: number, z: number, delay: number);
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


