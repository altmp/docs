### entityRemove

**Description**: This event is called when an entity gets removed from the server.

```javascript
alt.on('entityRemove', (entity) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| entity        | `Entity` |             |

#### Return

**Type**: `void`


#### Example Usage

```javascript
alt.on('entityRemove', (entity) => {
  alt.log(`server removed entity ${entity.id}`);
});
```
