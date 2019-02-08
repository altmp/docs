# Entity

> DOES_ENTITY_EXIST - 0x7239B21A38F536BA 0x3AC90869

BOOL DOES_ENTITY_EXIST(Entity entity)

```
Checks if the Entity exists
```

> DOES_ENTITY_BELONG_TO_THIS_SCRIPT - 0xDDE6DF5AE89981D2 0xACFEB3F9

BOOL DOES_ENTITY_BELONG_TO_THIS_SCRIPT(Entity entity, BOOL p1)



> DOES_ENTITY_HAVE_DRAWABLE - 0x060D6E96F8B8E48D 0xA5B33300

BOOL DOES_ENTITY_HAVE_DRAWABLE(Entity entity)



> DOES_ENTITY_HAVE_PHYSICS - 0xDA95EA3317CC5064 0x9BCD2979

BOOL DOES_ENTITY_HAVE_PHYSICS(Entity entity)



> HAS_ENTITY_ANIM_FINISHED - 0x20B711662962B472 0x1D9CAB92

BOOL HAS_ENTITY_ANIM_FINISHED(Entity entity, char* animDict, char* animName, int p3)

```
P3 is always 3 as far as i cant tell

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> HAS_ENTITY_BEEN_DAMAGED_BY_ANY_OBJECT - 0x95EB9964FF5C5C65 0x6B74582E

BOOL HAS_ENTITY_BEEN_DAMAGED_BY_ANY_OBJECT(Entity entity)



> HAS_ENTITY_BEEN_DAMAGED_BY_ANY_PED - 0x605F5A140F202491 0x53FD4A25

BOOL HAS_ENTITY_BEEN_DAMAGED_BY_ANY_PED(Entity entity)



> HAS_ENTITY_BEEN_DAMAGED_BY_ANY_VEHICLE - 0xDFD5033FDBA0A9C8 0x878C2CE0

BOOL HAS_ENTITY_BEEN_DAMAGED_BY_ANY_VEHICLE(Entity entity)



> HAS_ENTITY_BEEN_DAMAGED_BY_ENTITY - 0xC86D67D52A707CF8 0x07FC77E0

BOOL HAS_ENTITY_BEEN_DAMAGED_BY_ENTITY(Entity entity1, Entity entity2, BOOL p2)

```
Entity 1 = Victim
Entity 2 = Attacker

p2 seems to always be 1
```

> HAS_ENTITY_CLEAR_LOS_TO_ENTITY - 0xFCDFF7B72D23A1AC 0x53576FA7

BOOL HAS_ENTITY_CLEAR_LOS_TO_ENTITY(Entity entity1, Entity entity2, int traceType)

```
traceType is always 17 in the scripts.

*JulioNIB: There is other codes used for traceType:
19 - in jewelry_prep1a
126 - in am_hunt_the_beast
256 &amp; 287 - in fm_mission_controller
```

> HAS_ENTITY_CLEAR_LOS_TO_ENTITY_IN_FRONT - 0x0267D00AF114F17A 0x210D87C8

BOOL HAS_ENTITY_CLEAR_LOS_TO_ENTITY_IN_FRONT(Entity entity1, Entity entity2)

```
Has the entity1 got a clear line of sight to the other entity2 from the direction entity1 is facing.
This is one of the most CPU demanding BOOL natives in the game; avoid calling this in things like nested for-loops
```

> HAS_ENTITY_COLLIDED_WITH_ANYTHING - 0x8BAD02F0368D9E14 0x662A2F41

BOOL HAS_ENTITY_COLLIDED_WITH_ANYTHING(Entity entity)

```
Called on tick.
Tested with vehicles, returns true whenever the vehicle is touching any entity.

Note: for vehicles, the wheels can touch the ground and it will still return false, but if the body of the vehicle touches the ground, it will return true.
```

> GET_LAST_MATERIAL_HIT_BY_ENTITY - 0x5C3D0A935F535C4C 0xC0E3AA47

Hash GET_LAST_MATERIAL_HIT_BY_ENTITY(Entity entity)



> GET_COLLISION_NORMAL_OF_LAST_HIT_FOR_ENTITY - 0xE465D4AB7CA6AE72 0xAB415C07

Vector3 GET_COLLISION_NORMAL_OF_LAST_HIT_FOR_ENTITY(Entity entity)



> FORCE_ENTITY_AI_AND_ANIMATION_UPDATE - 0x40FDEDB72F8293B2 0x58D9775F

void FORCE_ENTITY_AI_AND_ANIMATION_UPDATE(Entity entity)

```
Based on carmod_shop script decompile this takes a vehicle parameter. It is called when repair is done on initial enter.
```

> GET_ENTITY_ANIM_CURRENT_TIME - 0x346D81500D088F42 0x83943F41

float GET_ENTITY_ANIM_CURRENT_TIME(Entity entity, char* animDict, char* animName)

```
Returns a float value representing animation's current playtime with respect to its total playtime. This value increasing in a range from [0 to 1] and wrap back to 0 when it reach 1.

Example:
0.000000 - mark the starting of animation.
0.500000 - mark the midpoint of the animation.
1.000000 - mark the end of animation.

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> GET_ENTITY_ANIM_TOTAL_TIME - 0x50BD2730B191E360 0x433A9D18

float GET_ENTITY_ANIM_TOTAL_TIME(Entity entity, char* animDict, char* animName)

```
Returns a float value representing animation's total playtime in milliseconds.

Example:
GET_ENTITY_ANIM_TOTAL_TIME(PLAYER_ID(),'amb@world_human_yoga@female@base','base_b') 
return 20800.000000

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> _GET_ENTITY_ANIM_DURATION - 0xFEDDF04D62B8D790 

float _GET_ENTITY_ANIM_DURATION(char* animDict, char* animName)

```
Console Hash: 0x8B5E3E3D = GET_ANIM_DURATION

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> GET_ENTITY_ATTACHED_TO - 0x48C2BED9180FE123 0xFE1589F9

Entity GET_ENTITY_ATTACHED_TO(Entity entity)



> GET_ENTITY_COORDS - 0x3FEF770D40960D5A 0x1647F1CB

Vector3 GET_ENTITY_COORDS(Entity entity, BOOL alive)

```
p1 = !IS_ENTITY_DEAD

```

> GET_ENTITY_FORWARD_VECTOR - 0x0A794A5A57F8DF91 0x84DCECBF

Vector3 GET_ENTITY_FORWARD_VECTOR(Entity entity)

```
Gets the entity's forward vector.
```

