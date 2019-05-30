# Class "Player"

`WARNING!` This class is abstract! Object can't be created!

### Properties

| Property name | Type | Access | Inherited from | Description |
| -------------- | ----------- | -------- | -------- | ----------- |
| name | String | get |  |  |
| scriptID | Integer | get |  |  |
| vehicle | number | get |  |  |
| id | Integer | get | Entity |  |
| model | Integer | get | Entity |  |
| rot | number | get | Entity |  |
| dimension | Integer | get | WorldObject |  |
| pos | number | get | WorldObject |  |
| type | Integer | get | BaseObject |  |


## Methods

* [addWeaponComponent](docs/ClientAPI/modules/alt/classes/Player/method_addWeaponComponent.md)
```js
function addWeaponComponent(weaponHash: number, componentHash: number);
```
* [getCurrentWeapon](docs/ClientAPI/modules/alt/classes/Player/method_getCurrentWeapon.md)
```js
function getCurrentWeapon();
```
* [getWeaponTintIndex](docs/ClientAPI/modules/alt/classes/Player/method_getWeaponTintIndex.md)
```js
function getWeaponTintIndex(weaponHash: number);
```
* [giveWeapon](docs/ClientAPI/modules/alt/classes/Player/method_giveWeapon.md)
```js
function giveWeapon(weaponHash: number, ammoCount: number);
```
* [removeAllWeapons](docs/ClientAPI/modules/alt/classes/Player/method_removeAllWeapons.md)
```js
function removeAllWeapons();
```
* [removeWeapon](docs/ClientAPI/modules/alt/classes/Player/method_removeWeapon.md)
```js
function removeWeapon(weaponHash: number);
```
* [removeWeaponComponent](docs/ClientAPI/modules/alt/classes/Player/method_removeWeaponComponent.md)
```js
function removeWeaponComponent(weaponHash: number, componentHash: number);
```
* [setCurrentWeapon](docs/ClientAPI/modules/alt/classes/Player/method_setCurrentWeapon.md)
```js
function setCurrentWeapon(weaponHash: number);
```
* [setWeaponTintIndex](docs/ClientAPI/modules/alt/classes/Player/method_setWeaponTintIndex.md)
```js
function setWeaponTintIndex(weaponHash: number, tintIndex: number);
```
* [weaponHasComponent](docs/ClientAPI/modules/alt/classes/Player/method_weaponHasComponent.md)
```js
function weaponHasComponent(weaponHash: number, componentHash: number);
```
* [getSyncedMeta](docs/ClientAPI/modules/alt/classes/Entity/method_getSyncedMeta.md)
```js
function getSyncedMeta(key: string);
```
* [getMeta](docs/ClientAPI/modules/alt/classes/BaseObject/method_getMeta.md)
```js
function getMeta(key: string);
```
* [setMeta](docs/ClientAPI/modules/alt/classes/BaseObject/method_setMeta.md)
```js
function setMeta(key: string, p1: any);
```


