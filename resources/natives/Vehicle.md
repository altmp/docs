# Vehicle

> CREATE_VEHICLE - 0xAF35D0D2583051B0 0xDD75460A

Any CREATE_VEHICLE(Hash modelHash, float x, float y, float z, float heading, BOOL networkHandle, BOOL vehiclehandle)

```
p6 - last parameter does not mean vehicle handle is returned
maybe a quick view in disassembly will tell us what is actually does


p6 seems to check for something with the script in the disassembly
```

> DELETE_VEHICLE - 0xEA386986E786A54F 0x9803AF60

void DELETE_VEHICLE(Vehicle* vehicle)

```
Deletes a vehicle.
The vehicle must be a mission entity to delete, so call this before deleting: SET_ENTITY_AS_MISSION_ENTITY(vehicle, true, true);

eg how to use:
SET_ENTITY_AS_MISSION_ENTITY(vehicle, true, true);
DELETE_VEHICLE(&amp;vehicle);

Deletes the specified vehicle, then sets the handle pointed to by the pointer to NULL.
```

> 0x7D6F9A3EF26136A0 0xBB54ECCA

void 0x7D6F9A3EF26136A0(Vehicle vehicle, BOOL p1, BOOL p2)

```
what does this native do?

Here's some pseudocode of the internal setter function:

__int64 __fastcall sub_140CD86B4(signed int vehicle, char a2, char a3)
{
  char v3; // di@1
  char v4; // bl@1
  __int64 result; // rax@1
  __int16 v6; // cx@3

  v3 = a3;
  v4 = a2;
  result = GetScriptHandleAddressVehicleCheck(vehicle);
  if ( result )
  {
    if ( v3 || (v6 = *(_WORD *)(result + 0xDA), (v6 &amp; 0xFu) - 6 &lt;= 1) )
    {
      *(_BYTE *)(result + 0x89B) &amp;= 0xDFu;
      *(_BYTE *)(result + 0x89B) |= 32 * (v4 &amp; 1);
    }
  }
  return result;
}

Now it's time for you to find out :P
```

> SET_VEHICLE_ALLOW_NO_PASSENGERS_LOCKON - 0x5D14D4154BFE7B2C 0x8BAAC437

void SET_VEHICLE_ALLOW_NO_PASSENGERS_LOCKON(Vehicle veh, BOOL p1)

```
Makes the vehicle accept no passengers.
```

> 0xE6B0E8CFC3633BF0 0xFBDE9FD8

int 0xE6B0E8CFC3633BF0(Vehicle vehicle)

```
GET_VEHICLE_*
```

> IS_VEHICLE_MODEL - 0x423E8DE37D934D89 0x013B10B6

BOOL IS_VEHICLE_MODEL(Vehicle vehicle, Hash model)



> DOES_SCRIPT_VEHICLE_GENERATOR_EXIST - 0xF6086BC836400876 0xF6BDDA30

BOOL DOES_SCRIPT_VEHICLE_GENERATOR_EXIST(int vehicleGenerator)



> CREATE_SCRIPT_VEHICLE_GENERATOR - 0x9DEF883114668116 0x25A9A261

int CREATE_SCRIPT_VEHICLE_GENERATOR(float x, float y, float z, float heading, float p4, float p5, Hash modelHash, int p7, int p8, int p9, int p10, BOOL p11, BOOL p12, BOOL p13, BOOL p14, BOOL p15, int p16)

```
Creates a script vehicle generator at the given coordinates. Most parameters after the model hash are unknown.

Parameters:
x/y/z - Generator position
heading - Generator heading
p4 - Unknown (always 5.0)
p5 - Unknown (always 3.0)
modelHash - Vehicle model hash
p7/8/9/10 - Unknown (always -1)
p11 - Unknown (usually TRUE, only one instance of FALSE)
p12/13 - Unknown (always FALSE)
p14 - Unknown (usally FALSE, only two instances of TRUE)
p15 - Unknown (always TRUE)
p16 - Unknown (always -1)

Vector3 coords = GET_ENTITY_COORDS(PLAYER_PED_ID(), 0);	CREATE_SCRIPT_VEHICLE_GENERATOR(coords.x, coords.y, coords.z, 1.0f, 5.0f, 3.0f, GET_HASH_KEY('adder'), -1. -1, -1, -1, -1, true, false, false, false, true, -1);
```

> DELETE_SCRIPT_VEHICLE_GENERATOR - 0x22102C9ABFCF125D 0xE4328E3F

void DELETE_SCRIPT_VEHICLE_GENERATOR(int vehicleGenerator)



> SET_SCRIPT_VEHICLE_GENERATOR - 0xD9D620E0AC6DC4B0 0x40D73747

void SET_SCRIPT_VEHICLE_GENERATOR(Any vehicleGenerator, BOOL enabled)

```
Only called once in the decompiled scripts. Presumably activates the specified generator.
```

> SET_ALL_VEHICLE_GENERATORS_ACTIVE_IN_AREA - 0xC12321827687FE4D 0xB4E0E69A

void SET_ALL_VEHICLE_GENERATORS_ACTIVE_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, BOOL p6, BOOL p7)



> SET_ALL_VEHICLE_GENERATORS_ACTIVE - 0x34AD89078831A4BC 0xAB1FDD76

void SET_ALL_VEHICLE_GENERATORS_ACTIVE()



> SET_ALL_LOW_PRIORITY_VEHICLE_GENERATORS_ACTIVE - 0x608207E7A8FB787C 0x87F767F2

void SET_ALL_LOW_PRIORITY_VEHICLE_GENERATORS_ACTIVE(BOOL active)



> 0x9A75585FB2E54FAD 0x935A95DA

void 0x9A75585FB2E54FAD(float p0, float p1, float p2, float p3)

```
Example gotten from chinese2.c4
    VEHICLE::_9A75585FB2E54FAD(2004.4471435546875, 3076.806640625, 46.60689926147461, 10.0);


```

> 0x0A436B8643716D14 0x6C73E45A

void 0x0A436B8643716D14()



> SET_VEHICLE_ON_GROUND_PROPERLY - 0x49733E92263139D1 0xE14FDBA6

BOOL SET_VEHICLE_ON_GROUND_PROPERLY(Vehicle vehicle)

```
Sets a vehicle on the ground on all wheels.  Returns whether or not the operation was successful.

sfink: This has an additional param(Vehicle vehicle, float p1) which is always set to 5.0f in the b944 scripts.
```

> SET_ALL_VEHICLES_SPAWN - 0xE023E8AC4EF7C117 0xA0909ADB

Any SET_ALL_VEHICLES_SPAWN(Vehicle p0, BOOL p1, BOOL p2, BOOL p3)

```
Most likely a hash collision
```

> IS_VEHICLE_STUCK_ON_ROOF - 0xB497F06B288DCFDF 0x18D07C6C

BOOL IS_VEHICLE_STUCK_ON_ROOF(Vehicle vehicle)



> ADD_VEHICLE_UPSIDEDOWN_CHECK - 0xB72E26D81006005B 0x3A13D384

void ADD_VEHICLE_UPSIDEDOWN_CHECK(Vehicle vehicle)



> REMOVE_VEHICLE_UPSIDEDOWN_CHECK - 0xC53EB42A499A7E90 0xF390BA1B

void REMOVE_VEHICLE_UPSIDEDOWN_CHECK(Vehicle vehicle)



> IS_VEHICLE_STOPPED - 0x5721B434AD84D57A 0x655F072C

BOOL IS_VEHICLE_STOPPED(Vehicle vehicle)

```
Returns true if the vehicle's current speed is less than, or equal to 0.0025f.
```

> GET_VEHICLE_NUMBER_OF_PASSENGERS - 0x24CB2137731FFE89 0x1EF20849

int GET_VEHICLE_NUMBER_OF_PASSENGERS(Vehicle vehicle)

```
Gets the number of passengers, NOT including the driver. Use IS_VEHICLE_SEAT_FREE(Vehicle, -1) to also check for the driver
```

> GET_VEHICLE_MAX_NUMBER_OF_PASSENGERS - 0xA7C4F2C6E744A550 0x0A2FC08C

int GET_VEHICLE_MAX_NUMBER_OF_PASSENGERS(Vehicle vehicle)



> _GET_VEHICLE_MODEL_MAX_NUMBER_OF_PASSENGERS - 0x2AD93716F184EDA4 0x838F7BF7

int _GET_VEHICLE_MODEL_MAX_NUMBER_OF_PASSENGERS(Hash modelHash)

```
Returns max number of passengers (including the driver) for the specified vehicle model.

For a full list, see here: pastebin.com/MdETCS1j
```

> 0xF7F203E31F96F6A1 0x769E5CF2

BOOL 0xF7F203E31F96F6A1(Vehicle vehicle, BOOL flag)

```
IS_S*
```

> 0xE33FFA906CE74880 

BOOL 0xE33FFA906CE74880(Vehicle vehicle, Any p1)

```
IS_*
```

> SET_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME - 0x245A6883D966D537 0xF4187E51

void SET_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME(float multiplier)

```
� Usage

> Use this native inside a looped function.
> Values:
   > 0.0 = no vehicles on streets
   > 1.0 = normal vehicles on streets




```

> SET_RANDOM_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME - 0xB3B3359379FE77D3 0x543F712B

void SET_RANDOM_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME(float multiplier)



> SET_PARKED_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME - 0xEAE6DCC7EEE3DB1D 0xDD46CEBE

void SET_PARKED_VEHICLE_DENSITY_MULTIPLIER_THIS_FRAME(float multiplier)



> 0xD4B8E3D1917BC86B 0x09462665

void 0xD4B8E3D1917BC86B(BOOL toggle)



> 0x90B6DA738A9A25DA 0xDAE2A2BE

void 0x90B6DA738A9A25DA(float value)

```
MulleDK19: Judging from the effect, this is some sort of vehicle density multiplier.
```

> SET_FAR_DRAW_VEHICLES - 0x26324F33423F3CC3 0x9F019C49

void SET_FAR_DRAW_VEHICLES(BOOL toggle)



> SET_NUMBER_OF_PARKED_VEHICLES - 0xCAA15F13EBD417FF 0x206A58E8

Any SET_NUMBER_OF_PARKED_VEHICLES(int value)



> SET_VEHICLE_DOORS_LOCKED - 0xB664292EAECF7FA6 0x4CDD35D0

void SET_VEHICLE_DOORS_LOCKED(Vehicle vehicle, int doorLockStatus)

```
0 - CARLOCK_NONE
1 - CARLOCK_UNLOCKED
2 - CARLOCK_LOCKED (locked)
3 - CARLOCK_LOCKOUT_PLAYER_ONLY
4 - CARLOCK_LOCKED_PLAYER_INSIDE (can get in, can't leave)

(maybe, these are leftovers from GTA:VC)
5 - CARLOCK_LOCKED_INITIALLY
6 - CARLOCK_FORCE_SHUT_DOORS
7 - CARLOCK_LOCKED_BUT_CAN_BE_DAMAGED

(source: GTA VC miss2 leak, matching constants for 0/2/4, testing)
```

> SET_PED_TARGETTABLE_VEHICLE_DESTROY - 0xBE70724027F85BCD 0xD61D182D

void SET_PED_TARGETTABLE_VEHICLE_DESTROY(Vehicle vehicle, int vehicleComponent, int destroyType)

```
destroyType is 1 for opens on damage, 2 for breaks on damage.
```

> DISABLE_VEHICLE_IMPACT_EXPLOSION_ACTIVATION - 0xD8050E0EB60CF274 0xC54156A9

void DISABLE_VEHICLE_IMPACT_EXPLOSION_ACTIVATION(Vehicle vehicle, BOOL toggle)

```
if set to true, prevents vehicle sirens from having sound, leaving only the lights.

HASH COLLISION !!! Please change to _SET_VEHICLE_SIREN_SOUND
```

> SET_VEHICLE_DOORS_LOCKED_FOR_PLAYER - 0x517AAF684BB50CD1 0x49829236

void SET_VEHICLE_DOORS_LOCKED_FOR_PLAYER(Vehicle vehicle, Player player, BOOL toggle)



> GET_VEHICLE_DOORS_LOCKED_FOR_PLAYER - 0xF6AF6CB341349015 0x1DC50247

BOOL GET_VEHICLE_DOORS_LOCKED_FOR_PLAYER(Vehicle vehicle, Player player)



> SET_VEHICLE_DOORS_LOCKED_FOR_ALL_PLAYERS - 0xA2F80B8D040727CC 0x891BA8A4

void SET_VEHICLE_DOORS_LOCKED_FOR_ALL_PLAYERS(Vehicle vehicle, BOOL toggle)

```
After some analysis, I've decided that these are what the parameters are.

We can see this being used in R* scripts such as 'am_mp_property_int.ysc.c4':
l_11A1 = PED::GET_VEHICLE_PED_IS_IN(PLAYER::PLAYER_PED_ID(), 1);
...
VEHICLE::SET_VEHICLE_DOORS_LOCKED_FOR_ALL_PLAYERS(l_11A1, 1);
```

> 0x9737A37136F07E75 0xE4EF6514

void 0x9737A37136F07E75(Vehicle vehicle, BOOL toggle)

```
SET_VEHICLE_DOORS_LOCKED_FOR_*
```

> SET_VEHICLE_DOORS_LOCKED_FOR_TEAM - 0xB81F6D4A8F5EEBA8 0x4F85E783

void SET_VEHICLE_DOORS_LOCKED_FOR_TEAM(Vehicle vehicle, int team, BOOL toggle)



> EXPLODE_VEHICLE - 0xBA71116ADF5B514C 0xBEDEACEB

void EXPLODE_VEHICLE(Vehicle vehicle, BOOL isAudible, BOOL isInvisible)

```
Explodes a selected vehicle.

Vehicle vehicle = Vehicle you want to explode.
BOOL isAudible = If explosion makes a sound.
BOOL isInvisible = If the explosion is invisible or not.

~ISOFX

First BOOL does not give any visual explosion, the vehicle just falls apart completely but slowly and starts to burn.
```

> SET_VEHICLE_OUT_OF_CONTROL - 0xF19D095E42D430CC 0x3764D734

void SET_VEHICLE_OUT_OF_CONTROL(Vehicle vehicle, BOOL killDriver, BOOL explodeOnImpact)

```
Tested on the player's current vehicle. Unless you kill the driver, the vehicle doesn't loose control, however, if enabled, explodeOnImpact is still active. The moment you crash, boom.
```

> SET_VEHICLE_TIMED_EXPLOSION - 0x2E0A74E1002380B1 0xDB8CB8E2

void SET_VEHICLE_TIMED_EXPLOSION(Vehicle vehicle, Ped ped, BOOL toggle)

```
                                                VEHICLE::SET_VEHICLE_TIMED_EXPLOSION(v_3, PLAYER::GET_PLAYER_PED(v_5), 1);
```

> 0x99AD4CCCB128CBC9 0x811373DE

void 0x99AD4CCCB128CBC9(Any p0)



> 0x6ADAABD3068C5235 0xA4E69134

Any 0x6ADAABD3068C5235()



> 0xEF49CF0270307CBE 0x65255524

void 0xEF49CF0270307CBE()



> 0xAE3FEE8709B39DCB 0xE39DAF36

BOOL 0xAE3FEE8709B39DCB(Any p0)



> SET_TAXI_LIGHTS - 0x598803E85E8448D9 0x68639D85

void SET_TAXI_LIGHTS(Vehicle vehicle, BOOL state)

```
This is not tested - it's just an assumption.
- Nac

Doesn't seem to work.  I'll try with an int instead. --JT

Read the scripts, im dumpass. 

                            if (!VEHICLE::IS_TAXI_LIGHT_ON(l_115)) {
                                VEHICLE::SET_TAXI_LIGHTS(l_115, 1);
                            }
```

> IS_TAXI_LIGHT_ON - 0x7504C0F113AB50FC 0x6FC4924A

BOOL IS_TAXI_LIGHT_ON(Vehicle vehicle)



> IS_VEHICLE_IN_GARAGE_AREA - 0xCEE4490CD57BB3C2 0xA90EC257

BOOL IS_VEHICLE_IN_GARAGE_AREA(char* garageName, Vehicle vehicle)

```
garageName example 'Michael - Beverly Hills'

For a full list, see here: pastebin.com/73VfwsmS
```

> SET_VEHICLE_COLOURS - 0x4F1D4BE3A7F24601 0x57F24253

void SET_VEHICLE_COLOURS(Vehicle vehicle, int colorPrimary, int colorSecondary)

```
colorPrimary &amp; colorSecondary are the paint index for the vehicle.
For a list of valid paint indexes, view: pastebin.com/pwHci0xK
-------------------------------------------------------------------------
Use this to get the number of color indices: pastebin.com/RQEeqTSM
Note: minimum color index is 0, maximum color index is (numColorIndices - 1)
```

> SET_VEHICLE_FULLBEAM - 0x8B7FD87F0DDB421E 0x9C49CC15

void SET_VEHICLE_FULLBEAM(Vehicle vehicle, BOOL toggle)

```
It switch to highbeam when p1 is set to true.
```

> STEER_UNLOCK_BIAS - 0x07116E24E9D1929D 0xA59E3DCD

void STEER_UNLOCK_BIAS(Vehicle vehicle, BOOL toggle)

```
This seems like a hash collision?

p1 (toggle) was always 1 (true) except in one case in the b678 scripts.
```

> SET_VEHICLE_CUSTOM_PRIMARY_COLOUR - 0x7141766F91D15BEA 0x8DF9F9BC

void SET_VEHICLE_CUSTOM_PRIMARY_COLOUR(Vehicle vehicle, int r, int g, int b)

```
p1, p2, p3 are RGB values for color (255,0,0 for Red, ect)
```

> GET_VEHICLE_CUSTOM_PRIMARY_COLOUR - 0xB64CF2CCA9D95F52 0x1C2B9FEF

void GET_VEHICLE_CUSTOM_PRIMARY_COLOUR(Vehicle vehicle, int* r, int* g, int* b)



