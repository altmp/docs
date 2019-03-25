### playerConnect

**Description**: This event is called when a player connects to the server.

```javascript
alt.on('playerDead', (player) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| player        | `Player` |             |

#### Return

**Type**: `void`


#### Example Usage

```javascript
alt.on('playerConnect', (player) => {
  alt.log(`${player.name} connected`);
});
```
