# Object

> CREATE_OBJECT - 0x509D5878EB39E842 0x2F7AA05C

Object CREATE_OBJECT(Hash modelHash, float x, float y, float z, BOOL networkHandle, BOOL createHandle, BOOL dynamic)

```
p5 - last parameter does not mean object handle is returned
maybe a quick view in disassembly will tell us what is actually does

----------

prop_tt_screenstatic (0xE2E039BC) is handled different. Not sure how yet but it I know it is.
thx fr Xenus.oida 
```

> CREATE_OBJECT_NO_OFFSET - 0x9A294B2138ABB884 0x58040420

Object CREATE_OBJECT_NO_OFFSET(Hash modelHash, float x, float y, float z, BOOL networkHandle, BOOL createHandle, BOOL dynamic)

```
p5 - does not mean object handle is returned
maybe a quick view in disassembly will tell us what is actually does
```

> DELETE_OBJECT - 0x539E0AE3E6634B9F 0xD6EF9DA7

void DELETE_OBJECT(Object* object)

```
Deletes the specified object, then sets the handle pointed to by the pointer to NULL.
```

> PLACE_OBJECT_ON_GROUND_PROPERLY - 0x58A850EAEE20FAA3 0x8F95A20B

BOOL PLACE_OBJECT_ON_GROUND_PROPERLY(Object object)



> SLIDE_OBJECT - 0x2FDFF4107B8C1147 0x63BFA7A0

BOOL SLIDE_OBJECT(Object object, float toX, float toY, float toZ, float speedX, float speedY, float speedZ, BOOL collision)

```
Returns true if the object has finished moving.

If false, moves the object towards the specified X, Y and Z coordinates with the specified X, Y and Z speed.

See also: gtag.gtagaming.com/opcode-database/opcode/034E/

-- also see (fivem.net/)
```

> SET_OBJECT_TARGETTABLE - 0x8A7391690F5AFD81 0x3F88CD86

Any SET_OBJECT_TARGETTABLE(Object object, BOOL targettable)



> 0x77F33F2CCF64B3AA 0x483C5C88

void 0x77F33F2CCF64B3AA(Object object, BOOL p1)



> GET_CLOSEST_OBJECT_OF_TYPE - 0xE143FA2249364369 0x45619B33

Object GET_CLOSEST_OBJECT_OF_TYPE(float x, float y, float z, float radius, Hash modelHash, BOOL isMission, BOOL p6, BOOL p7)

```
Has 8 params in the latest patches.

isMission - if true doesn't return mission objects
```

> HAS_OBJECT_BEEN_BROKEN - 0x8ABFB70C49CC43E2 0xFE21F891

BOOL HAS_OBJECT_BEEN_BROKEN(Object object)



> HAS_CLOSEST_OBJECT_OF_TYPE_BEEN_BROKEN - 0x761B0E69AC4D007E 0x6FC0353D

BOOL HAS_CLOSEST_OBJECT_OF_TYPE_BEEN_BROKEN(float p0, float p1, float p2, float p3, Hash modelHash, Any p5)



> 0x46494A2475701343 0x7DB578DD

BOOL 0x46494A2475701343(float p0, float p1, float p2, float p3, Hash modelHash, BOOL p5)



> _GET_OBJECT_OFFSET_FROM_COORDS - 0x163E252DE035A133 0x87A42A12

Vector3 _GET_OBJECT_OFFSET_FROM_COORDS(float xPos, float yPos, float zPos, float heading, float xOffset, float yOffset, float zOffset)



> 0x163F8B586BC95F2A 0x65213FC3

Any 0x163F8B586BC95F2A(Any coords, float radius, Hash modelHash, float x, float y, float z, Vector3* p6, int p7)

```
only documented params
dont know what this does.... To Be Continued... 
```

> SET_STATE_OF_CLOSEST_DOOR_OF_TYPE - 0xF82D8F1926A02C3D 0x38C951A4

void SET_STATE_OF_CLOSEST_DOOR_OF_TYPE(Hash type, float x, float y, float z, BOOL locked, float heading, BOOL p6)

