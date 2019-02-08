# Rope

> ADD_ROPE - 0xE832D760399EB220 0xA592EC74

Object ADD_ROPE(float x, float y, float z, float rotX, float rotY, float rotZ, float length, int ropeType, float maxLength, float minLength, float p10, BOOL p11, BOOL p12, BOOL rigid, float p14, BOOL breakWhenShot, Any* unkPtr)

```
Creates a rope at the specific position, that extends in the specified direction when not attached to any entities.
__

Add_Rope(pos.x,pos.y,pos.z,0.0,0.0,0.0,20.0,4,20.0,1.0,0.0,false,false,false,5.0,false,NULL)

When attached, Position&lt;vector&gt; does not matter
When attached, Angle&lt;vector&gt; does not matter

Rope Type:
4 and bellow is a thick rope
5 and up are small metal wires
0 crashes the game

Max_length - Rope is forced to this length, generally best to keep this the same as your rope length.

Rigid - If max length is zero, and this is set to false the rope will become rigid (it will force a specific distance, what ever length is, between the objects).

breakable - Whether or not shooting the rope will break it.

unkPtr - unknown ptr, always 0 in orig scripts
__

Lengths can be calculated like so:

float distance = abs(x1 - x2) + abs(y1 - y2) + abs(z1 - z2); // Rope length


NOTES:

Rope does NOT interact with anything you attach it to, in some cases it make interact with the world AFTER it breaks (seems to occur if you set the type to -1).

Rope will sometimes contract and fall to the ground like you'd expect it to, but since it doesn't interact with the world the effect is just jaring.
```

> DELETE_ROPE - 0x52B4829281364649 0x748D72AF

void DELETE_ROPE(Object* rope)



> DELETE_CHILD_ROPE - 0xAA5D6B1888E4DB20 0xB19B4706

Any DELETE_CHILD_ROPE(Object rope)



> DOES_ROPE_EXIST - 0xFD5448BE3111ED96 0x66E4A3AC

BOOL DOES_ROPE_EXIST(Object* rope)

```
Ptr is correct
```

> ROPE_DRAW_SHADOW_ENABLED - 0xF159A63806BB5BA8 0x51523B8C

void ROPE_DRAW_SHADOW_ENABLED(Object* rope, BOOL toggle)



> LOAD_ROPE_DATA - 0xCBB203C04D1ABD27 0x9E8F1644

Any LOAD_ROPE_DATA(Object rope, char* rope_preset)

```
Rope presets can be found in the gamefiles. One example is 'ropeFamily3', it is NOT a hash but rather a string.
```

> PIN_ROPE_VERTEX - 0x2B320CF14146B69A 0xAE1D101B

void PIN_ROPE_VERTEX(Object rope, int vertex, float x, float y, float z)



> UNPIN_ROPE_VERTEX - 0x4B5AE2EEE4A8F180 0xB30B552F

Any UNPIN_ROPE_VERTEX(Object rope, int vertex)



> GET_ROPE_VERTEX_COUNT - 0x3655F544CD30F0B5 0x5131CD2C

int GET_ROPE_VERTEX_COUNT(Object rope)



> ATTACH_ENTITIES_TO_ROPE - 0x3D95EC8B6D940AC3 0x7508668F

void ATTACH_ENTITIES_TO_ROPE(Object rope, Entity ent1, Entity ent2, float ent1_x, float ent1_y, float ent1_z, float ent2_x, float ent2_y, float ent2_z, float length, BOOL p10, BOOL p11, Any* p12, Any* p13)

```
Attaches entity 1 to entity 2.
```

> ATTACH_ROPE_TO_ENTITY - 0x4B490A6832559A65 0xB25D9536

void ATTACH_ROPE_TO_ENTITY(Object rope, Entity entity, float x, float y, float z, BOOL p5)

```
The position supplied can be anywhere, and the entity should anchor relative to that point from it's origin.
```

> DETACH_ROPE_FROM_ENTITY - 0xBCF3026912A8647D 0x3E720BEE

void DETACH_ROPE_FROM_ENTITY(Object rope, Entity entity)



> ROPE_SET_UPDATE_PINVERTS - 0xC8D667EE52114ABA 0xEAF291A0

void ROPE_SET_UPDATE_PINVERTS(Object rope)



> 0xDC57A637A20006ED 0x80DB77A7

void 0xDC57A637A20006ED(Any p0, Any p1)



> 0x36CCB9BE67B970FD 0xC67D5CF6

void 0x36CCB9BE67B970FD(Any p0, BOOL p1)



> 0x84DE3B5FB3E666F0 0x7A18BB9C

BOOL 0x84DE3B5FB3E666F0(Any* p0)



> GET_ROPE_LAST_VERTEX_COORD - 0x21BB0FBD3E217C2D 0x91F6848B

Any GET_ROPE_LAST_VERTEX_COORD(Object rope)



