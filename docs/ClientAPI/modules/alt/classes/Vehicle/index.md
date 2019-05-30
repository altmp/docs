# Class "Vehicle"

`WARNING!` This class is abstract! Object can't be created!

### Properties

| Property name | Type | Access | Inherited from | Description |
| -------------- | ----------- | -------- | -------- | ----------- |
| gear | number | get |  |  |
| rpm | number | get |  |  |
| scriptID | number | get |  |  |
| speed | number | get |  |  |
| id | number | get | Entity |  |
| model | number | get | Entity |  |
| rot | object | get | Entity |  |
| dimension | number | get | WorldObject |  |
| pos | object | get | WorldObject |  |
| type | number | get | BaseObject |  |


## Methods

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