> CLEAR_VEHICLE_CUSTOM_PRIMARY_COLOUR - 0x55E1D2758F34E437 0x51E1E33D

Any CLEAR_VEHICLE_CUSTOM_PRIMARY_COLOUR(Vehicle vehicle)



> GET_IS_VEHICLE_PRIMARY_COLOUR_CUSTOM - 0xF095C0405307B21B 0xD7EC8760

BOOL GET_IS_VEHICLE_PRIMARY_COLOUR_CUSTOM(Vehicle vehicle)



> SET_VEHICLE_CUSTOM_SECONDARY_COLOUR - 0x36CED73BFED89754 0x9D77259E

void SET_VEHICLE_CUSTOM_SECONDARY_COLOUR(Vehicle vehicle, int r, int g, int b)

```
p1, p2, p3 are RGB values for color (255,0,0 for Red, ect)
```

> GET_VEHICLE_CUSTOM_SECONDARY_COLOUR - 0x8389CD56CA8072DC 0x3FF247A2

void GET_VEHICLE_CUSTOM_SECONDARY_COLOUR(Vehicle vehicle, int* r, int* g, int* b)



> CLEAR_VEHICLE_CUSTOM_SECONDARY_COLOUR - 0x5FFBDEEC3E8E2009 0x7CE00B29

Any CLEAR_VEHICLE_CUSTOM_SECONDARY_COLOUR(Vehicle vehicle)



> GET_IS_VEHICLE_SECONDARY_COLOUR_CUSTOM - 0x910A32E7AAD2656C 0x288AD228

BOOL GET_IS_VEHICLE_SECONDARY_COLOUR_CUSTOM(Vehicle vehicle)

```
Check if Vehicle Secondary is avaliable for customize
```

> _SET_VEHICLE_PAINT_FADE - 0x3AFDC536C3D01674 0x8332730C

void _SET_VEHICLE_PAINT_FADE(Vehicle veh, float fade)

```
formerly known as _SET_VEHICLE_PAINT_FADE

The parameter fade is a value from 0-1, where 0 is fresh paint.
------------------------------------------------------------------------------------
The actual value isn't stored as a float but as an unsigned char (BYTE). More info here: pastebin.com/r0h6EM5s
```

> _GET_VEHICLE_PAINT_FADE - 0xA82819CAC9C4C403 0xD5F1EEE1

float _GET_VEHICLE_PAINT_FADE(Vehicle veh)

```
formerly known as _GET_VEHICLE_PAINT_FADE

The result is a value from 0-1, where 0 is fresh paint.
-----------------------------------------------------------------------
The actual value isn't stored as a float but as an unsigned char (BYTE).
```

> SET_CAN_RESPRAY_VEHICLE - 0x52BBA29D5EC69356 0x37677590

void SET_CAN_RESPRAY_VEHICLE(Vehicle vehicle, BOOL state)

```
Hardcoded to not work in multiplayer.
```

> 0x33506883545AC0DF 0x54E9EE75

void 0x33506883545AC0DF(Vehicle vehicle, BOOL p1)



> _JITTER_VEHICLE - 0xC59872A5134879C7 0x4A46E814

void _JITTER_VEHICLE(Vehicle vehicle, BOOL p1, float yaw, float pitch, float roll)

```
When I called this with what the script was doing, which was -190f for yaw pitch and roll, all my car did was jitter a little. I also tried 0 and 190f. I altered the p1 variable between TRUE and FALSE and didn't see a difference.

This might have something to do with the physbox of the vehicle, but I'm not sure.
```

> SET_BOAT_ANCHOR - 0x75DBEC174AEEAD10 0xA3906284

void SET_BOAT_ANCHOR(Vehicle vehicle, BOOL toggle)



> _GET_BOAT_ANCHOR - 0x26C10ECBDA5D043B 

BOOL _GET_BOAT_ANCHOR(Vehicle vehicle)

```
Console Hash: 0xE97A4F5E
```

> 0xE3EBAAE484798530 0x0ED84792

void 0xE3EBAAE484798530(Vehicle vehicle, BOOL p1)

```
No observed effect.
```

> 0xB28B1FE5BFADD7F5 0xA739012A

void 0xB28B1FE5BFADD7F5(Vehicle vehicle, BOOL p1)

```
No observed effect.
```

> 0xE842A9398079BD82 0x66FA450C

void 0xE842A9398079BD82(Vehicle vehicle, float p1)

```
Vehicle must be a boat.
```

> 0x8F719973E1445BA2 0x35614622

void 0x8F719973E1445BA2(Vehicle vehicle, BOOL p1)

```
No observed effect.
```

> SET_VEHICLE_SIREN - 0xF4924635A19EB37D 0x4AC1EFC7

void SET_VEHICLE_SIREN(Vehicle vehicle, BOOL toggle)

```
Activate siren on vehicle (Only works if the vehicle has a siren).
```

> IS_VEHICLE_SIREN_ON - 0x4C9BF537BE2634B2 0x25EB5873

BOOL IS_VEHICLE_SIREN_ON(Vehicle vehicle)



> _IS_VEHICLE_SIREN_SOUND_ON - 0xB5CC40FBCB586380 

BOOL _IS_VEHICLE_SIREN_SOUND_ON(Vehicle vehicle)



> SET_VEHICLE_STRONG - 0x3E8C8727991A8A0B 0xC758D19F

void SET_VEHICLE_STRONG(Vehicle vehicle, BOOL toggle)

```
If set to true, vehicle will not take crash damage, but is still susceptible to damage from bullets and explosives
```

> REMOVE_VEHICLE_STUCK_CHECK - 0x8386BFB614D06749 0x81594917

void REMOVE_VEHICLE_STUCK_CHECK(Any p0)



> GET_VEHICLE_COLOURS - 0xA19435F193E081AC 0x40D82D88

void GET_VEHICLE_COLOURS(Vehicle vehicle, int* colorPrimary, int* colorSecondary)



> IS_VEHICLE_SEAT_FREE - 0x22AC59A870E6A669 0xDAF42B02

BOOL IS_VEHICLE_SEAT_FREE(Vehicle vehicle, int seatIndex)

```
Check if a vehicle seat is free.
-1 being the driver seat.
Use GET_VEHICLE_MAX_NUMBER_OF_PASSENGERS(vehicle) - 1 for last seat index.
```

> GET_PED_IN_VEHICLE_SEAT - 0xBB40DD2270B65366 0x388FDE9A

Ped GET_PED_IN_VEHICLE_SEAT(Vehicle vehicle, int index)

```
-1 (driver) &lt;= index &lt; GET_VEHICLE_MAX_NUMBER_OF_PASSENGERS(vehicle)
```

> GET_LAST_PED_IN_VEHICLE_SEAT - 0x83F969AA1EE2A664 0xF7C6792D

Ped GET_LAST_PED_IN_VEHICLE_SEAT(Vehicle vehicle, int seatIndex)



> GET_VEHICLE_LIGHTS_STATE - 0xB91B4C20085BD12F 0x7C278621

BOOL GET_VEHICLE_LIGHTS_STATE(Vehicle vehicle, BOOL* lightsOn, BOOL* highbeamsOn)



> IS_VEHICLE_TYRE_BURST - 0xBA291848A0815CA9 0x48C80210

BOOL IS_VEHICLE_TYRE_BURST(Vehicle vehicle, int wheelID, BOOL completely)

```
wheelID used for 4 wheelers seem to be (0, 1, 4, 5)
completely - is to check if tire completely gone from rim.

*JulioNIB
'0 = wheel_lf / bike, plane or jet front
'1 = wheel_rf
'2 = wheel_lm / in 6 wheels trailer, plane or jet is first one on left
'3 = wheel_rm / in 6 wheels trailer, plane or jet is first one on right
'4 = wheel_lr / bike rear / in 6 wheels trailer, plane or jet is last one on left
'5 = wheel_rr / in 6 wheels trailer, plane or jet is last one on right
'45 = 6 wheels trailer mid wheel left
'47 = 6 wheels trailer mid wheel right
```

> SET_VEHICLE_FORWARD_SPEED - 0xAB54A438726D25D5 0x69880D14

void SET_VEHICLE_FORWARD_SPEED(Vehicle vehicle, float speed)

```
SCALE: Setting the speed to 30 would result in a speed of roughly 60mph, according to speedometer.

Speed is in meters per second
You can convert meters/s to mph here:
http://www.calculateme.com/Speed/MetersperSecond/ToMilesperHour.htm
```

> _SET_VEHICLE_HALT - 0x260BE8F09E326A20 0xCBC7D3C8

void _SET_VEHICLE_HALT(Vehicle vehicle, float distance, int killEngine, BOOL unknown)

```
This native makes the vehicle stop immediately, as happens when we enter a MP garage.

. distance defines how far it will travel until stopping. Garage doors use 3.0.

. If killEngine is set to 1, you cannot resume driving the vehicle once it stops. This looks like is a bitmapped integer.
```

> 0x37EBBF3117BD6A25 0x943A6CFC

void 0x37EBBF3117BD6A25(Vehicle vehicle, float p1)

```
Sets some values in a vehicle gadget (tow arm, digger arm, etc.). Don't know which one though.
```

> SET_PED_ENABLED_BIKE_RINGTONE - 0x57715966069157AD 0x7FB25568

BOOL SET_PED_ENABLED_BIKE_RINGTONE(Vehicle vehicle, Any p1)

```
This is a hash collision...

_IS_VEHICLE_NEAR_ENTITY
```

> 0x62CA17B74C435651 0x593143B9

BOOL 0x62CA17B74C435651(Vehicle vehicle)



> 0x375E7FC44F21C8AB 0x70DD5E25

Vehicle 0x375E7FC44F21C8AB(Object object)

```
Get the vehicle attached to the object/entity? May also just convert it to a vehicle, but I'm not sure.
```

> 0x89D630CF5EA96D23 0xFBF5536A

BOOL 0x89D630CF5EA96D23(Vehicle vehicle, Any p1)



> 0x6A98C2ECF57FA5D4 0x20AB5783

void 0x6A98C2ECF57FA5D4(Vehicle vehicle, Any p1)



> 0x7C0043FDFF6436BC 0x0F11D01F

void 0x7C0043FDFF6436BC(Vehicle vehicle)



> 0x8AA9180DE2FEDD45 0xAE040377

void 0x8AA9180DE2FEDD45(Vehicle vehicle, BOOL p1)



> 0x0A6A279F3AA4FD70 0x4C0E4031

void 0x0A6A279F3AA4FD70(Vehicle vehicle, BOOL p1)



> 0x634148744F385576 0x6346B7CC

BOOL 0x634148744F385576(Vehicle vehicle)



> 0xE6F13851780394DA 0xCCB41A55

void 0xE6F13851780394DA(Vehicle vehicle, float p1)



> SET_VEHICLE_TYRE_BURST - 0xEC6A202EE4960385 0x89D28068

void SET_VEHICLE_TYRE_BURST(Vehicle vehicle, int index, BOOL onRim, float p3)

```
'To burst tyres VEHICLE::SET_VEHICLE_TYRE_BURST(vehicle, 0, true, 1000.0)
to burst all tyres type it 8 times where p1 = 0 to 7.

p3 seems to be how much damage it has taken. 0 doesn't deflate them, 1000 completely deflates them.

*JulioNIB
'0 = wheel_lf / bike, plane or jet front
'1 = wheel_rf
'2 = wheel_lm / in 6 wheels trailer, plane or jet is first one on left
'3 = wheel_rm / in 6 wheels trailer, plane or jet is first one on right
'4 = wheel_lr / bike rear / in 6 wheels trailer, plane or jet is last one on left
'5 = wheel_rr / in 6 wheels trailer, plane or jet is last one on right
'45 = 6 wheels trailer mid wheel left
'47 = 6 wheels trailer mid wheel right
```

> SET_VEHICLE_DOORS_SHUT - 0x781B3D62BB013EF5 0xBB1FF6E7

void SET_VEHICLE_DOORS_SHUT(Vehicle vehicle, BOOL closeInstantly)

```
Closes all doors of a vehicle:
```

> SET_VEHICLE_TYRES_CAN_BURST - 0xEB9DC3C7D8596C46 0xA198DB54

void SET_VEHICLE_TYRES_CAN_BURST(Vehicle vehicle, BOOL toggle)

```
Allows you to toggle bulletproof tires.
```

> GET_VEHICLE_TYRES_CAN_BURST - 0x678B9BB8C3F58FEB 0x4D76CD2F

BOOL GET_VEHICLE_TYRES_CAN_BURST(Vehicle vehicle)



> SET_VEHICLE_WHEELS_CAN_BREAK - 0x29B18B4FD460CA8F 0x829ED654

Any SET_VEHICLE_WHEELS_CAN_BREAK(Vehicle vehicle, BOOL enabled)



> SET_VEHICLE_DOOR_OPEN - 0x7C65DAC73C35C862 0xBB75D38B

void SET_VEHICLE_DOOR_OPEN(Vehicle vehicle, int doorIndex, BOOL loose, BOOL openInstantly)

```
doorIndex:
0 = Front Left Door
1 = Front Right Door
2 = Back Left Door
3 = Back Right Door
4 = Hood
5 = Trunk
6 = Back
7 = Back2
```

> REMOVE_VEHICLE_WINDOW - 0xA711568EEDB43069 0xBB8104A3

void REMOVE_VEHICLE_WINDOW(Vehicle vehicle, int windowIndex)

```
windowIndex:
0 = Front Right Window
1 = Front Left Window
2 = Back Right Window
3 = Back Left Window
```

> ROLL_DOWN_WINDOWS - 0x85796B0549DDE156 0x51A16DC6

void ROLL_DOWN_WINDOWS(Vehicle vehicle)

```
Roll down all the windows of the vehicle passed through the first parameter.

-UNBOUND-
```

> ROLL_DOWN_WINDOW - 0x7AD9E6CE657D69E3 0xF840134C

Any ROLL_DOWN_WINDOW(Vehicle vehicle, int windowIndex)

```
windowIndex:
0 = Front Right Window
1 = Front Left Window
2 = Back Right Window
3 = Back Left Window
```

> ROLL_UP_WINDOW - 0x602E548F46E24D59 0x83B7E06A

Any ROLL_UP_WINDOW(Vehicle vehicle, int windowIndex)

```
0 = Front Right Window
1 = Front Left Window
2 = Back Right Window
3 = Back Left Window
```

> SMASH_VEHICLE_WINDOW - 0x9E5B5E4D2CCD2259 0xDDD9A8C2

Any SMASH_VEHICLE_WINDOW(Vehicle vehicle, int index)



> FIX_VEHICLE_WINDOW - 0x772282EBEB95E682 0x6B8E990D

Any FIX_VEHICLE_WINDOW(Vehicle vehicle, int index)



> _DETACH_VEHICLE_WINDSCREEN - 0x6D645D59FB5F5AD3 0xCC95C96B

void _DETACH_VEHICLE_WINDSCREEN(Vehicle vehicle)

```
Detaches the vehicle's windscreen.
For further information, see : gtaforums.com/topic/859570-glass/#entry1068894566
```

> _EJECT_JB700_ROOF - 0xE38CB9D7D39FDBCC 0xFDA7B6CA

void _EJECT_JB700_ROOF(Vehicle vehicle, float x, float y, float z)



> SET_VEHICLE_LIGHTS - 0x34E710FF01247C5A 0xE8930226

void SET_VEHICLE_LIGHTS(Vehicle vehicle, int state)

```
set's if the vehicle has lights or not.
not an on off toggle.
p1 = 0 ;vehicle normal lights, off then lowbeams, then highbeams
p1 = 1 ;vehicle doesn't have lights, always off
p1 = 2 ;vehicle has always on lights
p1 = 3 ;or even larger like 4,5,... normal lights like =1
note1: when using =2 on day it's lowbeam,highbeam
but at night it's lowbeam,lowbeam,highbeam
note2: when using =0 it's affected by day or night for highbeams don't exist in daytime.
```

> 0xC45C27EF50F36ADC 0x4221E435

void 0xC45C27EF50F36ADC(Vehicle vehicle, BOOL p1)



> 0x1FD09E7390A74D54 

void 0x1FD09E7390A74D54(Vehicle vehicle, int p1)

```
p1 can be either 0, 1 or 2.

Determines how vehicle lights behave when toggled.

0 = Default (Lights can be toggled between off, normal and high beams)
1 = Lights Disabled (Lights are fully disabled, cannot be toggled)
2 = Always On (Lights can be toggled between normal and high beams)
```

> SET_VEHICLE_ALARM - 0xCDE5E70C1DDB954C 0x24877D84

void SET_VEHICLE_ALARM(Vehicle vehicle, BOOL state)



> START_VEHICLE_ALARM - 0xB8FF7AB45305C345 0x5B451FF7

Any START_VEHICLE_ALARM(Vehicle vehicle)



> IS_VEHICLE_ALARM_ACTIVATED - 0x4319E335B71FFF34 0xF2630A4C

BOOL IS_VEHICLE_ALARM_ACTIVATED(Vehicle vehicle)



> SET_VEHICLE_INTERIORLIGHT - 0xBC2042F090AF6AD3 0x9AD1FE1E

void SET_VEHICLE_INTERIORLIGHT(Vehicle vehicle, BOOL toggle)



> SET_VEHICLE_LIGHT_MULTIPLIER - 0xB385454F8791F57C 0x48039D6A

void SET_VEHICLE_LIGHT_MULTIPLIER(Vehicle vehicle, float multiplier)

```
multiplier = brightness of head lights.
this value isn't capped afaik.

multiplier = 0.0 no lights
multiplier = 1.0 default game value

```

> ATTACH_VEHICLE_TO_TRAILER - 0x3C7D42D58F770B54 0x2133977F

void ATTACH_VEHICLE_TO_TRAILER(Vehicle vehicle, Vehicle trailer, float radius)



> 0x16B5E274BDE402F8 0x12AC1A16

void 0x16B5E274BDE402F8(Vehicle vehicle, Vehicle trailer, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11)

```
only documented to be continued...
```

> 0x374706271354CB18 0x40C4763F