> GET_ENTITY_FORWARD_X - 0x8BB4EF4214E0E6D5 0x49FAE914

float GET_ENTITY_FORWARD_X(Entity entity)

```
Gets the X-component of the entity's forward vector.
```

> GET_ENTITY_FORWARD_Y - 0x866A4A5FAE349510 0x9E2F917C

float GET_ENTITY_FORWARD_Y(Entity entity)

```
Gets the Y-component of the entity's forward vector.
```

> GET_ENTITY_HEADING - 0xE83D4F9BA2A38914 0x972CC383

float GET_ENTITY_HEADING(Entity entity)

```
Returns the heading of the entity in degrees. Also know as the 'Yaw' of an entity.
```

> _GET_ENTITY_PHYSICS_HEADING - 0x846BF6291198A71E 

float _GET_ENTITY_PHYSICS_HEADING(Entity entity)

```
Gets the heading of the entity physics in degrees, which tends to be more accurate than just 'GET_ENTITY_HEADING'. This can be clearly seen while, for example, ragdolling a ped/player.

NOTE: The name and description of this native are based on independent research. If you find this native to be more suitable under a different name and/or described differently, please feel free to do so.

```

> GET_ENTITY_HEALTH - 0xEEF059FAD016D209 0x8E3222B7

int GET_ENTITY_HEALTH(Entity entity)

```
Returns an integer value of entity's current health.

Example of range for ped:
- Player [0 to 200]
- Ped [100 to 200]
- Vehicle [0 to 1000]
- Object [0 to 1000]

Health is actually a float value but this native casts it to int.
In order to get the actual value, do:
float health = *(float *)(entityAddress + 0x280);
```

> GET_ENTITY_MAX_HEALTH - 0x15D757606D170C3C 0xC7AE6AA1

int GET_ENTITY_MAX_HEALTH(Entity entity)

```
Return an integer value of entity's maximum health.

Example:
- Player = 200
- Ped = 150
```

> SET_ENTITY_MAX_HEALTH - 0x166E7CF68597D8B5 0x96F84DF8

void SET_ENTITY_MAX_HEALTH(Entity entity, int value)

```
For instance: ENTITY::SET_ENTITY_MAX_HEALTH(PLAYER::PLAYER_PED_ID(), 200); // director_mode.c4: 67849
```

> GET_ENTITY_HEIGHT - 0x5A504562485944DD 0xEE443481

float GET_ENTITY_HEIGHT(Entity entity, float X, float Y, float Z, BOOL atTop, BOOL inWorldCoords)



> GET_ENTITY_HEIGHT_ABOVE_GROUND - 0x1DD55701034110E5 0x57F56A4D

float GET_ENTITY_HEIGHT_ABOVE_GROUND(Entity entity)

```
Return height (z-dimension) above ground. 
Example: The pilot in a titan plane is 1.844176 above ground.

How can i convert it to meters?
Everything seems to be in meters, probably this too.
```

> GET_ENTITY_MATRIX - 0xECB2FC7235A7D137 0xEB9EB001

void GET_ENTITY_MATRIX(Entity entity, Vector3* rightVector, Vector3* forwardVector, Vector3* upVector, Vector3* position)



> GET_ENTITY_MODEL - 0x9F47B058362C84B5 0xDAFCB3EC

Hash GET_ENTITY_MODEL(Entity entity)

```
Returns the model hash from the entity
```

> GET_OFFSET_FROM_ENTITY_GIVEN_WORLD_COORDS - 0x2274BC1C4885E333 0x6477EC9E

Vector3 GET_OFFSET_FROM_ENTITY_GIVEN_WORLD_COORDS(Entity entity, float posX, float posY, float posZ)

```
Converts world coords (posX - Z) to coords relative to the entity

Example:
posX is given as 50
entity's x coord is 40
the returned x coord will then be 10 or -10, not sure haven't used this in a while (think it is 10 though).
```

> GET_OFFSET_FROM_ENTITY_IN_WORLD_COORDS - 0x1899F328B0E12848 0xABCF043A

Vector3 GET_OFFSET_FROM_ENTITY_IN_WORLD_COORDS(Entity entity, float offsetX, float offsetY, float offsetZ)

```
Offset values are relative to the entity.

x = left/right
y = forward/backward
z = up/down
```

> GET_ENTITY_PITCH - 0xD45DC2893621E1FE 0xFCE6ECE5

float GET_ENTITY_PITCH(Entity entity)



> GET_ENTITY_QUATERNION - 0x7B3703D2D32DFA18 0x5154EC90

void GET_ENTITY_QUATERNION(Entity entity, float* x, float* y, float* z, float* w)

```
w is the correct parameter name!
```

> GET_ENTITY_ROLL - 0x831E0242595560DF 0x36610842

float GET_ENTITY_ROLL(Entity entity)

```
Displays the current ROLL axis of the entity [-180.0000/180.0000+]
(Sideways Roll) such as a vehicle tipped on its side
```

> GET_ENTITY_ROTATION - 0xAFBD61CC738D9EB9 0x8FF45B04

Vector3 GET_ENTITY_ROTATION(Entity entity, int rotationOrder)

```
rotationOrder refers to the order yaw pitch roll is applied
value ranges from 0 to 5. What you use for rotationOrder when getting must be the same as rotationOrder when setting the rotation. 
Unsure what value corresponds to what rotation order, more testing will be needed for that.
------
rotationOrder is usually 2 in scripts
------
ENTITY::GET_ENTITY_ROTATION(Any p0, false or true);
if false than return from -180 to 180
if true than return from -90 to 90

---

As said above, the value of p1 affects the outcome. R* uses 1 and 2 instead of 0 and 1, so I marked it as an int.

What it returns is the yaw on the z part of the vector, which makes sense considering R* considers z as vertical. Here's a picture for those of you who don't understand pitch, yaw, and roll:

www.allstar.fiu.edu/aero/images/pic5-1.gif

I don't know why it returns a Vec3, but sometimes the values x and y go negative, yet they're always zero. Just use GET_ENTITY_PITCH and GET_ENTITY_ROLL for pitch and roll.
```

> GET_ENTITY_ROTATION_VELOCITY - 0x213B91045D09B983 0x9BF8A73F

Vector3 GET_ENTITY_ROTATION_VELOCITY(Entity entity)



> GET_ENTITY_SCRIPT - 0xA6E9C38DB51D7748 0xB7F70784

char* GET_ENTITY_SCRIPT(Entity entity, ScrHandle* script)

