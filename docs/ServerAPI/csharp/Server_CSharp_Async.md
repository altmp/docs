## C# - Events & Methods (Async)

### Events

### On (Custom Events)



#### Supported Argument Types

`null`, `bool`, `int`, `uint,` `long`, `ulong`, `double`, `string`, `object`

All types above as an array, eg. `int []` or `string[]`



Furthermore Dictionaries with `string`-Type as Key, eg. `Dictionary<string, object>`

But also all interfaces of the API or extend these, eg. `IEntity`, `IVehicle`, `IBlip`, `ICheckpoint`, ...



#### Examples

```csharp
AltAsync.On("test", async args => { await Task.Delay(1000); AltAsync.Log("args=" + args[0]); });

Alt.Emit("test", "bla");
```



```csharp
AltAsync.On<string>("test", async str => { await Task.Delay(1000); AltAsync.Log("str=" + str); });

Alt.Emit("test", "bla");
```



```csharp
AltAsync.On("test", async delegate(string str){ await Task.Delay(1000); AltAsync.Log("str=" + str); });

Alt.Emit("test", "bla");
```



```csharp
AltAsync.On<string>("test", bla);
void bla(string str) {
    AltAsync.Log("str=" + str);
}
Alt.Emit("test", "bla");
```



##### Advanced Example

The first Generics (in our example below `int` and `string`) are the Types for the parameters, the last generic (`bool`) is the return-type.

**Note**: Return types are optional at events

```csharp
AltAsync.On<int, string, bool>("test", (number, str) => {
    AltAsync.Log("str=" + str + " - " + number);
	return true;
});
```





[View more Examples](docs/ServerAPI/csharp/Event_Examples_Async?id=complete-example)


### OnPlayerEvent

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=complete-example)

| Parameter Name | Type          | Description                         |
| -------------- | ------------- | ----------------------------------- |
| player	 	 | `IPlayer`     |								       |
| eventName      | `string`      |                                     |
| args           | `object[]`    |                                     |



### OnCheckpoint

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=oncheckpoint)

| Parameter Name | Type          | Description                         |
| -------------- | ------------- | ----------------------------------- |
| checkpoint     | `ICheckpoint` |                                     |
| entity         | `IEntity`     |                                     |
| state          | `bool`        | `true` = Enters<br />`false` = Exit |



### OnEntityRemove

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onentityremove)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| entity         | `IEntity` |             |



### OnPlayerConnect

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onplayerconnect)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnPlayerDamage

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onplayerdamage)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| attacker       | `IEntity` |             |
| weapon         | `uint`    |             |
| damage         | `byte`    |             |



### OnPlayerDead

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onplayerdead)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| killer         | `IEntity` |             |
| weapon         | `uint`    |             |



### OnPlayerDisconnect

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onplayerdisconnect)

| Parameter Name | Type      | Description |
| -------------- | --------- | ----------- |
| player         | `IPlayer` |             |
| reason         | `string`  |             |



### OnVehicleChangeSeat

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onvehiclechangeseat)

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| oldSeat        | `sbyte`    |             |
| newSeat        | `sbyte`    |             |



### OnVehicleEnter

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onvehicleenter)

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| seat           | `sbyte`    |             |



### OnVehicleLeave

[View Example](docs/ServerAPI/csharp/Event_Examples_Async?id=onvehicleleave)

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| vehicle        | `IVehicle` |             |
| player         | `IPlayer`  |             |
| seat           | `sbyte`    |             |

## Methods

### CreateBlip

```csharp
Task<IBlip> AltAsync.CreateBlip(IPlayer player, byte type, IEntity entityAttach)
Task<IBlip> AltAsync.CreateBlip(IPlayer player, byte type, Position pos)
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| player         | `IPlayer`  |             |
| type           | `byte`     |             |
| entityAttach   | `byte`     |             |
| pos            | `Position` |             |

#### Return

**Type**: `Task<IBlip>`

**Description**: -



### CreateCheckpoint

```csharp
Task<ICheckpoint> AltAsync.CreateCheckpoint(IPlayer player, byte type, Position pos, float radius, float height, Rgba color)
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

**Type**: `Task<ICheckpoint>`

**Description**: -



### CreateVehicle

```csharp
Task<IVehicle> AltAsync.CreateVehicle(VehicleHash vehicleHash, Position pos, float heading)
Task<IVehicle> AltAsync.CreateVehicle(uint model, Position pos, float heading)
```

#### Parameters

| Parameter Name | Type          | Description |
| -------------- | ------------- | ----------- |
| vehicleHash    | `VehicleHash` |             |
| pos            | `Position`    |             |
| heading        | `float`       |             |
| model          | `uint`        |             |

#### Return

**Type**: `Task<IVehicle>`

**Description**: -



### Do

```csharp
Task AltAsync.Do(system.Action action)
```

#### Parameters

| Parameter Name | Type                  | Description |
| -------------- | --------------------- | ----------- |
| action      	 | `system.Action`       |             |

#### Return

**Type**: `Task`

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