void 0x374706271354CB18(Vehicle p0, Entity p1, float p2)



> DETACH_VEHICLE_FROM_TRAILER - 0x90532EDF0D2BDD86 0xB5DBF91D

void DETACH_VEHICLE_FROM_TRAILER(Vehicle vehicle)

```
Public Sub detatchTrailer(vh1 As Vehicle)
        Native.Function.Call(Hash.DETACH_VEHICLE_FROM_TRAILER, vh1)
    End Sub
```

> IS_VEHICLE_ATTACHED_TO_TRAILER - 0xE7CF3C4F9F489F0C 0xE142BBCC

BOOL IS_VEHICLE_ATTACHED_TO_TRAILER(Vehicle vehicle)

```
Public Function isVehicleAttachedToTrailer(vh As Vehicle) As Boolean
        Return Native.Function.Call(Of Boolean)(Hash.IS_VEHICLE_ATTACHED_TO_TRAILER, vh)
    End Function
```

> 0x2A8F319B392E7B3F 0xE74E85CE

void 0x2A8F319B392E7B3F(Any p0, float p1)

```
                VEHICLE::_2A8F319B392E7B3F(vehicle, 0.5);

```

> 0x95CF53B3D687F9FA 0x06C47A6F

void 0x95CF53B3D687F9FA(Any p0)

```
in the decompiled scripts, seems to be always called on the vehicle right after being attached to a trailer.
```

> SET_VEHICLE_TYRE_FIXED - 0x6E13FC662B882D1D 0xA42EFA6B

void SET_VEHICLE_TYRE_FIXED(Vehicle vehicle, int tyreIndex)

```
tyreIndex = 0 to 4 on normal vehicles

'0 = wheel_lf / bike, plane or jet front
'1 = wheel_rf
'2 = wheel_lm / in 6 wheels trailer, plane or jet is first one on left
'3 = wheel_rm / in 6 wheels trailer, plane or jet is first one on right
'4 = wheel_lr / bike rear / in 6 wheels trailer, plane or jet is last one on left
'5 = wheel_rr / in 6 wheels trailer, plane or jet is last one on right
'45 = 6 wheels trailer mid wheel left
'47 = 6 wheels trailer mid wheel right
```

> SET_VEHICLE_NUMBER_PLATE_TEXT - 0x95A88F0B409CDA47 0x400F9556

void SET_VEHICLE_NUMBER_PLATE_TEXT(Vehicle vehicle, char* plateText)

```
Sets a vehicle's license plate text.  8 chars maximum.

Example:
Ped playerPed = PLAYER::PLAYER_PED_ID();
Vehicle veh = PED::GET_VEHICLE_PED_IS_USING(playerPed);
char *plateText = 'KING';
VEHICLE::SET_VEHICLE_NUMBER_PLATE_TEXT(veh, plateText);
```

> GET_VEHICLE_NUMBER_PLATE_TEXT - 0x7CE1CCB9B293020E 0xE8522D58

char* GET_VEHICLE_NUMBER_PLATE_TEXT(Vehicle vehicle)

```
Returns the license plate text from a vehicle.  8 chars maximum.
```

> GET_NUMBER_OF_VEHICLE_NUMBER_PLATES - 0x4C4D6B2644F458CB 0xD24BC1AE

int GET_NUMBER_OF_VEHICLE_NUMBER_PLATES()

```
Returns the number of *types* of licence plates, enumerated below in SET_VEHICLE_NUMBER_PLATE_TEXT_INDEX.
```

> SET_VEHICLE_NUMBER_PLATE_TEXT_INDEX - 0x9088EB5A43FFB0A1 0xA1A1890E

void SET_VEHICLE_NUMBER_PLATE_TEXT_INDEX(Vehicle vehicle, int plateIndex)

```
Plates:
Blue/White - 0
Yellow/black - 1
Yellow/Blue - 2
Blue/White2 - 3
Blue/White3 - 4
Yankton - 5
```

> GET_VEHICLE_NUMBER_PLATE_TEXT_INDEX - 0xF11BC2DD9A3E7195 0x499747B6

int GET_VEHICLE_NUMBER_PLATE_TEXT_INDEX(Vehicle vehicle)

```
Returns the PlateType of a vehicle
		Blue_on_White_1 = 3,
		Blue_on_White_2 = 0,
		Blue_on_White_3 = 4,
		Yellow_on_Blue = 2,
		Yellow_on_Black = 1,
		North_Yankton = 5,
```

> SET_RANDOM_TRAINS - 0x80D9F74197EA47D9 0xD461CA7F

void SET_RANDOM_TRAINS(BOOL toggle)



> CREATE_MISSION_TRAIN - 0x63C6CCA8E68AE8C8 0xD4C2EAFD

Vehicle CREATE_MISSION_TRAIN(int variation, float x, float y, float z, BOOL direction)

```
Train models HAVE TO be loaded (requested) before you use this.
For variation 15 - request:

freight
freightcar
freightgrain
freightcont1
freightcont2
freighttrailer


```

> SWITCH_TRAIN_TRACK - 0xFD813BB7DB977F20 0x68BFDD61

Any SWITCH_TRAIN_TRACK(int intersectionId, BOOL state)



> 0x21973BBF8D17EDFA 0xD5774FB7

void 0x21973BBF8D17EDFA(Any p0, Any p1)

```
Only called once inside main_persitant with the parameters, 0 - 120000
```

> DELETE_ALL_TRAINS - 0x736A718577F39C7D 0x83DE7ABF

void DELETE_ALL_TRAINS()



> SET_TRAIN_SPEED - 0xAA0BC91BE0B796E3 0xDFC35E4D

Any SET_TRAIN_SPEED(Vehicle train, float speed)



> SET_TRAIN_CRUISE_SPEED - 0x16469284DB8C62B5 0xB507F51D

Any SET_TRAIN_CRUISE_SPEED(Vehicle train, float speed)



> SET_RANDOM_BOATS - 0x84436EC293B1415F 0xB505BD89

Any SET_RANDOM_BOATS(BOOL toggle)



> SET_GARBAGE_TRUCKS - 0x2AFD795EEAC8D30D 0xD9ABB0FF

Any SET_GARBAGE_TRUCKS(BOOL toggle)



> DOES_VEHICLE_HAVE_STUCK_VEHICLE_CHECK - 0x57E4C39DE5EE8470 0x5D91D9AC

BOOL DOES_VEHICLE_HAVE_STUCK_VEHICLE_CHECK(Vehicle vehicle)

```
Maximum amount of vehicles with vehicle stuck check appears to be 16.
```

> GET_VEHICLE_RECORDING_ID - 0x21543C612379DB3C 0x328D601D

Any GET_VEHICLE_RECORDING_ID(Any p0, Any* p1)



> REQUEST_VEHICLE_RECORDING - 0xAF514CABE74CBF15 0x91AFEFD9

void REQUEST_VEHICLE_RECORDING(Any p0, Any* p1)



> HAS_VEHICLE_RECORDING_BEEN_LOADED - 0x300D614A4C785FC4 0xF52CD7F5

BOOL HAS_VEHICLE_RECORDING_BEEN_LOADED(Any p0, Any* p1)



> REMOVE_VEHICLE_RECORDING - 0xF1160ACCF98A3FC8 0xD3C05B00

void REMOVE_VEHICLE_RECORDING(Any p0, Any* p1)



> 0x92523B76657A517D 0xF31973BB

int 0x92523B76657A517D(Any p0, float p1)



> GET_POSITION_OF_VEHICLE_RECORDING_AT_TIME - 0xD242728AA6F0FBA2 0x7178558D

int GET_POSITION_OF_VEHICLE_RECORDING_AT_TIME(Any p0, float p1, Any* p2)

```
p1 is some kind of tolerance
```

> 0xF0F2103EFAF8CBA7 0x4D1C15C2

Vector3 0xF0F2103EFAF8CBA7(Any p0, float p1)



> GET_ROTATION_OF_VEHICLE_RECORDING_AT_TIME - 0x2058206FBE79A8AD 0xD96DEC68

int GET_ROTATION_OF_VEHICLE_RECORDING_AT_TIME(Any p0, float p1, Any* p2)



> GET_TOTAL_DURATION_OF_VEHICLE_RECORDING_ID - 0x102D125411A7B6E6 0x7116785E

float GET_TOTAL_DURATION_OF_VEHICLE_RECORDING_ID(Any p0)



> GET_TOTAL_DURATION_OF_VEHICLE_RECORDING - 0x0E48D1C262390950 0x5B35EEB7

Any GET_TOTAL_DURATION_OF_VEHICLE_RECORDING(Any p0, Any p1)



> GET_POSITION_IN_RECORDING - 0x2DACD605FC681475 0x7DCD644C

float GET_POSITION_IN_RECORDING(Any p0)



> GET_TIME_POSITION_IN_RECORDING - 0x5746F3A7AB7FE544 0xF8C3E4A2

float GET_TIME_POSITION_IN_RECORDING(Any p0)



> START_PLAYBACK_RECORDED_VEHICLE - 0x3F878F92B3A7A071 0xCF614CA8

void START_PLAYBACK_RECORDED_VEHICLE(Any p0, Any p1, Any* p2, BOOL p3)



> START_PLAYBACK_RECORDED_VEHICLE_WITH_FLAGS - 0x7D80FD645D4DA346 0x4E721AD2

void START_PLAYBACK_RECORDED_VEHICLE_WITH_FLAGS(Any p0, Any p1, Any* p2, Any p3, Any p4, Any p5)



> 0x1F2E4E06DEA8992B 0x01B91CD0

void 0x1F2E4E06DEA8992B(Any p0, BOOL p1)



> STOP_PLAYBACK_RECORDED_VEHICLE - 0x54833611C17ABDEA 0xAE99C57C

void STOP_PLAYBACK_RECORDED_VEHICLE(Any p0)



> PAUSE_PLAYBACK_RECORDED_VEHICLE - 0x632A689BF42301B1 0xCCF54912

void PAUSE_PLAYBACK_RECORDED_VEHICLE(Any p0)



> UNPAUSE_PLAYBACK_RECORDED_VEHICLE - 0x8879EE09268305D5 0x59060F75

void UNPAUSE_PLAYBACK_RECORDED_VEHICLE(Any p0)



> IS_PLAYBACK_GOING_ON_FOR_VEHICLE - 0x1C8A4C2C19E68EEC 0x61F7650D

BOOL IS_PLAYBACK_GOING_ON_FOR_VEHICLE(Any p0)



> IS_PLAYBACK_USING_AI_GOING_ON_FOR_VEHICLE - 0xAEA8FD591FAD4106 0x63022C58

BOOL IS_PLAYBACK_USING_AI_GOING_ON_FOR_VEHICLE(Any p0)



> GET_CURRENT_PLAYBACK_FOR_VEHICLE - 0x42BC05C27A946054 0xA3F44390

Any GET_CURRENT_PLAYBACK_FOR_VEHICLE(Any p0)



> SKIP_TO_END_AND_STOP_PLAYBACK_RECORDED_VEHICLE - 0xAB8E2EDA0C0A5883 0x8DEA18C8

void SKIP_TO_END_AND_STOP_PLAYBACK_RECORDED_VEHICLE(Any p0)



> SET_PLAYBACK_SPEED - 0x6683AB880E427778 0x684E26E4

Any SET_PLAYBACK_SPEED(Any p0, float speed)



> START_PLAYBACK_RECORDED_VEHICLE_USING_AI - 0x29DE5FA52D00428C 0x8DE8E24E

void START_PLAYBACK_RECORDED_VEHICLE_USING_AI(Any p0, Any p1, Any* p2, float p3, Any p4)



> SKIP_TIME_IN_PLAYBACK_RECORDED_VEHICLE - 0x9438F7AD68771A20 0xCF3EFA4B

void SKIP_TIME_IN_PLAYBACK_RECORDED_VEHICLE(Any p0, float p1)



> SET_PLAYBACK_TO_USE_AI - 0xA549C3B37EA28131 0xB536CCD7

void SET_PLAYBACK_TO_USE_AI(Vehicle vehicle, int flag)



> SET_PLAYBACK_TO_USE_AI_TRY_TO_REVERT_BACK_LATER - 0x6E63860BBB190730 0x0C8ABAA4

void SET_PLAYBACK_TO_USE_AI_TRY_TO_REVERT_BACK_LATER(Any p0, Any p1, Any p2, BOOL p3)



> 0x5845066D8A1EA7F7 0x943A58EB

void 0x5845066D8A1EA7F7(Vehicle vehicle, float x, float y, float z, Any p4)



> 0x796A877E459B99EA 0x5C9F477C

void 0x796A877E459B99EA(Any p0, float p1, float p2, float p3)



> 0xFAF2A78061FD9EF4 0xCD83C393

void 0xFAF2A78061FD9EF4(Any p0, float p1, float p2, float p3)



> 0x063AE2B2CC273588 0x2EF8435C

void 0x063AE2B2CC273588(Any p0, BOOL p1)



> EXPLODE_VEHICLE_IN_CUTSCENE - 0x786A4EB67B01BF0B 0xA85207B5

void EXPLODE_VEHICLE_IN_CUTSCENE(Vehicle p0, BOOL p1)



> ADD_VEHICLE_STUCK_CHECK_WITH_WARP - 0x2FA9923062DD396C 0xC8B789AD

void ADD_VEHICLE_STUCK_CHECK_WITH_WARP(Any p0, float p1, Any p2, BOOL p3, BOOL p4, BOOL p5, Any p6)



> SET_VEHICLE_MODEL_IS_SUPPRESSED - 0x0FC2D89AC25A5814 0x42A08C9B

void SET_VEHICLE_MODEL_IS_SUPPRESSED(Hash model, BOOL suppressed)

```
seems to make the vehicle stop spawning naturally in traffic. Here's an essential example:

VEHICLE::SET_VEHICLE_MODEL_IS_SUPPRESSED(GAMEPLAY::GET_HASH_KEY('taco'), true);

god I hate taco vans

Confirmed to work? Needs to be looped? Can not get it to work.
```

> GET_RANDOM_VEHICLE_IN_SPHERE - 0x386F6CE5BAF6091C 0x57216D03

Vehicle GET_RANDOM_VEHICLE_IN_SPHERE(float x, float y, float z, float radius, Hash modelHash, int flags)

```
Gets a random vehicle in a sphere at the specified position, of the specified radius.

x: The X-component of the position of the sphere.
y: The Y-component of the position of the sphere.
z: The Z-component of the position of the sphere.
radius: The radius of the sphere. Max is 9999.9004.
modelHash: The vehicle model to limit the selection to. Pass 0 for any model.
flags: The bitwise flags that modifies the behaviour of this function.
```

> GET_RANDOM_VEHICLE_FRONT_BUMPER_IN_SPHERE - 0xC5574E0AEB86BA68 0xDCADEB66

Vehicle GET_RANDOM_VEHICLE_FRONT_BUMPER_IN_SPHERE(float p0, float p1, float p2, float p3, int p4, int p5, int p6)



> GET_RANDOM_VEHICLE_BACK_BUMPER_IN_SPHERE - 0xB50807EABE20A8DC 0xD6343F6B

Vehicle GET_RANDOM_VEHICLE_BACK_BUMPER_IN_SPHERE(float p0, float p1, float p2, float p3, int p4, int p5, int p6)



> GET_CLOSEST_VEHICLE - 0xF73EB622C4F1689B 0xD7E26B2C

Vehicle GET_CLOSEST_VEHICLE(float x, float y, float z, float radius, Hash modelHash, int flags)

```
Example usage
VEHICLE::GET_CLOSEST_VEHICLE(x, y, z, radius, hash, unknown leave at 70) 

x, y, z: Position to get closest vehicle to.
radius: Max radius to get a vehicle.
modelHash: Limit to vehicles with this model. 0 for any.
flags: The bitwise flags altering the function's behaviour.

Does not return police cars or helicopters.

It seems to return police cars for me, does not seem to return helicopters, planes or boats for some reason

Only returns non police cars and motorbikes with the flag set to 70 and modelHash to 0. ModelHash seems to always be 0 when not a modelHash in the scripts, as stated above. 

These flags were found in the b617d scripts: 0,2,4,6,7,23,127,260,2146,2175,12294,16384,16386,20503,32768,67590,67711,98309,100359.
Converted to binary, each bit probably represents a flag as explained regarding another native here: gtaforums.com/topic/822314-guide-driving-styles

Conversion of found flags to binary: pastebin.com/kghNFkRi

At exactly 16384 which is 0100000000000000 in binary and 4000 in hexadecimal only planes are returned. 

It's probably more convenient to use worldGetAllVehicles(int *arr, int arrSize) and check the shortest distance yourself and sort if you want by checking the vehicle type with for example VEHICLE::IS_THIS_MODEL_A_BOAT

-------------------------------------------------------------------------

Conclusion: This native is not worth trying to use. Use something like this instead: pastebin.com/xiFdXa7h
```

> GET_TRAIN_CARRIAGE - 0x08AAFD0814722BC3 0x2544E7A6

Entity GET_TRAIN_CARRIAGE(Vehicle train, int carriage)

```
Corrected p1. it's basically the 'carriage/trailer number'. So if the train has 3 trailers you'd call the native once with a var or 3 times with 1, 2, 3.
```

> DELETE_MISSION_TRAIN - 0x5B76B14AE875C795 0x86C9497D

void DELETE_MISSION_TRAIN(Vehicle* train)



> SET_MISSION_TRAIN_AS_NO_LONGER_NEEDED - 0xBBE7648349B49BE8 0x19808560

void SET_MISSION_TRAIN_AS_NO_LONGER_NEEDED(Vehicle* train, BOOL p1)

```
p1 is always 0
```

> SET_MISSION_TRAIN_COORDS - 0x591CA673AA6AB736 0xD6D70803

void SET_MISSION_TRAIN_COORDS(Vehicle train, float x, float y, float z)



> IS_THIS_MODEL_A_BOAT - 0x45A9187928F4B9E3 0x10F6085C

BOOL IS_THIS_MODEL_A_BOAT(Hash model)



