## Vehicle

### Properties

| Property Name       | Type         | Access      | Description |
| ------------------- | ------------ | ----------- | ----------- |
| Position            | `Position`   | get, set    |             |
| Rotation            | `Rotation`   | get, set    |             |
| Type                | `EntityType` | get         |             |
| Dimension           | `short`     | get, set    |             |
| Exists              | `bool`       | get         |             |
| Id                  | `ushort`     | get         |             |
| BodyHealth          | `uint`       | get, set    |             |
| BodyAdditionalHealth | `uint`      | get, set    |             |
| HealthData          | `string`     | get, set    |             |
| DamageData          | `string`     | get, set    |             |
| EngineHealth        | `int`        | get, set    |             |
| PetrolTankHealth    | `int`        | get, set    |             |
| Model               | `uint`       | get         |             |
| EngineOn            | `bool`       | get         |             |
| ManualEngineControl | `bool`       | get, set    |             |
| LockState           | `VehicleLockState` | get, set |          |
| IsHandbrakeActive   | `bool`       | get, set    |             |
| RadioStation        | `uint`       | get, set    |             |
| SirenActive         | `bool`       | get, set    |             |
| CustomTires         | `bool`       | get, set    |             |
| DashboardColor      | `byte`       | get, set    |             |
| HeadlightColor      | `byte`       | get, set    |             |
| DirtLevel           | `byte`       | get, set    |             |
| Driver              | `IPlayer`    | get         |             |
| InteriorColor       | `byte`       | get, set    |             |
| IsPrimaryColorRgb   | `bool`       | get         |             |
| IsSecondaryColorRgb | `bool`       | get         |             |
| ModKit              | `byte`       | get, set    |             |
| ModKitsCount        | `byte`       | get         |             |
| NeonColor           | `Rgba`       | get, set    |             |
| IsNeonActive        | `bool`       | get         |             |
| NumberPlateIndex    | `uint`       | get, set    |             |
| NumberPlateText     | `string`     | get, set    |             |
| PearlColor          | `byte`       | get, set    |             |
| PrimaryColor        | `byte`       | get, set    |             |
| PrimaryColorRgb     | `Rgba`       | get, set    |             |
| SecondaryColor      | `byte`       | get, set    |             |
| SecondaryColorRgb   | `Rgba`       | get, set    |             |
| SpecialDarkness     | `byte`       | get, set    |             |
| IsTireSmokeColorCustom | `bool`    | get         |             |
| TireSmokeColor      | `Rgba`       | get, set    |             |
| WheelColor          | `byte`       | get, set    |             |
| WheelType           | `byte`       | get         |             |
| WheelVariation      | `byte`       | get         |             |
| WheelsCount         | `byte`       | get         |             |
| WindowTint          | `byte`       | get, set    |             |
| HasArmoredWindows   | `bool`       | get         |             |
| RepairsCount        | `byte`       | get         |             |
| IsDaylightOn        | `bool`       | get         |             |
| IsNightlightOn      | `bool`       | get         |             |
| RoofOpened          | `bool`       | get         |             |
| IsFlamethrowerActive | `bool`      | get         |             |
| State               | `string`     | get, set    |             |
| AppearanceData      | `string`     | get, set    |             |
| ScriptData          | `string`     | get, set    |             |
| NativePointer       | `IntPtr`     | get         |             |

## Methods

### GetId

```csharp
static ushort GetId(IntPtr vehiclePointer)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| vehiclePointer | `IntPtr` |           |

#### Return

**Type**: `ushort`

**Description**: -

### GetMod

```csharp
byte GetMod(byte category)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| category       | `byte` |             |

#### Return

**Type**: `byte`

**Description**: -



### GetModKitsCount

```csharp
byte GetModKitsCount()
```

#### Parameters

None

#### Return

**Type**: `byte`

**Description**: -



### GetModsCount

```csharp
byte GetModsCount(byte category)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| category       | `byte` |             |

#### Return

**Type**: `byte`

**Description**: -



### GetNeonActive

```csharp
void GetNeonActive(ref bool left, ref bool right, ref bool top, ref bool back)
```

#### Parameters

None

#### Return

| Variable Name | Type   | Description |
| ------------- | ------ | ----------- |
| left          | `bool` |             |
| right         | `bool` |             |
| top           | `bool` |             |
| back          | `bool` |             |



### IsExtraOn

```csharp
bool IsExtraOn(byte extraId)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| extraId        | `byte` |             |

#### Return

**Type**: `bool`

**Description**: -



### SetMod

```csharp
bool SetMod(byte category, byte id)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| category       | `byte` |             |
| id             | `byte` |             |

#### Return

**Type**: `byte`

**Description**: -



### SetNeonActive

```csharp
void SetNeonActive(bool left, bool right, bool top, bool back)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| left           | `bool` |             |
| right          | `bool` |             |
| top            | `bool` |             |
| back           | `bool` |             |

#### Return

None



### SetWheels

