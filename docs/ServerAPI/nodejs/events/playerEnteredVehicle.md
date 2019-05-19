### playerEnteredVehicle

**Description**: This event is called when a player enters a vehicle.

```javascript
alt.on('playerEnteredVehicle', (player, vehicle, seat) => {

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
alt.on('playerEnteredVehicle', (player, vehicle, seat) => {
  alt.log(`${player.name} has entered vehicle ${vehicle.id} in seat ${seat}`);
});
```