```
Hardcoded to not work in multiplayer.


Used to lock/unlock doors to interior areas of the game.

(Possible) Door Types:

pastebin.com/9S2m3qA4

Heading is either 1, 0 or -1 in the scripts. Means default closed(0) or opened either into(1) or out(-1) of the interior.
Locked means that the heading is locked.  
p6 is always 0. 

225 door types, model names and coords found in stripclub.c4:
pastebin.com/gywnbzsH

get door info: pastebin.com/i14rbekD
```

> GET_STATE_OF_CLOSEST_DOOR_OF_TYPE - 0xEDC1A5B84AEF33FF 0x4B44A83D

void GET_STATE_OF_CLOSEST_DOOR_OF_TYPE(Hash type, float x, float y, float z, BOOL* locked, float* heading)

```
locked is 0 if no door is found
locked is 0 if door is unlocked
locked is 1 if door is found and unlocked.

-------------
the locked bool is either 0(unlocked)(false) or 1(locked)(true)
```

> _DOOR_CONTROL - 0x9B12F9A24FABEDB0 0x4E0A260B

void _DOOR_CONTROL(Hash doorHash, float x, float y, float z, BOOL locked, float p5, float p6, float p7)

```
when you set locked to 0 the door open and to 1 the door close
OBJECT::_9B12F9A24FABEDB0(${prop_gate_prison_01}, 1845.0, 2605.0, 45.0, 0, 0.0, 50.0, 0);  //door open

OBJECT::_9B12F9A24FABEDB0(${prop_gate_prison_01}, 1845.0, 2605.0, 45.0, 1, 0.0, 50.0, 0);  //door close

p5-7 - Rot?
```

> ADD_DOOR_TO_SYSTEM - 0x6F8838D03D1DC226 0x9D2D778D

void ADD_DOOR_TO_SYSTEM(Hash doorHash, Hash modelHash, float x, float y, float z, BOOL p5, BOOL p6, BOOL p7)



> REMOVE_DOOR_FROM_SYSTEM - 0x464D8E1427156FE4 0x00253286

void REMOVE_DOOR_FROM_SYSTEM(Hash doorHash)



> _SET_DOOR_ACCELERATION_LIMIT - 0x6BAB9442830C7F53 0xDF83DB47

void _SET_DOOR_ACCELERATION_LIMIT(Hash doorHash, int limit, BOOL p2, BOOL p3)

```
Sets the acceleration limit of a door.
How fast it can open, or the inverse hinge resistance.

A limit of 0 seems to lock doors.

p2 is always 0, p3 is always 1.


```

> 0x160AA1B32F6139B8 0xD42A41C2

int 0x160AA1B32F6139B8(Hash doorHash)



> 0x4BC2854478F3A749 0xD649B7E1

int 0x4BC2854478F3A749(Hash doorHash)



> 0x03C27E13B42A0E82 0x4F44AF21

void 0x03C27E13B42A0E82(Hash doorHash, float p1, BOOL p2, BOOL p3)



> 0x9BA001CB45CBF627 0x47531446

void 0x9BA001CB45CBF627(Hash doorHash, float heading, BOOL p2, BOOL p3)



> _SET_DOOR_AJAR_ANGLE - 0xB6E6FBA95C7324AC 0x34883DE3

void _SET_DOOR_AJAR_ANGLE(Hash doorHash, float ajar, BOOL p2, BOOL p3)

```
Sets the ajar angle of a door.
Ranges from -1.0 to 1.0, and 0.0 is closed / default.

p2 is always 0, p3 is always 1.


```

> 0x65499865FCA6E5EC 0xB74C3BD7

float 0x65499865FCA6E5EC(Hash doorHash)

```
possibly called:
ADD_DOOR_EXPERIMENTAL_MATRIX
```

> 0xC485E07E4F0B7958 0xB4A9A558

void 0xC485E07E4F0B7958(Hash doorHash, BOOL p1, BOOL p2, BOOL p3)



> 0xD9B71952F78A2640 0xECE58AE0

void 0xD9B71952F78A2640(Hash doorHash, BOOL p1)