> _IS_THIS_MODEL_AN_EMERGENCY_BOAT - 0x9537097412CF75FE 

BOOL _IS_THIS_MODEL_AN_EMERGENCY_BOAT(Hash model)

```
Checks if model is a boat, then checks an additional flag.

Returns true for these models:
PREDATOR
SEASHARK2
SPEEDER
```

> IS_THIS_MODEL_A_PLANE - 0xA0948AB42D7BA0DE 0x3B3907BB

BOOL IS_THIS_MODEL_A_PLANE(Hash model)



> IS_THIS_MODEL_A_HELI - 0xDCE4334788AF94EA 0x8AF7F568

BOOL IS_THIS_MODEL_A_HELI(Hash model)



> IS_THIS_MODEL_A_CAR - 0x7F6DB52EEFC96DF8 0x60E4C22F

BOOL IS_THIS_MODEL_A_CAR(Hash model)

```
To check if the model is an amphibious car, see gtaforums.com/topic/717612-v-scriptnative-documentation-and-research/page-33#entry1069317363 (for build 944 and above only!)
```

> IS_THIS_MODEL_A_TRAIN - 0xAB935175B22E822B 0xF87DCFFD

BOOL IS_THIS_MODEL_A_TRAIN(Hash model)



> IS_THIS_MODEL_A_BIKE - 0xB50C0B0CEDC6CE84 0x7E702CDD

BOOL IS_THIS_MODEL_A_BIKE(Hash model)



> IS_THIS_MODEL_A_BICYCLE - 0xBF94DD42F63BDED2 0x328E6FF5

BOOL IS_THIS_MODEL_A_BICYCLE(Hash model)



> IS_THIS_MODEL_A_QUADBIKE - 0x39DAC362EE65FA28 0xC1625277

BOOL IS_THIS_MODEL_A_QUADBIKE(Hash model)



> SET_HELI_BLADES_FULL_SPEED - 0xA178472EBB8AE60D 0x033A9408

void SET_HELI_BLADES_FULL_SPEED(Vehicle vehicle)

```
Equivalent of SET_HELI_BLADES_SPEED(vehicleHandle, 1.0f);
```

> SET_HELI_BLADES_SPEED - 0xFD280B4D7F3ABC4D 0x5C7D4EA9

void SET_HELI_BLADES_SPEED(Vehicle vehicle, float speed)

```
Sets the speed of the helicopter blades in percentage of the full speed.

vehicleHandle: The helicopter.
speed: The speed in percentage, 0.0f being 0% and 1.0f being 100%.
```

> 0x99CAD8E7AFDB60FA 0x1128A45B

void 0x99CAD8E7AFDB60FA(Vehicle vehicle, float p1, float p2)



> SET_VEHICLE_CAN_BE_TARGETTED - 0x3750146A28097A82 0x64B70B1D

void SET_VEHICLE_CAN_BE_TARGETTED(Vehicle vehicle, BOOL state)

```
This has not yet been tested - it's just an assumption of what the types could be.
```

> 0xDBC631F109350B8C 0x486C1280

void 0xDBC631F109350B8C(Vehicle vehicle, BOOL p1)

```
Related to locking the vehicle or something similar.

In the decompiled scripts, its always called after
VEHICLE::_SET_EXCLUSIVE_DRIVER(a_0, 0, 0);
VEHICLE::SET_VEHICLE_DOORS_LOCKED_FOR_ALL_PLAYERS(a_0, 1);
VEHICLE::SET_VEHICLE_DOORS_LOCKED_FOR_PLAYER(a_0, PLAYER::PLAYER_ID(), 0);
--&gt;VEHICLE::_DBC631F109350B8C(a_0, 1);
```

> SET_VEHICLE_CAN_BE_VISIBLY_DAMAGED - 0x4C7028F78FFD3681 0xC5D94017

void SET_VEHICLE_CAN_BE_VISIBLY_DAMAGED(Vehicle vehicle, BOOL state)



> 0x1AA8A837D2169D94 0x009AB49E

void 0x1AA8A837D2169D94(Vehicle vehicle, BOOL p1)



> 0x2311DD7159F00582 0x758C5E2E

void 0x2311DD7159F00582(Vehicle vehicle, BOOL p1)



> GET_VEHICLE_DIRT_LEVEL - 0x8F17BC8BA08DA62B 0xFD15C065

float GET_VEHICLE_DIRT_LEVEL(Vehicle vehicle)

```
Dirt level 0..15
```

> SET_VEHICLE_DIRT_LEVEL - 0x79D3B596FE44EE8B 0x2B39128B

void SET_VEHICLE_DIRT_LEVEL(Vehicle vehicle, float dirtLevel)

```
You can't use values greater than 15.0
You can see why here: pastebin.com/Wbn34fGD

Also, R* does (float)(rand() % 15) to get a random dirt level when generating a vehicle.
```

> _IS_VEHICLE_DAMAGED - 0xBCDC5017D3CE1E9E 0xDAC523BC

BOOL _IS_VEHICLE_DAMAGED(Vehicle vehicle)

```
Appears to return true if the vehicle has any damage, including cosmetically.
```

> IS_VEHICLE_DOOR_FULLY_OPEN - 0x3E933CFF7B111C22 0xC2385B6F

BOOL IS_VEHICLE_DOOR_FULLY_OPEN(Vehicle vehicle, int doorIndex)

```
doorIndex:
0 = Front Left Door
1 = Front Right Door
2 = Back Left Door
3 = Back Right Door
4 = Hood
5 = Trunk
6 = Trunk2
```

> SET_VEHICLE_ENGINE_ON - 0x2497C4717C8B881E 0x7FBC86F1

void SET_VEHICLE_ENGINE_ON(Vehicle vehicle, BOOL value, BOOL instantly, BOOL otherwise)

```
Starts or stops the engine on the specified vehicle.

vehicle: The vehicle to start or stop the engine on.
value: true to turn the vehicle on; false to turn it off.
instantly: if true, the vehicle will be set to the state immediately; otherwise, the current driver will physically turn on or off the engine.

--------------------------------------
And what's with BOOL otherwise, what does it do???
--------------------------------------
I have no clue what 'otherwise' is either. Xbox360 of course ends at TU27 so that's our latest scripts and every script still only has the first 3 parameters. 
Side Note: It would of been nice though if it was to handle jet engines instead of having that separate native for it.
```

> SET_VEHICLE_UNDRIVEABLE - 0x8ABA6AF54B942B95 0x48D02A4E

void SET_VEHICLE_UNDRIVEABLE(Vehicle vehicle, BOOL toggle)



> SET_VEHICLE_PROVIDES_COVER - 0x5AFEEDD9BB2899D7 0xEFC01CA9

void SET_VEHICLE_PROVIDES_COVER(Vehicle vehicle, BOOL toggle)



> SET_VEHICLE_DOOR_CONTROL - 0xF2BFA0430F0A0FCB 0x572DD360

void SET_VEHICLE_DOOR_CONTROL(Vehicle vehicle, int doorIndex, int p2, float angle)

```
doorIndex:
0 = Front Left Door (driver door)
1 = Front Right Door
2 = Back Left Door
3 = Back Right Door
4 = Hood
5 = Trunk
6 = Trunk2

p2:
mostly use 0 and 1, very rare using 3 and 5

p3:
It seems it is an angle

Example in VB: 
    Public Shared Sub Set_Vehicle_Door_Angle(Vehicle As Vehicle, Door As VehicleDoor, Angle As Single)
        Native.Function.Call(Hash.SET_VEHICLE_DOOR_CONTROL, Vehicle.Handle, Door, 1, Angle)
    End Sub

I'm Not MentaL

sfink: p2 is speed, 5 is fast, 1 is slow 3 is medium
```

> SET_VEHICLE_DOOR_LATCHED - 0xA5A9653A8D2CAF48 0x4EB7BBFC

void SET_VEHICLE_DOOR_LATCHED(Vehicle vehicle, int doorIndex, BOOL p2, BOOL p3, BOOL p4)



> GET_VEHICLE_DOOR_ANGLE_RATIO - 0xFE3F9C29F7B32BD5 0x0E399C26

float GET_VEHICLE_DOOR_ANGLE_RATIO(Vehicle vehicle, int door)

```
example in vb:
    Public Shared Function Get_Vehicle_Door_Angle(Vehicle As Vehicle, Door As VehicleDoor) As Single
        Return Native.Function.Call(Of Single)(Hash.GET_VEHICLE_DOOR_ANGLE_RATIO, Vehicle.Handle, Door)
    End Function

I'm Not MentaL
```

> _GET_PED_USING_VEHICLE_DOOR - 0x218297BF0CFD853B 

Ped _GET_PED_USING_VEHICLE_DOOR(Vehicle vehicle, int doorIndex)

```
MulleDK19: Quick disassembly and test seems to indicate that this native gets the Ped currently using the specified door.
```

> SET_VEHICLE_DOOR_SHUT - 0x93D9BD300D7789E5 0x142606BD

void SET_VEHICLE_DOOR_SHUT(Vehicle vehicle, int doorIndex, BOOL closeInstantly)

```
doorIndex:
0 = Front Left Door
1 = Front Right Door
2 = Back Left Door
3 = Back Right Door
4 = Hood
5 = Trunk
6 = Trunk2
```

> SET_VEHICLE_DOOR_BROKEN - 0xD4D4F6A4AB575A33 0x8147FEA7

void SET_VEHICLE_DOOR_BROKEN(Vehicle vehicle, int doorIndex, BOOL createDoorObject)

```
doorIndex:
0 = Front Right Door
1 = Front Left Door
2 = Back Right Door
3 = Back Left Door
4 = Hood
5 = Trunk

Changed last paramater from CreateDoorObject To NoDoorOnTheFloor because when on false, the door object is created,and not created when on true...the former parameter name was counter intuitive...(by Calderon)

Calderon is a moron.
```

> SET_VEHICLE_CAN_BREAK - 0x59BF8C3D52C92F66 0x90A810D1

void SET_VEHICLE_CAN_BREAK(Vehicle vehicle, BOOL toggle)



> DOES_VEHICLE_HAVE_ROOF - 0x8AC862B0B32C5B80 0xDB817403

BOOL DOES_VEHICLE_HAVE_ROOF(Vehicle vehicle)



> IS_BIG_VEHICLE - 0x9F243D3919F442FE 0x9CDBA8DE

BOOL IS_BIG_VEHICLE(Vehicle vehicle)



> GET_NUMBER_OF_VEHICLE_COLOURS - 0x3B963160CD65D41E 0xF2442EE2

int GET_NUMBER_OF_VEHICLE_COLOURS(Vehicle vehicle)

```
Actually number of color combinations
```

> SET_VEHICLE_COLOUR_COMBINATION - 0x33E8CD3322E2FE31 0xA557AEAD

void SET_VEHICLE_COLOUR_COMBINATION(Vehicle vehicle, int numCombos)

```
dont be a dick
```

> GET_VEHICLE_COLOUR_COMBINATION - 0x6A842D197F845D56 0x77AC1B4C

int GET_VEHICLE_COLOUR_COMBINATION(Vehicle vehicle)



> SET_VEHICLE_IS_CONSIDERED_BY_PLAYER - 0x31B927BBC44156CD 0x14413319

void SET_VEHICLE_IS_CONSIDERED_BY_PLAYER(Vehicle vehicle, BOOL toggle)

```
Setting this to false, makes the specified vehicle to where if you press Y your character doesn't even attempt the animation to enter the vehicle. Hence it's not considered aka ignored.
```

> 0xBE5C1255A1830FF5 0xA6D8D7A5

void 0xBE5C1255A1830FF5(Vehicle vehicle, BOOL p1)



> 0x9BECD4B9FEF3F8A6 0xACAB8FF3

void 0x9BECD4B9FEF3F8A6(Vehicle vehicle, BOOL p1)



> 0x88BC673CA9E0AE99 0xF0E5C41D

void 0x88BC673CA9E0AE99(Vehicle vehicle, BOOL p1)



> 0xE851E480B814D4BA 0x2F98B4B7

void 0xE851E480B814D4BA(Vehicle vehicle, BOOL p1)



> GET_RANDOM_VEHICLE_MODEL_IN_MEMORY - 0x055BF0AC0C34F4FD 0xE2C45631

void GET_RANDOM_VEHICLE_MODEL_IN_MEMORY(BOOL p0, Hash* modelHash, int* p2)

```
Not present in the retail version! It's just a nullsub.

p0 always true (except in one case)
p1 returns a random vehicle hash loaded in memory
p2 unsure, maybe returns a different model
```

> GET_VEHICLE_DOOR_LOCK_STATUS - 0x25BC98A59C2EA962 0x0D72CEF2

int GET_VEHICLE_DOOR_LOCK_STATUS(Vehicle vehicle)



> IS_VEHICLE_DOOR_DAMAGED - 0xB8E181E559464527 0x4999E3C3

BOOL IS_VEHICLE_DOOR_DAMAGED(Vehicle veh, int doorID)

```
doorID starts at 0, not seeming to skip any numbers. Four door vehicles intuitively range from 0 to 3.
```

> _SET_VEHICLE_DOOR_BREAKABLE - 0x2FA133A4A9D37ED8 0x065B92B3

void _SET_VEHICLE_DOOR_BREAKABLE(Vehicle vehicle, int doorIndex, BOOL isBreakable)

```
Keeps Vehicle Doors/Hood/Trunk from breaking off
```

> 0x27B926779DEB502D 0xB3A2CC4F

BOOL 0x27B926779DEB502D(Vehicle vehicle, BOOL p1)



> IS_VEHICLE_BUMPER_BROKEN_OFF - 0x468056A6BB6F3846 0xAF25C027

BOOL IS_VEHICLE_BUMPER_BROKEN_OFF(Vehicle vehicle, BOOL front)



> IS_COP_VEHICLE_IN_AREA_3D - 0x7EEF65D5F153E26A 0xFB16C6D1

BOOL IS_COP_VEHICLE_IN_AREA_3D(float x1, float x2, float y1, float y2, float z1, float z2)

```
Usage:

public bool isCopInRange(Vector3 Location, float Range)
        {
            return Function.Call&lt;bool&gt;(Hash.IS_COP_PED_IN_AREA_3D, Location.X - Range, Location.Y - Range, Location.Z - Range, Location.X + Range, Location.Y + Range, Location.Z + Range);
        }
```

> IS_VEHICLE_ON_ALL_WHEELS - 0xB104CD1BABF302E2 0x10089F8E

BOOL IS_VEHICLE_ON_ALL_WHEELS(Vehicle vehicle)

```
 Public Function isVehicleOnAllWheels(vh As Vehicle) As Boolean
        Return Native.Function.Call(Of Boolean)(Hash.IS_VEHICLE_ON_ALL_WHEELS, vh)
    End Function

```

> GET_VEHICLE_LAYOUT_HASH - 0x28D37D4F71AC5C58 0xE0B35187

Hash GET_VEHICLE_LAYOUT_HASH(Vehicle vehicle)



> 0xA01BC64DD4BFBBAC 

Any 0xA01BC64DD4BFBBAC(Vehicle vehicle, int p1)



> SET_RENDER_TRAIN_AS_DERAILED - 0x317B11A312DF5534 0x899D9092

void SET_RENDER_TRAIN_AS_DERAILED(Vehicle train, BOOL toggle)

```
makes the train all jumbled up and derailed as it moves on the tracks (though that wont stop it from its normal operations)
```

> SET_VEHICLE_EXTRA_COLOURS - 0x2036F561ADD12E33 0x515DB2A0

void SET_VEHICLE_EXTRA_COLOURS(Vehicle vehicle, int pearlescentColor, int wheelColor)

```
They use the same color indexs as SET_VEHICLE_COLOURS.
```

> GET_VEHICLE_EXTRA_COLOURS - 0x3BC4245933A166F7 0x80E4659B

void GET_VEHICLE_EXTRA_COLOURS(Vehicle vehicle, int* pearlescentColor, int* wheelColor)



> STOP_ALL_GARAGE_ACTIVITY - 0x0F87E938BDF29D66 0x17A0BCE5

void STOP_ALL_GARAGE_ACTIVITY()



> SET_VEHICLE_FIXED - 0x115722B1B9C14C1C 0x17469AA1

void SET_VEHICLE_FIXED(Vehicle vehicle)



> SET_VEHICLE_DEFORMATION_FIXED - 0x953DA1E1B12C0491 0xDD2920C8

void SET_VEHICLE_DEFORMATION_FIXED(Vehicle vehicle)



> 0x206BC5DC9D1AC70A 

void 0x206BC5DC9D1AC70A(Vehicle vehicle, BOOL p1)



> 0x51BB2D88D31A914B 0x88F0F7E7

void 0x51BB2D88D31A914B(Vehicle vehicle, BOOL p1)



> 0x192547247864DFDD 0x90D6EE57

void 0x192547247864DFDD(Vehicle vehicle, BOOL p1)



> SET_DISABLE_VEHICLE_PETROL_TANK_FIRES - 0x465BF26AB9684352 0xC40192B5

void SET_DISABLE_VEHICLE_PETROL_TANK_FIRES(Vehicle vehicle, BOOL toggle)



> SET_DISABLE_VEHICLE_PETROL_TANK_DAMAGE - 0x37C8252A7C92D017 0xAD3E05F2

void SET_DISABLE_VEHICLE_PETROL_TANK_DAMAGE(Vehicle vehicle, BOOL toggle)



> 0x91A0BD635321F145 0x1784BA1A

void 0x91A0BD635321F145(Vehicle vehicle, BOOL p1)



> 0xC50CE861B55EAB8B 0x40C323AE

void 0xC50CE861B55EAB8B(Vehicle vehicle, BOOL p1)



> 0x6EBFB22D646FFC18 0x847F1304

void 0x6EBFB22D646FFC18(Vehicle vehicle, BOOL p1)

