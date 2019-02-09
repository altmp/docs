# C# - Server API

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
Alt.On("test", delegate(string str){ Alt.Log("str=" + str); });
            
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



## Blip

### Properties

| Property Name | Type         | Description |
| ------------- | ------------ | ----------- |
| AttachedTo    | `IEntity`    |             |
| BlipType      | `byte`       |             |
| Color         | `byte`       |             |
| IsAttached    | `bool`       |             |
| IsGlobal      | `bool`       |             |
| Route         | `bool`       |             |
| RouteColor    | `byte`       |             |
| Sprite        | `ushort`     |             |
| Type          | `EntityType` |             |
| Dimension     | `ushort`     |             |
| Exists        | `bool`       |             |
| Id            | `ushort`     |             |
| NativePointer |              |             |
| Position      | `Position`   |             |
| Rotation      | `Rotation`   |             |



### Methods

#### GetData

##### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| key            | `string`    |             |
| result         | **out** `T` |             |

##### Return

**Type**: `bool`

**Description**: -



#### GetMetaData

##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |

##### Return

**Type**: `MValue`

**Description**:



#### Remove

##### Parameters

None

##### Return

**Type**: `bool`

**Description**:



#### SetData

##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |
| value          | `object` |             |

##### Return

None



#### SetMetaData

##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | string   |             |
| value          | `MValue` |             |

##### Return

None



#### SetPosition

##### Parameters

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| x              | `float` |             |
| y              | `float` |             |
| z              | `float` |             |



##### Return

None



#### SetRotation

##### Parameters

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| roll           | `float` |             |
| pitch          | `float` |             |
| yaw            | `float` |             |

##### Return

None



## Checkpoint



## Player



## Vehicle

