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
| NativePointer | `IntPtr`     |             |
| Position      | `Position`   |             |
| Rotation      | `Rotation`   |             |


## Methods

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
MValue GetMetaData(string key)
```



#### Parameters

| Parameter Name | Type     | Description |
| -------------- | -------- | ----------- |
| key            | `string` |             |

#### Return

**Type**: `MValue`

**Description**:



### Remove

```csharp
bool Remove()
```



#### Parameters

None

#### Return

**Type**: `bool`

**Description**:


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
| value          | `MValue` |             |

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
