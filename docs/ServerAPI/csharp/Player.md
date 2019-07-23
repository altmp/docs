## Player

### Properties

| Property Name | Type         | Access		 | Description |
| ------------- | ------------ | ----------- | ----------- |
| Name          | `string`     | get         |             |
| Model         | `IVehicle`   | get, set    |             |
| Health        | `ushort`     | get, set    |             |
| MaxHealth     | `ushort`     | get, set    |             |
| Armor         | `ushort`     | get, set    |             |
| MaxArmor      | `ushort`     | get, set    |             |
| IsDead        | `bool`       | get         |             |
| SocialClubId  | `ulong`      | get         |             |
| HardwareIdHash | `ulong`     | get         |             |
| HardwareIdExHash | `ulong`   | get         |             |
| AuthToken     | `string`     | get         |             |
| IsConnected   | `bool`       | get         |             |
| Ping 		    | `uint`       | get         |             |
| Ip 		    | `string`     | get         |             |
| IsInVehicle   | `bool`       | get         |             |
| Vehicle       | `IVehicle`   | get         |             |
| Seat          | `byte`       | get         |             |
| AimPosition   | `Position`   | get         |             |
| Weapon        | `uint`       | get         |             |
| CurrentWeapon | `uint`       | get, set    |             |
| Ammo          | `ushort`     | get         |             |
| IsAiming      | `bool`       | get         |             |
| EntityAimingAt | `IEntity`   | get         |             |
| EntityAimOffset | `Position` | get         |             |
| IsInRagdoll   | `bool`       | get         |             |
| IsReloading   | `bool`       | get         |             |
| IsShooting    | `bool`       | get         |             |
| MoveSpeed     | `float`      | get         |             |
| IsJumping     | `bool`       | get         |             |
| IsFlashlightActive | `bool`  | get         |             |
| Type          | `EntityType` |             |             |
| Dimension     | `ushort`     |             |             |
| Exists        | `bool`       |             |             |
| Id            | `ushort`     |             |             |
| NativePointer | `IntPtr`     |             |             |
| Position      | `Position`   |             |             |
| Rotation      | `Rotation`   |             |             |
| HeadRotation  | `Rotation`   | get         |             |

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



### GiveWeapon

```csharp
void GiveWeapon(uint weapon, int ammo, bool selectWeapon);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weapon         | `uint`	  |             |
| ammo	         | `int`	  |             |
| selectWeapon   | `bool`	  |             |

#### Return

None


### RemoveWeapon

```csharp
void RemoveWeapon(uint weapon);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weapon         | `uint`	  |             |

#### Return

None


### RemoveAllWeapons

```csharp
void RemoveAllWeapons();
```

#### Parameters

None

#### Return

None


### AddWeaponComponent

```csharp
void AddWeaponComponent(uint weapon, uint weaponComponent);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weapon         | `uint`	  |             |
| weaponComponent | `uint`	  |             |

#### Return

None


### RemoveWeaponComponent

```csharp
void RemoveWeaponComponent(uint weapon, uint weaponComponent);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weapon         | `uint`	  |             |
| weaponComponent | `uint`	  |             |

#### Return

None


### GetCurrentWeaponComponents

```csharp
void GetCurrentWeaponComponents(out uint[] weaponComponents);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weaponComponents | **out** `uint[]` |     |

#### Return

None


### SetWeaponTintIndex

```csharp
void SetWeaponTintIndex(uint weapon, byte tintIndex);
```

#### Parameters

| Parameter Name | Type       | Description |
| -------------- | ---------- | ----------- |
| weapon         | `uint`	  |             |
| tintIndex		 | `byte`	  |             |

#### Return

None


### GetCurrentWeaponTintIndex

```csharp
byte GetCurrentWeaponTintIndex();
```

#### Parameters

None

#### Return

**Type**: `byte`

**Description**:



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