```
All ambient entities in-world seem to have the same value for the second argument (Any *script), depending on when the scripthook was activated/re-activated. I've seen numbers from ~5 to almost 70 when the value was translated with to_string. The function return value seems to always be 0.
```

> GET_ENTITY_SPEED - 0xD5037BA82E12416F 0x9E1E4798

float GET_ENTITY_SPEED(Entity entity)

```
result is in meters per second

------------------------------------------------------------
So would the conversion to mph and km/h, be along the lines of this.

float speed = GET_ENTITY_SPEED(veh);
float kmh = (speed * 3.6);
float mph = (speed * 2.236936);
------------------------------------------------------------
```

> GET_ENTITY_SPEED_VECTOR - 0x9A8D700A51CB7B0D 0x3ED2B997

Vector3 GET_ENTITY_SPEED_VECTOR(Entity entity, BOOL relative)

```
Relative can be used for getting speed relative to the frame of the vehicle, to determine for example, if you are going in reverse (-y speed) or not (+y speed). 
```

> GET_ENTITY_UPRIGHT_VALUE - 0x95EED5A694951F9F 0xF4268190

float GET_ENTITY_UPRIGHT_VALUE(Entity entity)



> GET_ENTITY_VELOCITY - 0x4805D2B1D8CF94A9 0xC14C9B6B

Vector3 GET_ENTITY_VELOCITY(Entity entity)



> GET_OBJECT_INDEX_FROM_ENTITY_INDEX - 0xD7E3B9735C0F89D6 0xBC5A9C58

Object GET_OBJECT_INDEX_FROM_ENTITY_INDEX(Entity entity)

```
Simply returns whatever is passed to it (Regardless of whether the handle is valid or not).
```

> GET_PED_INDEX_FROM_ENTITY_INDEX - 0x04A2A40C73395041 0xC46F74AC

Ped GET_PED_INDEX_FROM_ENTITY_INDEX(Entity entity)

```
Simply returns whatever is passed to it (Regardless of whether the handle is valid or not).
```

> GET_VEHICLE_INDEX_FROM_ENTITY_INDEX - 0x4B53F92932ADFAC0 0xC69CF43D

Vehicle GET_VEHICLE_INDEX_FROM_ENTITY_INDEX(Entity entity)

```
Simply returns whatever is passed to it (Regardless of whether the handle is valid or not).
```

> GET_WORLD_POSITION_OF_ENTITY_BONE - 0x44A8FCB8ED227738 0x7C6339DF

Vector3 GET_WORLD_POSITION_OF_ENTITY_BONE(Entity entity, int boneIndex)

```
Returns the coordinates of an entity-bone.
```

> GET_NEAREST_PLAYER_TO_ENTITY - 0x7196842CB375CDB3 0xCE17FDEC

Player GET_NEAREST_PLAYER_TO_ENTITY(Entity entity)



> GET_NEAREST_PLAYER_TO_ENTITY_ON_TEAM - 0x4DC9A62F844D9337 0xB1808F56

Player GET_NEAREST_PLAYER_TO_ENTITY_ON_TEAM(Entity entity, int team)



> GET_ENTITY_TYPE - 0x8ACD366038D14505 0x0B1BD08D

int GET_ENTITY_TYPE(Entity entity)

```
Returns:
0 = no entity
1 = ped
2 = vehicle
3 = object
```

> _GET_ENTITY_POPULATION_TYPE - 0xF6F5161F4534EDFF 

int _GET_ENTITY_POPULATION_TYPE(Entity entity)

```
Console Hash: 0xFC30DDFF

Returns range from 0-10

--------------------------------------------------------------

The type name can be retrieved by using this:

typedef LPSTR(__fastcall *GetEntityPopulationTypeName_t)(unsigned __int16 entityPopulationType, bool scriptName);
	GetEntityPopulationTypeName_t GetEntityPopulationTypeName = (GetEntityPopulationTypeName_t)FindPattern('44 0F B7 C1 4C 8D 0D ?? ?? ?? ?? 41 83 F8 07');
```

> IS_AN_ENTITY - 0x731EC8A916BD11A1 0xD4B9715A

BOOL IS_AN_ENTITY(int handle)



> IS_ENTITY_A_PED - 0x524AC5ECEA15343E 0x55D33EAB

BOOL IS_ENTITY_A_PED(Entity entity)



> IS_ENTITY_A_MISSION_ENTITY - 0x0A7B270912999B3C 0x2632E124

BOOL IS_ENTITY_A_MISSION_ENTITY(Entity entity)



> IS_ENTITY_A_VEHICLE - 0x6AC7003FA6E5575E 0xBE800B01

BOOL IS_ENTITY_A_VEHICLE(Entity entity)



> IS_ENTITY_AN_OBJECT - 0x8D68C8FD0FACA94E 0x3F52E561

BOOL IS_ENTITY_AN_OBJECT(Entity entity)



> IS_ENTITY_AT_COORD - 0x20B60995556D004F 0xD749B606

BOOL IS_ENTITY_AT_COORD(Entity entity, float xPos, float yPos, float zPos, float xSize, float ySize, float zSize, BOOL p7, BOOL p8, int p9)

```
Checks if entity is within x/y/zSize distance of x/y/z. 

Last three are unknown ints, almost always p7 = 0, p8 = 1, p9 = 0
```

> IS_ENTITY_AT_ENTITY - 0x751B70C3D034E187 0xDABDCB52

BOOL IS_ENTITY_AT_ENTITY(Entity entity1, Entity entity2, float xSize, float ySize, float zSize, BOOL p5, BOOL p6, int p7)

```
Checks if entity1 is within the box defined by x/y/zSize of entity2.

Last three parameters are almost alwasy p5 = 0, p6 = 1, p7 = 0
```

> IS_ENTITY_ATTACHED - 0xB346476EF1A64897 0xEC1479D5

BOOL IS_ENTITY_ATTACHED(Entity entity)



> IS_ENTITY_ATTACHED_TO_ANY_OBJECT - 0xCF511840CEEDE0CC 0x0B5DE340

BOOL IS_ENTITY_ATTACHED_TO_ANY_OBJECT(Entity entity)



> IS_ENTITY_ATTACHED_TO_ANY_PED - 0xB1632E9A5F988D11 0x9D7A609C

BOOL IS_ENTITY_ATTACHED_TO_ANY_PED(Entity entity)



> IS_ENTITY_ATTACHED_TO_ANY_VEHICLE - 0x26AA915AD89BFB4B 0xDE5C995E

