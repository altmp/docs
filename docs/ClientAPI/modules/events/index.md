## Clientside Events
---

### keyup
Called when a key is released.
```
alt.on('keyup', (key) => {
    if (key == 'E'.charCodeAt(0)) {
        alt.log('You let go of E!');
    }
});
```

### keydown
Called when a key is pressed down.
```
alt.on('keydown', (key) => {
    if (key == 'E'.charCodeAt(0)) {
        alt.log('You pressed E!');
    }
});
```

### connectionComplete
Called when a local connection is completed.
```
alt.on('connectionComplete', (hasMapChanged) => {
    alt.log('You just connected!');

    if(hasMapChanged) {
        alt.log('The map has changed!');
    }
});
```

### disconnect
Called when the client disconnects.
```
alt.on('disconnect', () => {
    alt.log('You disconnected.');
});
```

### consoleCommand
Called when you type something into the F8 console menu.
```
alt.on('consoleCommand', (msg) => {
    alt.log(`You Typed: ${msg}`);
});
```

### gameEntityCreate
Called when a game entity is created.
```
alt.on('gameEntityCreate', (entity) => {
    alt.log(`${entity.model} was created.`);
});
```

### gameEntityDestroy
Called when a game entity is destroyed.
```
alt.on('gameEntityDestroy', (entity) => {
    alt.log(`${entity.model} was destroyed.`);
});
```

### syncedMetaChange
When an entities meta values change; this gets called.
```
alt.on('syncedMetaChange', (entity, key, value) => {

});
```