> 0xA85A21582451E951 0xF736227C

void 0xA85A21582451E951(Hash doorHash, BOOL p1)



> _DOES_DOOR_EXIST - 0xC153C43EA202C8C1 0x5AFCD8A1

BOOL _DOES_DOOR_EXIST(Hash doorHash)

```
Always used prior a door functions Example 

if (OBJECT::_DOES_DOOR_EXIST(doorHash)) 
{
    OBJECT::REMOVE_DOOR_FROM_SYSTEM(doorHash);
}
```

> IS_DOOR_CLOSED - 0xC531EE8A1145A149 0x48659CD7

BOOL IS_DOOR_CLOSED(Hash door)



> 0xC7F29CA00F46350E 0x9BF33E41

void 0xC7F29CA00F46350E(BOOL p0)



> 0x701FDA1E82076BA4 0xF592AD10

void 0x701FDA1E82076BA4()



> 0xDF97CDD4FC08FD34 0x17FF9393

BOOL 0xDF97CDD4FC08FD34(Any p0)



> 0x589F80B325CC82C5 0xE9AE494F

BOOL 0x589F80B325CC82C5(float p0, float p1, float p2, Any p3, Any* p4)



> IS_GARAGE_EMPTY - 0x90E47239EA1980B8 0xA8B37DEA

BOOL IS_GARAGE_EMPTY(Any garage, BOOL p1, int p2)



> 0x024A60DEB0EA69F0 0xC33ED360

BOOL 0x024A60DEB0EA69F0(Any p0, Player player, float p2, int p3)



> 0x1761DC5D8471CBAA 0x41924877

BOOL 0x1761DC5D8471CBAA(Any p0, Player player, int p2)



> 0x85B6C850546FDDE2 0x4BD59750

BOOL 0x85B6C850546FDDE2(Any p0, BOOL p1, BOOL p2, BOOL p3, Any p4)



> 0x673ED815D6E323B7 0x7B44D659

BOOL 0x673ED815D6E323B7(Any p0, BOOL p1, BOOL p2, BOOL p3, Any p4)



> 0x372EF6699146A1E4 0x142C8F76

BOOL 0x372EF6699146A1E4(Any p0, Entity entity, float p2, int p3)



> 0xF0EED5A6BC7B237A 0x95A9AB2B

BOOL 0xF0EED5A6BC7B237A(Any p0, Entity entity, int p2)

```
IS_OBJECT_???
```

> 0x190428512B240692 0xA565E27E

void 0x190428512B240692(Any p0, BOOL p1, BOOL p2, BOOL p3, BOOL p4)



> 0xF2E1A7133DD356A6 0x43BB7E48

void 0xF2E1A7133DD356A6(Hash hash, BOOL toggle)



> 0x66A49D021870FE88 0x6158959E

void 0x66A49D021870FE88()



> DOES_OBJECT_OF_TYPE_EXIST_AT_COORDS - 0xBFA48E2FF417213F 0x23FF2BA4

BOOL DOES_OBJECT_OF_TYPE_EXIST_AT_COORDS(float x, float y, float z, float radius, Hash hash, BOOL p5)

```
p5 is usually 0.
```

> IS_POINT_IN_ANGLED_AREA - 0x2A70BAE8883E4C81 0x73BCFFDC

BOOL IS_POINT_IN_ANGLED_AREA(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, BOOL p10, BOOL p11)



> 0x4D89D607CB3DD1D2 0x19B17769

void 0x4D89D607CB3DD1D2(Object object, BOOL toggle)



> SET_OBJECT_PHYSICS_PARAMS - 0xF6DF6E90DE7DF90F 0xE8D11C58

void SET_OBJECT_PHYSICS_PARAMS(Object object, float weight, float p2, float p3, float p4, float p5, float gravity, float p7, float p8, float p9, float p10, float buoyancy)

```
Known parameters: 

p1 = weight, units unknown
p6 = object (downwards? (No shit, Sherlock...)) gravity

p11 = buoyancy, affects how much the object floats. set to at least 2.0f to make an object float
```