BOOL IS_ENTITY_ATTACHED_TO_ANY_VEHICLE(Entity entity)



> IS_ENTITY_ATTACHED_TO_ENTITY - 0xEFBE71898A993728 0xB0ABFEA8

BOOL IS_ENTITY_ATTACHED_TO_ENTITY(Entity from, Entity to)



> IS_ENTITY_DEAD - 0x5F9532F3B5CC2551 0xB6F7CBAC

BOOL IS_ENTITY_DEAD(Entity entity)



> IS_ENTITY_IN_AIR - 0x886E37EC497200B6 0xA4157987

BOOL IS_ENTITY_IN_AIR(Entity entity)



> IS_ENTITY_IN_ANGLED_AREA - 0x51210CED3DA1C78A 0x883622FA

BOOL IS_ENTITY_IN_ANGLED_AREA(Entity entity, float originX, float originY, float originZ, float edgeX, float edgeY, float edgeZ, float angle, BOOL p8, BOOL p9, Any p10)

```
Creates a spherical cone at origin that extends to surface with the angle specified. Then returns true if the entity is inside the spherical cone

Angle is measured in degrees.
These values are constant, most likely bogus:
p8 = 0, p9 = 1, p10 = 0

This method can also take two float&lt;3&gt; instead of 6 floats.
```

> IS_ENTITY_IN_AREA - 0x54736AA40E271165 0x8C2DFA9D

BOOL IS_ENTITY_IN_AREA(Entity entity, float x1, float y1, float z1, float x2, float y2, float z2, BOOL p7, BOOL p8, Any p9)



> IS_ENTITY_IN_ZONE - 0xB6463CF6AF527071 0x45C82B21

BOOL IS_ENTITY_IN_ZONE(Entity entity, char* zone)



> IS_ENTITY_IN_WATER - 0xCFB0A0D8EDD145A3 0x4C3C2508

BOOL IS_ENTITY_IN_WATER(Entity entity)



> GET_ENTITY_SUBMERGED_LEVEL - 0xE81AFC1BC4CC41CE 0x0170F68C

float GET_ENTITY_SUBMERGED_LEVEL(Entity entity)

```
Get how much of the entity is submerged.  1.0f is whole entity.
```

> 0x694E00132F2823ED 0x40C84A74

void 0x694E00132F2823ED(Entity entity, BOOL p1)

```
what does it do?
```

> IS_ENTITY_ON_SCREEN - 0xE659E47AF827484B 0xC1FEC5ED

BOOL IS_ENTITY_ON_SCREEN(Entity entity)

```
Returns true if the entity is in between the minimum and maximum values for the 2d screen coords. 
This means that it will return true even if the entity is behind a wall for example, as long as you're looking at their location. 
Chipping
```

> IS_ENTITY_PLAYING_ANIM - 0x1F0B79228E461EC9 0x0D130D34

BOOL IS_ENTITY_PLAYING_ANIM(Entity entity, char* animDict, char* animName, int p4)

