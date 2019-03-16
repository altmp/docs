[//]: # (version=c364ec0449bcdd47d6b810322697a31263ff60bb929455266ce7b076231b93d4)

```js
int setTimeout.setTimeout(function function, int delay)
```

Sets a timer which executes a function once the timer expires (MDN)

#### Parameters
| Parameter Name | Type | Description |
| -------------- | ----------- | ----------- |
| function | `function` | A function to be executed after the timer expires |
| delay | `int` | The time, in milliseconds, the timer should wait before the specified function is executed |#### Return

**Type**: `int`
**Description**: Positive integer value which identifies the timer created by the call to setTimeout this value can be passed to clearTimeout to cancel the timeout
