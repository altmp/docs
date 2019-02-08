# Interior

> GET_INTERIOR_GROUP_ID - 0xE4A84ABF135EF91A 0x09D6376F

int GET_INTERIOR_GROUP_ID(int interiorID)

```
Returns the group ID of the specified interior. For example, regular interiors have group 0, subway interiors have group 1. There are a few other groups too.
```

> GET_OFFSET_FROM_INTERIOR_IN_WORLD_COORDS - 0x9E3B3E6D66F6E22F 0x7D8F26A1

Vector3 GET_OFFSET_FROM_INTERIOR_IN_WORLD_COORDS(int interiorID, float x, float y, float z)



> IS_INTERIOR_SCENE - 0xBC72B5D7A1CBD54D 0x55226C13

BOOL IS_INTERIOR_SCENE()



> IS_VALID_INTERIOR - 0x26B0E73D7EAAF4D3 0x39C0B635

BOOL IS_VALID_INTERIOR(int interiorID)

```
Return if interior is valid.
```

> CLEAR_ROOM_FOR_ENTITY - 0xB365FC0C4E27FFA7 0x7DDADB92

void CLEAR_ROOM_FOR_ENTITY(Entity entity)



> FORCE_ROOM_FOR_ENTITY - 0x52923C4710DD9907 0x10BD4435

void FORCE_ROOM_FOR_ENTITY(Entity entity, int interiorID, Hash roomHashKey)

```
Does anyone know what this does? I know online modding isn't generally supported especially by the owner of this db, but I first thought this could be used to force ourselves into someones apartment, but I see now that isn't possible.
```

> GET_ROOM_KEY_FROM_ENTITY - 0x47C2A06D4F5F424B 0xE4ACF8C3

Hash GET_ROOM_KEY_FROM_ENTITY(Entity entity)

```
Gets the room hash key from the room that the specified entity is in. Each room in every interior has a unique key. Returns 0 if the entity is outside.
```

> GET_KEY_FOR_ENTITY_IN_ROOM - 0x399685DB942336BC 0x91EA80EF

Hash GET_KEY_FOR_ENTITY_IN_ROOM(Entity entity)

```
Seems to do the exact same as INTERIOR::GET_ROOM_KEY_FROM_ENTITY
```

> GET_INTERIOR_FROM_ENTITY - 0x2107BA504071A6BB 0x5C644614

int GET_INTERIOR_FROM_ENTITY(Entity entity)

```
Returns the handle of the interior that the entity is in. Returns 0 if outside.
```

> 0x82EBB79E258FA2B7 0xE645E162

void 0x82EBB79E258FA2B7(Entity entity, int interiorID)



> 0x920D853F3E17F1DA 0xD79803B5

void 0x920D853F3E17F1DA(int interiorID, Hash roomHashKey)



> 0xAF348AFCB575A441 0x1F6B4B13

void 0xAF348AFCB575A441(char* roomName)

```
Exemple of use(carmod_shop.c4)
 INTERIOR::_AF348AFCB575A441('V_CarModRoom');
```

> 0x405DC2AEF6AF95B9 0x0E9529CC

void 0x405DC2AEF6AF95B9(Hash roomHashKey)

```
Usage: INTERIOR::_0x405DC2AEF6AF95B9(INTERIOR::GET_KEY_FOR_ENTITY_IN_ROOM(PLAYER::PLAYER_PED_ID()));
```

> _GET_ROOM_KEY_FROM_GAMEPLAY_CAM - 0xA6575914D2A0B450 0x4FF3D3F5

Hash _GET_ROOM_KEY_FROM_GAMEPLAY_CAM()

```
Returns the room hash key from the current gameplay cam.
```

> 0x23B59D8912F94246 0x617DC75D

void 0x23B59D8912F94246()



> GET_INTERIOR_AT_COORDS - 0xB0F7F8663821D9C3 0xA17FBF37

int GET_INTERIOR_AT_COORDS(float x, float y, float z)

```
Returns interior ID from specified coordinates. If coordinates are outside, then it returns 0.

Example for VB.NET
Dim interiorID As Integer = Native.Function.Call(Of Integer)(Hash.GET_INTERIOR_AT_COORDS, X, Y, Z)
```

> ADD_PICKUP_TO_INTERIOR_ROOM_BY_NAME - 0x3F6167F351168730 0xA2A73564

void ADD_PICKUP_TO_INTERIOR_ROOM_BY_NAME(Pickup pickup, char* roomName)



> 0x2CA429C029CCF247 0x3ADA414E

void 0x2CA429C029CCF247(int interiorID)

```
Load interior
```

> UNPIN_INTERIOR - 0x261CCE7EED010641 0xFCFF792A

