# Fire

> START_SCRIPT_FIRE - 0x6B83617E04503888 0xE7529357

int START_SCRIPT_FIRE(float X, float Y, float Z, int maxChildren, BOOL isGasFire)

```
Starts a fire:

xyz: Location of fire
maxChildren: The max amount of times a fire can spread to other objects. Must be 25 or less, or the function will do nothing.
isGasFire: Whether or not the fire is powered by gasoline.
```

> REMOVE_SCRIPT_FIRE - 0x7FF548385680673F 0x6B21FE26

void REMOVE_SCRIPT_FIRE(int fireHandle)



> START_ENTITY_FIRE - 0xF6A9D9708F6F23DF 0x8928428E

Any START_ENTITY_FIRE(Entity entity)



> STOP_ENTITY_FIRE - 0x7F0DD2EBBB651AFF 0xCE8C9066

void STOP_ENTITY_FIRE(Entity entity)



> IS_ENTITY_ON_FIRE - 0x28D3FED7190D3A0B 0x8C73E64F

BOOL IS_ENTITY_ON_FIRE(Entity entity)



> GET_NUMBER_OF_FIRES_IN_RANGE - 0x50CAD495A460B305 0x654D93B7

int GET_NUMBER_OF_FIRES_IN_RANGE(float x, float y, float z, float radius)



> STOP_FIRE_IN_RANGE - 0x056A8A219B8E829F 0x725C7205

void STOP_FIRE_IN_RANGE(float x, float y, float z, float radius)



> GET_CLOSEST_FIRE_POS - 0x352A9F6BCF90081F 0xC4977B47

BOOL GET_CLOSEST_FIRE_POS(Vector3* outPosition, float x, float y, float z)

```
Returns TRUE if it found something. FALSE if not.
```

> ADD_EXPLOSION - 0xE3AD2BDBAEE269AC 0x10AF5258

void ADD_EXPLOSION(float x, float y, float z, int explosionType, float damageScale, BOOL isAudible, BOOL isInvisible, float cameraShake)

```
BOOL isAudible = If explosion makes a sound.
BOOL isInvisible = If the explosion is invisible or not.

this native is missing a new argument: noDamage
nodamage = false: damage || nodamage = true: no damage

enum ExplosionTypes
{
	EXPLOSION_GRENADE,
	EXPLOSION_GRENADELAUNCHER,
	EXPLOSION_STICKYBOMB,
	EXPLOSION_MOLOTOV,
	EXPLOSION_ROCKET,
	EXPLOSION_TANKSHELL,
	EXPLOSION_HI_OCTANE,
	EXPLOSION_CAR,
	EXPLOSION_PLANE,
	EXPLOSION_PETROL_PUMP,
	EXPLOSION_BIKE,
	EXPLOSION_DIR_STEAM,
	EXPLOSION_DIR_FLAME,
	EXPLOSION_DIR_WATER_HYDRANT,
	EXPLOSION_DIR_GAS_CANISTER,
	EXPLOSION_BOAT,
	EXPLOSION_SHIP_DESTROY,
	EXPLOSION_TRUCK,
	EXPLOSION_BULLET,
	EXPLOSION_SMOKEGRENADELAUNCHER,
	EXPLOSION_SMOKEGRENADE,
	EXPLOSION_BZGAS,
	EXPLOSION_FLARE,
	EXPLOSION_GAS_CANISTER,
	EXPLOSION_EXTINGUISHER,
	EXPLOSION_PROGRAMMABLEAR,
	EXPLOSION_TRAIN,
	EXPLOSION_BARREL,
	EXPLOSION_PROPANE,
	EXPLOSION_BLIMP,
	EXPLOSION_DIR_FLAME_EXPLODE,
	EXPLOSION_TANKER,
	EXPLOSION_PLANE_ROCKET,
	EXPLOSION_VEHICLE_BULLET,
	EXPLOSION_GAS_TANK,
	EXPLOSION_BIRD_CRAP
};
```