> GET_OBJECT_FRAGMENT_DAMAGE_HEALTH - 0xB6FBFD079B8D0596 0xF0B330AD

float GET_OBJECT_FRAGMENT_DAMAGE_HEALTH(Any p0, BOOL p1)



> SET_ACTIVATE_OBJECT_PHYSICS_AS_SOON_AS_IT_IS_UNFROZEN - 0x406137F8EF90EAF5 0x3E263AE1

void SET_ACTIVATE_OBJECT_PHYSICS_AS_SOON_AS_IT_IS_UNFROZEN(Object object, BOOL toggle)



> IS_ANY_OBJECT_NEAR_POINT - 0x397DC58FF00298D1 0xE9E46941

BOOL IS_ANY_OBJECT_NEAR_POINT(float x, float y, float z, float range, BOOL p4)



> IS_OBJECT_NEAR_POINT - 0x8C90FE4B381BA60A 0x50A62C43

BOOL IS_OBJECT_NEAR_POINT(Hash objectHash, float x, float y, float z, float range)



> 0x4A39DB43E47CF3AA 0xE3261B35

void 0x4A39DB43E47CF3AA(Any p0)



> 0xE7E4C198B0185900 0x1E82C2AE

void 0xE7E4C198B0185900(Object p0, Any p1, BOOL p2)



> 0xF9C1681347C8BD15 

void 0xF9C1681347C8BD15(Object object)



> TRACK_OBJECT_VISIBILITY - 0xB252BC036B525623 0x46D06B9A

void TRACK_OBJECT_VISIBILITY(Any p0)



> IS_OBJECT_VISIBLE - 0x8B32ACE6326A7546 0xF4FD8AE4

BOOL IS_OBJECT_VISIBLE(Object object)



> 0xC6033D32241F6FB5 0xF4A1A14A

void 0xC6033D32241F6FB5(Any p0, BOOL p1)



> 0xEB6F1A9B5510A5D2 0xAF016CC1

void 0xEB6F1A9B5510A5D2(Any p0, BOOL p1)



> 0xBCE595371A5FBAAF 0x3A68AA46

void 0xBCE595371A5FBAAF(Any p0, BOOL p1)



> 0xB48FCED898292E52 0xA286DE96

Any 0xB48FCED898292E52(float x, float y, float z, float p3, char* p4)

```
Example:
OBJECT::_B48FCED898292E52(-809.9619750976562, 170.919, 75.7406997680664, 3.0, 'des_tvsmash');

All found arguments for p4 starts with 'des_' like 'DES_FIB_Floor' and 'des_shipsink'.
```

> 0x5C29F698D404C5E1 0x21F51560

void 0x5C29F698D404C5E1(Any p0, Any p1)

```
Defines the state of a 'DES_' object.
Use the '0xB48FCED898292E52' native to find an object's handle with its name / coords
```

> 0x899BA936634A322E 0xF1B8817A

Any 0x899BA936634A322E(Any p0)



> 0x52AF537A0C5B8AAD 0xE08C834D

BOOL 0x52AF537A0C5B8AAD(Any p0)



> 0x260EE4FDBDF4DB01 0x020497DE

float 0x260EE4FDBDF4DB01(Any p0)



> CREATE_PICKUP - 0xFBA08C503DD5FA58 0x5E14DF68

Pickup CREATE_PICKUP(Hash pickupHash, float posX, float posY, float posZ, int p4, int value, BOOL p6, Hash modelHash)



> CREATE_PICKUP_ROTATE - 0x891804727E0A98B7 0xF015BFE2

Pickup CREATE_PICKUP_ROTATE(Hash pickupHash, float posX, float posY, float posZ, float rotX, float rotY, float rotZ, int flag, int amount, Any p9, BOOL p10, Hash modelHash)

```
flags:
8 (1 &lt;&lt; 3): place on ground
512 (1 &lt;&lt; 9): spin around
```

> CREATE_AMBIENT_PICKUP - 0x673966A0C0FD7171 0x17B99CE7

