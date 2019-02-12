# C# - Server API

## Events

### On (Custom Events)



#### Supported Argument Types

`null`, `bool`, `int`, `uint,` `long`, `ulong`, `double`, `string`, `object`

All types above as an array, eg. `int []` or `string[]`



Furthermore Dictionaries with `string`-Type as Key, eg. `Dictionary<string, object>`

But also all interfaces of the API or extend these, eg. `IEntity`, `IVehicle`, `IBlip`, `ICheckpoint`, ...



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



##### Advanced Example

The first Generics (in our example below `int` and `string`) are the Types for the parameters, the last generic (`bool`) is the return-type.

**Note**: Return types are optional at events

```csharp
Alt.On<int, string, bool>("test", (number, str) => {
    Alt.Log("str=" + str + " - " + number);
	return true;
});
```





[View more Examples](csharp/Event_Examples?id=complete-example)



### OnCheckpoint

[View Example](csharp/Event_Examples?id=oncheckpoint)

| Parameter Name | Type          | Description                         |
| -------------- | ------------- | ----------------------------------- |
| checkpoint     | `ICheckpoint` |                                     |
| entity         | `IEntity`     |                                     |
| state          | `bool`        | `true` = Enters<br />`false` = Exit |



### OnEntityRemove

[View Example](csharp/Event_Examples?id=onentityremove)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| entity         | `IEntity` |             |



### OnPlayerConnect

[View Example](csharp/Event_Examples?id=onplayerconnect)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnPlayerDamage

[View Example](csharp/Event_Examples?id=onplayerdamage)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| attacker       | `IEntity` |             |
| weapon         | `uint`    |             |
| damage         | `byte`    |             |



### OnPlayerDead

[View Example](csharp/Event_Examples?id=onplayerdead)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| killer         | `IEntity` |             |
| weapon         | `uint`    |             |



### OnPlayerDisconnect

[View Example](csharp/Event_Examples?id=onplayerdisconnect)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnVehicleChangeSeat

[View Example](csharp/Event_Examples?id=onvehiclechangeseat)

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| oldSeat        | `sbyte`    |             |
| newSeat        | `sbyte`    |             |



### OnVehicleEnter

[View Example](csharp/Event_Examples?id=onvehicleenter)

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| seat           | `sbyte`    |             |



### OnVehicleLeave

[View Example](csharp/Event_Examples?id=onvehicleleave)

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
Dictionary<IntPtr,IBlip>.ValueCollection Alt.GetAllBlips()
```

#### Parameters

None

#### Return

**Type**: `Dictionary<IntPtr,IBlip>.ValueCollection`

**Description**: -



### GetAllCheckpoints

```csharp
Dictionary<IntPtr,ICheckpoint>.ValueCollection Alt.GetAllCheckpoints()
```

#### Parameters

None

#### Return

**Type**: `Dictionary<IntPtr,ICheckpoint>.ValueCollection`

**Description**: -



### GetAllPlayers

```csharp
Dictionary<IntPtr,IPlayer>.ValueCollection Alt.GetAllPlayers()
```

#### Parameters

None

#### Return

**Type**: `Dictionary<IntPtr,IPlayer>.ValueCollection`

**Description**: -



### GetAllVehicles

```csharp
Dictionary<IntPtr,IVehicle>.ValueCollection Alt.GetAllVehicles()
```

#### Parameters

None

#### Return

**Type**: `Dictionary<IntPtr,IVehicle>.ValueCollection`

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