```
sfink: sets bit in vehicle's structure, used by maintransition, fm_mission_controller, mission_race and a couple of other scripts. see dissassembly: 
CVehicle *__fastcall sub_140CDAA10(signed int a1, char a2)
{
    CVehicle *result; // rax@1

    result = EntityAsCVehicle(a1);
    if ( result )
    {
        result-&gt;field_886 &amp;= 0xEFu;
        result-&gt;field_886 |= 16 * (a2 &amp; 1);
    }
    return result;
}
```

> 0x25367DE49D64CF16 0xCBD98BA1

void 0x25367DE49D64CF16(Vehicle vehicle, BOOL p1)



> REMOVE_VEHICLES_FROM_GENERATORS_IN_AREA - 0x46A1E1A299EC4BBA 0x42CC15E0

void REMOVE_VEHICLES_FROM_GENERATORS_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, Any unk)



> SET_VEHICLE_STEER_BIAS - 0x42A8EC77D5150CBE 0x7357C1EB

void SET_VEHICLE_STEER_BIAS(Vehicle vehicle, float value)

```
Locks the vehicle's steering to the desired angle, explained below.

Requires to be called onTick. Steering is unlocked the moment the function stops being called on the vehicle.

Steer bias:
-1.0 = full right
0.0 = centered steering
1.0 = full left
```

> IS_VEHICLE_EXTRA_TURNED_ON - 0xD2E6822DBFD6C8BD 0x042098B5

BOOL IS_VEHICLE_EXTRA_TURNED_ON(Vehicle vehicle, int extraId)



> SET_VEHICLE_EXTRA - 0x7EE3A3C5E4A40CC9 0x642D065C

void SET_VEHICLE_EXTRA(Vehicle vehicle, int extraId, int toggle)

```
Note: only some vehicle have extras
extra ids are from 1 - 9 depending on the vehicle

-------------------------------------------------

^ not sure if outdated or simply wrong. Max extra ID for b944 is 14

-------------------------------------------------
p2 is not a on/off toggle. mostly 0 means on and 1 means off.
not sure if it really should be a BOOL.
```

> DOES_EXTRA_EXIST - 0x1262D55792428154 0x409411CC

BOOL DOES_EXTRA_EXIST(Vehicle vehicle, int extraId)

```
Checks via CVehicleModelInfo
```

> SET_CONVERTIBLE_ROOF - 0xF39C4F538B5124C2 0xC87B6A51

void SET_CONVERTIBLE_ROOF(Vehicle vehicle, BOOL p1)



> LOWER_CONVERTIBLE_ROOF - 0xDED51F703D0FA83D 0xC5F72EAE

void LOWER_CONVERTIBLE_ROOF(Vehicle vehicle, BOOL instantlyLower)



> RAISE_CONVERTIBLE_ROOF - 0x8F5FB35D7E88FC70 0xA4E4CBA3

void RAISE_CONVERTIBLE_ROOF(Vehicle vehicle, BOOL instantlyRaise)



> GET_CONVERTIBLE_ROOF_STATE - 0xF8C397922FC03F41 0x1B09714D

int GET_CONVERTIBLE_ROOF_STATE(Vehicle vehicle)

```
0 -&gt; up
1 -&gt; lowering down
2 -&gt; down
3 -&gt; raising up
```

> IS_VEHICLE_A_CONVERTIBLE - 0x52F357A30698BCCE 0x6EF54490

BOOL IS_VEHICLE_A_CONVERTIBLE(Vehicle vehicle, BOOL p1)

```
p1 is false almost always.

However, in launcher_carwash/carwash1/carwash2 scripts, p1 is true and is accompanied by DOES_VEHICLE_HAVE_ROOF 
```

> IS_VEHICLE_STOPPED_AT_TRAFFIC_LIGHTS - 0x2959F696AE390A99 0x69200FA4

BOOL IS_VEHICLE_STOPPED_AT_TRAFFIC_LIGHTS(Vehicle vehicle)

```
is this for red lights only?  more testing required. -sob

```

> SET_VEHICLE_DAMAGE - 0xA1DD317EA8FD4F29 0x21B458B2

void SET_VEHICLE_DAMAGE(Vehicle vehicle, float xOffset, float yOffset, float zOffset, float damage, float radius, BOOL p6)

```
Apply damage to vehicle at a location. Location is relative to vehicle model (not world).

Radius of effect damage applied in a sphere at impact location
```

> GET_VEHICLE_ENGINE_HEALTH - 0xC45D23BAF168AAB8 0x8880038A

float GET_VEHICLE_ENGINE_HEALTH(Vehicle vehicle)

```
Returns 1000.0 if the function is unable to get the address of the specified vehicle or if it's not a vehicle.

Minimum: -4000
Maximum: 1000

-4000: Engine is destroyed
0 and below: Engine catches fire and health rapidly declines
300: Engine is smoking and losing functionality
1000: Engine is perfect
```

> SET_VEHICLE_ENGINE_HEALTH - 0x45F6D8EEF34ABEF1 0x1B760FB5

void SET_VEHICLE_ENGINE_HEALTH(Vehicle vehicle, float health)

```
1000 is max health
Begins leaking gas at around 650 health
-999.90002441406 appears to be minimum health, although nothing special occurs
```

> GET_VEHICLE_PETROL_TANK_HEALTH - 0x7D5DABE888D2D074 0xE41595CE

float GET_VEHICLE_PETROL_TANK_HEALTH(Vehicle vehicle)

```
1000 is max health
Begins leaking gas at around 650 health
-999.90002441406 appears to be minimum health, although nothing special occurs
```

> SET_VEHICLE_PETROL_TANK_HEALTH - 0x70DB57649FA8D0D8 0x660A3692

void SET_VEHICLE_PETROL_TANK_HEALTH(Vehicle vehicle, float fix)

```
1000 is max health
Begins leaking gas at around 650 health
-999.90002441406 appears to be minimum health, although nothing special occurs
```

> IS_VEHICLE_STUCK_TIMER_UP - 0x679BE1DAF71DA874 0x2FCF58C1

BOOL IS_VEHICLE_STUCK_TIMER_UP(Vehicle vehicle, int p1, int p2)

```
p1 can be anywhere from 0 to 3 in the scripts. p2 is generally somewhere in the 1000 to 10000 range.
```

> RESET_VEHICLE_STUCK_TIMER - 0xD7591B0065AFAA7A 0xEF2A6016

void RESET_VEHICLE_STUCK_TIMER(Vehicle vehicle, BOOL nullAttributes)

```
nullAttributes is always 0 in the scripts. In IDA it calls a second function that's entirely dependent on the 2nd parameter being true, and all it does is set a bunch of offsets to 0.


MulleDK19: That's not true at all. The second parameter is an int, not a bool. The inner function has a switch on the second parameter. It's the stuck timer index.

Here's some pseudo code I wrote for the inner function:
void __fastcall NATIVE_RESET_VEHICLE_STUCK_TIMER_INNER(CUnknown* unknownClassInVehicle, int timerIndex)
{
	switch (timerIndex)
	{
	case 0:
		unknownClassInVehicle-&gt;FirstStuckTimer = (WORD)0u;
	case 1:
		unknownClassInVehicle-&gt;SecondStuckTimer = (WORD)0u;
	case 2:
		unknownClassInVehicle-&gt;ThirdStuckTimer = (WORD)0u;
	case 3:
		unknownClassInVehicle-&gt;FourthStuckTimer = (WORD)0u;
	case 4:
		unknownClassInVehicle-&gt;FirstStuckTimer = (WORD)0u;
		unknownClassInVehicle-&gt;SecondStuckTimer = (WORD)0u;
		unknownClassInVehicle-&gt;ThirdStuckTimer = (WORD)0u;
		unknownClassInVehicle-&gt;FourthStuckTimer = (WORD)0u;
		break;
	};
}
```

> IS_VEHICLE_DRIVEABLE - 0x4C241E39B23DF959 0x41A7267A

BOOL IS_VEHICLE_DRIVEABLE(Vehicle vehicle, BOOL p1)

```
p1 is always 0 in the scripts.
```

> SET_VEHICLE_HAS_BEEN_OWNED_BY_PLAYER - 0x2B5F9D2AF1F1722D 0xB4D3DBFB

void SET_VEHICLE_HAS_BEEN_OWNED_BY_PLAYER(Vehicle vehicle, BOOL owned)



> SET_VEHICLE_NEEDS_TO_BE_HOTWIRED - 0xFBA550EA44404EE6 0xD8260751

void SET_VEHICLE_NEEDS_TO_BE_HOTWIRED(Vehicle vehicle, BOOL toggle)



> 0x9F3F689B814F2599 

void 0x9F3F689B814F2599(Vehicle vehicle, BOOL p1)



> 0x4E74E62E0A97E901 

void 0x4E74E62E0A97E901(Vehicle vehicle, BOOL p1)



> START_VEHICLE_HORN - 0x9C8C6504B5B63D2C 0x0DF5ADB3

void START_VEHICLE_HORN(Vehicle vehicle, int duration, Hash mode, BOOL forever)

```
Sounds the horn for the specified vehicle.

vehicle: The vehicle to activate the horn for.
mode: The hash of 'NORMAL' or 'HELDDOWN'. Can be 0.
duration: The duration to sound the horn, in milliseconds.

Note: If a player is in the vehicle, it will only sound briefly.
```

> _SET_VEHICLE_SILENT - 0x9D44FCCE98450843 0x968E5770

void _SET_VEHICLE_SILENT(Vehicle vehicle, BOOL toggle)

```
If set to TRUE, it seems to suppress door noises and doesn't allow the horn to be continuous.

-Doesn't seem to suppress door noises for me, at least with the vehicle add-on I tried
```

> SET_VEHICLE_HAS_STRONG_AXLES - 0x92F0CF722BC4202F 0x0D1CBC65

void SET_VEHICLE_HAS_STRONG_AXLES(Vehicle vehicle, BOOL toggle)

```
if true, axles won't bend.
```

> GET_DISPLAY_NAME_FROM_VEHICLE_MODEL - 0xB215AAC32D25D019 0xEC86DF39

char* GET_DISPLAY_NAME_FROM_VEHICLE_MODEL(Hash modelHash)

```
Returns model name of vehicle in all caps. Needs to be displayed through localizing text natives to get proper display name.
-----------------------------------------------------------------------------------------------------------------------------------------
While often the case, this does not simply return the model name of the vehicle (which could be hashed to return the model hash). Variations of the same vehicle may also use the same display name.
-----------------------------------------------------------------------------------------------------------------------------------------

Returns 'CARNOTFOUND' if the hash doesn't match a vehicle hash.

Using UI::_GET_LABEL_TEXT, you can get the localized name.

For a full list, see here: pastebin.com/wvpyS4kS (pastebin.com/dA3TbkZw)


```

> GET_VEHICLE_DEFORMATION_AT_POS - 0x4EC6CFBC7B2E9536 0xABF02075

Vector3 GET_VEHICLE_DEFORMATION_AT_POS(Vehicle vehicle, float offsetX, float offsetY, float offsetZ)

```
The only example I can find of this function in the scripts, is this:

struct _s = VEHICLE::GET_VEHICLE_DEFORMATION_AT_POS(rPtr((A_0) + 4), 1.21f, 6.15f, 0.3f);

-----------------------------------------------------------------------------------------------------------------------------------------
PC scripts:

v_5/*{3}*/ = VEHICLE::GET_VEHICLE_DEFORMATION_AT_POS(a_0._f1, 1.21, 6.15, 0.3);
```

> SET_VEHICLE_LIVERY - 0x60BF608F1B8CD1B6 0x7AD87059

void SET_VEHICLE_LIVERY(Vehicle vehicle, int livery)

```
Note: Only seems to work on Emergency Vehicles
```

> GET_VEHICLE_LIVERY - 0x2BB9230590DA5E8A 0xEC82A51D

int GET_VEHICLE_LIVERY(Vehicle vehicle)

```
-1 = no livery
```

> GET_VEHICLE_LIVERY_COUNT - 0x87B63E25A529D526 0xFB0CA947

int GET_VEHICLE_LIVERY_COUNT(Vehicle vehicle)

```
Returns -1 if the vehicle has no livery
```

> IS_VEHICLE_WINDOW_INTACT - 0x46E571A0E20D01F1 0xAC4EF23D

BOOL IS_VEHICLE_WINDOW_INTACT(Vehicle vehicle, int windowIndex)



> ARE_ALL_VEHICLE_WINDOWS_INTACT - 0x11D862A3E977A9EF 0xBB619744

BOOL ARE_ALL_VEHICLE_WINDOWS_INTACT(Vehicle vehicle)

```
Appears to return false if any window is broken.
```

> _IS_ANY_VEHICLE_SEAT_EMPTY - 0x2D34FC3BC4ADB780 0x648E685A

BOOL _IS_ANY_VEHICLE_SEAT_EMPTY(Vehicle vehicle)

```
Returns false if every seat is occupied.
```

> RESET_VEHICLE_WHEELS - 0x21D2E5662C1F6FED 0xD5FFE779

void RESET_VEHICLE_WHEELS(Vehicle vehicle, BOOL toggle)



> IS_HELI_PART_BROKEN - 0xBC74B4BE25EB6C8A 0xF4E4C439

BOOL IS_HELI_PART_BROKEN(Vehicle vehicle, BOOL p1, BOOL p2, BOOL p3)



> _GET_HELI_MAIN_ROTOR_HEALTH - 0xE4CB7541F413D2C5 0xF01E2AAB

float _GET_HELI_MAIN_ROTOR_HEALTH(Vehicle vehicle)

```
Max 1000.
At 0 the main rotor will stall.
```

> _GET_HELI_TAIL_ROTOR_HEALTH - 0xAE8CE82A4219AC8C 0xA41BC13D

float _GET_HELI_TAIL_ROTOR_HEALTH(Vehicle vehicle)

```
Max 1000.
At 0 the tail rotor will stall.

```

> _GET_HELI_ENGINE_HEALTH - 0xAC51915D27E4A5F7 0x8A68388F

float _GET_HELI_ENGINE_HEALTH(Vehicle vehicle)

```
Max 1000.
At -100 both helicopter rotors will stall.
```

> WAS_COUNTER_ACTIVATED - 0x3EC8BF18AA453FE9 0x2916D69B

BOOL WAS_COUNTER_ACTIVATED(Vehicle vehicle, Any p1)

```
Hash collision
```

> SET_VEHICLE_NAME_DEBUG - 0xBFDF984E2C22B94F 0xA712FF5C

void SET_VEHICLE_NAME_DEBUG(Vehicle vehicle, char* name)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> SET_VEHICLE_EXPLODES_ON_HIGH_EXPLOSION_DAMAGE - 0x71B0892EC081D60A 0x38CC692B

void SET_VEHICLE_EXPLODES_ON_HIGH_EXPLOSION_DAMAGE(Vehicle vehicle, BOOL toggle)

```
Sets a vehicle to be strongly resistant to explosions. p0 is the vehicle; set p1 to false to toggle the effect on/off.
```

> 0x3441CAD2F2231923 0xC306A9A3

void 0x3441CAD2F2231923(Vehicle vehicle, BOOL p1)



> 0x2B6747FAA9DB9D6B 0x95A9ACCB

Any 0x2B6747FAA9DB9D6B(Vehicle vehicle, BOOL p1)



> _SET_VEHICLE_LANDING_GEAR - 0xCFC8BE9A5E1FE575 0x24F873FB

void _SET_VEHICLE_LANDING_GEAR(Vehicle vehicle, int state)

```
Works for vehicles with a retractable landing gear

landing gear states:

0: Deployed
1: Closing
2: Opening
3: Retracted
```

> GET_LANDING_GEAR_STATE - 0x9B0F3DCA3DB0F4CD 0xA6F02670

int GET_LANDING_GEAR_STATE(Vehicle vehicle)

```
landing gear states:

0: Deployed
1: Closing
2: Opening
3: Retracted
```

> IS_ANY_VEHICLE_NEAR_POINT - 0x61E1DD6125A3EEE6 0x2867A834

BOOL IS_ANY_VEHICLE_NEAR_POINT(float x, float y, float z, float radius)



> REQUEST_VEHICLE_HIGH_DETAIL_MODEL - 0xA6E9FDCB2C76785E 0x9DA21956

void REQUEST_VEHICLE_HIGH_DETAIL_MODEL(Vehicle vehicle)



> REMOVE_VEHICLE_HIGH_DETAIL_MODEL - 0x00689CDE5F7C6787 0x382BE070

void REMOVE_VEHICLE_HIGH_DETAIL_MODEL(Vehicle vehicle)



> IS_VEHICLE_HIGH_DETAIL - 0x1F25887F3C104278 0x55D41928

BOOL IS_VEHICLE_HIGH_DETAIL(Vehicle vehicle)



> REQUEST_VEHICLE_ASSET - 0x81A15811460FAB3A 0x902B4F06

void REQUEST_VEHICLE_ASSET(Hash vehicleHash, int vehicleAsset)

```
REQUEST_VEHICLE_ASSET(GET_HASH_KEY(cargobob3), 3);

vehicle found that have asset's:
cargobob3
submersible
blazer
```

> HAS_VEHICLE_ASSET_LOADED - 0x1BBE0523B8DB9A21 0x8DAAC3CB

BOOL HAS_VEHICLE_ASSET_LOADED(int vehicleAsset)



> REMOVE_VEHICLE_ASSET - 0xACE699C71AB9DEB5 0x9620E9C6

void REMOVE_VEHICLE_ASSET(int vehicleAsset)



> _SET_TOW_TRUCK_CRANE_HEIGHT - 0xFE54B92A344583CA 0x88236E22

void _SET_TOW_TRUCK_CRANE_HEIGHT(Vehicle towTruck, float height)

```
Sets how much the crane on the tow truck is raised, where 0.0 is fully lowered and 1.0 is fully raised.
```

> ATTACH_VEHICLE_TO_TOW_TRUCK - 0x29A16F8D621C4508 0x8151571A

void ATTACH_VEHICLE_TO_TOW_TRUCK(Vehicle towTruck, Vehicle vehicle, BOOL rear, float hookOffsetX, float hookOffsetY, float hookOffsetZ)

```
HookOffset defines where the hook is attached. leave at 0 for default attachment.
```