```
See also PED::IS_SCRIPTED_SCENARIO_PED_USING_CONDITIONAL_ANIM 0x6EC47A344923E1ED 0x3C30B447

Taken from ENTITY::IS_ENTITY_PLAYING_ANIM(PLAYER::PLAYER_PED_ID(), 'creatures@shark@move', 'attack_player', 3)

p4 is always 3 in the scripts.

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> IS_ENTITY_STATIC - 0x1218E6886D3D8327 0x928E12E9

BOOL IS_ENTITY_STATIC(Entity entity)

```
a static ped will not react to natives like 'APPLY_FORCE_TO_ENTITY' or 'SET_ENTITY_VELOCITY' and oftentimes will not react to task-natives like 'AI::TASK_COMBAT_PED'. The only way I know of to make one of these peds react is to ragdoll them (or sometimes to use CLEAR_PED_TASKS_IMMEDIATELY(). Static peds include almost all far-away peds, beach-combers, peds in certain scenarios, peds crossing a crosswalk, peds walking to get back into their cars, and others. If anyone knows how to make a ped non-static without ragdolling them, please edit this with the solution.

how to i meik static entyti??
```

> IS_ENTITY_TOUCHING_ENTITY - 0x17FFC1B2BA35A494 0x6B931477

BOOL IS_ENTITY_TOUCHING_ENTITY(Entity entity, Entity targetEntity)



> IS_ENTITY_TOUCHING_MODEL - 0x0F42323798A58C8C 0x307E7611

BOOL IS_ENTITY_TOUCHING_MODEL(Entity entity, Hash modelHash)



> IS_ENTITY_UPRIGHT - 0x5333F526F6AB19AA 0x3BCDF4E1

BOOL IS_ENTITY_UPRIGHT(Entity entity, float angle)



> IS_ENTITY_UPSIDEDOWN - 0x1DBD58820FA61D71 0x5ACAA48F

BOOL IS_ENTITY_UPSIDEDOWN(Entity entity)



> IS_ENTITY_VISIBLE - 0x47D6F43D77935C75 0x120B4ED5

BOOL IS_ENTITY_VISIBLE(Entity entity)



> IS_ENTITY_VISIBLE_TO_SCRIPT - 0xD796CB5BA8F20E32 0x5D240E9D

BOOL IS_ENTITY_VISIBLE_TO_SCRIPT(Entity entity)



> IS_ENTITY_OCCLUDED - 0xE31C2C72B8692B64 0x46BC5B40

BOOL IS_ENTITY_OCCLUDED(Entity entity)



> WOULD_ENTITY_BE_OCCLUDED - 0xEE5D2A122E09EC42 0xEA127CBC

BOOL WOULD_ENTITY_BE_OCCLUDED(Hash hash, float x, float y, float z, BOOL p4)

```
First parameter was previously an Entity but after further research it is definitely a hash.
```

> IS_ENTITY_WAITING_FOR_WORLD_COLLISION - 0xD05BFF0C0A12C68F 0x00AB7A4A

BOOL IS_ENTITY_WAITING_FOR_WORLD_COLLISION(Entity entity)



> APPLY_FORCE_TO_ENTITY_CENTER_OF_MASS - 0x18FF00FC7EFF559E 0x28924E98

void APPLY_FORCE_TO_ENTITY_CENTER_OF_MASS(Entity entity, int forceType, float x, float y, float z, BOOL p5, BOOL isRel, BOOL highForce, BOOL p8)

```
p6/relative - makes the xyz force not relative to world coords, but to something else
p7/highForce - setting false will make the force really low
```

> APPLY_FORCE_TO_ENTITY - 0xC5F68BE9613E2D18 0xC1C0855A

void APPLY_FORCE_TO_ENTITY(Entity entity, int forceType, float x, float y, float z, float xRot, float yRot, float zRot, int boneIndex, BOOL isRel, BOOL p10, BOOL highForce, BOOL p12, BOOL p13)

```
forceType - 0 to 5 (any number greater then 5 force does nothing)
p8 - no effect (a quick disassembly will tell us what it does)
isRel - specifies if the force direction is relative to direction entity is facing (true), or static world direction (false).
p11/highForce - setting false will make the force really low

enum ForceTypes
{
	MIN_FORCE = 0,
	MAX_FORCE_ROT = 1,
	MIN_FORCE_2 = 2,
	MAX_FORCE_ROT_2 = 3, //stable, good for custom handling
	FORCE_NO_ROT = 4,
	FORCE_ROT_PLUS_FORCE = 5
};


```

> ATTACH_ENTITY_TO_ENTITY - 0x6B9BBD38AB0796DF 0xEC024237

void ATTACH_ENTITY_TO_ENTITY(Entity entity1, Entity entity2, int boneIndex, float xPos, float yPos, float zPos, float xRot, float yRot, float zRot, BOOL p9, BOOL useSoftPinning, BOOL collision, BOOL isPed, int vertexIndex, BOOL fixedRot)

```
Attaches entity1 to bone (boneIndex) of entity2.

boneIndex - this is different to boneID, use GET_PED_BONE_INDEX to get the index from the ID. use the index for attaching to specific bones. entity1 will be attached to entity2's centre if bone index given doesn't correspond to bone indexes for that entity type.

useSoftPinning - if set to false attached entity will not detach when fixed
collision - controls collision between the two entities (FALSE disables collision).
isPed - pitch doesnt work when false and roll will only work on negative numbers (only peds)
vertexIndex - position of vertex
fixedRot - if false it ignores entity vector 

```

> ATTACH_ENTITY_TO_ENTITY_PHYSICALLY - 0xC3675780C92F90F9 0x0547417F

void ATTACH_ENTITY_TO_ENTITY_PHYSICALLY(Entity entity1, Entity entity2, int boneIndex1, int boneIndex2, float xPos1, float yPos1, float zPos1, float xPos2, float yPos2, float zPos2, float xRot, float yRot, float zRot, float breakForce, BOOL fixedRot, BOOL p15, BOOL collision, BOOL p17, int p18)

```
breakForce is the amount of force required to break the bond.
p14 - is always 1 in scripts
p15 - is 1 or 0 in scripts - unknoun what it does
p16 - controls collision between the two entities (FALSE disables collision).
p17 - do not teleport entity to be attached to the position of the bone Index of the target entity (if 1, entity will not be teleported to target bone)
p18 - is always 2 in scripts.


```

> PROCESS_ENTITY_ATTACHMENTS - 0xF4080490ADC51C6F 0x6909BA59

void PROCESS_ENTITY_ATTACHMENTS(Entity entity)

```
Called to update entity attachments.
```

> GET_ENTITY_BONE_INDEX_BY_NAME - 0xFB71170B7E76ACBA 0xE4ECAC22

int GET_ENTITY_BONE_INDEX_BY_NAME(Entity entity, char* boneName)

```
Returns the index of the bone. If the bone was not found, -1 will be returned. 

list:
pastebin.com/D7JMnX1g

BoneNames:
	chassis,
	windscreen,
	seat_pside_r,
	seat_dside_r,
	bodyshell,
	suspension_lm,
	suspension_lr,
	platelight,
	attach_female,
	attach_male,
	bonnet,
	boot,
	chassis_dummy,	//Center of the dummy
	chassis_Control,	//Not found yet
	door_dside_f,	//Door left, front
	door_dside_r,	//Door left, back
	door_pside_f,	//Door right, front
	door_pside_r,	//Door right, back
	Gun_GripR,
	windscreen_f,
	platelight,	//Position where the light above the numberplate is located
	VFX_Emitter,
	window_lf,	//Window left, front
	window_lr,	//Window left, back
	window_rf,	//Window right, front
	window_rr,	//Window right, back
	engine,	//Position of the engine
	gun_ammo,
	ROPE_ATTATCH,	//Not misspelled. In script 'finale_heist2b.c4'.
	wheel_lf,	//Wheel left, front
	wheel_lr,	//Wheel left, back
	wheel_rf,	//Wheel right, front
	wheel_rr,	//Wheel right, back
	exhaust,	//Exhaust. shows only the position of the stock-exhaust
	overheat,	//A position on the engine(not exactly sure, how to name it)
	misc_e,	//Not a car-bone.
	seat_dside_f,	//Driver-seat
	seat_pside_f,	//Seat next to driver
	Gun_Nuzzle,
	seat_r

I doubt that the function is case-sensitive, since I found a 'Chassis' and a 'chassis'. - Just tested: Definitely not case-sensitive.


```

> CLEAR_ENTITY_LAST_DAMAGE_ENTITY - 0xA72CD9CA74A5ECBA 0x2B83F43B

Any CLEAR_ENTITY_LAST_DAMAGE_ENTITY(Entity entity)



> DELETE_ENTITY - 0xAE3CBE5BF394C9C9 0xFAA3D236

void DELETE_ENTITY(Entity* entity)

```
Deletes the specified entity, then sets the handle pointed to by the pointer to NULL.
```

> DETACH_ENTITY - 0x961AC54BF0613F5D 0xC8EFCB41

void DETACH_ENTITY(Entity entity, BOOL p1, BOOL collision)

```
p1 and p2 have no effect 
maybe a quick disassembly will tell us what they do

if p2 is set to true, the both entities won't collide with the other until the distance between them is above 4 meters.


p1?
```

> FREEZE_ENTITY_POSITION - 0x428CA6DBD1094446 0x65C16D57

void FREEZE_ENTITY_POSITION(Entity entity, BOOL toggle)



> 0x3910051CCECDB00C 0xD3850671

void 0x3910051CCECDB00C(Entity entity, BOOL toggle)

```
this is not for network entities 

does this native even do what it does?
```

> PLAY_ENTITY_ANIM - 0x7FB218262B810701 0x878753D5

BOOL PLAY_ENTITY_ANIM(Entity entity, char* animName, char* propName, float p3, BOOL p4, BOOL p5, BOOL p6, float delta, Any bitset)

```
delta and bitset are guessed fields. They are based on the fact that most of the calls have 0 or nil field types passed in.

The only time bitset has a value is 0x4000 and the only time delta has a value is during stealth with usually &lt;1.0f values.

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> PLAY_SYNCHRONIZED_ENTITY_ANIM - 0xC77720A12FE14A86 0x012760AA

BOOL PLAY_SYNCHRONIZED_ENTITY_ANIM(Entity entity, int syncedScene, char* animation, char* propName, float p4, float p5, Any p6, float p7)

```
p4 and p7 are usually 1000.0f.

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> PLAY_SYNCHRONIZED_MAP_ENTITY_ANIM - 0xB9C54555ED30FBC4 0xEB4CBA74

BOOL PLAY_SYNCHRONIZED_MAP_ENTITY_ANIM(float p0, float p1, float p2, float p3, Any p4, Any p5, Any* p6, Any* p7, float p8, float p9, Any p10, float p11)

```
Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> STOP_SYNCHRONIZED_MAP_ENTITY_ANIM - 0x11E79CAB7183B6F5 0x7253D5B2

BOOL STOP_SYNCHRONIZED_MAP_ENTITY_ANIM(float p0, float p1, float p2, float p3, Any p4, float p5)



> STOP_ENTITY_ANIM - 0x28004F88151E03E0 0xC4769830

Any STOP_ENTITY_ANIM(Entity entity, char* animation, char* animGroup, float p3)

```
Animations List : www.ls-multiplayer.com/dev/index.php?section=3

RAGEPluginHook list: docs.ragepluginhook.net/html/62951c37-a440-478c-b389-c471230ddfc5.htm
```

> STOP_SYNCHRONIZED_ENTITY_ANIM - 0x43D3807C077261E3 0xE27D2FC1

BOOL STOP_SYNCHRONIZED_ENTITY_ANIM(Entity entity, float p1, BOOL p2)

```
p1 sync task id?
```

> HAS_ANIM_EVENT_FIRED - 0xEAF4CD9EA3E7E922 0x66571CA0

BOOL HAS_ANIM_EVENT_FIRED(Entity entity, Hash actionHash)

```
if (ENTITY::HAS_ANIM_EVENT_FIRED(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('CreateObject')))
```

> FIND_ANIM_EVENT_PHASE - 0x07F1BE2BCCAA27A7 0xC41DDA62

BOOL FIND_ANIM_EVENT_PHASE(char* animDictionary, char* animName, char* p2, Any* p3, Any* p4)

```
In the script 'player_scene_t_bbfight.c4':
'if (ENTITY::FIND_ANIM_EVENT_PHASE(&amp;l_16E, &amp;l_19F[v_4/*16*/], v_9, &amp;v_A, &amp;v_B))'
-- &amp;l_16E (p0) is requested as an anim dictionary earlier in the script.
-- &amp;l_19F[v_4/*16*/] (p1) is used in other natives in the script as the 'animation' param.
-- v_9 (p2) is instantiated as 'victim_fall'; I'm guessing that's another anim
--v_A and v_B (p3 &amp; p4) are both set as -1.0, but v_A is used immediately after this native for: 
'if (v_A &lt; ENTITY::GET_ENTITY_ANIM_CURRENT_TIME(...))'
Both v_A and v_B are seemingly used to contain both Vector3's and floats, so I can't say what either really is other than that they are both output parameters. p4 looks more like a *Vector3 though
-alphazolam

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> SET_ENTITY_ANIM_CURRENT_TIME - 0x4487C259F0F70977 0x99D90735

void SET_ENTITY_ANIM_CURRENT_TIME(Entity entity, char* animDictionary, char* animName, float time)

```
Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> SET_ENTITY_ANIM_SPEED - 0x28D1A16553C51776 0x3990C90A

void SET_ENTITY_ANIM_SPEED(Entity entity, char* animDictionary, char* animName, float speedMultiplier)

```
Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> SET_ENTITY_AS_MISSION_ENTITY - 0xAD738C3085FE7E11 0x5D1F9E0F

void SET_ENTITY_AS_MISSION_ENTITY(Entity entity, BOOL p1, BOOL byThisScript)

```
Makes the specified entity (ped, vehicle or object) persistent. Persistent entities will not automatically be removed by the engine.

p1 has no effect when either its on or off 
maybe a quick disassembly will tell us what it does

p2 has no effect when either its on or off 
maybe a quick disassembly will tell us what it does
```

> SET_ENTITY_AS_NO_LONGER_NEEDED - 0xB736A491E64A32CF 0xADF2267C

void SET_ENTITY_AS_NO_LONGER_NEEDED(Entity* entity)

```
Marks the specified entity (ped, vehicle or object) as no longer needed.
Entities marked as no longer needed, will be deleted as the engine sees fit.
```

> SET_PED_AS_NO_LONGER_NEEDED - 0x2595DD4236549CE3 0x9A388380

void SET_PED_AS_NO_LONGER_NEEDED(Ped* ped)

```
This is an alias of SET_ENTITY_AS_NO_LONGER_NEEDED.
```

> SET_VEHICLE_AS_NO_LONGER_NEEDED - 0x629BFA74418D6239 0x9B0E10BE

void SET_VEHICLE_AS_NO_LONGER_NEEDED(Vehicle* vehicle)

```
This is an alias of SET_ENTITY_AS_NO_LONGER_NEEDED.
```

> SET_OBJECT_AS_NO_LONGER_NEEDED - 0x3AE22DEB5BA5A3E6 0x3F6B949F

void SET_OBJECT_AS_NO_LONGER_NEEDED(Object* object)

```
This is an alias of SET_ENTITY_AS_NO_LONGER_NEEDED.
```

> SET_ENTITY_CAN_BE_DAMAGED - 0x1760FFA8AB074D66 0x60B6E744

void SET_ENTITY_CAN_BE_DAMAGED(Entity entity, BOOL toggle)



> SET_ENTITY_CAN_BE_DAMAGED_BY_RELATIONSHIP_GROUP - 0xE22D8FDE858B8119 0x34165B5D

void SET_ENTITY_CAN_BE_DAMAGED_BY_RELATIONSHIP_GROUP(Entity entity, BOOL p1, Any p2)



> SET_ENTITY_CAN_BE_TARGETED_WITHOUT_LOS - 0xD3997889736FD899 0x3B13797C

void SET_ENTITY_CAN_BE_TARGETED_WITHOUT_LOS(Entity entity, BOOL toggle)

```
Sets whether the entity can be targeted without being in line-of-sight.
```

> SET_ENTITY_COLLISION - 0x1A9205C1B9EE827F 0x139FD37D

void SET_ENTITY_COLLISION(Entity entity, BOOL toggle, BOOL keepPhysics)



> _IS_ENTITY_COLLISON_DISABLED - 0xCCF1E97BEFDAE480 

BOOL _IS_ENTITY_COLLISON_DISABLED(Entity entity)

```
console hash: 0xE8C0C629
```

> 0x9EBC85ED0FFFE51C 

void 0x9EBC85ED0FFFE51C(Entity entity, BOOL p1, BOOL p2)

```
p2 - mainly set as false in scripts
```

> SET_ENTITY_COORDS - 0x06843DA7060A026B 0xDF70B41B

void SET_ENTITY_COORDS(Entity entity, float xPos, float yPos, float zPos, BOOL xAxis, BOOL yAxis, BOOL zAxis, BOOL clearArea)

```
p7 is always 1 in the scripts. Set to 1, an area around the destination coords for the moved entity is cleared from other entities. 
 
Often ends with 1, 0, 0, 1); in the scripts. It works. 