```csharp
void SetWheels(byte type, byte variation)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| type           | `byte` |             |
| variation      | `byte` |             |

#### Return

None



### ToggleExtra

```csharp
void ToggleExtra(byte extraId, bool state)
```

#### Parameters

| Parameter Name | Type   | Description |
| -------------- | ------ | ----------- |
| extraId        | `byte` |             |
| state          | `bool` |             |

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


### GetDoorState

```csharp
byte GetDoorState(byte doorId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| doorId         | `byte` 	   |             |

#### Return

**Type**: `byte`

**Description**:


### SetDoorState

```csharp
void SetDoorState(byte doorId, byte state)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| doorId         | `byte`	   |             |
| state	         | `byte`	   |             |

#### Return

None


### IsWindowOpened

```csharp
bool IsWindowOpened(byte windowId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId       | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| doorId         | `byte`	   |             |
| state	         | `byte`	   |             |

#### Return

None


### SetWindowOpened

```csharp
void SetWindowOpened(byte windowId, bool state)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId       | `byte`  	   |             |
| state       	 | `bool`  	   |             |

#### Return

None


### IsWheelBurst

```csharp
bool IsWheelBurst(byte wheelId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:


### SetWheelBurst

```csharp
void SetWheelBurst(byte wheelId, bool state)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |
| state    	     | `bool`  	   |             |

#### Return

None


### DoesWheelHasTire

```csharp
bool DoesWheelHasTire(byte wheelId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:



### SetWheelHasTire

```csharp
void SetWheelHasTire(byte wheelId, bool state)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |
| state    	     | `bool`  	   |             |

#### Return

None


### GetWheelHealth

```csharp
float GetWheelHealth(byte wheelId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |

#### Return

**Type**: `float`

**Description**:


### SetWheelHealth

```csharp
void SetWheelHealth(byte wheelId, float health)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| wheelId        | `byte`  	   |             |
| health       	 | `float` 	   |             |

#### Return

None


### GetPartDamageLevel

```csharp
byte GetPartDamageLevel(byte partId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| partId         | `byte`  	   |             |

#### Return

**Type**: `byte`

**Description**:


### SetPartDamageLevel

```csharp
void SetPartDamageLevel(byte partId, byte damage)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| partId         | `byte`  	   |             |
| damage         | `byte`  	   |             |

#### Return

None


### GetPartBulletHoles

```csharp
byte GetPartBulletHoles(byte partId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| partId         | `byte`  	   |             |

#### Return

**Type**: `byte`

**Description**:


### SetPartBulletHoles

```csharp
void SetPartBulletHoles(byte partId, byte shootsCount)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| partId         | `byte`  	   |             |
| shootsCount    | `byte`  	   |             |

#### Return

None


### IsLightDamaged

```csharp
bool IsLightDamaged(byte lightId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| lightId        | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:



### SetLightDamaged

```csharp
void SetLightDamaged(byte lightId, bool isDamaged)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| lightId        | `byte`  	   |             |
| isDamaged      | `bool`  	   |             |

#### Return

None



### IsWindowDamaged

```csharp
bool IsWindowDamaged(byte windowId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId       | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:



### SetWindowDamaged

```csharp
void SetWindowDamaged(byte windowId, bool isDamaged)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId       | `byte`  	   |             |
| isDamaged      | `bool`  	   |             |

#### Return

None


### IsSpecialLightDamaged

```csharp
bool IsSpecialLightDamaged(byte specialLightId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| specialLightId | `byte`  	   |             |

#### Return

**Type**: `bool`

**Description**:


### SetSpecialLightDamaged

```csharp
void SetSpecialLightDamaged(byte specialLightId, bool isDamaged)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| specialLightId | `byte`  	   |             |
| isDamaged 	 | `bool`  	   |             |

#### Return

None


### GetArmoredWindowHealth

```csharp
float GetArmoredWindowHealth(byte windowId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId		 | `byte`  	   |             |

#### Return

**Type**: `float`

**Description**:


### SetArmoredWindowHealth

```csharp
void SetArmoredWindowHealth(byte windowId, float health)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId		 | `byte`  	   |             |
| health		 | `float`     |             |

#### Return

None


### GetArmoredWindowShootCount

```csharp
byte GetArmoredWindowShootCount(byte windowId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId		 | `byte`  	   |             |

#### Return

**Type**: `byte`

**Description**:


### SetArmoredWindowShootCount

```csharp
void SetArmoredWindowShootCount(byte windowId, byte count)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| windowId		 | `byte`  	   |             |
| count			 | `byte`  	   |             |

#### Return

None




### GetBumperDamageLevel

```csharp
byte GetBumperDamageLevel(byte bumperId)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| bumperId		 | `byte`  	   |             |

#### Return

**Type**: `byte`

**Description**:


### SetBumperDamageLevel

```csharp
void SetBumperDamageLevel(byte bumperId, byte damageLevel)
```



#### Parameters

| Parameter Name | Type        | Description |
| -------------- | ----------- | ----------- |
| bumperId		 | `byte`  	   |             |
| damageLevel	 | `byte`  	   |             |

#### Return

None
