### consoleCommand

**Description**: This event is called when you enter something in the server console.

```javascript
alt.on('consoleCommand', (input) => {

});
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| input        | `string` |             |

#### Return

**Type**: `void`


#### Example Usage

```javascript
alt.on('consoleCommand', (input) => {
  alt.log(`console: ${input}`);
});
```