> DETACH_VEHICLE_FROM_TOW_TRUCK - 0xC2DB6B6708350ED8 0xC666CF33

void DETACH_VEHICLE_FROM_TOW_TRUCK(Vehicle towTruck, Vehicle vehicle)

```
First two parameters swapped. Scripts verify that towTruck is the first parameter, not the second.
```

> DETACH_VEHICLE_FROM_ANY_TOW_TRUCK - 0xD0E9CE05A1E68CD8 0x3BF93651

BOOL DETACH_VEHICLE_FROM_ANY_TOW_TRUCK(Vehicle vehicle)



> IS_VEHICLE_ATTACHED_TO_TOW_TRUCK - 0x146DF9EC4C4B9FD4 0x9699CFDC

BOOL IS_VEHICLE_ATTACHED_TO_TOW_TRUCK(Vehicle towTruck, Vehicle vehicle)

```
MulleDK19: First two parameters swapped. Scripts verify that towTruck is the first parameter, not the second.
```

> GET_ENTITY_ATTACHED_TO_TOW_TRUCK - 0xEFEA18DCF10F8F75 0x11EC7844

Entity GET_ENTITY_ATTACHED_TO_TOW_TRUCK(Vehicle towTruck)



> SET_VEHICLE_AUTOMATICALLY_ATTACHES - 0x8BA6F76BC53A1493 0x4273A8D3

Any SET_VEHICLE_AUTOMATICALLY_ATTACHES(Vehicle vehicle, Any p1, Any p2)

```
Please change to void.
```

> 0xF8EBCCC96ADB9FB7 0xED23C8A3

void 0xF8EBCCC96ADB9FB7(Any p0, float p1, BOOL p2)



> 0x56B94C6D7127DFBA 0xB1A52EF7

void 0x56B94C6D7127DFBA(Any p0, float p1, BOOL p2)



> 0x1093408B4B9D1146 0xF30C566F

void 0x1093408B4B9D1146(Any p0, float p1)



> 0x30D779DE7C4F6DD3 0xA7DF64D7

void 0x30D779DE7C4F6DD3(Any p0, float p1)

```
possibly   ENABLE_VEHICLE_FOREVER_HYDRAULICS
```

> 0x9AA47FFF660CB932 0xDD7936F5

void 0x9AA47FFF660CB932(Any p0, float p1)



> 0xA4822F1CF23F4810 0x34E02FCD

BOOL 0xA4822F1CF23F4810(Vector3* outVec, Any p1, Vector3* outVec1, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8)



> SET_VEHICLE_BURNOUT - 0xFB8794444A7D60FB 0x9B6EF0EA

void SET_VEHICLE_BURNOUT(Vehicle vehicle, BOOL toggle)

```
On accelerating, spins the driven wheels with the others braked, so you don't go anywhere.
```

> IS_VEHICLE_IN_BURNOUT - 0x1297A88E081430EB 0x6632BC12

BOOL IS_VEHICLE_IN_BURNOUT(Vehicle vehicle)

```
Returns whether the specified vehicle is currently in a burnout.


vb.net
Public Function isVehicleInBurnout(vh As Vehicle) As Boolean
        Return Native.Function.Call(Of Boolean)(Hash.IS_VEHICLE_IN_BURNOUT, vh)
    End Function
```

> SET_VEHICLE_REDUCE_GRIP - 0x222FF6A823D122E2 0x90D3A0D9

void SET_VEHICLE_REDUCE_GRIP(Vehicle vehicle, BOOL toggle)

```
Reduces grip significantly so it's hard to go anywhere.
```

> SET_VEHICLE_INDICATOR_LIGHTS - 0xB5D45264751B7DF0 0xA6073B5D

void SET_VEHICLE_INDICATOR_LIGHTS(Vehicle vehicle, int turnSignal, BOOL toggle)

```
Sets the turn signal enabled for a vehicle.
Set turnSignal to 1 for left light, 0 for right light.
```

> SET_VEHICLE_BRAKE_LIGHTS - 0x92B35082E0B42F66 0x6D9BA11E

void SET_VEHICLE_BRAKE_LIGHTS(Vehicle vehicle, BOOL toggle)



> SET_VEHICLE_HANDBRAKE - 0x684785568EF26A22 0xBA729A25

void SET_VEHICLE_HANDBRAKE(Vehicle vehicle, BOOL toggle)

```
does this work while in air?
```

> 0x48ADC8A773564670 0x37BC6ACB

void 0x48ADC8A773564670()



> 0x91D6DD290888CBAB 0x71D898EF

Any 0x91D6DD290888CBAB()



> 0x51DB102F4A3BA5E0 0x0B0523B0

void 0x51DB102F4A3BA5E0(BOOL p0)



> GET_VEHICLE_TRAILER_VEHICLE - 0x1CDD6BADC297830D 0xAE84D758

BOOL GET_VEHICLE_TRAILER_VEHICLE(Vehicle vehicle, Vehicle* trailer)

```
Gets the trailer of a vehicle and puts it into the trailer parameter.
```

> 0xCAC66558B944DA67 0x0B200CE2

void 0xCAC66558B944DA67(Vehicle vehicle, BOOL p1)



> SET_VEHICLE_RUDDER_BROKEN - 0x09606148B6C71DEF 0x3FAC3CD4

void SET_VEHICLE_RUDDER_BROKEN(Vehicle vehicle, BOOL p1)



> 0x1A78AD3D8240536F 0x0858678C

void 0x1A78AD3D8240536F(Vehicle vehicle, BOOL p1)



> 0x53AF99BAA671CA47 0x7D1A0616

float 0x53AF99BAA671CA47(Vehicle vehicle)

```
GET_VEHICLE_MAX_*
sfink: this returns the vehicle property 'Assisted Steering' or at least, it returned 37.5 when i was in a car with that value as assisted steering.
```

> GET_VEHICLE_MAX_BRAKING - 0xAD7E85FC227197C4 0x03B926F6

float GET_VEHICLE_MAX_BRAKING(Vehicle vehicle)



> GET_VEHICLE_MAX_TRACTION - 0xA132FB5370554DB0 0x7E5A1587

float GET_VEHICLE_MAX_TRACTION(Vehicle vehicle)



> GET_VEHICLE_ACCELERATION - 0x5DD35C8D074E57AE 0x00478321

float GET_VEHICLE_ACCELERATION(Vehicle vehicle)

```
static - max acceleration
```

> _GET_VEHICLE_MODEL_MAX_SPEED - 0xF417C2502FFFED43 0x8F291C4A

float _GET_VEHICLE_MODEL_MAX_SPEED(Hash modelHash)

```
Returns max speed (without mods) of the specified vehicle model in m/s.

For a full list, see here: pastebin.com/AUuHHK06

GET_VEHICLE_MODEL_*
```

> GET_VEHICLE_MODEL_MAX_BRAKING - 0xDC53FD41B4ED944C 0x7EF02883

float GET_VEHICLE_MODEL_MAX_BRAKING(Hash modelHash)

```
Returns max braking of the specified vehicle model.

For a full list, see here: pastebin.com/3N8DVbpG
```

> 0xBFBA3BA79CFF7EBF 0xF3A7293F

float 0xBFBA3BA79CFF7EBF(Hash modelHash)

```
GET_VEHICLE_MODEL_MAX_*
max braking if air vehicle, else max braking + 0.1

-------------------

For a full list, see here: pastebin.com/Cb9L1Cn0
```

> GET_VEHICLE_MODEL_MAX_TRACTION - 0x539DE94D44FDFD0D 0x7F985597

float GET_VEHICLE_MODEL_MAX_TRACTION(Hash modelHash)

```
Returns max traction of the specified vehicle model.

For a full list, see here: pastebin.com/ERnntVjK
```

> GET_VEHICLE_MODEL_ACCELERATION - 0x8C044C5C84505B6A 0x29CB3537

float GET_VEHICLE_MODEL_ACCELERATION(Hash modelHash)

```
Returns the acceleration of the specified model.

For a full list, see here: pastebin.com/GaN6vT4R

```

> 0x53409B5163D5B846 0x37FBA7BC

float 0x53409B5163D5B846(Hash modelHash)

```
GET_VEHICLE_MODEL_*

9.8 * thrust if air vehicle, else 0.38 + drive force?

For a full list, see here: pastebin.com/bJQeDqNd
```

> 0xC6AD107DDC9054CC 0x95BB67EB

float 0xC6AD107DDC9054CC(Hash modelHash)

```
GET_VEHICLE_MODEL_*

Function pertains only to aviation vehicles.

For a full list, see here: pastebin.com/JwuGNp2K
```

> 0x5AA3F878A178C4FC 0x87C5D271

float 0x5AA3F878A178C4FC(Hash modelHash)

```
GET_VEHICLE_MODEL_*

called if the vehicle is a boat -- returns vecMoveResistanceX?

For a full list, see here: pastebin.com/Pyb2RhZ9
```

> 0x00C09F246ABEDD82 0xCE67162C

float 0x00C09F246ABEDD82(Any p0)

```
GET_VEHICLE_CLASS_*
```

> GET_VEHICLE_CLASS_MAX_TRACTION - 0xDBC86D85C5059461 0x5B4FDC16

float GET_VEHICLE_CLASS_MAX_TRACTION(Any p0)



> GET_VEHICLE_CLASS_MAX_AGILITY - 0x4F930AD022D6DE3B 0x45F2BD83

float GET_VEHICLE_CLASS_MAX_AGILITY(Any p0)



> GET_VEHICLE_CLASS_MAX_ACCELERATION - 0x2F83E7E45D9EA7AE 0x3E220A9B

float GET_VEHICLE_CLASS_MAX_ACCELERATION(Any p0)



> GET_VEHICLE_CLASS_MAX_BRAKING - 0x4BF54C16EC8FEC03 0xD08CC1A5

float GET_VEHICLE_CLASS_MAX_BRAKING(Any p0)



> 0x2CE544C68FB812A0 0xD6685803

Any 0x2CE544C68FB812A0(float p0, float p1, float p2, float p3, float p4, BOOL p5)



> 0x1033371FC8E842A7 0x0C0332A6

BOOL 0x1033371FC8E842A7(Any p0)



> OPEN_BOMB_BAY_DOORS - 0x87E7F24270732CB1 0x6574041D

void OPEN_BOMB_BAY_DOORS(Vehicle vehicle)



> CLOSE_BOMB_BAY_DOORS - 0x3556041742A0DC74 0xF8EC5751

void CLOSE_BOMB_BAY_DOORS(Vehicle vehicle)



> IS_VEHICLE_SEARCHLIGHT_ON - 0xC0F97FCE55094987 0xADAF3513

BOOL IS_VEHICLE_SEARCHLIGHT_ON(Vehicle vehicle)

```
Possibly: Returns whether the searchlight (found on police vehicles) is toggled on.

@Author Nac
```

> SET_VEHICLE_SEARCHLIGHT - 0x14E85C5EE7A4D542 0xE2C0DD8A

void SET_VEHICLE_SEARCHLIGHT(Vehicle heli, BOOL toggle, BOOL canBeUsedByAI)

```
Only works during nighttime.
```

> 0x639431E895B9AA57 0xAB0E79EB

BOOL 0x639431E895B9AA57(Any p0, Any p1, Any p2, BOOL p3, BOOL p4)



> CAN_SHUFFLE_SEAT - 0x30785D90C956BF35 0xB3EB01ED

BOOL CAN_SHUFFLE_SEAT(Vehicle vehicle, Any p1)



> GET_NUM_MOD_KITS - 0x33F2E3FE70EAAE1D 0xE4903AA0

int GET_NUM_MOD_KITS(Vehicle vehicle)



> SET_VEHICLE_MOD_KIT - 0x1F2AA07F00B3217A 0xB8132158

void SET_VEHICLE_MOD_KIT(Vehicle vehicle, int modKit)

```
Set modKit to 0 if you plan to call SET_VEHICLE_MOD. That's what the game does. Most body modifications through SET_VEHICLE_MOD will not take effect until this is set to 0.
```

> GET_VEHICLE_MOD_KIT - 0x6325D1A044AE510D 0x9FE60927

int GET_VEHICLE_MOD_KIT(Vehicle vehicle)



> GET_VEHICLE_MOD_KIT_TYPE - 0xFC058F5121E54C32 0xE5F76765

int GET_VEHICLE_MOD_KIT_TYPE(Vehicle vehicle)



> GET_VEHICLE_WHEEL_TYPE - 0xB3ED1BFB4BE636DC 0xDA58D7AE

int GET_VEHICLE_WHEEL_TYPE(Vehicle vehicle)

```
Returns an int

Wheel Types:
0: Sport
1: Muscle
2: Lowrider
3: SUV
4: Offroad
5: Tuner
6: Bike Wheels
7: High End

Tested in Los Santos Customs
```

> SET_VEHICLE_WHEEL_TYPE - 0x487EB21CC7295BA1 0x64BDAAAD

Any SET_VEHICLE_WHEEL_TYPE(Vehicle vehicle, int WheelType)

```
0: Sport
1: Muscle
2: Lowrider
3: SUV
4: Offroad
5: Tuner
6: Bike Wheels
7: High End
```

> GET_NUM_MOD_COLORS - 0xA551BE18C11A476D 0x73722CD9

int GET_NUM_MOD_COLORS(int p0, BOOL p1)



> SET_VEHICLE_MOD_COLOR_1 - 0x43FEB945EE7F85B8 0xCBE9A54D

void SET_VEHICLE_MOD_COLOR_1(Vehicle vehicle, int paintType, int color, int p3)

```
paintType:
0: Normal
1: Metallic
2: Pearl
3: Matte
4: Metal
5: Chrome

color: number of the color.

p3 seems to always be 0.
```

> SET_VEHICLE_MOD_COLOR_2 - 0x816562BADFDEC83E 0xC32613C2

void SET_VEHICLE_MOD_COLOR_2(Vehicle vehicle, int paintType, int color)

```
Changes the secondary paint type and color
paintType:
0: Normal
1: Metallic
2: Pearl
3: Matte
4: Metal
5: Chrome

color: number of the color
```

> GET_VEHICLE_MOD_COLOR_1 - 0xE8D65CA700C9A693 0xE625510A

void GET_VEHICLE_MOD_COLOR_1(Vehicle vehicle, int* paintType, int* color, int* p3)



> GET_VEHICLE_MOD_COLOR_2 - 0x81592BE4E3878728 0x9B76BB8E

void GET_VEHICLE_MOD_COLOR_2(Vehicle vehicle, int* paintType, int* color)



> _GET_VEHICLE_MOD_COLOR_1_TEXT_LABEL - 0xB45085B721EFD38C 0x9A0840FD

char* _GET_VEHICLE_MOD_COLOR_1_TEXT_LABEL(Vehicle vehicle, BOOL p1)

```
returns a string which is the codename of the vehicle's currently selected primary color

p1 is always 0
```

> _GET_VEHICLE_MOD_COLOR_2_TEXT_LABEL - 0x4967A516ED23A5A1 0x9BDC0B49

char* _GET_VEHICLE_MOD_COLOR_2_TEXT_LABEL(Vehicle vehicle)

```
returns a string which is the codename of the vehicle's currently selected secondary color
```

> 0x9A83F5F9963775EF 0x112D637A

BOOL 0x9A83F5F9963775EF(Any p0)



> SET_VEHICLE_MOD - 0x6AF0636DDEDCB6DD 0xB52E5ED5

void SET_VEHICLE_MOD(Vehicle vehicle, int modType, int modIndex, BOOL customTires)

```
In b944, there are 50 (0 - 49) mod types.

Sets the vehicle mod.
The vehicle must have a mod kit first.

Any out of range ModIndex is stock.

#Mod Type
Spoilers - 0
Front Bumper - 1
Rear Bumper - 2
Side Skirt - 3
Exhaust - 4
Frame - 5
Grille - 6
Hood - 7
Fender - 8
Right Fender - 9
Roof - 10
Engine - 11
Brakes - 12
Transmission - 13
Horns - 14 (modIndex from 0 to 51)
Suspension - 15
Armor - 16
Front Wheels - 23
Back Wheels - 24 //only for motocycles
Plate holders - 25
Trim Design - 27
Ornaments - 28
Dial Design - 30
Steering Wheel - 33
Shifter Leavers - 34
Plaques - 35
Hydraulics - 38
Livery - 48

ENUMS: pastebin.com/QzEAn02v
```

> GET_VEHICLE_MOD - 0x772960298DA26FDB 0xDC520069

int GET_VEHICLE_MOD(Vehicle vehicle, int modType)

```
In b944, there are 50 (0 - 49) mod types.

Returns -1 if the vehicle mod is stock
```

> GET_VEHICLE_MOD_VARIATION - 0xB3924ECD70E095DC 0xC1B92003

BOOL GET_VEHICLE_MOD_VARIATION(Vehicle vehicle, int modType)

```
Only used for wheels(ModType = 23/24) Returns true if the wheels are custom wheels
```

> GET_NUM_VEHICLE_MODS - 0xE38E9162A2500646 0x8A814FF9

int GET_NUM_VEHICLE_MODS(Vehicle vehicle, int modType)

```
Returns how many possible mods a vehicle has for a given mod type
```

> REMOVE_VEHICLE_MOD - 0x92D619E420858204 0x9CC80A43

void REMOVE_VEHICLE_MOD(Vehicle vehicle, int modType)



> TOGGLE_VEHICLE_MOD - 0x2A1F4F37F95BAD08 0xD095F811

void TOGGLE_VEHICLE_MOD(Vehicle vehicle, int modType, BOOL toggle)

```
Toggles:
UNK17 - 17
Turbo - 18
UNK19 - 19
Tire Smoke - 20
UNK21 - 21
Xenon Headlights - 22
```

> IS_TOGGLE_MOD_ON - 0x84B233A8C8FC8AE7 0xF0E1689F

BOOL IS_TOGGLE_MOD_ON(Vehicle vehicle, int modType)



> GET_MOD_TEXT_LABEL - 0x8935624F8C5592CC 0x0BA39CA7

