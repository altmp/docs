## Serverside Events
---

### consoleCommand
Called when the server owners types a message into the console.
```js
alt.on('consoleCommand', (msg) => {
    alt.log(msg);
});
```

### entityEnterCheckpoint
Called when an entity enters a checkpoint.
```js
alt.on('entityEnterCheckpoint', (checkPoint, entity) => {
    if (entity.constructor.name === "Vehicle") {
        alt.log('A vehicle entered a checkpoint.');
    }

    if (entity.constructor.name === "Player") {
        alt.log('A player entered a checkpoint.');
    }
});
```

### entityLeaveCheckpoint
Called when an entity leaves a checkpoint.
```js
alt.on('entityLeaveCheckpoint', (checkPoint, entity) => {
    if (entity.constructor.name === "Vehicle") {
        alt.log('A vehicle left a checkpoint.');
    }

    if (entity.constructor.name === "Player") {
        alt.log('A player left a checkpoint.');
    }
});
```

### entityEnterColshape
Called when an entity enters a colshape.
```js
alt.on('entityEnterColshape', (colshape, entity) => {
    if (entity.constructor.name == "Player")
        alt.log(`Player ${entity.name} enter Colshape`);
});
```

### entityLeaveColshape
Called when an entity leave a colshape.
```js
alt.on('entityLeaveColshape', (colshape, entity) => {
    if (entity.constructor.name == "Player")
        alt.log(`Player ${entity.name} leave Colshape`);
});
```

### metaChange
Called when an entities meta value changes.
```js
alt.on('metaChange', (entity, key, value) => {

});
```

### playerChangedVehicleSeat
Called when a player changes their vehicle seat.
```js
alt.on('playerChangedVehicleSeat', (player, vehicle, oldseat, newseat) => {

});
```

### playerConnect
Called when a player connects to the server.
```js
alt.on('playerConnect', (player) => {
	alt.log(`${player.name} has joined the server!`);
});
```

### playerDamage
Called when a player takes damage.
```js
alt.on('playerDamage', (target, attacker, damage, weapon) => {
    alt.log(`${target.name} was attacked by ${attacker.name}`);
});
```

### playerDeath
Called when a player dies.
```js
alt.on('playerDeath', (target, killer, weapon) => {
    alt.log(`${target.name} was killed by ${killer.name}`);
});
```

### playerDisconnect
Called when a player disconnects from the server.
```js
alt.on('playerDisconnect', (player, reason) => {
    alt.log(`${player.name} has disconnected.`);
});
```

### playerEnteredVehicle
Called when a player enters a vehicle.
```js
alt.on('playerEnteredVehicle', (player, vehicle, seat) => {

});
```

### playerLeftVehicle
Called when a player exits a vehicle.
```js
alt.on('playerLeftVehicle', (player, vehicle, seat) => {
    
});
```

### removeEntity
Called when an entity is removed / deleted.
```js
alt.on('removeEntity', (target) => {

});
```

### syncedMetaChange
Called when an entities synced meta value changes.
```js
alt.on('syncedMetaChange', (entity, key, value) => {

});
```