Pickup CREATE_AMBIENT_PICKUP(Hash pickupHash, float posX, float posY, float posZ, int p4, int value, Hash modelHash, BOOL p7, BOOL p8)



> CREATE_PORTABLE_PICKUP - 0x2EAF1FDB2FB55698 0x8C886BE5

Pickup CREATE_PORTABLE_PICKUP(Hash pickupHash, float x, float y, float z, BOOL placeOnGround, Hash modelHash)

```
List of pickupHash - ecb2.pw/releases/GTAV/lists/pickups.txt
```

> _CREATE_PORTABLE_PICKUP_2 - 0x125494B98A21AAF7 0x56A02502

Pickup _CREATE_PORTABLE_PICKUP_2(Hash pickupHash, float x, float y, float z, BOOL placeOnGround, Hash modelHash)



> ATTACH_PORTABLE_PICKUP_TO_PED - 0x8DC39368BDD57755 0x184F6AB3

void ATTACH_PORTABLE_PICKUP_TO_PED(Ped ped, Any p1)



> DETACH_PORTABLE_PICKUP_FROM_PED - 0xCF463D1E9A0AECB1 0x1D094562

void DETACH_PORTABLE_PICKUP_FROM_PED(Ped ped)



> 0x0BF3B3BD47D79C08 0x7EFBA039

void 0x0BF3B3BD47D79C08(Any p0, Any p1)



> 0x78857FC65CADB909 0xA3CDF152

void 0x78857FC65CADB909(BOOL p0)



> GET_SAFE_PICKUP_COORDS - 0x6E16BC2503FF1FF0 0x618B5F67

Vector3 GET_SAFE_PICKUP_COORDS(float x, float y, float z, Any p3, Any p4)



> GET_PICKUP_COORDS - 0x225B8B35C88029B3 0xC2E1E2C5

int GET_PICKUP_COORDS(Any p0)



> REMOVE_ALL_PICKUPS_OF_TYPE - 0x27F9D613092159CF 0x40062C53

void REMOVE_ALL_PICKUPS_OF_TYPE(Any p0)



> HAS_PICKUP_BEEN_COLLECTED - 0x80EC48E6679313F9 0x0BE5CCED

BOOL HAS_PICKUP_BEEN_COLLECTED(Any p0)



> REMOVE_PICKUP - 0x3288D8ACAECD2AB2 0x64A7A0E0

void REMOVE_PICKUP(Pickup pickup)



> CREATE_MONEY_PICKUPS - 0x0589B5E791CE9B2B 0x36C9A5EA

void CREATE_MONEY_PICKUPS(float x, float y, float z, int value, int amount, Hash model)

```
Spawns one or more money pickups.

x: The X-component of the world position to spawn the money pickups at.
y: The Y-component of the world position to spawn the money pickups at.
z: The Z-component of the world position to spawn the money pickups at.
value: The combined value of the pickups (in dollars).
amount: The number of pickups to spawn.
model: The model to use, or 0 for default money model.

Example:
CREATE_MONEY_PICKUPS(x, y, z, 1000, 3, 0x684a97ae);

Spawns 3 spray cans that'll collectively give $1000 when picked up. (Three spray cans, each giving $334, $334, $332 = $1000).
```

> DOES_PICKUP_EXIST - 0xAFC1CA75AD4074D1 0x9C6DA0B3

BOOL DOES_PICKUP_EXIST(Any p0)



> DOES_PICKUP_OBJECT_EXIST - 0xD9EFB6DBF7DAAEA3 0xE0B32108

BOOL DOES_PICKUP_OBJECT_EXIST(Any p0)



> GET_PICKUP_OBJECT - 0x5099BC55630B25AE 0x6052E62E

Object GET_PICKUP_OBJECT(Object object)



> 0x0378C08504160D0D 

BOOL 0x0378C08504160D0D(Any p0)



> _IS_PICKUP_WITHIN_RADIUS - 0xF9C36251F6E48E33 0xF139681B

BOOL _IS_PICKUP_WITHIN_RADIUS(Hash pickupHash, float x, float y, float z, float radius)



