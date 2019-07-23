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
