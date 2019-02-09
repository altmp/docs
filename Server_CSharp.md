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

<hr/>

### Methods

#### GetData

```csharp
bool GetData(string key, out T result)
```



##### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| key            | `string`    |             |
| result         | **out** `T` |             |

##### Return

**Type**: `bool`

**Description**: -

<hr/>

#### GetMetaData

```csharp
MValue GetMetaData(string key)
```



##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |

##### Return

**Type**: `MValue`

**Description**:

<hr/>

#### Remove

##### Parameters

None

##### Return

**Type**: `bool`

**Description**:

<hr/>

#### SetData

```csharp
void SetData(string key, object value)
```



##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |
| value          | `object` |             |

##### Return

None

<hr/>

#### SetMetaData

```csharp
void SetMetaData(string key, MValue value)
```



##### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | string   |             |
| value          | `MValue` |             |

##### Return

None

<hr/>

#### SetPosition

```csharp
void SetPosition(float x, float y, float z)
```



##### Parameters

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| x              | `float` |             |
| y              | `float` |             |
| z              | `float` |             |



##### Return

None

<hr/>

#### SetRotation

```csharp
void SetRotation(float roll, float pitch, float yaw)
```



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