char* GET_MOD_TEXT_LABEL(Vehicle vehicle, int modType, int modValue)

```
Returns the text label of a mod type for a given vehicle

Use _GET_LABEL_TEXT to get the part name in the game's language
```

> GET_MOD_SLOT_NAME - 0x51F0FEB9F6AE98C0 0x5E113483

char* GET_MOD_SLOT_NAME(Vehicle vehicle, int modType)

```
Returns the name for the type of vehicle mod(Armour, engine etc)

```

> GET_LIVERY_NAME - 0xB4C7A93837C91A1F 0xED80B5BE

char* GET_LIVERY_NAME(Vehicle vehicle, int liveryIndex)

```
Second Param = LiveryIndex

example 

int count = VEHICLE::GET_VEHICLE_LIVERY_COUNT(veh);
for (int i = 0; i &lt; count; i++)  
	{
		char* LiveryName = VEHICLE::GET_LIVERY_NAME(veh, i);
	}


this example will work fine to fetch all names 
for example for Sanchez we get 

SANC_LV1
SANC_LV2
SANC_LV3
SANC_LV4
SANC_LV5

Edited By KiLLerBoy_001
---------------------------------
Using _GET_LABEL_TEXT, you can get the localized livery name.
```

> GET_VEHICLE_MOD_MODIFIER_VALUE - 0x90A38E9838E0A8C1 0x73AE5505

Any GET_VEHICLE_MOD_MODIFIER_VALUE(Vehicle vehicle, int modType, int modIndex)



> 0x4593CF82AA179706 0x94850968

Any 0x4593CF82AA179706(Any p0, Any p1, Any p2)

```
Can be used for IS_DLC_VEHICLE_MOD and _0xC098810437312FFF
```

> PRELOAD_VEHICLE_MOD - 0x758F49C24925568A 0x6EA5F4A8

void PRELOAD_VEHICLE_MOD(Any p0, Any p1, Any p2)



> HAS_PRELOAD_MODS_FINISHED - 0x06F43E5175EB6D96 0xA8A0D246

BOOL HAS_PRELOAD_MODS_FINISHED(Any p0)



> RELEASE_PRELOAD_MODS - 0x445D79F995508307 0xD442521F

void RELEASE_PRELOAD_MODS(Vehicle vehicle)



> SET_VEHICLE_TYRE_SMOKE_COLOR - 0xB5BA80F839791C0F 0x3EDEC0DB

void SET_VEHICLE_TYRE_SMOKE_COLOR(Vehicle vehicle, int r, int g, int b)

```
Sets the tire smoke's color of this vehicle.

vehicle: The vehicle that is the target of this method.
r: The red level in the RGB color code.
g: The green level in the RGB color code.
b: The blue level in the RGB color code.

Note:
setting r,g,b to 0 will give the car independance day tyre smoke
```

> GET_VEHICLE_TYRE_SMOKE_COLOR - 0xB635392A4938B3C3 0x75280015

void GET_VEHICLE_TYRE_SMOKE_COLOR(Vehicle vehicle, int* r, int* g, int* b)



> SET_VEHICLE_WINDOW_TINT - 0x57C51E6BAD752696 0x497C8787

void SET_VEHICLE_WINDOW_TINT(Vehicle vehicle, int tint)

```
enum WindowTints
{
	WINDOWTINT_NONE,
	WINDOWTINT_PURE_BLACK,
	WINDOWTINT_DARKSMOKE,
	WINDOWTINT_LIGHTSMOKE,
	WINDOWTINT_STOCK,
	WINDOWTINT_LIMO,
	WINDOWTINT_GREEN
};
```

> GET_VEHICLE_WINDOW_TINT - 0x0EE21293DAD47C95 0x13D53892

int GET_VEHICLE_WINDOW_TINT(Vehicle vehicle)



> GET_NUM_VEHICLE_WINDOW_TINTS - 0x9D1224004B3A6707 0x625C7B66

int GET_NUM_VEHICLE_WINDOW_TINTS()



> GET_VEHICLE_COLOR - 0xF3CC740D36221548 0x03BC8F1B

void GET_VEHICLE_COLOR(Vehicle vehicle, int* r, int* g, int* b)



> 0xEEBFC7A7EFDC35B4 0x749DEEA2

int 0xEEBFC7A7EFDC35B4(Vehicle vehicle)

```
MulleDK19: Some kind of flags.
```

> GET_VEHICLE_CAUSE_OF_DESTRUCTION - 0xE495D1EF4C91FD20 0x7F8C20DD

Hash GET_VEHICLE_CAUSE_OF_DESTRUCTION(Vehicle vehicle)

```
iVar3 = get_vehicle_cause_of_destruction(uLocal_248[iVar2]);
if (iVar3 == joaat('weapon_stickybomb'))
{
     func_171(726);
     iLocal_260 = 1;
}
```

> GET_IS_LEFT_VEHICLE_HEADLIGHT_DAMAGED - 0x5EF77C9ADD3B11A3 0xA0777943

BOOL GET_IS_LEFT_VEHICLE_HEADLIGHT_DAMAGED(Vehicle vehicle)

```
From the driver's perspective, is the left headlight broken.
```

> GET_IS_RIGHT_VEHICLE_HEADLIGHT_DAMAGED - 0xA7ECB73355EB2F20 0xF178390B

BOOL GET_IS_RIGHT_VEHICLE_HEADLIGHT_DAMAGED(Vehicle vehicle)

```
From the driver's perspective, is the right headlight broken.
```

> _SET_VEHICLE_ENGINE_POWER_MULTIPLIER - 0x93A3996368C94158 0xE943B09C

void _SET_VEHICLE_ENGINE_POWER_MULTIPLIER(Vehicle vehicle, float value)

```
Vehicle power multiplier.
Does not have to be looped each frame. Can be set once.
Values lower than 1f don't work.

Note: If the value is set with GET_RANDOM_FLOAT_IN_RANGE, the vehicle will have an absurdly high ammount of power, and will become almost undrivable for the player or NPCs. The range doesn't seem to matter.

An high value like 10000000000f will visually remove the wheels that apply the power (front wheels for FWD, rear wheels for RWD), but the power multiplier will still apply, and the wheels still work.
```

> 0x1CF38D529D7441D9 0xDF594D8D

void 0x1CF38D529D7441D9(Vehicle vehicle, BOOL toggle)

```
what does this do?
```

> 0x1F9FB66F3A3842D2 0x4D840FC4

void 0x1F9FB66F3A3842D2(Any p0, BOOL p1)



> 0x54B0F614960F4A5F 0x5AB26C2B

Any 0x54B0F614960F4A5F(float p0, float p1, float p2, float p3, float p4, float p5, float p6)



> 0xE30524E1871F481D 0xEF05F807

void 0xE30524E1871F481D(Any p0)

```
REMOTE_VEHICLE_*
```

> 0x291E373D483E7EE7 0xD656E7E5

BOOL 0x291E373D483E7EE7(Any p0)



> _SET_VEHICLE_ENGINE_TORQUE_MULTIPLIER - 0xB59E4BD37AE292DB 0x642DA5AA

void _SET_VEHICLE_ENGINE_TORQUE_MULTIPLIER(Vehicle vehicle, float value)

```
&lt;1.0 - Decreased torque
=1.0 - Default torque
&gt;1.0 - Increased torque

Negative values will cause the vehicle to go backwards instead of forwards while accelerating.

value - is between 0.2 and 1.8 in the decompiled scripts. 

This needs to be called every frame to take effect.
```

> 0x0AD9E8F87FF7C16F 0x04F5546C

void 0x0AD9E8F87FF7C16F(Any p0, BOOL p1)



> SET_VEHICLE_IS_WANTED - 0xF7EC25A3EBEEC726 0xDAA388E8

void SET_VEHICLE_IS_WANTED(Vehicle vehicle, BOOL state)

```
Sets the wanted state of this vehicle.

```

> 0xF488C566413B4232 0xA25CCB8C

void 0xF488C566413B4232(Any p0, float p1)



> 0xC1F981A6F74F0C23 0x00966934

void 0xC1F981A6F74F0C23(Any p0, BOOL p1)

```
same call as VEHICLE::_0x0F3B4D4E43177236
```

> 0x0F3B4D4E43177236 0x113DF5FD

void 0x0F3B4D4E43177236(Any p0, BOOL p1)



> 0x6636C535F6CC2725 0x7C8D6464

float 0x6636C535F6CC2725(Any p0)

```
Something related to vehicle lean? (References CVehicleLeanHelper)
```

> DISABLE_PLANE_AILERON - 0x23428FC53C60919C 0x7E84C45C

void DISABLE_PLANE_AILERON(Vehicle vehicle, BOOL p1, BOOL p2)

```
hash collision??? - Don't think so. I fits alphabetically and it used with a plane in the scripts
```

> GET_IS_VEHICLE_ENGINE_RUNNING - 0xAE31E7DF9B5B132E 0x7DC6D022

BOOL GET_IS_VEHICLE_ENGINE_RUNNING(Vehicle vehicle)

```
Returns true when in a vehicle, false whilst entering/exiting.
```

> 0x1D97D1E3A70A649F 0xA03E42DF

void 0x1D97D1E3A70A649F(Vehicle vehicle, BOOL p1)

```
Related to Hao races.
```

> _SET_BIKE_LEAN_ANGLE - 0x9CFA4896C3A53CBB 0x15D40761

void _SET_BIKE_LEAN_ANGLE(Vehicle vehicle, float x, float y)

```
Only works on bikes, both X and Y work in the -1 - 1 range.

X forces the bike to turn left or right (-1, 1)
Y forces the bike to lean to the left or to the right (-1, 1)

Example with X -1/Y 1
http://i.imgur.com/TgIuAPJ.jpg
```

> 0xAB04325045427AAE 0x1984F88D

void 0xAB04325045427AAE(Vehicle vehicle, BOOL p1)



> 0xCFD778E7904C255E 0x3FBE904F

void 0xCFD778E7904C255E(Vehicle vehicle)

```
what does this do?
```

> 0xACFB2463CC22BED2 0xD1B71A25

void 0xACFB2463CC22BED2(Any p0)



> GET_LAST_DRIVEN_VEHICLE - 0xB2D06FAEDE65B577 0xFEB0C0C8

Vehicle GET_LAST_DRIVEN_VEHICLE()

```
Not exactly sure on this one, but here's a snippet of code:

if (PED::IS_PED_IN_ANY_VEHICLE(PLAYER::PLAYER_PED_ID(), 0)) {
    v_2 = PED::GET_VEHICLE_PED_IS_IN(PLAYER::PLAYER_PED_ID(), 0);
} else { 
    v_2 = VEHICLE::_B2D06FAEDE65B577();
}
```

> 0xE01903C47C7AC89E 

void 0xE01903C47C7AC89E()



> 0x02398B627547189C 0x08CD58F9

void 0x02398B627547189C(Any p0, BOOL p1)



> _SET_PLANE_MIN_HEIGHT_ABOVE_GROUND - 0xB893215D8D4C015B 0x8C4B63E2

void _SET_PLANE_MIN_HEIGHT_ABOVE_GROUND(Vehicle plane, int height)



> SET_VEHICLE_LOD_MULTIPLIER - 0x93AE6A61BE015BF1 0x569E5AE3

void SET_VEHICLE_LOD_MULTIPLIER(Vehicle vehicle, float multiplier)



> 0x428BACCDF5E26EAD 0x1604C2F5

void 0x428BACCDF5E26EAD(Vehicle vehicle, BOOL p1)

```
if (!ENTITY::DOES_ENTITY_BELONG_TO_THIS_SCRIPT(g_10A5A._f8B[a_0/*1*/], 1)) {
    sub_20af7('No longer needed: Vehicle owned by other script');
    if ((((a_0 == 24) &amp;&amp; (!sub_3a04(g_10A5A._f8B[a_0/*1*/]))) &amp;&amp; (!sub_39c9(g_10A5A._f8B[a_0/*1*/]))) &amp;&amp; (ENTITY::GET_ENTITY_MODEL(g_10A5A._f8B[a_0/*1*/]) != ${monster})) {
        VEHICLE::_428BACCDF5E26EAD(g_10A5A._f8B[a_0/*1*/], 1);
    }
    g_10A5A._f8B[a_0/*1*/] = 0;
    g_10A5A[a_0/*1*/] = 1;
    sub_20ada(a_0);
    return ;
}
```

> 0x42A4BEB35D372407 0x8CDB0C09

Any 0x42A4BEB35D372407(Any p0)

```
LOD related
```

> 0x2C8CBFE1EA5FC631 0xABC99E21

Any 0x2C8CBFE1EA5FC631(Any p0)



> 0x4D9D109F63FEE1D4 0x900C878C

void 0x4D9D109F63FEE1D4(Any p0, BOOL p1)



> 0x279D50DE5652D935 0xB3200F72

void 0x279D50DE5652D935(Any p0, BOOL p1)



> 0xE44A982368A4AF23 0xBAE491C7

void 0xE44A982368A4AF23(Vehicle vehicle, Vehicle vehicle2)



> 0xF25E02CB9C5818F8 0xF0E59BC1

void 0xF25E02CB9C5818F8()



> 0xBC3CCA5844452B06 0x929801C6

void 0xBC3CCA5844452B06(float p0)



> SET_VEHICLE_SHOOT_AT_TARGET - 0x74CD9A9327A282EA 0x2343FFDF

void SET_VEHICLE_SHOOT_AT_TARGET(Ped driver, Entity entity, float xTarget, float yTarget, float zTarget)

```
Commands the driver of an armed vehicle (p0) to shoot its weapon at a target (p1). p3, p4 and p5 are the coordinates of the target. Example:

WEAPON::SET_CURRENT_PED_VEHICLE_WEAPON(pilot,GAMEPLAY::GET_HASH_KEY('VEHICLE_WEAPON_PLANE_ROCKET'));						VEHICLE::SET_VEHICLE_SHOOT_AT_TARGET(pilot, target, targPos.x, targPos.y, targPos.z);
```

> _GET_VEHICLE_OWNER - 0x8F5EBAB1F260CFCE 0x4A557117

BOOL _GET_VEHICLE_OWNER(Vehicle vehicle, Entity* entity)

```
The resulting entity can be a Vehicle or Ped.

The native is stored between GET_VEHICLE_LIVERY_COUNT and GET_VEHICLE_MAX_BRAKING so the actual name is either GET_VEHICLE_L* or GET_VEHICLE_M*

```

> 0x97CE68CB032583F0 0xE0FC6A32

void 0x97CE68CB032583F0(Vehicle vehicle, BOOL p1)



> 0x182F266C2D9E2BEB 0x7D0DE7EA

void 0x182F266C2D9E2BEB(Vehicle vehicle, float p1)



> GET_VEHICLE_PLATE_TYPE - 0x9CCC9525BF2408E0 0x65CA9286

int GET_VEHICLE_PLATE_TYPE(Vehicle vehicle)



> TRACK_VEHICLE_VISIBILITY - 0x64473AEFDCF47DCA 0x78122DC1

void TRACK_VEHICLE_VISIBILITY(Vehicle vehicle)

```
in script hook .net 

Vehicle v = ...;
Function.Call(Hash.TRACK_VEHICLE_VISIBILITY, v.Handle);
```

> IS_VEHICLE_VISIBLE - 0xAA0A52D24FB98293 0x7E0D6056

BOOL IS_VEHICLE_VISIBLE(Vehicle vehicle)

```
must be called after TRACK_VEHICLE_VISIBILITY 

it's not instant so probabilly must pass an 'update' to see correct result.
```

> SET_VEHICLE_GRAVITY - 0x89F149B6131E57DA 0x07B2A6DC

void SET_VEHICLE_GRAVITY(Vehicle vehicle, BOOL toggle)



> 0xE6C0C80B8C867537 0xD2B8ACBD

void 0xE6C0C80B8C867537(BOOL p0)



> 0x36492C2F0D134C56 0xA4A75FCF

Any 0x36492C2F0D134C56(Any p0)

```
Returns a float value related to slipstream.
```

> 0x06582AFF74894C75 0x50F89338

void 0x06582AFF74894C75(Any p0, BOOL p1)



> 0xDFFCEF48E511DB48 0xEB7D7C27

void 0xDFFCEF48E511DB48(Any p0, BOOL p1)



> 0x8D474C8FAEFF6CDE 0x5EB00A6A

BOOL 0x8D474C8FAEFF6CDE(Vehicle vehicle)

```
MulleDK19: Checks some flag in the vehicle's model. If this function returns false, mod shops will not allow respray.
```

> SET_VEHICLE_ENGINE_CAN_DEGRADE - 0x983765856F2564F9 0x081DAC12

void SET_VEHICLE_ENGINE_CAN_DEGRADE(Vehicle vehicle, BOOL toggle)



> 0xF0E4BA16D1DB546C 0x5BD8D82D

void 0xF0E4BA16D1DB546C(Vehicle vehicle, int p1, int p2)

```
Adds some kind of shadow to the vehicle.

-1 disables the effect.
```

> 0xF87D9F2301F7D206 0x450AD03A

void 0xF87D9F2301F7D206(Any p0)



> 0x4198AB0022B15F87 0xBD085DCA

BOOL 0x4198AB0022B15F87(Any p0)

```
Vehicle has landing gear?
```

> 0x755D6D5267CBBD7E 0xABBDD5C6

BOOL 0x755D6D5267CBBD7E(Any p0)

```
Found this in the decompiled scripts, I'd do more research before changing the name --

if (!ENTITY::IS_ENTITY_DEAD(l_1911)) {
    if (!VEHICLE::_755D6D5267CBBD7E(l_1911)) {
        sub_1ba80('TRAFFICKING AIR: FAILING - PROPELLERS ARE DAMAGED');
        l_12CE = 9;
    }
}
```

> 0x0CDDA42F9E360CA6 0x9B581DE7

void 0x0CDDA42F9E360CA6(Any p0, BOOL p1)



> IS_VEHICLE_STOLEN - 0x4AF9BD80EEBEB453 0x20B61DDE

BOOL IS_VEHICLE_STOLEN(Vehicle vehicle)



