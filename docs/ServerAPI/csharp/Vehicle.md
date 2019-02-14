# Vehicle

## Properties

| Property Name       | Type         | Description |
| ------------------- | ------------ | ----------- |
| CustomTires         | `bool`       |             |
| DashboardColor      | `byte`       |             |
| DirtLevel           | `byte`       |             |
| Driver              | `IPlayer`    |             |
| InteriorColor       | `byte`       |             |
| IsPrimaryColorRgb   | `bool`       |             |
| IsSecondaryColorRgb | `bool`       |             |
| ModKit              | `byte`       |             |
| NeonColor           | `Rgba`       |             |
| NumberPlateIndex    | `uint`       |             |
| NumberPlateText     | `string`     |             |
| PearlColor          | `byte`       |             |
| PrimaryColor        | `byte`       |             |
| PrimaryColorRgb     | `Rgba`       |             |
| SecondaryColor      | `byte`       |             |
| SecondaryColorRgb   | `Rgba`       |             |
| SpecialDarkness     | `byte`       |             |
| TireSmokeColor      | `Rgba`       |             |
| WheelColor          | `byte`       |             |
| WheelType           | `byte`       |             |
| WheelVariation      | `byte`       |             |
| WindowTint          | `byte`       |             |
| Type                | `EntityType` |             |
| Dimension           | `ushort`     |             |
| Exists              | `bool`       |             |
| Id                  | `ushort`     |             |
| NativePointer       | `IntPtr`     |             |
| Position            | `Position`   |             |
| Rotation            | `Rotation`   |             |

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

