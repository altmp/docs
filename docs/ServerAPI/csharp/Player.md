## Player

### Properties

| Property Name | Type         | Description |
| ------------- | ------------ | ----------- |
| Vehicle       | `IVehicle`   |             |
| AimPosition   | `Position`   |             |
| Ammo          | `ushort`     |             |
| Armor         | `ushort`     |             |
| HeadRotation  | `Rotation`   |             |
| Health        | `ushort`     |             |
| IsAiming      | `bool`       |             |
| IsConnected   | `bool`       |             |
| IsDead        | `bool`       |             |
| IsInRagdoll   | `bool`       |             |
| IsInVehicle   | `bool`       |             |
| IsJumping     | `bool`       |             |
| IsReloading   | `bool`       |             |
| IsShooting    | `bool`       |             |
| MoveSpeed     | `float`      |             |
| Name          | `string`     |             |
| Seat          | `byte`       |             |
| Weapon        | `uint`       |             |
| Type          | `EntityType` |             |
| Dimension     | `ushort`     |             |
| Exists        | `bool`       |             |
| Id            | `ushort`     |             |
| NativePointer | `IntPtr`     |             |
| Position      | `Position`   |             |
| Rotation      | `Rotation`   |             |

## Methods

### Copy

```csharp
ReadOnlyPlayer Copy()
```

#### Parameters

None

#### Return

**Type**: `ReadOnlyPlayer`

**Description**: -



### Despawn

```csharp
void Despawn()
```

#### Parameters

None

#### Return

None



### Emit

```csharp
void Emit(string eventName, params object[] args)
```

#### Parameters

| Parameter Name | Type                  | Description |
| -------------- | --------------------- | ----------- |
| eventName      | `string`              |             |
| args           | **params** `object[]` |             |

#### Return

None



### Kick

```csharp
void Kick(string reason)
```

#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| reason         | `string` |             |

#### Return

None



### SetDateTime

```csharp
void SetDateTime(int day, int month, int year, int hour, int minute, int second)
```

#### Parameters

| Parameter Name | Type  | Description |
| -------------- | ----- | ----------- |
| day            | `int` |             |
| month          | `int` |             |
| year           | `int` |             |
| hour           | `int` |             |
| minute         | `int` |             |
| second         | `int` |             |

#### Return

None



### SetWeather

```csharp
void SetWeather(uint weather)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| weather        | `uint` |             |

#### Return

None



### Spawn

```csharp
void Spawn(Positon position)
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| position       | `position` |             |

#### Return

None



### GetData

```csharp
bool GetData(string key, out T result)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| key            | `string`    |             |
| result         | **out** `T` |             |

#### Return

**Type**: `bool`

**Description**: -


### GetMetaData

```csharp
bool GetMetaData<T>(string key, out T result)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| key            | `string`    |             |
| result         | **out** `T` |             |

#### Return

**Type**: `bool`

**Description**:


### GetSyncedMetaData

```csharp
bool GetSyncedMetaData<T>(string key, out T result)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| key            | `string`    |             |
| result         | **out** `T` |             |

#### Return

**Type**: `bool`

**Description**:




### Remove

```csharp
bool Remove()
```



#### Parameters

None

#### Return

None


### SetData

```csharp
void SetData(string key, object value)
```



#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |
| value          | `object` |             |

#### Return

None


### SetMetaData

```csharp
void SetMetaData(string key, MValue value)
```



#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | string   |             |
| value          | `object` |             |

#### Return

None


### SetSyncedMetaData

```csharp
void SetSyncedMetaData(string key, object value)
```



#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | string   |             |
| value          | `object` |             |

#### Return

None


### SetPosition

```csharp
void SetPosition(float x, float y, float z)
```



#### Parameters

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| x              | `float` |             |
| y              | `float` |             |
| z              | `float` |             |



#### Return

None


### SetRotation

```csharp
void SetRotation(float roll, float pitch, float yaw)
```



#### Parameters

| Parameter Name | Type    | Description |
| -------------- | ------- | ----------- |
| roll           | `float` |             |
| pitch          | `float` |             |
| yaw            | `float` |             |

#### Return

None
