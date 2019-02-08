# Worldprobe

> START_SHAPE_TEST_LOS_PROBE - 0x7EE9F5D83DD4F90E 0xEFAF4BA6

int START_SHAPE_TEST_LOS_PROBE(float x1, float y1, float z1, float x2, float y2, float z2, int flags, Entity entity, int p8)

```
Returns a ray (?) going from x1, y1, z1 to x2, y2, z2.
entity = 0 most of the time.
p8 = 7 most of the time.

Result of this function is passed to WORLDPROBE::_GET_RAYCAST_RESULT as a first argument.
```

> _CAST_RAY_POINT_TO_POINT - 0x377906D8A31E5586 0x8251485D

int _CAST_RAY_POINT_TO_POINT(float x1, float y1, float z1, float x2, float y2, float z2, int flags, Entity entity, int p8)

```
Not sure how or why this differs from 0x7EE9F5D83DD4F90E, but it does.

This function casts a ray from Point1 to Point2 and returns it's ray handle.  A simple ray cast will 'shoot' a line from point A to point B, and return whether or not the ray reached it's destination or if it hit anything and if it did hit anything, will return the handle of what it hit (entity handle) and coordinates of where the ray reached.

You can use _GET_RAYCAST_RESULT to get the result of the raycast

Entity is an entity to ignore, such as the player.

Flags are intersection bit flags.  They tell the ray what to care about and what not to care about when casting. Passing -1 will intersect with everything, presumably.

Flags:
1: Intersect with map
2: Intersect with vehicles (used to be mission entities?) (includes train)
4: Intersect with peds? (same as 8)
8: Intersect with peds? (same as 4)
16: Intersect with objects
32: Unknown
64: Unknown
128: Unknown
256: Intersect with vegetation (plants, coral. trees not included)

NOTE: Raycasts that intersect with mission_entites (flag = 2) has limited range and will not register for far away entites. The range seems to be about 30 metres. 
```

> START_SHAPE_TEST_BOUNDING_BOX - 0x052837721A854EC7 0xCEEAD94B

Any START_SHAPE_TEST_BOUNDING_BOX(Entity entity, int flags1, int flags2)



> START_SHAPE_TEST_BOX - 0xFE466162C4401D18 0x249BC876

Any START_SHAPE_TEST_BOX(float x, float y, float z, float x1, float y2, float z2, float rotX, float rotY, float rotZ, Any p9, Any p10, Any entity, Any p12)



> START_SHAPE_TEST_BOUND - 0x37181417CE7C8900 0x13BC46C0

Any START_SHAPE_TEST_BOUND(Entity entity, int flags1, int flags2)



> START_SHAPE_TEST_CAPSULE - 0x28579D1B8F8AAC80 0x591EA833

int START_SHAPE_TEST_CAPSULE(float x1, float y1, float z1, float x2, float y2, float z2, float radius, int flags, Entity entity, int p9)

```
Raycast from point to point, where the ray has a radius. 

flags:
vehicles=10
peds =12

Iterating through flags yields many ped / vehicle/ object combinations

p9 = 7, but no idea what it does

Entity is an entity to ignore
```

> 0xE6AC6C45FBE83004 0x4559460A

int 0xE6AC6C45FBE83004(float x1, float y1, float z1, float x2, float y2, float z2, float radius, int flags, Entity entity, Any p9)

```
Performs the same type of trace as START_SHAPE_TEST_CAPSULE, but with some different hardcoded parameters.
```

> 0xFF6BE494C7987F34 

Any 0xFF6BE494C7987F34(Any p0, Any p1, Any p2, Any p3, Any p4)

```
Actual name starts with START_SHAPE_TEST_??? and it returns a ShapeTest handle that can be used with GET_SHAPE_TEST_RESULT.

In its only usage in game scripts its called with flag set to 511, entity to player_ped_id and flag2 set to 7
```

> GET_SHAPE_TEST_RESULT - 0x3D87450E15D98694 0xF3C2875A

int GET_SHAPE_TEST_RESULT(int rayHandle, BOOL* hit, Vector3* endCoords, Vector3* surfaceNormal, Entity* entityHit)

```
Parameters:
rayHandle - Ray Handle from a casted ray, as returned by CAST_RAY_POINT_TO_POINT
hit - Where to store whether or not it hit anything. False is when the ray reached its destination.
endCoords - Where to store the world-coords of where the ray was stopped (by hitting its desired max range or by colliding with an entity/the map)
surfaceNormal - Where to store the surface-normal coords (NOT relative to the game world) of where the entity was hit by the ray
entityHit - Where to store the handle of the entity hit by the ray

Returns:
Result? Some type of enum.

NOTE: To get the offset-coords of where the ray hit relative to the entity that it hit (which is NOT the same as surfaceNormal), you can use these two natives:
Vector3 offset = ENTITY::GET_OFFSET_FROM_ENTITY_GIVEN_WORLD_COORDS(entityHit, endCoords.x, endCoords.y, endCoords.z);
Vector3 entitySpotCoords = ENTITY::GET_OFFSET_FROM_ENTITY_IN_WORLD_COORDS(entityHit, offset.x, offset.y, offset.z);

Use ENTITY::GET_ENTITY_TYPE(entityHit) to quickly distinguish what type of entity you hit (ped/vehicle/object - 1/2/3)
```

> _GET_SHAPE_TEST_RESULT_EX - 0x65287525D951F6BE 0x4301E10C

int _GET_SHAPE_TEST_RESULT_EX(int rayHandle, BOOL* hit, Vector3* endCoords, Vector3* surfaceNormal, Hash* _materialHash, Entity* entityHit)

```
behaves exactly the same way as GET_SHAPE_TEST_RESULT except it has one extra parameter (_materialHash).

Quick disassembly seems to indicate that the unknown is a hash. EDIT: Seems to be the hash of the hit material or surface type.

found a materialFX.dat list of them but not sure if it has to do with this native yet.
```

> 0x2B3334BCA57CD799 0xEC2AAF06

void 0x2B3334BCA57CD799(Entity p0)



