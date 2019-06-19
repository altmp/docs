## Serverside Events
---

### consoleCommand
Called when the server owners types a message into the console.
```
alt.on('consoleCommand', (msg) => {
    alt.log(msg);
});
```

### entityEnterCheckpoint
Called when an entity enters a checkpoint.
```
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
```
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
```
alt.on('entityEnterColshape', (colshape, entity) => {
    if (entity.constructor.name == "Player")
        alt.log(`Player ${entity.name} enter Colshape`);
});
```

### entityLeaveColshape
Called when an entity leave a colshape.
```
alt.on('entityLeaveColshape', (colshape, entity) => {
    if (entity.constructor.name == "Player")
        alt.log(`Player ${entity.name} leave Colshape`);
});
```

### metaChange
Called when an entities meta value changes.
```
alt.on('metaChange', (entity, key, value) => {

});
```

### playerChangedVehicleSeat
Called when a player changes their vehicle seat.
```
alt.on('playerChangedVehicleSeat', (vehicle, player, oldseat, newseat) => {

});
```

### playerConnect
Called when a player connects to the server.
```
alt.on('playerConnect', (player) => {
	alt.log(`${player.name} has joined the server!`);
});
```

### playerDamage
Called when a player takes damage.
```
alt.on('playerDamage', (target, attacker, damage, weapon) => {
    alt.log(`${target.name} was attacked by ${attacker.name}`);
});
```

### playerDeath
Called when a player dies.
```
alt.on('playerDeath', (target, killer, weapon) => {
    alt.log(`${target.name} was killed by ${killer.name}`);
});
```

### playerDisconnect
Called when a player disconnects from the server.
```
alt.on('playerDisconnect', (player, reason) => {
    alt.log(`${player.name} has disconnected.`);
});
```

### playerEnteredVehicle
Called when a player enters a vehicle.
```
alt.on('playerEnteredVehicle', (vehicle, player, seat) => {

});
```

### playerLeftVehicle
Called when a player exits a vehicle.
```
alt.on('playerLeftVehicle', (vehicle, player, seat) => {
    
});
```

### removeEntity
Called when an entity is removed / deleted.
```
alt.on('removeEntity', (target) => {

});
```

### syncedMetaChange
Called when an entities synced meta value changes.
```
alt.on('syncedMetaChange', (entity, key, value) => {

});
```