Axis - Invert Axis Flags
```

> _SET_ENTITY_COORDS_2 - 0x621873ECE1178967 

void _SET_ENTITY_COORDS_2(Entity entity, float xPos, float yPos, float zPos, BOOL xAxis, BOOL yAxis, BOOL zAxis, BOOL clearArea)

```
does the same as SET_ENTITY_COORDS.

Console Hash: 0x749B282E
```

> SET_ENTITY_COORDS_NO_OFFSET - 0x239A3351AC1DA385 0x4C83DE8D

void SET_ENTITY_COORDS_NO_OFFSET(Entity entity, float xPos, float yPos, float zPos, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
Axis - Invert Axis Flags
```

> SET_ENTITY_DYNAMIC - 0x1718DE8E3F2823CA 0x236F525B

void SET_ENTITY_DYNAMIC(Entity entity, BOOL toggle)



> SET_ENTITY_HEADING - 0x8E2530AA8ADA980E 0xE0FF064D

void SET_ENTITY_HEADING(Entity entity, float heading)



> SET_ENTITY_HEALTH - 0x6B76DC1F3AE6E6A3 0xFBCD1831

void SET_ENTITY_HEALTH(Entity entity, int health)

```
health &gt;= 0
```

> SET_ENTITY_INVINCIBLE - 0x3882114BDE571AD4 0xC1213A21

