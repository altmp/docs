### playerLeftVehicle

**Description**: This event is called when a player leaves a vehicle.

```javascript
alt.on('playerLeftVehicle', (player, vehicle, seat) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| player        | `Player` |             |
| vehicle        | `Vehicle` |             |
| seat        | `number` |             |

#### Return

**Type**: `void`

#### Example Usage

```javascript
alt.on('playerLeftVehicle', (player, vehicle, seat) => {
  alt.log(`${player.name} has left vehicle ${vehicle.id} from seat ${seat}`);
});
```