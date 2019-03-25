### playerDead

**Description**: This event is called when a player dies.

```javascript
alt.on('playerDead', (player, killer, weapon) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| player        | `Player` |             |
| killer        | `Player` |             |
| weapon        | `hash` |     weapon hash e.g. 'WEAPON_BAT'        |

#### Return

**Type**: `void`


#### Example Usage

```javascript
alt.on('playerDead', (player, killer, weapon) => {
  alt.log(`${killer.name} has killed ${player.name}`);
});
```
