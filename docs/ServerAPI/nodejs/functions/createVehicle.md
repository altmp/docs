## createVehicle

**Description**: Creates a new vehicle entity

```javascript
alt.createVehicle(model, posX, posY, posZ, heading)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| model        | `number` or `string` |     [Vehicle Models](docs/Resources/Vehicles/Models.md)          |
| posX        | `number` |             |
| posY        | `number` |             |
| posZ        | `number` |             |
| heading      | `number` |    -180 to 180         |

#### Return

**Type**: `Vehicle`


#### Example Usage

```javascript
 alt.createVehicle("faction", 414.20746, -972.52386, 29.44237, 0);
```
