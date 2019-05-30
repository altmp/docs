# Class "Vehicle"

`WARNING!` This class is abstract! Object can't be created!

### Properties

| Property name | Type | Access | Inherited from | Description |
| -------------- | ----------- | -------- | -------- | ----------- |
| gear | Integer | get |  |  |
| rpm | Number | get |  |  |
| scriptID | Integer | get |  |  |
| speed | Number | get |  |  |
| id | Integer | get | Entity |  |
| model | Integer | get | Entity |  |
| rot | number | get | Entity |  |
| dimension | Integer | get | WorldObject |  |
| pos | number | get | WorldObject |  |
| type | Integer | get | BaseObject |  |


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


