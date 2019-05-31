### playerChangedVehicleSeat

**Description**: This event is called when a player changes seat in a vehicle.

```javascript
alt.on('playerChangedVehicleSeat', (player, vehicle, oldseat, newseat) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| player        | `Player` |             |
| vehicle        | `Vehicle` |             |
| oldseat        | `number` |             |
| newseat        | `number` |             |

#### Return

**Type**: `void`

#### Notes

**•** This event will only get called if you switch seat whilst in a vehicle, it will not get called if you enter the drivers seat directly.


#### Example Usage

```javascript
alt.on('playerChangedVehicleSeat', (player, vehicle, oldseat, newseat) => {
  alt.log(`${player.name} has changed seat from ${oldseat} to ${newseat} in vehicle ${vehicle.id}`);
});
```