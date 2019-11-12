## Clientside Events
---

### keyup
Called when a key is released.
```js
alt.on('keyup', (key) => {
    if (key == 'E'.charCodeAt(0)) {
        alt.log('You let go of E!');
    }
});
```

### keydown
Called when a key is pressed down.
```js
alt.on('keydown', (key) => {
    if (key == 'E'.charCodeAt(0)) {
        alt.log('You pressed E!');
    }
});
```

### connectionComplete
Called when a local connection is completed.
```js
alt.on('connectionComplete', (hasMapChanged) => {
    alt.log('You just connected!');

    if(hasMapChanged) {
        alt.log('The map has changed!');
    }
});
```

### disconnect
Called when the client disconnects.
```js
alt.on('disconnect', () => {
    alt.log('You disconnected.');
});
```

### consoleCommand
Called when you type something into the F8 console menu.
```js
alt.on('consoleCommand', (msg) => {
    alt.log(`You Typed: ${msg}`);
});
```

### gameEntityCreate
Called when a game entity is created.
```js
alt.on('gameEntityCreate', (entity) => {
    alt.log(`${entity.model} was created.`);
});
```

### gameEntityDestroy
Called when a game entity is destroyed.
```js
alt.on('gameEntityDestroy', (entity) => {
    alt.log(`${entity.model} was destroyed.`);
});
```

### syncedMetaChange
When an entities meta values change; this gets called.
```js
alt.on('syncedMetaChange', (entity, key, value) => {

});
```