> SET_VEHICLE_IS_STOLEN - 0x67B2C79AA7FF5738 0x70912E42

Any SET_VEHICLE_IS_STOLEN(Vehicle vehicle, BOOL isStolen)



> 0xAD2D28A1AFDFF131 0xED159AE6

void 0xAD2D28A1AFDFF131(Any p0, float p1)

```
Set vehicle wheels?
```

> 0x5991A01434CE9677 0xAF8CB3DF

BOOL 0x5991A01434CE9677(Any p0)



> 0xB264C4D2F2B0A78B 0x45F72495

void 0xB264C4D2F2B0A78B(Vehicle vehicle)

```
This native doesn't seem to do anything, might be a debug-only native.

~Fireboyd78
```

> DETACH_VEHICLE_FROM_CARGOBOB - 0x0E21D3DF1051399D 0x83D3D331

void DETACH_VEHICLE_FROM_CARGOBOB(Vehicle vehicle, Vehicle cargobob)



> DETACH_VEHICLE_FROM_ANY_CARGOBOB - 0xADF7BE450512C12F 0x50E0EABE

BOOL DETACH_VEHICLE_FROM_ANY_CARGOBOB(Vehicle vehicle)



> IS_VEHICLE_ATTACHED_TO_CARGOBOB - 0xD40148F22E81A1D9 0x5DEEC76C

BOOL IS_VEHICLE_ATTACHED_TO_CARGOBOB(Vehicle cargobob, Vehicle vehicleAttached)



> GET_VEHICLE_ATTACHED_TO_CARGOBOB - 0x873B82D42AC2B9E5 0x301A1D24

Vehicle GET_VEHICLE_ATTACHED_TO_CARGOBOB(Vehicle cargobob)

```
Returns attached vehicle (Vehicle in parameter must be cargobob)
```

> ATTACH_VEHICLE_TO_CARGOBOB - 0x4127F1D84E347769 0x607DC9D5

void ATTACH_VEHICLE_TO_CARGOBOB(Vehicle vehicle, Vehicle cargobob, int p2, float x, float y, float z)



> 0x571FEB383F629926 

void 0x571FEB383F629926(Any p0, BOOL p1)



> _GET_CARGOBOB_HOOK_POSITION - 0xCBDB9B923CACC92D 

Vector3 _GET_CARGOBOB_HOOK_POSITION(Vehicle cargobob)

```
Gets the position of the cargobob hook, in world coords.
```

> _IS_CARGOBOB_HOOK_ACTIVE - 0x1821D91AD4B56108 0xAF769B81

BOOL _IS_CARGOBOB_HOOK_ACTIVE(Vehicle cargobob)

```
Returns true only when the hook is active, will return false if the magnet is active
```

> _ENABLE_CARGOBOB_HOOK - 0x7BEB0C7A235F6F3B 0x4D3C9A99

void _ENABLE_CARGOBOB_HOOK(Vehicle cargobob, int state)

```
Drops the Hook/Magnet on a cargobob

state
enum eCargobobHook
{
	CARGOBOB_HOOK = 0,
	CARGOBOB_MAGNET = 1,
};
```

> _RETRACT_CARGOBOB_HOOK - 0x9768CF648F54C804 0xA8211EE9

void _RETRACT_CARGOBOB_HOOK(Vehicle cargobob)

```
Retracts the hook on the cargobob.

Note: after you retract it the natives for dropping the hook no longer work
```

> _SET_CARGOBOB_HOOK_POSITION - 0x877C1EAEAC531023 0x3A8AB081

void _SET_CARGOBOB_HOOK_POSITION(Any p0, float p1, float p2, BOOL p3)



> 0xCF1182F682F65307 

void 0xCF1182F682F65307(Any p0, float p1)



> _IS_CARGOBOB_MAGNET_ACTIVE - 0x6E08BF5B3722BAC9 

BOOL _IS_CARGOBOB_MAGNET_ACTIVE(Vehicle cargobob)

```
Returns true only when the magnet is active, will return false if the hook is active
```

> _CARGOBOB_MAGNET_GRAB_VEHICLE - 0x9A665550F8DA349B 

void _CARGOBOB_MAGNET_GRAB_VEHICLE(Vehicle cargobob, BOOL toggle)

```
Console Hash: 0xF57066DA
Won't attract or magnetize to any helicopters or planes of course, but that's common sense. 
```

> 0xBCBFCD9D1DAC19E2 

void 0xBCBFCD9D1DAC19E2(Any p0, float p1)



> 0xA17BAD153B51547E 

void 0xA17BAD153B51547E(Any p0, float p1)



> 0x66979ACF5102FD2F 

void 0x66979ACF5102FD2F(Any p0, float p1)



> 0x6D8EAC07506291FB 

void 0x6D8EAC07506291FB(Any p0, float p1)

```
0x60E29B78
```

> 0xED8286F71A819BAA 

void 0xED8286F71A819BAA(Any p0, float p1)



> 0x685D5561680D088B 

void 0x685D5561680D088B(Any p0, float p1)



> 0xE301BD63E9E13CF0 

void 0xE301BD63E9E13CF0(Any p0, Any p1)



> 0x9BDDC73CC6A115D4 

void 0x9BDDC73CC6A115D4(Any p0, BOOL p1, BOOL p2)

```
Console Hash: 0x50CDB295
```

> 0x56EB5E94318D3FB6 

void 0x56EB5E94318D3FB6(Any p0, BOOL p1)



> DOES_VEHICLE_HAVE_WEAPONS - 0x25ECB9F8017D98E0 0xB2E1E1FB

BOOL DOES_VEHICLE_HAVE_WEAPONS(Vehicle vehicle)



> 0x2C4A1590ABF43E8B 0x2EC19A8B

void 0x2C4A1590ABF43E8B(Any p0, BOOL p1)



> DISABLE_VEHICLE_WEAPON - 0xF4FC6A6F67D8D856 0xA688B7D1

void DISABLE_VEHICLE_WEAPON(BOOL disabled, Hash weaponHash, Vehicle vehicle, Ped owner)



> 0xE05DD0E9707003A3 0x123E5B90

void 0xE05DD0E9707003A3(Any p0, BOOL p1)



> 0x21115BCD6E44656A 0xEBC225C1

void 0x21115BCD6E44656A(Any p0, BOOL p1)



> GET_VEHICLE_CLASS - 0x29439776AAA00A62 0xC025338E

int GET_VEHICLE_CLASS(Vehicle vehicle)

```
Returns an int

Vehicle Classes:
0: Compacts
1: Sedans
2: SUVs
3: Coupes
4: Muscle
5: Sports Classics
6: Sports
7: Super
8: Motorcycles
9: Off-road
10: Industrial
11: Utility
12: Vans
13: Cycles
14: Boats
15: Helicopters
16: Planes
17: Service
18: Emergency
19: Military
20: Commercial
21: Trains

char buffer[128];
std::sprintf(buffer, 'VEH_CLASS_%i', VEHICLE::GET_VEHICLE_CLASS(vehicle));

char* className = UI::_GET_LABEL_TEXT(buffer);
```

> GET_VEHICLE_CLASS_FROM_NAME - 0xDEDF1C8BD47C2200 0xEA469980

int GET_VEHICLE_CLASS_FROM_NAME(Hash modelHash)

```
For a full enum, see here : pastebin.com/i2GGAjY0

char buffer[128];
std::sprintf(buffer, 'VEH_CLASS_%i', VEHICLE::GET_VEHICLE_CLASS_FROM_NAME (hash));

char* className = UI::_GET_LABEL_TEXT(buffer);
```

> SET_PLAYERS_LAST_VEHICLE - 0xBCDF8BAF56C87B6A 0xDE86447D

Any SET_PLAYERS_LAST_VEHICLE(Vehicle vehicle)



> SET_VEHICLE_CAN_BE_USED_BY_FLEEING_PEDS - 0x300504B23BD3B711 0x5130DB1E

void SET_VEHICLE_CAN_BE_USED_BY_FLEEING_PEDS(Vehicle vehicle, BOOL toggle)



> 0xE5810AC70602F2F5 0xB6BE07E0

void 0xE5810AC70602F2F5(Vehicle vehicle, float p1)



> _SET_VEHICLE_CREATES_MONEY_PICKUPS_WHEN_EXPLODED - 0x068F64F2470F9656 0x4BB5605D

void _SET_VEHICLE_CREATES_MONEY_PICKUPS_WHEN_EXPLODED(Vehicle vehicle, BOOL toggle)

```
Money pickups are created around cars when they explodes. Only works when the vehicle model is a car. A single pickup is between 1 and 18 dollars in size. All car models seems to give the same amount of money.

youtu.be/3arlUxzHl5Y 
i.imgur.com/WrNpYFs.jpg

From the scripts:
VEHICLE::_068F64F2470F9656(l_36, 0);

Found a 'correct' name for this :P
_dead_vehicle_pickups_dies_when_set_exploded_destroy_it_drops_on_money

SET_VEHICLE_D* or SET_VEHICLE_E*
```

> _SET_VEHICLE_JET_ENGINE_ON - 0xB8FBC8B1330CA9B4 0x51E0064F

void _SET_VEHICLE_JET_ENGINE_ON(Vehicle vehicle, BOOL toggle)

```
VEHICLE::SET_VEHICLE_ENGINE_ON is not enough to start jet engines when not inside the vehicle. But with this native set to true it works: youtu.be/OK0ps2fDpxs 
i.imgur.com/7XA14pX.png
Certain planes got jet engines.
```

> 0x10655FAB9915623D 

void 0x10655FAB9915623D(Any p0, Any p1)



> 0x79DF7E806202CE01 0xAEF9611C

void 0x79DF7E806202CE01(Any p0, Any p1)



> 0x9007A2F21DC108D4 0x585E49B6

void 0x9007A2F21DC108D4(Any p0, float p1)



> _SET_HELICOPTER_ROLL_PITCH_YAW_MULT - 0x6E0859B530A365CC 0x6E67FD35

void _SET_HELICOPTER_ROLL_PITCH_YAW_MULT(Vehicle helicopter, float multiplier)

```
value between 0.0 and 1.0
```

> SET_VEHICLE_FRICTION_OVERRIDE - 0x1837AF7C627009BA 0x32AFD42E

void SET_VEHICLE_FRICTION_OVERRIDE(Vehicle vehicle, float friction)

```
In the decompiled scripts are 2 occurencies of this method. One is in the 'country_race', setting the friction to 2, whereas in the 'trevor1'-file there are 4 values: 0.3, 0.35, 0.4 and 0.65.
I couldn't really figure out any difference, but you might succeed. In that case, please edit this.

*JulioNIB: Seems to be related to the metal parts, not tyres (like i was expecting lol)
```

> SET_VEHICLE_WHEELS_CAN_BREAK_OFF_WHEN_BLOW_UP - 0xA37B9A517B133349 0x670913A4

void SET_VEHICLE_WHEELS_CAN_BREAK_OFF_WHEN_BLOW_UP(Vehicle vehicle, BOOL toggle)



> 0xF78F94D60248C737 

BOOL 0xF78F94D60248C737(Any p0, BOOL p1)



> SET_VEHICLE_CEILING_HEIGHT - 0xA46413066687A328 0x98A10A86

void SET_VEHICLE_CEILING_HEIGHT(Vehicle vehicle, float p1)

```
Previously named GET_VEHICLE_DEFORMATION_GET_TREE (hash collision)

from Decrypted Scripts I found
VEHICLE::SET_VEHICLE_CEILING_HEIGHT(l_BD9[2/*2*/], 420.0);
```

> 0x5E569EC46EC21CAE 0xBC649C49

void 0x5E569EC46EC21CAE(Vehicle vehicle, BOOL toggle)



> 0x6D6AF961B72728AE 0x8DD9AA0C

void 0x6D6AF961B72728AE(Vehicle vehicle)



> DOES_VEHICLE_EXIST_WITH_DECORATOR - 0x956B409B984D9BF7 0x39E68EDD

BOOL DOES_VEHICLE_EXIST_WITH_DECORATOR(char* decorator)



> 0x41062318F23ED854 0xAA8BD440

void 0x41062318F23ED854(Any p0, BOOL p1)



> _SET_VEHICLE_EXCLUSIVE_DRIVER - 0xB5C51B5502E85E83 

void _SET_VEHICLE_EXCLUSIVE_DRIVER(Vehicle vehicle, Ped ped, int p2)



> 0x500873A45724C863 

void 0x500873A45724C863(Vehicle vehicle, Any p1)

```
console hash: 0x004926A3
```

> 0xB055A34527CB8FD7 

void 0xB055A34527CB8FD7(Vehicle vehicle, BOOL p1)



> _DISPLAY_DISTANT_VEHICLES - 0xF796359A959DF65D 0xB5CC548B

void _DISPLAY_DISTANT_VEHICLES(BOOL toggle)

```
Toggles to render distant vehicles. They may not be vehicles but images to look like vehicles.
```

> _SET_VEHICLE_NEON_LIGHTS_COLOUR - 0x8E0A582209A62695 

void _SET_VEHICLE_NEON_LIGHTS_COLOUR(Vehicle vehicle, int r, int g, int b)

```
Sets the color of the neon lights of the specified vehicle.

More info: pastebin.com/G49gqy8b
```

> _GET_VEHICLE_NEON_LIGHTS_COLOUR - 0x7619EEE8C886757F 

void _GET_VEHICLE_NEON_LIGHTS_COLOUR(Vehicle vehicle, int* r, int* g, int* b)

```
Gets the color of the neon lights of the specified vehicle.

See _SET_VEHICLE_NEON_LIGHTS_COLOUR (0x8E0A582209A62695) for more information
```

> _SET_VEHICLE_NEON_LIGHT_ENABLED - 0x2AA720E4287BF269 

void _SET_VEHICLE_NEON_LIGHT_ENABLED(Vehicle vehicle, int index, BOOL toggle)

```
Sets the neon lights of the specified vehicle on/off.

Indices:
0 = Left
1 = Right
2 = Front
3 = Back
```

> _IS_VEHICLE_NEON_LIGHT_ENABLED - 0x8C4B92553E4766A5 

BOOL _IS_VEHICLE_NEON_LIGHT_ENABLED(Vehicle vehicle, int index)

```
indices:
0 = Left
1 = Right
2 = Front
3 = Back
```

> 0x35E0654F4BAD7971 

void 0x35E0654F4BAD7971(BOOL p0)



> 0xB088E9A47AE6EDD5 

void 0xB088E9A47AE6EDD5(Vehicle vehicle, BOOL p1)



> 0xDBA3C090E3D74690 

void 0xDBA3C090E3D74690(Vehicle vehicle)

```
REQUEST_VEHICLE_*
```

> GET_VEHICLE_BODY_HEALTH - 0xF271147EB7B40F12 0x2B2FCC28

float GET_VEHICLE_BODY_HEALTH(Vehicle vehicle)

```
Seems related to vehicle health, like the one in IV.
Max 1000, min 0.
Vehicle does not necessarily explode or become undrivable at 0.
```

> SET_VEHICLE_BODY_HEALTH - 0xB77D05AC8C78AADB 0x920C2517

void SET_VEHICLE_BODY_HEALTH(Vehicle vehicle, float value)

```
p2 often set to 1000.0 in the decompiled scripts.
```

> 0xDF7E3EEB29642C38 

void 0xDF7E3EEB29642C38(Vehicle vehicle, Any p1, Any p2)



> _GET_VEHICLE_SUSPENSION_HEIGHT - 0x53952FD2BAA19F17 0xB73A1486

float _GET_VEHICLE_SUSPENSION_HEIGHT(Vehicle vehicle)

```
Gets the height of the vehicle's suspension.
The higher the value the lower the suspension. Each 0.002 corresponds with one more level lowered.
0.000 is the stock suspension.
0.008 is Ultra Suspension.
```

> 0x84FD40F56075E816 

void 0x84FD40F56075E816(float p0)

```
Something to do with 'high speed bump severity'?

if (!sub_87a46('SET_CAR_HIGH_SPEED_BUMP_SEVERITY_MULTIPLIER')) {
    VEHICLE::_84FD40F56075E816(0.0);
    sub_8795b('SET_CAR_HIGH_SPEED_BUMP_SEVERITY_MULTIPLIER', 1);
}
```

> 0xA7DCDF4DED40A8F4 

void 0xA7DCDF4DED40A8F4(Vehicle vehicle, BOOL p1)



> _GET_VEHICLE_BODY_HEALTH_2 - 0xB8EF61207C2393A9 

float _GET_VEHICLE_BODY_HEALTH_2(Vehicle vehicle)

```
0 min 100 max
starts at 100
Seams to have health zones
Front of vehicle when damaged goes from 100-50 and stops at 50.
Rear can be damaged from 100-0
Only tested with two cars.

any idea how this differs from the first one?

--
May return the vehicle health on a scale of 0.0 - 100.0 (needs to be confirmed)

example:

v_F = ENTITY::GET_ENTITY_MODEL(v_3);
if (((v_F == ${tanker}) || (v_F == ${armytanker})) || (v_F == ${tanker2})) {
    if (VEHICLE::_GET_VEHICLE_BODY_HEALTH_2(v_3) &lt;= 1.0) {
        NETWORK::NETWORK_EXPLODE_VEHICLE(v_3, 1, 1, -1);
    }
}
```

> 0xD4C4642CB7F50B5D 

BOOL 0xD4C4642CB7F50B5D(Vehicle vehicle)

```
Only used like this:

if (VEHICLE::_D4C4642CB7F50B5D(ENTITY::GET_VEHICLE_INDEX_FROM_ENTITY_INDEX(v_3))) {                                                        sub_157e9c(g_40001._f1868, 0);
}
```

> 0xC361AA040D6637A8 

void 0xC361AA040D6637A8(Any p0, BOOL p1)



> 0x99C82F8A139F3E4E 

void 0x99C82F8A139F3E4E(Any p0, BOOL p1)

```
console hash: 0x71CDD52F
```

> 0xE16142B94664DEFD 

void 0xE16142B94664DEFD(Any p0, BOOL p1)