> ADD_OWNED_EXPLOSION - 0x172AA1B624FA1013 0x27EE0D67

void ADD_OWNED_EXPLOSION(Ped ped, float x, float y, float z, int explosionType, float damageScale, BOOL isAudible, BOOL isInvisible, float cameraShake)

```
enum ExplosionTypes
{
	EXPLOSION_GRENADE,
	EXPLOSION_GRENADELAUNCHER,
	EXPLOSION_STICKYBOMB,
	EXPLOSION_MOLOTOV,
	EXPLOSION_ROCKET,
	EXPLOSION_TANKSHELL,
	EXPLOSION_HI_OCTANE,
	EXPLOSION_CAR,
	EXPLOSION_PLANE,
	EXPLOSION_PETROL_PUMP,
	EXPLOSION_BIKE,
	EXPLOSION_DIR_STEAM,
	EXPLOSION_DIR_FLAME,
	EXPLOSION_DIR_WATER_HYDRANT,
	EXPLOSION_DIR_GAS_CANISTER,
	EXPLOSION_BOAT,
	EXPLOSION_SHIP_DESTROY,
	EXPLOSION_TRUCK,
	EXPLOSION_BULLET,
	EXPLOSION_SMOKEGRENADELAUNCHER,
	EXPLOSION_SMOKEGRENADE,
	EXPLOSION_BZGAS,
	EXPLOSION_FLARE,
	EXPLOSION_GAS_CANISTER,
	EXPLOSION_EXTINGUISHER,
	EXPLOSION_PROGRAMMABLEAR,
	EXPLOSION_TRAIN,
	EXPLOSION_BARREL,
	EXPLOSION_PROPANE,
	EXPLOSION_BLIMP,
	EXPLOSION_DIR_FLAME_EXPLODE,
	EXPLOSION_TANKER,
	EXPLOSION_PLANE_ROCKET,
	EXPLOSION_VEHICLE_BULLET,
	EXPLOSION_GAS_TANK,
	EXPLOSION_BIRD_CRAP
};


BOOL isAudible = If explosion makes a sound.
BOOL isInvisible = If the explosion is invisible or not.
```

> _ADD_SPECFX_EXPLOSION - 0x36DD3FE58B5E5212 0xCF358946

void _ADD_SPECFX_EXPLOSION(float x, float y, float z, int explosionType, Hash explosionFx, float damageScale, BOOL isAudible, BOOL isInvisible, float cameraShake)

```


```

> IS_EXPLOSION_IN_AREA - 0x2E2EBA0EE7CED0E0 0xFB40075B

BOOL IS_EXPLOSION_IN_AREA(int explosionType, float x1, float y1, float z1, float x2, float y2, float z2)



> 0x6070104B699B2EF4 

Any 0x6070104B699B2EF4(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)

```
Console Hash: 0x37C388DB
```

> IS_EXPLOSION_IN_SPHERE - 0xAB0F816885B0E483 0xD455A7F3

BOOL IS_EXPLOSION_IN_SPHERE(int explosionType, float x, float y, float z, float radius)



> IS_EXPLOSION_IN_ANGLED_AREA - 0xA079A6C51525DC4B 0x0128FED9

BOOL IS_EXPLOSION_IN_ANGLED_AREA(int explosionType, float x1, float y1, float z1, float x2, float y2, float z2, float angle)



> _GET_PED_INSIDE_EXPLOSION_AREA - 0x14BA4BA137AF6CEC 0xAEC0D176

Entity _GET_PED_INSIDE_EXPLOSION_AREA(int explosionType, float x1, float y1, float z1, float x2, float y2, float z2, float radius)

```
Returns a handle to the first entity within the a circle spawned inside the 2 points from a radius. It could return a ped or an entity, but the scripts expect a ped, but still check if it's a ped.
```

