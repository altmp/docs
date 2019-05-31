### playerDamage

**Description**: This event is called when a player gets damaged.

```javascript
alt.on('playerDamage', (player, attacker, damage, weapon) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| player        | `Player` |             |
| attacker        | `Player` |             |
| damage        | `number` |             |
| weapon        | `hash` |     weapon hash e.g. 'WEAPON_BAT'        |

#### Return

**Type**: `void`

#### Notes

**•** Apparently the damage parameter outputs wrong values, an issue (and a workaround solution) has been opened and can be found here: https://github.com/altmp/altv/issues/51


#### Example Usage

```javascript
alt.on('playerDamage', (player, attacker, damage, weapon) => {
  alt.log(`${attacker.name} has damaged ${player.name} for ${damage} with a ${weapon}`);
});
```