void SET_ENTITY_INVINCIBLE(Entity entity, BOOL toggle)

```
Sets a ped or an object totally invincible. It doesn't take any kind of damage. Peds will not ragdoll on explosions and the tazer animation won't apply either.

If you use this for a ped and you want Ragdoll to stay enabled, then do:
*(DWORD *)(pedAddress + 0x188) |= (1 &lt;&lt; 9);

Use this if you want to get the invincibility status:
	bool IsPedInvincible(Ped ped)
	{
		auto addr = getScriptHandleBaseAddress(ped);	

		if (addr)
		{
			DWORD flag = *(DWORD *)(addr + 0x188);
			return ((flag &amp; (1 &lt;&lt; 8)) != 0) || ((flag &amp; (1 &lt;&lt; 9)) != 0);
		}

		return false;
	}
```

> SET_ENTITY_IS_TARGET_PRIORITY - 0xEA02E132F5C68722 0x9729EE32

void SET_ENTITY_IS_TARGET_PRIORITY(Entity entity, BOOL p1, float p2)



> SET_ENTITY_LIGHTS - 0x7CFBA6A80BDF3874 0xE8FC85AF

void SET_ENTITY_LIGHTS(Entity entity, BOOL toggle)



> SET_ENTITY_LOAD_COLLISION_FLAG - 0x0DC7CABAB1E9B67E 0xC52F295B

void SET_ENTITY_LOAD_COLLISION_FLAG(Entity entity, BOOL toggle)



> HAS_COLLISION_LOADED_AROUND_ENTITY - 0xE9676F61BC0B3321 0x851687F9

BOOL HAS_COLLISION_LOADED_AROUND_ENTITY(Entity entity)



> SET_ENTITY_MAX_SPEED - 0x0E46A3FCBDE2A1B1 0x46AFFED3

void SET_ENTITY_MAX_SPEED(Entity entity, float speed)



> SET_ENTITY_ONLY_DAMAGED_BY_PLAYER - 0x79F020FF9EDC0748 0x4B707F50

void SET_ENTITY_ONLY_DAMAGED_BY_PLAYER(Entity entity, BOOL toggle)



> SET_ENTITY_ONLY_DAMAGED_BY_RELATIONSHIP_GROUP - 0x7022BD828FA0B082 0x202237E2

void SET_ENTITY_ONLY_DAMAGED_BY_RELATIONSHIP_GROUP(Entity entity, BOOL p1, Any p2)



> SET_ENTITY_PROOFS - 0xFAEE099C6F890BB8 0x7E9EAB66

void SET_ENTITY_PROOFS(Entity entity, BOOL bulletProof, BOOL fireProof, BOOL explosionProof, BOOL collisionProof, BOOL meleeProof, BOOL p6, BOOL p7, BOOL drownProof)

```
Enable / disable each type of damage.

Can't get drownProof to work.
--------------
p7 is to to '1' in am_mp_property_ext/int: entity::set_entity_proofs(uParam0-&gt;f_19, true, true, true, true, true, true, 1, true);

```

> SET_ENTITY_QUATERNION - 0x77B21BE7AC540F07 0x83B6046F

void SET_ENTITY_QUATERNION(Entity entity, float x, float y, float z, float w)

```
w is the correct parameter name!
```

> SET_ENTITY_RECORDS_COLLISIONS - 0x0A50A1EEDAD01E65 0x6B189A1A

void SET_ENTITY_RECORDS_COLLISIONS(Entity entity, BOOL toggle)



> SET_ENTITY_ROTATION - 0x8524A8B0171D5E07 0x0A345EFE

void SET_ENTITY_ROTATION(Entity entity, float pitch, float roll, float yaw, int rotationOrder, BOOL p5)

```
rotationOrder refers to the order yaw pitch roll is applied
value ranges from 0 to 5. What you use for rotationOrder when setting must be the same as rotationOrder when getting the rotation. 
Unsure what value corresponds to what rotation order, more testing will be needed for that.
For the most part R* uses 1 or 2 as the order.
p5 is usually set as true

```