> SET_PICKUP_REGENERATION_TIME - 0x78015C9B4B3ECC9D 0xAB11267D

void SET_PICKUP_REGENERATION_TIME(Any p0, Any p1)



> 0x616093EC6B139DD9 0x7FADB4B9

void 0x616093EC6B139DD9(Any p0, Any p1, BOOL p2)

```
From the scripts:

OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_portable_package}, 0);
OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_portable_package}, 0);
OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_portable_package}, 1);
OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_portable_package}, 0);
OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_armour_standard}, 0);
OBJECT::_616093EC6B139DD9(PLAYER::PLAYER_ID(), ${pickup_armour_standard}, 1);

SET_PLAYER_P*
```

> 0x88EAEC617CD26926 0x3A8F1BF7

void 0x88EAEC617CD26926(Hash p0, BOOL p1)

```
SET_LOCAL_PLAYER_*
```

> SET_TEAM_PICKUP_OBJECT - 0x53E0DF1A2A3CF0CA 0x77687DC5

void SET_TEAM_PICKUP_OBJECT(Any p0, Any p1, BOOL p2)



> 0x92AEFB5F6E294023 0xCBB5F9B6

void 0x92AEFB5F6E294023(Object object, BOOL p1, BOOL p2)



> 0xA08FE5E49BDC39DD 0x276A7807

void 0xA08FE5E49BDC39DD(Any p0, float p1, BOOL p2)



> 0xDB41D07A45A6D4B7 0x000E92DC

Any 0xDB41D07A45A6D4B7(Any p0)



> 0x318516E02DE3ECE2 0x9879AC51

void 0x318516E02DE3ECE2(float p0)



> 0x31F924B53EADDF65 0xDB18FA01

void 0x31F924B53EADDF65(BOOL p0)



> 0xF92099527DB8E2A7 0xA7E936FD

void 0xF92099527DB8E2A7(Any p0, Any p1)



> 0xA2C1F5E92AFE49ED 0xB241806C

void 0xA2C1F5E92AFE49ED()



> 0x762DB2D380B48D04 0xD1BAAFB7

void 0x762DB2D380B48D04(Any p0)



> _HIGHLIGHT_PLACEMENT_COORDS - 0x3430676B11CDF21D 0x63B02FAD

void _HIGHLIGHT_PLACEMENT_COORDS(float x, float y, float z, int colorIndex)

```
draws circular marker at pos
-1 = none
0 = red
1 = green
2 = blue
3 = green larger
4 = nothing
5 = green small
```

> 0xB2D0BDE54F0E8E5A 0x132B6D92

void 0xB2D0BDE54F0E8E5A(Object object, BOOL toggle)



> 0x08F96CA6C551AD51 0xEDD01937

Hash 0x08F96CA6C551AD51(Pickup pickupHash)

```
returns the weapon hash of pickup
```

> 0x11D1E53A726891FE 

BOOL 0x11D1E53A726891FE(Any p0)



> 0x971DA0055324D033 

void 0x971DA0055324D033(Object object, int paintIndex)

```
enum BoatPaintIDs
{
	Pacific = 0,
	Azure = 1,
	Nautical = 2,
	Continental = 3,
	Battleship = 4,
	Intrepid = 5,
	Uniform = 6,
	Classico = 7,
	Mediterranean = 8,
	Command = 9,
	Mariner = 10,
	Ruby = 11,
	Vintage = 12,
	Pristine = 13,
	Merchant = 14,
	Voyager = 15
};
```

> 0x5EAAD83F8CFB4575 0x6AE36192

Hash 0x5EAAD83F8CFB4575(Pickup pickupHash)

```
returns pickup hash.
```

> SET_FORCE_OBJECT_THIS_FRAME - 0xF538081986E49E9D 0x3DA41C1A

void SET_FORCE_OBJECT_THIS_FRAME(Any p0, Any p1, Any p2, Any p3)



> _MARK_OBJECT_FOR_DELETION - 0xADBE4809F19F927A 0x2048A7DD

void _MARK_OBJECT_FOR_DELETION(Object object)

```
is this like setting is as no longer needed?
```

