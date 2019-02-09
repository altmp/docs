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

## Methods

### CreateBlip

```csharp
IBlip Alt.CreateBlip(IPlayer player, byte type, IEntity entityAttach)
IBlip Alt.CreateBlip(IPlayer player, byte type, Position pos)
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| player         | `IPlayer`  |             |
| type           | `byte`     |             |
| entityAttach   | `byte`     |             |
| pos            | `Position` |             |

#### Return

**Type**: `IBlip`

**Description**: -



### CreateCheckpoint

```csharp
ICheckpoint Alt.CreateCheckpoint(IPlayer player, byte type, Position pos, float radius, float height, Rgba color)
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| player         | `IPlayer`  |             |
| type           | `byte`     |             |
| pos            | `Position` |             |
| radius         | `float`    |             |
| height         | `float`    |             |
| color          | `Rgba`     |             |

#### Return

**Type**: `ICheckpoint`

**Description**: -



### CreateVehicle

```csharp
IVehicle Alt.CreateVehicle(VehicleHash vehicleHash, Position pos, float heading)
IVehicle Alt.CreateVehicle(uint model, Position pos, float heading)
```

#### Parameters

| Parameter Name | Type          | Description |
| -------------- | ------------- | ----------- |
| vehicleHash    | `VehicleHash` |             |
| pos            | `Position`    |             |
| heading        | `float`       |             |
| model          | `uint`        |             |

#### Return

**Type**: `IVehicle`

**Description**: -



### Emit

```csharp
void Alt.Emit(string eventName, params object[] args)
```

#### Parameters

| Parameter Name | Type                  | Description |
| -------------- | --------------------- | ----------- |
| eventName      | `string`              |             |
| args           | **params** `object[]` |             |

#### Return

None



### EmitAllClients

```csharp
void Alt.EmitAllClients(string eventName, params object[] args)
```

#### Parameters

| Parameter Name | Type                  | Description |
| -------------- | --------------------- | ----------- |
| eventName      | `string`              |             |
| args           | **params** `object[]` |             |

#### Return

None



### GetAllBlips

```csharp
ReadOnlyCollection<IBlip> Alt.GetAllBlips()
```

#### Parameters

None

#### Return

**Type**: `ReadonlyCollection<IBlip>`

**Description**: -



### GetAllCheckpoints

```csharp
RadOnlyCollection<ICheckpoint> Alt.GetAllCheckpoints()
```

#### Parameters

None

#### Return

**Type**: `ReadOnlyCollection<ICheckpoint>`

**Description**: -



### GetAllPlayers

```csharp
ReadOnlyCollection<IPlayer> Alt.GetAllPlayers()
```

#### Parameters

None

#### Return

**Type**: `ReadOnlyCollection<IPlayer>`

**Description**: -



### GetAllVehicles

```csharp
ReadOnlyCollection<IVehicle> Alt.GetAllVehicles()
```

#### Parameters

None

#### Return

**Type**: `ReadOnlyCollection<IVehicle>`

**Description**: -



### Log

```csharp
void Alt.Log(string message)
```

#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| message        | `string` |             |

#### Return

None



### RemoveEntity

```csharp
bool Alt.RemoveEntity(Entity entity)
```

#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| entity         | `Entity` |             |

#### Return

**Type**: `bool`

**Description**: -