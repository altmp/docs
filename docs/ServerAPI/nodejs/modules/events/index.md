## Serverside Events
---

### playerConnect
Called when a player connects to the server.
```
alt.on('playerConnect', (player) => {
	alt.log(`${player.name} has joined the server!`);
});
```

### playerDisconnect
Called when a player disconnects from the server.
```
alt.on('playerDisconnect', (player, reason) => {
    alt.log(`${player.name} has disconnected.`);
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

### entityEnterCheckpoint
Called when a player enters a checkpoint.
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
Called when a player leaves a checkpoint.
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

### playerEnteredVehicle
Called when a player enters a vehicle.
```
alt.on('playerEnteredVehicle', (vehicle, player, seat) => {

});
```

### playerLeftVehicle
Called when a player enters a vehicle.
```
alt.on('playerLeftVehicle', (vehicle, player, seat) => {
    
});
```

### playerChangedVehicleSeat
Called when a player changes their vehicle seat.
```
alt.on('playerChangedVehicleSeat', (vehicle, player, oldseat, newseat) => {

});
```

### removeEntity
Called when an entity is removed / deleted.
```
alt.on('removeEntity', (target) => {

});
```

### consoleCommand
Called when the server owners types a message into the console.
```
alt.on('consoleCommand', (msg) => {
    alt.log(msg);
});
```

### syncedMetaChange
When an entities meta values change; this gets called.
```
alt.on('syncedMetaChange', (entity, key, value) => {

});
```

### metaChange
When an entities meta values change on the server.
```
alt.on('metaChange', (entity, key, value) => {

});
```