> GET_ROPE_VERTEX_COORD - 0xEA61CA8E80F09E4D 0x84374452

Any GET_ROPE_VERTEX_COORD(Object rope, int vertex)



> START_ROPE_WINDING - 0x1461C72C889E343E 0x5187BED3

void START_ROPE_WINDING(Object rope)



> STOP_ROPE_WINDING - 0xCB2D4AB84A19AA7C 0x46826B53

void STOP_ROPE_WINDING(Object rope)



> START_ROPE_UNWINDING_FRONT - 0x538D1179EC1AA9A9 0xFC0DB4C3

void START_ROPE_UNWINDING_FRONT(Object rope)



> STOP_ROPE_UNWINDING_FRONT - 0xFFF3A50779EFBBB3 0x2EEDB18F

void STOP_ROPE_UNWINDING_FRONT(Object rope)



> ROPE_CONVERT_TO_SIMPLE - 0x5389D48EFA2F079A 0x43E92628

void ROPE_CONVERT_TO_SIMPLE(Object rope)



> ROPE_LOAD_TEXTURES - 0x9B9039DBF2D258C1 0xBA97CE91

Any ROPE_LOAD_TEXTURES()

```
Loads rope textures for all ropes in the current scene.
```

> ROPE_ARE_TEXTURES_LOADED - 0xF2D0E6A75CC05597 0x5FDC1047

BOOL ROPE_ARE_TEXTURES_LOADED()



> ROPE_UNLOAD_TEXTURES - 0x6CE36C35C1AC8163 0x584463E0

Any ROPE_UNLOAD_TEXTURES()

```
Unloads rope textures for all ropes in the current scene.
```

> 0x271C9D3ACA5D6409 

BOOL 0x271C9D3ACA5D6409(Object rope)



> 0xBC0CE682D4D05650 0x106BA127

void 0xBC0CE682D4D05650(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8, Any p9, Any p10, Any p11, Any p12, Any p13)

```
Most likely ROPE_ATTACH_*
```

> 0xB1B6216CA2E7B55E 0x7C6F7668

void 0xB1B6216CA2E7B55E(Any p0, BOOL p1, BOOL p2)



> 0xB743F735C03D7810 0x686672DD

void 0xB743F735C03D7810(Any p0, Any p1)



> _GET_ROPE_LENGTH - 0x73040398DFF9A4A6 0xFD309DC8

float _GET_ROPE_LENGTH(Object rope)

```
Get a rope's length.  Can be modified with ROPE_FORCE_LENGTH
```

> ROPE_FORCE_LENGTH - 0xD009F759A723DB1B 0xABF3130F

Any ROPE_FORCE_LENGTH(Object rope, float length)

```
Forces a rope to a certain length.
```

> ROPE_RESET_LENGTH - 0xC16DE94D9BEA14A0 0xC8A423A3

Any ROPE_RESET_LENGTH(Object rope, BOOL length)

```
Reset a rope to a certain length.
```

> APPLY_IMPULSE_TO_CLOTH - 0xE37F721824571784 0xA2A5C9FE

void APPLY_IMPULSE_TO_CLOTH(float posX, float posY, float posZ, float vecX, float vecY, float vecZ, float impulse)



> SET_DAMPING - 0xEEA3B200A6FEB65B 0xCFB37773

void SET_DAMPING(Object rope, int vertex, float value)



> ACTIVATE_PHYSICS - 0x710311ADF0E20730 0x031711B8

void ACTIVATE_PHYSICS(Entity entity)

```
seems to be frequently used with the NETWORK::NET_TO_x natives, particularly with vehicles. It is often the only ROPE:: native in a script.

-- This is because the ROPE namespace should most likely be called PHYSICS alphabetically.
```

> SET_CGOFFSET - 0xD8FA3908D7B86904 0x59910AB2

void SET_CGOFFSET(Object rope, float x, float y, float z)



> GET_CGOFFSET - 0x8214A4B5A7A33612 0x49A11F0D

Vector3 GET_CGOFFSET(Object rope)



> SET_CG_AT_BOUNDCENTER - 0xBE520D9761FF811F 0xA5B55421

void SET_CG_AT_BOUNDCENTER(Object rope)



> BREAK_ENTITY_GLASS - 0x2E648D16F6E308F3 0xD0E0402F

void BREAK_ENTITY_GLASS(Any p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, Any p9, BOOL p10)



> SET_DISABLE_BREAKING - 0x5CEC1A84620E7D5B 0xEE77C326

Any SET_DISABLE_BREAKING(Object rope, BOOL enabled)



> 0xCC6E963682533882 

void 0xCC6E963682533882(Any p0)

```
RESET_*
```

> SET_DISABLE_FRAG_DAMAGE - 0x01BA3AED21C16CFB 0x97269DC8

void SET_DISABLE_FRAG_DAMAGE(Object object, BOOL toggle)

```
sometimes used used with NET_TO_OBJ
hash collision last 2 words
```

