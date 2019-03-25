### playerDisconnect

**Description**: This event is called when a player disconnect from the server.

```javascript
alt.on('playerDisconnect', (player) => {

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
alt.on('playerDisconnect', (player) => {
  alt.log(`${player.name} has disconnected`);
});
```