void UNPIN_INTERIOR(int interiorID)

```
Does something similar to INTERIOR::DISABLE_INTERIOR.

You don't fall through the floor but everything is invisible inside and looks the same as when INTERIOR::DISABLE_INTERIOR is used. Peds behaves normally inside. 
```

> IS_INTERIOR_READY - 0x6726BDCCC1932F0E 0xE1EF6450

BOOL IS_INTERIOR_READY(int interiorID)



> 0x4C2330E61D3DEB56 

Any 0x4C2330E61D3DEB56(int interiorID)

```
Only used once in the entire game scripts, probably useless. Always returns 0.
```

> GET_INTERIOR_AT_COORDS_WITH_TYPE - 0x05B7A89BD78797FC 0x96525B06

int GET_INTERIOR_AT_COORDS_WITH_TYPE(float x, float y, float z, char* interiorType)

```
Returns the interior ID representing the requested interior at that location (if found?). The supplied interior string is not the same as the one used to load the interior.

Use: INTERIOR::UNPIN_INTERIOR(INTERIOR::GET_INTERIOR_AT_COORDS_WITH_TYPE(x, y, z, interior))

Interior types include: 'V_Michael', 'V_Franklins', 'V_Franklinshouse', etc.. you can find them in the scripts.

Not a very useful native as you could just use GET_INTERIOR_AT_COORDS instead and get the same result, without even having to specify the interior type.
```

> _UNK_GET_INTERIOR_AT_COORDS - 0xF0F77ADB9F67E79D 

int _UNK_GET_INTERIOR_AT_COORDS(float x, float y, float z, int unk)

```
Returns the interior ID at the given coords, but only if the unknown variable is set to 0, otherwise it will return 0.
```

> _ARE_COORDS_COLLIDING_WITH_EXTERIOR - 0xEEA5AC2EDA7C33E8 0x7762249C

BOOL _ARE_COORDS_COLLIDING_WITH_EXTERIOR(float x, float y, float z)

```
Returns true if the coords are colliding with the outdoors, and false if they collide with an interior.
```

> GET_INTERIOR_FROM_COLLISION - 0xEC4CF9FCB29A4424 0x7ED33DC1

int GET_INTERIOR_FROM_COLLISION(float x, float y, float z)



> _ENABLE_INTERIOR_PROP - 0x55E86AF2712B36A1 0xC80A5DDF

void _ENABLE_INTERIOR_PROP(int interiorID, char* propName)

```
More info: http://gtaforums.com/topic/836367-adding-props-to-interiors/
```

> _DISABLE_INTERIOR_PROP - 0x420BD37289EEE162 0xDBA768A1

void _DISABLE_INTERIOR_PROP(int interiorID, char* propName)



> _IS_INTERIOR_PROP_ENABLED - 0x35F7DD45E8C0A16D 0x39A3CC6F

BOOL _IS_INTERIOR_PROP_ENABLED(int interiorID, char* propName)



> REFRESH_INTERIOR - 0x41F37C3427C75AE0 0x9A29ACE6

void REFRESH_INTERIOR(int interiorID)



> _HIDE_MAP_OBJECT_THIS_FRAME - 0xA97F257D0151A6AB 0x1F375B4C

void _HIDE_MAP_OBJECT_THIS_FRAME(Hash mapObjectHash)

```
This is the native that is used to hide the exterior of GTA Online apartment buildings when you are inside an apartment.

More info: http://gtaforums.com/topic/836301-hiding-gta-online-apartment-exteriors/
```

> DISABLE_INTERIOR - 0x6170941419D7D8EC 0x093ADEA5

void DISABLE_INTERIOR(int interiorID, BOOL toggle)

```
Example: 
This removes the interior from the strip club and when trying to walk inside the player just falls:

INTERIOR::DISABLE_INTERIOR(118018, true);
```

> IS_INTERIOR_DISABLED - 0xBC5115A5A939DD15 0x81F34C71

BOOL IS_INTERIOR_DISABLED(int interiorID)



> CAP_INTERIOR - 0xD9175F941610DB54 0x34E735A6

void CAP_INTERIOR(int interiorID, BOOL toggle)

```
Does something similar to INTERIOR::DISABLE_INTERIOR
```

> IS_INTERIOR_CAPPED - 0x92BAC8ACF88CEC26 0x18B17C80

BOOL IS_INTERIOR_CAPPED(int interiorID)



> 0x9E6542F0CE8E70A3 0x5EF9C5C2

void 0x9E6542F0CE8E70A3(BOOL toggle)

```
Only found 4 times in Rockstar scripts.
Clearly has something to do with Cutscenes.
```

