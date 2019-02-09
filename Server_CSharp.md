# Server API

## Events

### On (Custom Events)

#### Examples

```csharp
Alt.On("test", args => { Alt.Log("args=" + args[0]); });
            
Alt.Emit("test", "bla");
```



```csharp
Alt.On<string>("test", str => { Alt.Log("str=" + str); });
            
Alt.Emit("test", "bla");
```



```csharp
Alt.On<string>("test", delegate(string str){ Alt.Log("str=" + str); });
            
Alt.Emit("test", "bla");
```



```csharp
Alt.On<string>("test", bla);
void bla(string str) {
    Alt.Log("str=" + str);
}
Alt.Emit("test", "bla");
```





### OnCheckpoint

| Parameter Name | Type          | Description                         |
| -------------- | ------------- | ----------------------------------- |
| checkpoint     | `ICheckpoint` |                                     |
| entity         | `IEntity`     |                                     |
| state          | `bool`        | `true` = Enters<br />`false` = Exit |



### OnEntityRemove

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| entity         | `IEntity` |             |



### OnPlayerConnect

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnPlayerDamage

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| attacker       | `IEntity` |             |
| weapon         | `uint`    |             |
| damage         | `byte`    |             |



### OnPlayerDead

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| killer         | `IEntity` |             |
| weapon         | `uint`    |             |



### OnPlayerDisconnect

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnVehicleChangeSeat

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| oldSeat        | `sbyte`    |             |
| newSeat        | `sbyte`    |             |



### OnVehicleEnter

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| seat           | `sbyte`    |             |



### OnVehicleLeave

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| seat           | `sbyte`    |             |




## Vehicle

## Player