> SET_ENTITY_VISIBLE - 0xEA1C610A04DB6BBB 0xD043E8E1

void SET_ENTITY_VISIBLE(Entity entity, BOOL toggle, BOOL unk)

```
unk was always 0.
```

> SET_ENTITY_VELOCITY - 0x1C99BB7B6E96D16F 0xFF5A1988

void SET_ENTITY_VELOCITY(Entity entity, float x, float y, float z)

```
Note that the third parameter(denoted as z) is 'up and down' with positive numbers encouraging upwards movement.
```

> SET_ENTITY_HAS_GRAVITY - 0x4A4722448F18EEF5 0xE2F262BF

void SET_ENTITY_HAS_GRAVITY(Entity entity, BOOL toggle)



> SET_ENTITY_LOD_DIST - 0x5927F96A78577363 0xD7ACC7AD

void SET_ENTITY_LOD_DIST(Entity entity, int value)



> GET_ENTITY_LOD_DIST - 0x4159C2762B5791D6 0x4DA3D51F

int GET_ENTITY_LOD_DIST(Entity entity)

```
Returns the LOD distance of an entity.
```

> SET_ENTITY_ALPHA - 0x44A0870B7E92D7C0 0xAE667CB0

void SET_ENTITY_ALPHA(Entity entity, int alphaLevel, BOOL skin)

```
skin - everything alpha except skin
Set entity alpha level. Ranging from 0 to 255 but chnages occur after every 20 percent (after every 51).
```

> GET_ENTITY_ALPHA - 0x5A47B3B5E63E94C6 0x1560B017

int GET_ENTITY_ALPHA(Entity entity)



> RESET_ENTITY_ALPHA - 0x9B1E824FFBB7027A 0x8A30761C

Any RESET_ENTITY_ALPHA(Entity entity)



> 0x5C3B791D580E0BC2 

void 0x5C3B791D580E0BC2(Entity entity, float p1)

```
Only called once in the scripts.

Related to weapon objects.

```

> SET_ENTITY_ALWAYS_PRERENDER - 0xACAD101E1FB66689 0xD8FF798A

void SET_ENTITY_ALWAYS_PRERENDER(Entity entity, BOOL toggle)



> SET_ENTITY_RENDER_SCORCHED - 0x730F5F8D3F0F2050 0xAAC9317B

void SET_ENTITY_RENDER_SCORCHED(Entity entity, BOOL toggle)



> SET_ENTITY_TRAFFICLIGHT_OVERRIDE - 0x57C5DB656185EAC4 0xC47F5B91

void SET_ENTITY_TRAFFICLIGHT_OVERRIDE(Entity entity, int state)

```
Example here: www.gtaforums.com/topic/830463-help-with-turning-lights-green-and-causing-peds-to-crash-into-each-other/#entry1068211340

0 = green
1 = red
2 = yellow
changing lights may not change the behavior of vehicles
```

> 0x78E8E3A640178255 

void 0x78E8E3A640178255(Entity entity)

```
Related to cutscene entities. Unsure about the use.
```

> CREATE_MODEL_SWAP - 0x92C47782FDA8B2A3 0x0BC12F9E

void CREATE_MODEL_SWAP(float x, float y, float z, float radius, Hash originalModel, Hash newModel, BOOL p6)

```
Only works with objects!
Network players do not see changes done with this.
- Did ya try modifying p6 lol
```

> REMOVE_MODEL_SWAP - 0x033C0F9A64E229AE 0xCE0AA8BC

void REMOVE_MODEL_SWAP(float x, float y, float z, float radius, Hash originalModel, Hash newModel, BOOL p6)



> CREATE_MODEL_HIDE - 0x8A97BCA30A0CE478 0x7BD5CF2F

void CREATE_MODEL_HIDE(float x, float y, float z, float radius, Hash model, BOOL p5)

```
p5 = sets as true in scripts
Same as the comment for CREATE_MODEL_SWAP unless for some reason p5 affects it this only works with objects as well.

Network players do not see changes done with this.
```

> CREATE_MODEL_HIDE_EXCLUDING_SCRIPT_OBJECTS - 0x3A52AE588830BF7F 0x07AAF22C

void CREATE_MODEL_HIDE_EXCLUDING_SCRIPT_OBJECTS(float x, float y, float z, float radius, Hash model, BOOL p5)



> REMOVE_MODEL_HIDE - 0xD9E3006FB3CBD765 0x993DBC10

void REMOVE_MODEL_HIDE(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)



> CREATE_FORCED_OBJECT - 0x150E808B375A385A 0x335190A2

void CREATE_FORCED_OBJECT(float x, float y, float z, Any p3, Hash modelHash, BOOL p5)



> REMOVE_FORCED_OBJECT - 0x61B6775E83C0DB6F 0xAED73ADD

void REMOVE_FORCED_OBJECT(Any p0, Any p1, Any p2, Any p3, Any p4)



> SET_ENTITY_NO_COLLISION_ENTITY - 0xA53ED5520C07654A 0x1E11BFE9

void SET_ENTITY_NO_COLLISION_ENTITY(Entity entity1, Entity entity2, BOOL collision)

```
Calling this function, regardless of the 'unknown' value, disabled collision between two entities.

Importance of entity1 and 2 order is unclear.
```

> SET_ENTITY_MOTION_BLUR - 0x295D82A8559F9150 0xE90005B8

void SET_ENTITY_MOTION_BLUR(Entity entity, BOOL toggle)



> 0xE12ABE5E3A389A6C 0x44767B31

void 0xE12ABE5E3A389A6C(Entity entity, BOOL p1)

```
p1 always false.
```

> 0xA80AE305E0A3044F 0xE224A6A5

void 0xA80AE305E0A3044F(Entity entity, BOOL p1)

```
p1 always false.
```

> 0xDC6F8601FAF2E893 

void 0xDC6F8601FAF2E893(Entity entity, BOOL p1)

```
SET_ENTITY_*

x360 Hash: 0xA0466A69

Only called within 1 script for x360. 'fm_mission_controller' and it used on an object. 

Ran after these 2 natives,
set_object_targettable(uParam0, 0);
set_entity_invincible(uParam0, 1);
```

> 0x2C2E3DC128F44309 

void 0x2C2E3DC128F44309(Entity entity, BOOL p1)

```
SET_ENTITY_*
```

> 0x1A092BB0C3808B96 

void 0x1A092BB0C3808B96(Entity entity, BOOL p1)

```
SET_ENTITY_*
```

