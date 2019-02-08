# Ped

> CREATE_PED - 0xD49F9B0955C367DE 0x0389EF71

Ped CREATE_PED(int pedType, Hash modelHash, float x, float y, float z, float heading, BOOL networkHandle, BOOL pedHandle)

```
p7 - last parameter does not mean ped handle is returned
maybe a quick view in disassembly will tell us what is actually does


*Heading*: 0.0
*Heading* is the Z axis spawn rotation of the ped 0-&gt;5th parameter.

Ped Types:
[Player,1|Male,4|Female,5|Cop,6|Human,26|SWAT,27|Animal,28|Army,29]
You can also use GET_PED_TYPE
```

> DELETE_PED - 0x9614299DCB53E54B 0x13EFB9A0

void DELETE_PED(Ped* ped)

```
Deletes the specified ped, then sets the handle pointed to by the pointer to NULL.
```

> CLONE_PED - 0xEF29A16337FACADB 0x8C8A8D6E

Ped CLONE_PED(Ped ped, float heading, BOOL networkHandle, BOOL pedHandle)

```
p3 - last parameter does not mean ped handle is returned
maybe a quick view in disassembly will tell us what is actually does


Example of Cloning Your Player:
CLONE_PED(PLAYER_PED_ID(), GET_ENTITY_HEADING(PLAYER_PED_ID()), 0, 1);
```

> CLONE_PED_TO_TARGET - 0xE952D6431689AD9A 0xFC70EEC7

void CLONE_PED_TO_TARGET(Ped ped1, Ped ped2)



> IS_PED_IN_VEHICLE - 0xA3EE4A07279BB9DB 0x7DA6BC83

BOOL IS_PED_IN_VEHICLE(Ped ped, Vehicle vehicle, BOOL atGetIn)

```
Gets a value indicating whether the specified ped is in the specified vehicle.

If 'atGetIn' is false, the function will not return true until the ped is sitting in the vehicle and is about to close the door. If it's true, the function returns true the moment the ped starts to get onto the seat (after opening the door). Eg. if false, and the ped is getting into a submersible, the function will not return true until the ped has descended down into the submersible and gotten into the seat, while if it's true, it'll return true the moment the hatch has been opened and the ped is about to descend into the submersible.
```

> IS_PED_IN_MODEL - 0x796D90EFB19AA332 0xA6438D4B

BOOL IS_PED_IN_MODEL(Ped ped, Hash modelHash)



> IS_PED_IN_ANY_VEHICLE - 0x997ABD671D25CA0B 0x3B0171EE

BOOL IS_PED_IN_ANY_VEHICLE(Ped ped, BOOL atGetIn)

```
Gets a value indicating whether the specified ped is in any vehicle.

If 'atGetIn' is false, the function will not return true until the ped is sitting in the vehicle and is about to close the door. If it's true, the function returns true the moment the ped starts to get onto the seat (after opening the door). Eg. if false, and the ped is getting into a submersible, the function will not return true until the ped has descended down into the submersible and gotten into the seat, while if it's true, it'll return true the moment the hatch has been opened and the ped is about to descend into the submersible.
```

> IS_COP_PED_IN_AREA_3D - 0x16EC4839969F9F5E 0xB98DB96B

BOOL IS_COP_PED_IN_AREA_3D(float x1, float y1, float z1, float x2, float y2, float z2)

```
xyz - relative to the world origin.
```

> IS_PED_INJURED - 0x84A2DD9AC37C35C1 0x2530A087

BOOL IS_PED_INJURED(Ped ped)

```
Gets a value indicating whether this ped's health is below its injured threshold.

The default threshold is 100.
```

> IS_PED_HURT - 0x5983BB449D7FDB12 0x69DFA0AF

BOOL IS_PED_HURT(Ped ped)

```
Returns whether the specified ped is hurt.
```

> IS_PED_FATALLY_INJURED - 0xD839450756ED5A80 0xBADA0093

BOOL IS_PED_FATALLY_INJURED(Ped ped)

```
MulleDK19: Gets a value indicating whether this ped's health is below its fatally injured threshold. The default threshold is 100.
If the handle is invalid, the function returns true.
```

> IS_PED_DEAD_OR_DYING - 0x3317DEDB88C95038 0xCBDB7739

BOOL IS_PED_DEAD_OR_DYING(Ped ped, BOOL p1)

```
Seems to consistently return true if the ped is dead.

p1 is always passed 1 in the scripts.

I suggest to remove 'OR_DYING' part, because it does not detect dying phase.

That's what the devs call it, cry about it.

lol
```

> IS_CONVERSATION_PED_DEAD - 0xE0A0AEC214B1FABA 0x1FA39EFE

BOOL IS_CONVERSATION_PED_DEAD(Ped ped)



> IS_PED_AIMING_FROM_COVER - 0x3998B1276A3300E5 0xDEBAB2AF

BOOL IS_PED_AIMING_FROM_COVER(Ped ped)



> IS_PED_RELOADING - 0x24B100C68C645951 0x961E1745

BOOL IS_PED_RELOADING(Ped ped)

```
Returns whether the specified ped is reloading.
```

> IS_PED_A_PLAYER - 0x12534C348C6CB68B 0x404794CA

BOOL IS_PED_A_PLAYER(Ped ped)

```
Returns true if the given ped has a valid pointer to CPlayerInfo in its CPed class. That's all.
```

> CREATE_PED_INSIDE_VEHICLE - 0x7DD959874C1FD534 0x3000F092

Ped CREATE_PED_INSIDE_VEHICLE(Vehicle vehicle, int pedType, Hash modelHash, int seat, BOOL networkHandle, BOOL pedHandle)

```
p5 - last parameter does not mean ped handle is returned
maybe a quick view in disassembly will tell us what is actually does


Ped Types:
Player = 1
Male = 4 
Female = 5 
Cop = 6
Taxi Driver = 25 (sfink)
Human = 26
SWAT = 27 
Animal = 28
Army = 29
```

> SET_PED_DESIRED_HEADING - 0xAA5A7ECE2AA8FE70 0x961458F9

void SET_PED_DESIRED_HEADING(Ped ped, float heading)



> 0xFF287323B0E2C69A 0x290421BE

void 0xFF287323B0E2C69A(Ped ped)



> IS_PED_FACING_PED - 0xD71649DB0A545AA3 0x0B775838

BOOL IS_PED_FACING_PED(Ped ped, Ped otherPed, float angle)

```
angle is ped's view cone
```

> IS_PED_IN_MELEE_COMBAT - 0x4E209B2C1EAD5159 0xFD7814A5

BOOL IS_PED_IN_MELEE_COMBAT(Ped ped)

```
Notes: The function only returns true while the ped is: 
A.) Swinging a random melee attack (including pistol-whipping)

B.) Reacting to being hit by a melee attack (including pistol-whipping)

C.) Is locked-on to an enemy (arms up, strafing/skipping in the default fighting-stance, ready to dodge+counter). 

You don't have to be holding the melee-targetting button to be in this stance; you stay in it by default for a few seconds after swinging at someone. If you do a sprinting punch, it returns true for the duration of the punch animation and then returns false again, even if you've punched and made-angry many peds
```

> IS_PED_STOPPED - 0x530944F6F4B8A214 0xA0DC0B87

BOOL IS_PED_STOPPED(Ped ped)

```
Returns true if the ped doesn't do any movement. If the ped is being pushed forwards by using APPLY_FORCE_TO_ENTITY for example, the function returns false.
```

> IS_PED_SHOOTING_IN_AREA - 0x7E9DFE24AC1E58EF 0x741BF04F

BOOL IS_PED_SHOOTING_IN_AREA(Ped ped, float x1, float y1, float z1, float x2, float y2, float z2, BOOL p7, BOOL p8)



> IS_ANY_PED_SHOOTING_IN_AREA - 0xA0D3D71EA1086C55 0x91833867

BOOL IS_ANY_PED_SHOOTING_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, BOOL p6, BOOL p7)



> IS_PED_SHOOTING - 0x34616828CD07F1A1 0xE7C3405E

BOOL IS_PED_SHOOTING(Ped ped)

```
Returns whether the specified ped is shooting.
```

> SET_PED_ACCURACY - 0x7AEFB85C1D49DEB6 0x6C17122E

Any SET_PED_ACCURACY(Ped ped, int accuracy)

```
accuracy = 0-100, 100 being perfectly accurate
```

> GET_PED_ACCURACY - 0x37F4AD56ECBC0CD6 0x0A2A0AA0

int GET_PED_ACCURACY(Ped ped)



> IS_PED_MODEL - 0xC9D55B1A358A5BF7 0x5F1DDFCB

BOOL IS_PED_MODEL(Ped ped, Hash modelHash)



> EXPLODE_PED_HEAD - 0x2D05CED3A38D0F3A 0x05CC1380

void EXPLODE_PED_HEAD(Ped ped, Hash weaponHash)

```
Forces the ped to fall back and kills it.
```

> REMOVE_PED_ELEGANTLY - 0xAC6D445B994DF95E 0x4FFB8C6C

void REMOVE_PED_ELEGANTLY(Ped* ped)

```
MulleDK19: Judging purely from a quick disassembly, if the ped is in a vehicle, the ped will be deleted immediately. If not, it'll be marked as no longer needed.
```

> ADD_ARMOUR_TO_PED - 0x5BA652A0CD14DF2F 0xF686B26E

void ADD_ARMOUR_TO_PED(Ped ped, int amount)

```
Same as SET_PED_ARMOUR, but ADDS 'amount' to the armor the Ped already has.
```

> SET_PED_ARMOUR - 0xCEA04D83135264CC 0x4E3A0CC4

void SET_PED_ARMOUR(Ped ped, int amount)

```
Sets the armor of the specified ped.

ped: The Ped to set the armor of.
amount: A value between 0 and 100 indicating the value to set the Ped's armor to.
```

> SET_PED_INTO_VEHICLE - 0xF75B0D629E1C063D 0x07500C79

void SET_PED_INTO_VEHICLE(Ped ped, Vehicle vehicle, int seatIndex)

```
Ped: The ped to warp.
vehicle: The vehicle to warp the ped into.
Seat_Index: [-1 is driver seat, -2 first free passenger seat]

Moreinfo of Seat Index
DriverSeat = -1
Passenger = 0
Left Rear = 1
RightRear = 2
```

> SET_PED_ALLOW_VEHICLES_OVERRIDE - 0x3C028C636A414ED9 0x58A80BD5

void SET_PED_ALLOW_VEHICLES_OVERRIDE(Ped ped, BOOL toggle)



> CAN_CREATE_RANDOM_PED - 0x3E8349C08E4B82E4 0xF9ABE88F

BOOL CAN_CREATE_RANDOM_PED(BOOL unk)



> CREATE_RANDOM_PED - 0xB4AC7D0CF06BFE8F 0x5A949543

Ped CREATE_RANDOM_PED(float posX, float posY, float posZ)

```
vb.net
Dim ped_handle As Integer
                    With Game.Player.Character
                        Dim pos As Vector3 = .Position + .ForwardVector * 3
                        ped_handle = Native.Function.Call(Of Integer)(Hash.CREATE_RANDOM_PED, pos.X, pos.Y, pos.Z)
                    End With

Creates a Ped at the specified location, returns the Ped Handle.  
Ped will not act until SET_PED_AS_NO_LONGER_NEEDED is called.
```

> CREATE_RANDOM_PED_AS_DRIVER - 0x9B62392B474F44A0 0xB927CE9A

Ped CREATE_RANDOM_PED_AS_DRIVER(Vehicle vehicle, BOOL returnHandle)



> CAN_CREATE_RANDOM_DRIVER - 0xB8EB95E5B4E56978 0x99861609

BOOL CAN_CREATE_RANDOM_DRIVER()



> CAN_CREATE_RANDOM_BIKE_RIDER - 0xEACEEDA81751915C 0x7018BE31

BOOL CAN_CREATE_RANDOM_BIKE_RIDER()



> SET_PED_MOVE_ANIMS_BLEND_OUT - 0x9E8C908F41584ECD 0x20E01957

void SET_PED_MOVE_ANIMS_BLEND_OUT(Ped ped)



> SET_PED_CAN_BE_DRAGGED_OUT - 0xC1670E958EEE24E5 0xAA7F1131

void SET_PED_CAN_BE_DRAGGED_OUT(Ped ped, BOOL toggle)



> 0xF2BEBCDFAFDAA19E 0x6CD58238

void 0xF2BEBCDFAFDAA19E(BOOL toggle)

```
toggle was always 0 except in one instance (b678).

The one time this is set to true seems to do with when you fail the mission.
```

> IS_PED_MALE - 0x6D9F5FAA7488BA46 0x90950455

BOOL IS_PED_MALE(Ped ped)

```
Returns true/false if the ped is/isn't male.

Edited by: Enumerator
```

> IS_PED_HUMAN - 0xB980061DA992779D 0x194BB7B0

BOOL IS_PED_HUMAN(Ped ped)

```
Returns true/false if the ped is/isn't humanoid.

Edited by: Enumerator
```

> GET_VEHICLE_PED_IS_IN - 0x9A9112A0FE9A4713 0xAFE92319

Vehicle GET_VEHICLE_PED_IS_IN(Ped ped, BOOL getLastVehicle)

```
Gets the vehicle the specified Ped is/was in depending on bool value.

[False = CurrentVehicle, True = LastVehicle]
```

> RESET_PED_LAST_VEHICLE - 0xBB8DE8CF6A8DD8BB 0x5E3B5942

void RESET_PED_LAST_VEHICLE(Ped ped)

```
Resets the value for the last vehicle driven by the Ped.
```

> SET_PED_DENSITY_MULTIPLIER_THIS_FRAME - 0x95E3D6257B166CF2 0x039C82BB

void SET_PED_DENSITY_MULTIPLIER_THIS_FRAME(float multiplier)

```

� Usage

> Use this native inside a looped function.
> Values:
> 0.0 = no peds on streets
> 1.0 = normal peds on streets
```

> SET_SCENARIO_PED_DENSITY_MULTIPLIER_THIS_FRAME - 0x7A556143A1C03898 0x2909ABF0

void SET_SCENARIO_PED_DENSITY_MULTIPLIER_THIS_FRAME(float p0, float p1)



> 0x5A7F62FDA59759BD 0xB48C0C04

void 0x5A7F62FDA59759BD()



> SET_SCRIPTED_CONVERSION_COORD_THIS_FRAME - 0x5086C7843552CF85 0x25EA2AA5

void SET_SCRIPTED_CONVERSION_COORD_THIS_FRAME(float x, float y, float z)



> SET_PED_NON_CREATION_AREA - 0xEE01041D559983EA 0x7A97283F

void SET_PED_NON_CREATION_AREA(float x1, float y1, float z1, float x2, float y2, float z2)

```
The distance between these points, is the diagonal of a box (remember it's 3D).
```

> CLEAR_PED_NON_CREATION_AREA - 0x2E05208086BA0651 0x6F7043A3

void CLEAR_PED_NON_CREATION_AREA()



> 0x4759CC730F947C81 0x8C555ADD

void 0x4759CC730F947C81()



> IS_PED_ON_MOUNT - 0x460BC76A0E10655E 0x43103006

BOOL IS_PED_ON_MOUNT(Ped ped)

```
Same function call as PED::GET_MOUNT, aka just returns 0
```

> GET_MOUNT - 0xE7E11B8DCBED1058 0xDD31EC4E

Ped GET_MOUNT(Ped ped)

```

Function just returns 0
void __fastcall ped__get_mount(NativeContext *a1)
{
  NativeContext *v1; // rbx@1

  v1 = a1;
  GetAddressOfPedFromScriptHandle(a1-&gt;Args-&gt;Arg1);
  v1-&gt;Returns-&gt;Item1= 0;
}
```

> IS_PED_ON_VEHICLE - 0x67722AEB798E5FAB 0xA1AE7CC7

BOOL IS_PED_ON_VEHICLE(Ped ped)

```
Gets a value indicating whether the specified ped is on top of any vehicle.

Return 1 when ped is on vehicle.
Return 0 when ped is not on a vehicle.

```

> IS_PED_ON_SPECIFIC_VEHICLE - 0xEC5F66E459AF3BB2 0x63CB4603

BOOL IS_PED_ON_SPECIFIC_VEHICLE(Ped ped, Vehicle vehicle)



> SET_PED_MONEY - 0xA9C8960E8684C1B5 0x40D90BF2

void SET_PED_MONEY(Ped ped, int amount)

```
Maximum possible amount of money on MP is 2000. ~JX

-----------------------------------------------------------------------------

Maximum amount that a ped can theoretically have is 65535 (0xFFFF) since the amount is stored as an unsigned short (uint16_t) value.
```

> GET_PED_MONEY - 0x3F69145BBA87BAE7 0xEB3C4C7E

int GET_PED_MONEY(Ped ped)



> 0xFF4803BC019852D9 0xD41C9AED

void 0xFF4803BC019852D9(float p0, Any p1)



> 0x6B0E6172C9A4D902 0x30B98369

void 0x6B0E6172C9A4D902(BOOL p0)



> 0x9911F4A24485F653 0x02A080C8

void 0x9911F4A24485F653(BOOL p0)



> SET_PED_SUFFERS_CRITICAL_HITS - 0xEBD76F2359F190AC 0x6F6FC7E6

void SET_PED_SUFFERS_CRITICAL_HITS(Ped ped, BOOL toggle)

```
ped cannot be headshot if this is set to false
```

> 0xAFC976FD0580C7B3 0x1572022A

void 0xAFC976FD0580C7B3(Ped ped, BOOL toggle)



> IS_PED_SITTING_IN_VEHICLE - 0xA808AA1D79230FC2 0xDDDE26FA

BOOL IS_PED_SITTING_IN_VEHICLE(Ped ped, Vehicle vehicle)

```
Detect if ped is sitting in the specified vehicle
[True/False]
```

> IS_PED_SITTING_IN_ANY_VEHICLE - 0x826AA586EDB9FEF8 0x0EA9CA03

BOOL IS_PED_SITTING_IN_ANY_VEHICLE(Ped ped)

```
Detect if ped is in any vehicle
[True/False]

Edited by: Enumerator
```

> IS_PED_ON_FOOT - 0x01FEE67DB37F59B2 0xC60D0785

BOOL IS_PED_ON_FOOT(Ped ped)



> IS_PED_ON_ANY_BIKE - 0x94495889E22C6479 0x4D885B2E

BOOL IS_PED_ON_ANY_BIKE(Ped ped)



> IS_PED_PLANTING_BOMB - 0xC70B5FAE151982D8 0x0EDAC574

BOOL IS_PED_PLANTING_BOMB(Ped ped)



> GET_DEAD_PED_PICKUP_COORDS - 0xCD5003B097200F36 0x129F9DC1

Vector3 GET_DEAD_PED_PICKUP_COORDS(Ped ped, float p1, float p2)



> IS_PED_IN_ANY_BOAT - 0x2E0E1C2B4F6CB339 0x1118A947

BOOL IS_PED_IN_ANY_BOAT(Ped ped)



> IS_PED_IN_ANY_SUB - 0xFBFC01CCFB35D99E 0xE65F8059

BOOL IS_PED_IN_ANY_SUB(Ped ped)



> IS_PED_IN_ANY_HELI - 0x298B91AE825E5705 0x7AB5523B

BOOL IS_PED_IN_ANY_HELI(Ped ped)



> IS_PED_IN_ANY_PLANE - 0x5FFF4CFC74D8FB80 0x51BBCE7E

BOOL IS_PED_IN_ANY_PLANE(Ped ped)



> IS_PED_IN_FLYING_VEHICLE - 0x9134873537FA419C 0xCA072485

BOOL IS_PED_IN_FLYING_VEHICLE(Ped ped)



> SET_PED_DIES_IN_WATER - 0x56CEF0AC79073BDE 0x604C872B

void SET_PED_DIES_IN_WATER(Ped ped, BOOL toggle)



> SET_PED_DIES_IN_SINKING_VEHICLE - 0xD718A22995E2B4BC 0x8D4D9ABB

void SET_PED_DIES_IN_SINKING_VEHICLE(Ped ped, BOOL toggle)



> GET_PED_ARMOUR - 0x9483AF821605B1D8 0x2CE311A7

int GET_PED_ARMOUR(Ped ped)



> SET_PED_STAY_IN_VEHICLE_WHEN_JACKED - 0xEDF4079F9D54C9A1 0xB014A09C

void SET_PED_STAY_IN_VEHICLE_WHEN_JACKED(Ped ped, BOOL toggle)



> SET_PED_CAN_BE_SHOT_IN_VEHICLE - 0xC7EF1BA83230BA07 0x5DB7B3A9

void SET_PED_CAN_BE_SHOT_IN_VEHICLE(Ped ped, BOOL toggle)



> GET_PED_LAST_DAMAGE_BONE - 0xD75960F6BD9EA49C 0xAB933841

BOOL GET_PED_LAST_DAMAGE_BONE(Ped ped, int* outBone)



> CLEAR_PED_LAST_DAMAGE_BONE - 0x8EF6B7AC68E2F01B 0x56CB715E

void CLEAR_PED_LAST_DAMAGE_BONE(Ped ped)



> SET_AI_WEAPON_DAMAGE_MODIFIER - 0x1B1E2A40A65B8521 0x516E30EE

void SET_AI_WEAPON_DAMAGE_MODIFIER(float value)



> RESET_AI_WEAPON_DAMAGE_MODIFIER - 0xEA16670E7BA4743C 0x6E965420

void RESET_AI_WEAPON_DAMAGE_MODIFIER()



> SET_AI_MELEE_WEAPON_DAMAGE_MODIFIER - 0x66460DEDDD417254 0x0F9A401F

void SET_AI_MELEE_WEAPON_DAMAGE_MODIFIER(float modifier)



> RESET_AI_MELEE_WEAPON_DAMAGE_MODIFIER - 0x46E56A7CD1D63C3F 0x97886238

void RESET_AI_MELEE_WEAPON_DAMAGE_MODIFIER()



> 0x2F3C3D9F50681DE4 0xCC9D7F1A

void 0x2F3C3D9F50681DE4(Any p0, BOOL p1)



> SET_PED_CAN_BE_TARGETTED - 0x63F58F7C80513AAD 0x75C49F74

void SET_PED_CAN_BE_TARGETTED(Ped ped, BOOL toggle)



> SET_PED_CAN_BE_TARGETTED_BY_TEAM - 0xBF1CA77833E58F2C 0xB103A8E1

void SET_PED_CAN_BE_TARGETTED_BY_TEAM(Ped ped, int team, BOOL toggle)



> SET_PED_CAN_BE_TARGETTED_BY_PLAYER - 0x66B57B72E0836A76 0xD050F490

void SET_PED_CAN_BE_TARGETTED_BY_PLAYER(Ped ped, Player player, BOOL toggle)



> 0x061CB768363D6424 0x7DA12905

void 0x061CB768363D6424(Any p0, BOOL p1)



> SET_TIME_EXCLUSIVE_DISPLAY_TEXTURE - 0xFD325494792302D7 0x7F67671D

void SET_TIME_EXCLUSIVE_DISPLAY_TEXTURE(Any p0, BOOL p1)

```
Hash collision. Please change back to _0x_
```

> IS_PED_IN_ANY_POLICE_VEHICLE - 0x0BD04E29640C9C12 0x84FA790D

BOOL IS_PED_IN_ANY_POLICE_VEHICLE(Ped ped)



> FORCE_PED_TO_OPEN_PARACHUTE - 0x16E42E800B472221 0xA819680B

void FORCE_PED_TO_OPEN_PARACHUTE(Ped ped)



> IS_PED_IN_PARACHUTE_FREE_FALL - 0x7DCE8BDA0F1C1200 0xCD71F11B

BOOL IS_PED_IN_PARACHUTE_FREE_FALL(Ped ped)



> IS_PED_FALLING - 0xFB92A102F1C4DFA3 0xABF77334

BOOL IS_PED_FALLING(Ped ped)



> IS_PED_JUMPING - 0xCEDABC5900A0BF97 0x07E5BC0E

BOOL IS_PED_JUMPING(Ped ped)



> IS_PED_CLIMBING - 0x53E8CB4F48BFE623 0xBCE03D35

BOOL IS_PED_CLIMBING(Ped ped)



> IS_PED_VAULTING - 0x117C70D1F5730B5E 0xC3169BDA

BOOL IS_PED_VAULTING(Ped ped)



> IS_PED_DIVING - 0x5527B8246FEF9B11 0x7BC5BF3C

BOOL IS_PED_DIVING(Ped ped)



> IS_PED_JUMPING_OUT_OF_VEHICLE - 0x433DDFFE2044B636 0xB19215F6

BOOL IS_PED_JUMPING_OUT_OF_VEHICLE(Ped ped)



> 0x26AF0E8E30BD2A2C 

BOOL 0x26AF0E8E30BD2A2C(Ped ped)



> GET_PED_PARACHUTE_STATE - 0x79CFD9827CC979B6 0x7D4BC475

int GET_PED_PARACHUTE_STATE(Ped ped)

```
Returns:

-1: Normal
0: Wearing parachute on back
1: Parachute opening
2: Parachute open
3: Falling to doom (e.g. after exiting parachute)

Normal means no parachute?
```

> GET_PED_PARACHUTE_LANDING_TYPE - 0x8B9F1FC6AE8166C0 0x01F3B035

int GET_PED_PARACHUTE_LANDING_TYPE(Ped ped)

```
-1: no landing
0: landing on both feet
1: stumbling
2: rolling
3: ragdoll
```

> SET_PED_PARACHUTE_TINT_INDEX - 0x333FC8DB079B7186 0x5AEFEC3A

void SET_PED_PARACHUTE_TINT_INDEX(Ped ped, Any tintIndex)



> GET_PED_PARACHUTE_TINT_INDEX - 0xEAF5F7E5AE7C6C9D 0xE9E7FAC5

void GET_PED_PARACHUTE_TINT_INDEX(Ped ped, Any* outTintIndex)



> SET_PED_RESERVE_PARACHUTE_TINT_INDEX - 0xE88DA0751C22A2AD 0x177EFC79

void SET_PED_RESERVE_PARACHUTE_TINT_INDEX(Any p0, Any p1)



> 0x8C4F3BF23B6237DB 

Entity 0x8C4F3BF23B6237DB(Ped ped, BOOL p1, BOOL p2)



> SET_PED_DUCKING - 0x030983CA930B692D 0xB90353D7

void SET_PED_DUCKING(Ped ped, BOOL toggle)

```
MulleDK19: Does nothing. Characters cannot duck in GTA V.

^^
Wrong this is for ducking in the vehicle.
- jedijosh920

MulleDK19: ^ Wrong. This is the SET_CHAR_DUCKING from GTA IV, that makes Peds duck. This function does nothing in GTA V. It cannot set the ped as ducking in vehicles, and IS_PED_DUCKING will always return false.
```

> IS_PED_DUCKING - 0xD125AE748725C6BC 0x9199C77D

BOOL IS_PED_DUCKING(Ped ped)



> IS_PED_IN_ANY_TAXI - 0x6E575D6A898AB852 0x16FD386C

BOOL IS_PED_IN_ANY_TAXI(Ped ped)



> SET_PED_ID_RANGE - 0xF107E836A70DCE05 0xEF3B4ED9

void SET_PED_ID_RANGE(Ped ped, float value)



> 0x52D59AB61DDC05DD 0x9A2180FF

void 0x52D59AB61DDC05DD(Ped ped, BOOL p1)



> 0xEC4B4B3B9908052A 0xF30658D2

void 0xEC4B4B3B9908052A(Any p0, float p1)

```
SET_PED_*

Has most likely to do with some shooting attributes as it sets the float which is in the same range as shootRate.
```

> 0x733C87D4CE22BEA2 0x43709044

void 0x733C87D4CE22BEA2(Any p0)



> SET_PED_SEEING_RANGE - 0xF29CF591C4BF6CEE 0x4BD72FE8

void SET_PED_SEEING_RANGE(Ped ped, float value)



> SET_PED_HEARING_RANGE - 0x33A8F7F7D5F7F33C 0xB32087E0

void SET_PED_HEARING_RANGE(Ped ped, float value)



> SET_PED_VISUAL_FIELD_MIN_ANGLE - 0x2DB492222FB21E26 0x72E2E18B

void SET_PED_VISUAL_FIELD_MIN_ANGLE(Ped ped, float value)



> SET_PED_VISUAL_FIELD_MAX_ANGLE - 0x70793BDCA1E854D4 0x0CEA0F9A

void SET_PED_VISUAL_FIELD_MAX_ANGLE(Ped ped, float value)



> SET_PED_VISUAL_FIELD_MIN_ELEVATION_ANGLE - 0x7A276EB2C224D70F 0x5CC2F1B8

void SET_PED_VISUAL_FIELD_MIN_ELEVATION_ANGLE(Ped ped, float angle)

```
This native refers to the field of vision the ped has below them, starting at 0 degrees. The angle value should be negative.
-90f should let the ped see 90 degrees below them, for example.
```

> SET_PED_VISUAL_FIELD_MAX_ELEVATION_ANGLE - 0x78D0B67629D75856 0x39D9102F

void SET_PED_VISUAL_FIELD_MAX_ELEVATION_ANGLE(Ped ped, float angle)

```
This native refers to the field of vision the ped has above them, starting at 0 degrees. 90f would let the ped see enemies directly above of them.
```

> SET_PED_VISUAL_FIELD_PERIPHERAL_RANGE - 0x9C74B0BC831B753A 0xFDF2F7C2

void SET_PED_VISUAL_FIELD_PERIPHERAL_RANGE(Ped ped, float range)



> SET_PED_VISUAL_FIELD_CENTER_ANGLE - 0x3B6405E8AB34A907 0xE57202A1

void SET_PED_VISUAL_FIELD_CENTER_ANGLE(Ped ped, float angle)



> SET_PED_STEALTH_MOVEMENT - 0x88CBB5CEB96B7BD2 0x67E28E1D

void SET_PED_STEALTH_MOVEMENT(Ped ped, BOOL p1, char* action)

```
p1 is usually 0 in the scripts. action is either 0 or a pointer to 'DEFAULT_ACTION'.
```

> GET_PED_STEALTH_MOVEMENT - 0x7C2AC9CA66575FBF 0x40321B83

BOOL GET_PED_STEALTH_MOVEMENT(Ped ped)

```
Returns whether the entity is in stealth mode
```

> CREATE_GROUP - 0x90370EBE0FEE1A3D 0x8DC0368D

int CREATE_GROUP(int unused)

```
Creates a new ped group.
Groups can contain up to 8 peds.

The parameter is unused.

Returns a handle to the created group, or 0 if a group couldn't be created.
```

> SET_PED_AS_GROUP_LEADER - 0x2A7819605465FBCE 0x7265BEA2

void SET_PED_AS_GROUP_LEADER(Ped ped, int groupId)



> SET_PED_AS_GROUP_MEMBER - 0x9F3480FE65DB31B5 0x0EE13F92

void SET_PED_AS_GROUP_MEMBER(Ped ped, int groupId)



> SET_PED_CAN_TELEPORT_TO_GROUP_LEADER - 0x2E2F4240B3F24647 0xD0D8BDBC

void SET_PED_CAN_TELEPORT_TO_GROUP_LEADER(Ped pedHandle, int groupHandle, BOOL toggle)

```
This only will teleport the ped to the group leader if the group leader teleports (sets coords).

Only works in singleplayer
```

> REMOVE_GROUP - 0x8EB2F69076AF7053 0x48D72B88

void REMOVE_GROUP(int groupId)



> REMOVE_PED_FROM_GROUP - 0xED74007FFB146BC2 0x82697713

void REMOVE_PED_FROM_GROUP(Ped ped)



> IS_PED_GROUP_MEMBER - 0x9BB01E3834671191 0x876D5363

BOOL IS_PED_GROUP_MEMBER(Ped ped, int groupId)



> IS_PED_HANGING_ON_TO_VEHICLE - 0x1C86D8AEF8254B78 0x9678D4FF

BOOL IS_PED_HANGING_ON_TO_VEHICLE(Ped ped)



> SET_GROUP_SEPARATION_RANGE - 0x4102C7858CFEE4E4 0x7B820CD5

void SET_GROUP_SEPARATION_RANGE(int groupHandle, float separationRange)

```
Sets the range at which members will automatically leave the group.
```

> SET_PED_MIN_GROUND_TIME_FOR_STUNGUN - 0xFA0675AB151073FA 0x2F0D0973

void SET_PED_MIN_GROUND_TIME_FOR_STUNGUN(Ped ped, int ms)

```
Ped will stay on the ground after being stunned for at lest ms time. (in milliseconds)
```

> IS_PED_PRONE - 0xD6A86331A537A7B9 0x02C2A6C3

BOOL IS_PED_PRONE(Ped ped)



> IS_PED_IN_COMBAT - 0x4859F1FC66A6278E 0xFE027CB5

BOOL IS_PED_IN_COMBAT(Ped ped, Ped target)

```
Checks to see if ped and target are in combat with eachother. Only goes one-way: if target is engaged in combat with ped but ped has not yet reacted, the function will return false until ped starts fighting back.

p1 is usually 0 in the scripts because it gets the ped id during the task sequence. For instance: PED::IS_PED_IN_COMBAT(l_42E[4/*14*/], PLAYER::PLAYER_PED_ID()) // armenian2.ct4: 43794
```

> CAN_PED_IN_COMBAT_SEE_TARGET - 0xEAD42DE3610D0721 0xCCD525E1

BOOL CAN_PED_IN_COMBAT_SEE_TARGET(Ped ped, Ped target)



> IS_PED_DOING_DRIVEBY - 0xB2C086CC1BF8F2BF 0xAC3CEB9C

BOOL IS_PED_DOING_DRIVEBY(Ped ped)



> IS_PED_JACKING - 0x4AE4FF911DFB61DA 0x3B321816

BOOL IS_PED_JACKING(Ped ped)



> IS_PED_BEING_JACKED - 0x9A497FE2DF198913 0xD45D605C

BOOL IS_PED_BEING_JACKED(Ped ped)



> IS_PED_BEING_STUNNED - 0x4FBACCE3B4138EE8 0x0A66CE30

BOOL IS_PED_BEING_STUNNED(Ped ped, int p1)

```
p1 is always 0
```

> GET_PEDS_JACKER - 0x9B128DC36C1E04CF 0xDE1DBB59

Ped GET_PEDS_JACKER(Ped ped)



> GET_JACK_TARGET - 0x5486A79D9FBD342D 0x1D196361

Ped GET_JACK_TARGET(Ped ped)



> IS_PED_FLEEING - 0xBBCCE00B381F8482 0x85D813C6

BOOL IS_PED_FLEEING(Ped ped)



> IS_PED_IN_COVER - 0x60DFD0691A170B88 0x972C5A8B

BOOL IS_PED_IN_COVER(Ped ped, BOOL p1)

```
p1 is nearly always 0 in the scripts. 
```

> IS_PED_IN_COVER_FACING_LEFT - 0x845333B3150583AB 0xB89DBB80

BOOL IS_PED_IN_COVER_FACING_LEFT(Ped ped)



> 0x6A03BF943D767C93 

BOOL 0x6A03BF943D767C93(Ped ped)

```
Console Hash: 0xDD5D08A7
```

> IS_PED_GOING_INTO_COVER - 0x9F65DBC537E59AD5 0xA3589628

BOOL IS_PED_GOING_INTO_COVER(Ped ped)



> SET_PED_PINNED_DOWN - 0xAAD6D1ACF08F4612 0xCC78999D

Any SET_PED_PINNED_DOWN(Ped ped, BOOL pinned, int i)

```
i could be time. Only example in the decompiled scripts uses it as -1.
```

> GET_SEAT_PED_IS_TRYING_TO_ENTER - 0x6F4C85ACD641BCD2 0xACF162E0

int GET_SEAT_PED_IS_TRYING_TO_ENTER(Ped ped)



> GET_VEHICLE_PED_IS_TRYING_TO_ENTER - 0x814FA8BE5449445D 0x99968B37

Vehicle GET_VEHICLE_PED_IS_TRYING_TO_ENTER(Ped ped)



> GET_PED_SOURCE_OF_DEATH - 0x93C8B64DEB84728C 0x84ADF9EB

Entity GET_PED_SOURCE_OF_DEATH(Ped ped)

```
Returns the Entity (Ped, Vehicle, or ?Object?) that killed the 'ped'

Is best to check if the Ped is dead before asking for its killer.
```

> GET_PED_CAUSE_OF_DEATH - 0x16FFE42AB2D2DC59 0x63458C27

Hash GET_PED_CAUSE_OF_DEATH(Ped ped)

```
Returns the hash of the weapon/model/object that killed the ped.

Edited by: Enumerator
```

> _GET_PED_TIME_OF_DEATH - 0x1E98817B311AE98A 

int _GET_PED_TIME_OF_DEATH(Ped ped)

```
Console Hash: 0xDF6D5D54

There is no way this is the correct name. The only time this is called it's compared with the game timer and I used this to test something and noticed when I was killed by no matter what it was my 'Time Of Death' via this native was always 0, but my friends was some random big number like so, 147591.

Retreives [CPed + 15CC] (as of 944)
```

> 0x5407B7288D0478B7 0xEF0B78E6

int 0x5407B7288D0478B7(Any p0)



> 0x336B3D200AB007CB 0xFB18CB19

Any 0x336B3D200AB007CB(Any p0, float p1, float p2, float p3, float p4)



> SET_PED_RELATIONSHIP_GROUP_DEFAULT_HASH - 0xADB3F206518799E8 0x423B7BA2

void SET_PED_RELATIONSHIP_GROUP_DEFAULT_HASH(Ped ped, Hash hash)



> SET_PED_RELATIONSHIP_GROUP_HASH - 0xC80A74AC829DDD92 0x79F8C18C

void SET_PED_RELATIONSHIP_GROUP_HASH(Ped ped, Hash hash)



> SET_RELATIONSHIP_BETWEEN_GROUPS - 0xBF25EB89375A37AD 0xD4A215BA

void SET_RELATIONSHIP_BETWEEN_GROUPS(int relationship, Hash group1, Hash group2)

```
Sets the relationship between two groups. This should be called twice (once for each group).

Relationship types:
0 = Companion
1 = Respect
2 = Like
3 = Neutral
4 = Dislike
5 = Hate
255 = Pedestrians

Example:
PED::SET_RELATIONSHIP_BETWEEN_GROUPS(2, l_1017, 0xA49E591C);
PED::SET_RELATIONSHIP_BETWEEN_GROUPS(2, 0xA49E591C, l_1017);
```

> CLEAR_RELATIONSHIP_BETWEEN_GROUPS - 0x5E29243FB56FC6D4 0x994B8C2D

void CLEAR_RELATIONSHIP_BETWEEN_GROUPS(int relationship, Hash group1, Hash group2)

```
Clears the relationship between two groups. This should be called twice (once for each group).

Relationship types:
0 = Companion
1 = Respect
2 = Like
3 = Neutral
4 = Dislike
5 = Hate
255 = Pedestrians
(Credits: Inco)

Example:
PED::CLEAR_RELATIONSHIP_BETWEEN_GROUPS(2, l_1017, 0xA49E591C);
PED::CLEAR_RELATIONSHIP_BETWEEN_GROUPS(2, 0xA49E591C, l_1017);
```

> ADD_RELATIONSHIP_GROUP - 0xF372BC22FCB88606 0x8B635546

Any ADD_RELATIONSHIP_GROUP(char* name, Hash* groupHash)

```
Can't select void. This function returns nothing. The hash of the created relationship group is output in the second parameter.
```

> REMOVE_RELATIONSHIP_GROUP - 0xB6BA2444AB393DA2 0x4A1DC59A

void REMOVE_RELATIONSHIP_GROUP(Hash groupHash)



> GET_RELATIONSHIP_BETWEEN_PEDS - 0xEBA5AD3A0EAF7121 0xE254C39C

int GET_RELATIONSHIP_BETWEEN_PEDS(Ped ped1, Ped ped2)

```
Gets the relationship between two peds. This should be called twice (once for each ped).

Relationship types:
0 = Companion
1 = Respect
2 = Like
3 = Neutral
4 = Dislike
5 = Hate
255 = Pedestrians
(Credits: Inco)

Example:
PED::GET_RELATIONSHIP_BETWEEN_PEDS(2, l_1017, 0xA49E591C);
PED::GET_RELATIONSHIP_BETWEEN_PEDS(2, 0xA49E591C, l_1017);
```

> GET_PED_RELATIONSHIP_GROUP_DEFAULT_HASH - 0x42FDD0F017B1E38E 0x714BD6E4

Hash GET_PED_RELATIONSHIP_GROUP_DEFAULT_HASH(Ped ped)



> GET_PED_RELATIONSHIP_GROUP_HASH - 0x7DBDD04862D95F04 0x354F283C

Hash GET_PED_RELATIONSHIP_GROUP_HASH(Ped ped)



> GET_RELATIONSHIP_BETWEEN_GROUPS - 0x9E6B70061662AE5C 0x4E372FE2

int GET_RELATIONSHIP_BETWEEN_GROUPS(Hash group1, Hash group2)

```
Gets the relationship between two groups. This should be called twice (once for each group).

Relationship types:
0 = Companion
1 = Respect
2 = Like
3 = Neutral
4 = Dislike
5 = Hate
255 = Pedestrians

Example:
PED::GET_RELATIONSHIP_BETWEEN_GROUPS(l_1017, 0xA49E591C);
PED::GET_RELATIONSHIP_BETWEEN_GROUPS(0xA49E591C, l_1017);
```

> SET_PED_CAN_BE_TARGETED_WITHOUT_LOS - 0x4328652AE5769C71 0x7FDDC0A6

void SET_PED_CAN_BE_TARGETED_WITHOUT_LOS(Ped ped, BOOL toggle)



> SET_PED_TO_INFORM_RESPECTED_FRIENDS - 0x112942C6E708F70B 0xD78AC46C

void SET_PED_TO_INFORM_RESPECTED_FRIENDS(Ped ped, float radius, int maxFriends)



> IS_PED_RESPONDING_TO_EVENT - 0x625B774D75C87068 0x7A877554

BOOL IS_PED_RESPONDING_TO_EVENT(Any p0, Any p1)



> SET_PED_FIRING_PATTERN - 0x9AC577F5A12AD8A9 0xB4629D66

void SET_PED_FIRING_PATTERN(Ped ped, Hash patternHash)

```
FIRING_PATTERN_BURST_FIRE = 0xD6FF6D61 ( 1073727030 )
FIRING_PATTERN_BURST_FIRE_IN_COVER = 0x026321F1 ( 40051185 )
FIRING_PATTERN_BURST_FIRE_DRIVEBY = 0xD31265F2 ( -753768974 )
FIRING_PATTERN_FROM_GROUND = 0x2264E5D6 ( 577037782 )
FIRING_PATTERN_DELAY_FIRE_BY_ONE_SEC = 0x7A845691 ( 2055493265 )
FIRING_PATTERN_FULL_AUTO = 0xC6EE6B4C ( -957453492 )
FIRING_PATTERN_SINGLE_SHOT = 0x5D60E4E0 ( 1566631136 )
FIRING_PATTERN_BURST_FIRE_PISTOL = 0xA018DB8A ( -1608983670 )
FIRING_PATTERN_BURST_FIRE_SMG = 0xD10DADEE ( 1863348768 )
FIRING_PATTERN_BURST_FIRE_RIFLE = 0x9C74B406 ( -1670073338 )
FIRING_PATTERN_BURST_FIRE_MG = 0xB573C5B4 ( -1250703948 )
FIRING_PATTERN_BURST_FIRE_PUMPSHOTGUN = 0x00BAC39B ( 12239771 )
FIRING_PATTERN_BURST_FIRE_HELI = 0x914E786F ( -1857128337 )
FIRING_PATTERN_BURST_FIRE_MICRO = 0x42EF03FD ( 1122960381 )
FIRING_PATTERN_SHORT_BURSTS = 0x1A92D7DF ( 445831135 )
FIRING_PATTERN_SLOW_FIRE_TANK = 0xE2CA3A71 ( -490063247 )

if anyone is interested firing pattern info: pastebin.com/Px036isB
```

> SET_PED_SHOOT_RATE - 0x614DA022990752DC 0xFB301746

void SET_PED_SHOOT_RATE(Ped ped, int shootRate)

```
shootRate 0-1000
```

> SET_COMBAT_FLOAT - 0xFF41B4B141ED981C 0xD8B7637C

void SET_COMBAT_FLOAT(Ped ped, int combatType, float p2)

```
combatType can be between 0-14. See GET_COMBAT_FLOAT below for a list of possible parameters.
```

> GET_COMBAT_FLOAT - 0x52DFF8A10508090A 0x511D7EF8

float GET_COMBAT_FLOAT(Ped p0, int p1)

```
p0: Ped Handle
p1: int i | 0 &lt;= i &lt;= 27

p1 probably refers to the attributes configured in combatbehavior.meta. There are 13. Example:

&lt;BlindFireChance value='0.1'/&gt;
&lt;WeaponShootRateModifier value='1.0'/&gt;
&lt;TimeBetweenBurstsInCover value='1.25'/&gt;
&lt;BurstDurationInCover value='2.0'/&gt;
&lt;TimeBetweenPeeks value='10.0'/&gt;
&lt;WeaponAccuracy value='0.18'/&gt;
&lt;FightProficiency value='0.8'/&gt;
&lt;StrafeWhenMovingChance value='1.0'/&gt;
&lt;WalkWhenStrafingChance value='0.0'/&gt;
&lt;AttackWindowDistanceForCover value='55.0'/&gt;
&lt;TimeToInvalidateInjuredTarget value='9.0'/&gt;
&lt;TriggerChargeTime_Near value='4.0'/&gt;
&lt;TriggerChargeTime_Far value='10.0'/&gt;

-------------Confirmed by editing combatbehavior.meta:
p1:
0=BlindFireChance
1=BurstDurationInCover
3=TimeBetweenBurstsInCover
4=TimeBetweenPeeks
5=StrafeWhenMovingChance
8=WalkWhenStrafingChance
11=AttackWindowDistanceForCover
12=TimeToInvalidateInjuredTarget
16=OptimalCoverDistance

```

> GET_GROUP_SIZE - 0x8DE69FE35CA09A45 0xF7E1A691

void GET_GROUP_SIZE(int groupID, Any* unknown, int* sizeInMembers)

```
p1 may be a BOOL representing whether or not the group even exists
```

> DOES_GROUP_EXIST - 0x7C6B0C22F9F40BBE 0x935C978D

BOOL DOES_GROUP_EXIST(int groupId)



> GET_PED_GROUP_INDEX - 0xF162E133B4E7A675 0x134E0785

int GET_PED_GROUP_INDEX(Ped ped)

```
Returns the group id of which the specified ped is a member of.
```

> IS_PED_IN_GROUP - 0x5891CAC5D4ACFF74 0x836D9795

BOOL IS_PED_IN_GROUP(Ped ped)



> GET_PLAYER_PED_IS_FOLLOWING - 0x6A3975DEA89F9A17 0xDE7442EE

Player GET_PLAYER_PED_IS_FOLLOWING(Ped Ped)



> SET_GROUP_FORMATION - 0xCE2F5FC3AF7E8C1E 0x08FAC739

void SET_GROUP_FORMATION(int groupId, int formationType)

```
0: Default
1: Circle Around Leader
2: Alternative Circle Around Leader
3: Line, with Leader at center
```

> SET_GROUP_FORMATION_SPACING - 0x1D9D45004C28C916 0xB1E086FF

void SET_GROUP_FORMATION_SPACING(int groupId, float p1, float p2, float p3)



> RESET_GROUP_FORMATION_DEFAULT_SPACING - 0x63DAB4CCB3273205 0x267FCEAD

void RESET_GROUP_FORMATION_DEFAULT_SPACING(int groupHandle)



> GET_VEHICLE_PED_IS_USING - 0x6094AD011A2EA87D 0x6DE3AADA

Vehicle GET_VEHICLE_PED_IS_USING(Ped ped)

```
Gets ID of vehicle player using. It means it can get ID at any interaction with vehicle. Enter/exit for example. And that means it is faster than GET_VEHICLE_PED_IS_IN but less safe.
```

> SET_EXCLUSIVE_PHONE_RELATIONSHIPS - 0xF92691AED837A5FC 0x56E0C163

Vehicle SET_EXCLUSIVE_PHONE_RELATIONSHIPS(Ped pedToCheck)

```
In appcamera.c4, Line 106:
if (VEHICLE::IS_VEHICLE_DRIVEABLE(PED::SET_EXCLUSIVE_PHONE_RELATIONSHIPS(PLAYER::PLAYER_PED_ID()), 0))
So return type could be a vehicle?

!Hash collision - gets the vehicle handle from ped which is about entering the vehicle!

sfink: agreed, 100%
Proper name is GET_VEHICLE_PED_IS_ENTERING
```

> SET_PED_GRAVITY - 0x9FF447B6B6AD960A 0x3CA16652

void SET_PED_GRAVITY(Ped ped, BOOL toggle)



> APPLY_DAMAGE_TO_PED - 0x697157CED63F18D4 0x4DC27FCF

void APPLY_DAMAGE_TO_PED(Ped ped, int damageAmount, BOOL p2)



> 0x36B77BB84687C318 

Any 0x36B77BB84687C318(Ped ped, Any p1)

```
GET_TIME_SINCE_???
```

> SET_PED_ALLOWED_TO_DUCK - 0xDA1F1B7BE1A8766F 0xC4D122F8

void SET_PED_ALLOWED_TO_DUCK(Ped ped, BOOL toggle)



> SET_PED_NEVER_LEAVES_GROUP - 0x3DBFC55D5C9BB447 0x0E038813

void SET_PED_NEVER_LEAVES_GROUP(Ped ped, BOOL toggle)



> GET_PED_TYPE - 0xFF059E1E4C01E63C 0xB1460D43

int GET_PED_TYPE(Ped ped)

```
Ped Types: (ordered by return priority)

Michael = 0
Franklin = 1
Trevor = 2

Army = 29
Animal = 28
SWAT = 27
LSFD = 21
Paramedic = 20

Cop = 6

Male = 4
Female = 5 

Human = 26

Note/Exception
hc_gunman : 4 // Mix male and female
hc_hacker : 4 // Mix male and female
mp_f_misty_01 : 4 // Female character
s_f_y_ranger_01 : 5 // Ranger
s_m_y_ranger_01 : 4 // Ranger
s_m_y_uscg_01 : 6 // US Coast Guard
```

> SET_PED_AS_COP - 0xBB03C38DD3FB7FFD 0x84E7DE9F

void SET_PED_AS_COP(Ped ped, BOOL toggle)

```
Turns the desired ped into a cop. If you use this on the player ped, you will become almost invisible to cops dispatched for you. You will also report your own crimes, get a generic cop voice, get a cop-vision-cone on the radar, and you will be unable to shoot at other cops. SWAT and Army will still shoot at you. Toggling ped as 'false' has no effect; you must change p0's ped model to disable the effect.
```

> SET_PED_MAX_HEALTH - 0xF5F6378C4F3419D3 0x5533F60B

void SET_PED_MAX_HEALTH(Ped ped, int value)



> GET_PED_MAX_HEALTH - 0x4700A416E8324EF3 0xA45B6C8D

int GET_PED_MAX_HEALTH(Ped ped)



> SET_PED_MAX_TIME_IN_WATER - 0x43C851690662113D 0xFE0A106B

void SET_PED_MAX_TIME_IN_WATER(Ped ped, float value)



> SET_PED_MAX_TIME_UNDERWATER - 0x6BA428C528D9E522 0x082EF240

void SET_PED_MAX_TIME_UNDERWATER(Ped ped, float value)



> 0x2735233A786B1BEF 0x373CC405

void 0x2735233A786B1BEF(Ped ped, float p1)



> 0x952F06BEECD775CC 

void 0x952F06BEECD775CC(Any p0, Any p1, Any p2, Any p3)



> 0xE6CA85E7259CE16B 

void 0xE6CA85E7259CE16B(Any p0)



> SET_PED_CAN_BE_KNOCKED_OFF_VEHICLE - 0x7A6535691B477C48 0x8A251612

void SET_PED_CAN_BE_KNOCKED_OFF_VEHICLE(Ped ped, int state)

```
0 = can (bike)
1 = can't (bike)
2 = unk 
3 = unk
```

> CAN_KNOCK_PED_OFF_VEHICLE - 0x51AC07A44D4F5B8A 0xC9D098B3

BOOL CAN_KNOCK_PED_OFF_VEHICLE(Ped ped)



> KNOCK_PED_OFF_VEHICLE - 0x45BBCBA77C29A841 0xACDD0674

void KNOCK_PED_OFF_VEHICLE(Ped ped)



> SET_PED_COORDS_NO_GANG - 0x87052FE446E07247 0x9561AD98

void SET_PED_COORDS_NO_GANG(Ped ped, float posX, float posY, float posZ)



> GET_PED_AS_GROUP_MEMBER - 0x51455483CF23ED97 0x9AA3CC8C

Ped GET_PED_AS_GROUP_MEMBER(int groupID, int memberNumber)

```
from fm_mission_controller.c4 (variable names changed for clarity):

int groupID = PLAYER::GET_PLAYER_GROUP(PLAYER::PLAYER_ID());
PED::GET_GROUP_SIZE(group, &amp;unused, &amp;groupSize);
if (groupSize &gt;= 1) {
. . . . for (int memberNumber = 0; memberNumber &lt; groupSize; memberNumber++) {
. . . . . . . . Ped ped1 = PED::GET_PED_AS_GROUP_MEMBER(groupID, memberNumber);
. . . . . . . . //and so on
```

> _GET_PED_AS_GROUP_LEADER - 0x5CCE68DBD5FE93EC 

Ped _GET_PED_AS_GROUP_LEADER(int groupID)



> SET_PED_KEEP_TASK - 0x971D38760FBC02EF 0xA7EC79CE

void SET_PED_KEEP_TASK(Ped ped, BOOL toggle)



> 0x49E50BDB8BA4DAB2 0x397F06E3

void 0x49E50BDB8BA4DAB2(Ped ped, BOOL p1)



> IS_PED_SWIMMING - 0x9DE327631295B4C2 0x7AB43DB8

BOOL IS_PED_SWIMMING(Ped ped)



> IS_PED_SWIMMING_UNDER_WATER - 0xC024869A53992F34 0x0E8D524F

BOOL IS_PED_SWIMMING_UNDER_WATER(Ped ped)



> SET_PED_COORDS_KEEP_VEHICLE - 0x9AFEFF481A85AB2E 0xD66AE1D3

void SET_PED_COORDS_KEEP_VEHICLE(Ped ped, float posX, float posY, float posZ)

```
teleports ped to coords along with the vehicle ped is in
```

> SET_PED_DIES_IN_VEHICLE - 0x2A30922C90C9B42C 0x6FE1E440

void SET_PED_DIES_IN_VEHICLE(Ped ped, BOOL toggle)



> SET_CREATE_RANDOM_COPS - 0x102E68B2024D536D 0x23441648

void SET_CREATE_RANDOM_COPS(BOOL toggle)



> SET_CREATE_RANDOM_COPS_NOT_ON_SCENARIOS - 0x8A4986851C4EF6E7 0x82E548CC

void SET_CREATE_RANDOM_COPS_NOT_ON_SCENARIOS(BOOL toggle)



> SET_CREATE_RANDOM_COPS_ON_SCENARIOS - 0x444CB7D7DBE6973D 0xEDC31475

void SET_CREATE_RANDOM_COPS_ON_SCENARIOS(BOOL toggle)



> CAN_CREATE_RANDOM_COPS - 0x5EE2CAFF7F17770D 0xAA73DAD9

BOOL CAN_CREATE_RANDOM_COPS()



> SET_PED_AS_ENEMY - 0x02A0C9720B854BFA 0xAE620A1B

void SET_PED_AS_ENEMY(Ped ped, BOOL toggle)



> SET_PED_CAN_SMASH_GLASS - 0x1CCE141467FF42A2 0x149C60A8

void SET_PED_CAN_SMASH_GLASS(Ped ped, BOOL p1, BOOL p2)



> IS_PED_IN_ANY_TRAIN - 0x6F972C1AB75A1ED0 0x759EF63A

BOOL IS_PED_IN_ANY_TRAIN(Ped ped)



> IS_PED_GETTING_INTO_A_VEHICLE - 0xBB062B2B5722478E 0x90E805AC

BOOL IS_PED_GETTING_INTO_A_VEHICLE(Ped ped)



> IS_PED_TRYING_TO_ENTER_A_LOCKED_VEHICLE - 0x44D28D5DDFE5F68C 0x46828B4E

BOOL IS_PED_TRYING_TO_ENTER_A_LOCKED_VEHICLE(Ped ped)



> SET_ENABLE_HANDCUFFS - 0xDF1AF8B5D56542FA 0xAC9BBA23

void SET_ENABLE_HANDCUFFS(Ped ped, BOOL toggle)

```
ped can not pull out a weapon when true
```

> SET_ENABLE_BOUND_ANKLES - 0xC52E0F855C58FC2E 0x9208D689

void SET_ENABLE_BOUND_ANKLES(Ped ped, BOOL toggle)



> SET_ENABLE_SCUBA - 0xF99F62004024D506 0x7BF61471

void SET_ENABLE_SCUBA(Ped ped, BOOL toggle)

```
Enables diving motion when underwater.
```

> SET_CAN_ATTACK_FRIENDLY - 0xB3B1CB349FF9C75D 0x47C60963

void SET_CAN_ATTACK_FRIENDLY(Ped ped, BOOL toggle, BOOL p2)

```
Setting ped to true allows the ped to shoot 'friendlies'.

p2 set to true when toggle is also true seams to make peds permanently unable to aim at, even if you set p2 back to false.

p1 = false &amp; p2 = false for unable to aim at.
p1 = true &amp; p2 = false for able to aim at. 
```

> GET_PED_ALERTNESS - 0xF6AA118530443FD2 0xF83E4DAF

int GET_PED_ALERTNESS(Ped ped)

```
Returns the ped's alertness (0-3).

Values : 

0 : Neutral
1 : Heard something (gun shot, hit, etc)
2 : Knows (the origin of the event)
3 : Fully alerted (is facing the event?)

MulleDK19: If the Ped does not exist, returns -1.
```

> SET_PED_ALERTNESS - 0xDBA71115ED9941A6 0x2C32D9AE

void SET_PED_ALERTNESS(Ped ped, int value)

```
value ranges from 0 to 3.
```

> SET_PED_GET_OUT_UPSIDE_DOWN_VEHICLE - 0xBC0ED94165A48BC2 0x89AD49FF

void SET_PED_GET_OUT_UPSIDE_DOWN_VEHICLE(Ped ped, BOOL toggle)



> SET_PED_MOVEMENT_CLIPSET - 0xAF8A94EDE7712BEF 0xA817CDEB

void SET_PED_MOVEMENT_CLIPSET(Ped ped, char* clipSet, float p2)

```
p2 is usually 1.0f

EDIT 12/24/16: 
p2 does absolutely nothing no matter what the value is. 

- sollaholla
```

> RESET_PED_MOVEMENT_CLIPSET - 0xAA74EC0CB0AAEA2C 0xB83CEE93

void RESET_PED_MOVEMENT_CLIPSET(Ped ped, float p1)

```
If p1 is 0.0, I believe you are back to normal. 
If p1 is 1.0, it looks like you can only rotate the ped, not walk.

Using the following code to reset back to normal
PED::RESET_PED_MOVEMENT_CLIPSET(PLAYER::PLAYER_PED_ID(), 0.0);
```

> SET_PED_STRAFE_CLIPSET - 0x29A28F3F8CF6D854 0x0BACF010

void SET_PED_STRAFE_CLIPSET(Ped ped, char* clipSet)



> RESET_PED_STRAFE_CLIPSET - 0x20510814175EA477 0xF1967A12

void RESET_PED_STRAFE_CLIPSET(Ped ped)



> SET_PED_WEAPON_MOVEMENT_CLIPSET - 0x2622E35B77D3ACA2 0xF8BE54DC

void SET_PED_WEAPON_MOVEMENT_CLIPSET(Ped ped, char* clipSet)



> RESET_PED_WEAPON_MOVEMENT_CLIPSET - 0x97B0DB5B4AA74E77 0xC60C9ACD

void RESET_PED_WEAPON_MOVEMENT_CLIPSET(Ped ped)



> SET_PED_DRIVE_BY_CLIPSET_OVERRIDE - 0xED34AB6C5CB36520 0xD4C73595

void SET_PED_DRIVE_BY_CLIPSET_OVERRIDE(Ped ped, char* clipset)



> CLEAR_PED_DRIVE_BY_CLIPSET_OVERRIDE - 0x4AFE3690D7E0B5AC 0xAEC9163B

void CLEAR_PED_DRIVE_BY_CLIPSET_OVERRIDE(Ped ped)



> 0x9DBA107B4937F809 

void 0x9DBA107B4937F809(Any p0, char* p1)

```
Found in the b617d scripts:
PED::_9DBA107B4937F809(v_7, 'trevor_heist_cover_2h');
```

> 0xC79196DCB36F6121 

void 0xC79196DCB36F6121(Any p0)



> 0x80054D7FCC70EEC6 

void 0x80054D7FCC70EEC6(Any p0)



> SET_PED_IN_VEHICLE_CONTEXT - 0x530071295899A8C6 0x27F25C0E

void SET_PED_IN_VEHICLE_CONTEXT(Ped ped, Hash context)

```
PED::SET_PED_IN_VEHICLE_CONTEXT(l_128, GAMEPLAY::GET_HASH_KEY('MINI_PROSTITUTE_LOW_PASSENGER'));
PED::SET_PED_IN_VEHICLE_CONTEXT(l_128, GAMEPLAY::GET_HASH_KEY('MINI_PROSTITUTE_LOW_RESTRICTED_PASSENGER'));
PED::SET_PED_IN_VEHICLE_CONTEXT(l_3212, GAMEPLAY::GET_HASH_KEY('MISS_FAMILY1_JIMMY_SIT'));
PED::SET_PED_IN_VEHICLE_CONTEXT(l_3212, GAMEPLAY::GET_HASH_KEY('MISS_FAMILY1_JIMMY_SIT_REAR'));
PED::SET_PED_IN_VEHICLE_CONTEXT(l_95, GAMEPLAY::GET_HASH_KEY('MISS_FAMILY2_JIMMY_BICYCLE'));
PED::SET_PED_IN_VEHICLE_CONTEXT(num3, GAMEPLAY::GET_HASH_KEY('MISSFBI2_MICHAEL_DRIVEBY'));
PED::SET_PED_IN_VEHICLE_CONTEXT(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('MISS_ARMENIAN3_FRANKLIN_TENSE'));
PED::SET_PED_IN_VEHICLE_CONTEXT(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('MISSFBI5_TREVOR_DRIVING'));

- Kryptus
```

> RESET_PED_IN_VEHICLE_CONTEXT - 0x22EF8FF8778030EB 0x3C94D88A

void RESET_PED_IN_VEHICLE_CONTEXT(Ped ped)



> IS_SCRIPTED_SCENARIO_PED_USING_CONDITIONAL_ANIM - 0x6EC47A344923E1ED 0x3C30B447

BOOL IS_SCRIPTED_SCENARIO_PED_USING_CONDITIONAL_ANIM(Ped ped, char* animDict, char* anim)

```
Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> SET_PED_ALTERNATE_WALK_ANIM - 0x6C60394CB4F75E9A 0x895E1D67

void SET_PED_ALTERNATE_WALK_ANIM(Any p0, Any* p1, Any* p2, float p3, BOOL p4)



> CLEAR_PED_ALTERNATE_WALK_ANIM - 0x8844BBFCE30AA9E9 0x5736FB23

void CLEAR_PED_ALTERNATE_WALK_ANIM(Any p0, float p1)



> SET_PED_ALTERNATE_MOVEMENT_ANIM - 0x90A43CC281FFAB46 0xBA84FD8C

void SET_PED_ALTERNATE_MOVEMENT_ANIM(Ped ped, int stance, char* animDictionary, char* animationName, float p4, BOOL p5)

```
stance:
0 = idle
1 = walk
2 = running

p5 = usually set to true

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> CLEAR_PED_ALTERNATE_MOVEMENT_ANIM - 0xD8D19675ED5FBDCE 0x7A7F5BC3

void CLEAR_PED_ALTERNATE_MOVEMENT_ANIM(Ped ped, int stance, float p2)



> SET_PED_GESTURE_GROUP - 0xDDF803377F94AAA8 0x170DA109

void SET_PED_GESTURE_GROUP(Ped ped, Any* p1)

```
From the scripts:
PED::SET_PED_GESTURE_GROUP(PLAYER::PLAYER_PED_ID(),
'ANIM_GROUP_GESTURE_MISS_FRA0');
PED::SET_PED_GESTURE_GROUP(PLAYER::PLAYER_PED_ID(),
'ANIM_GROUP_GESTURE_MISS_DocksSetup1');
```

> GET_ANIM_INITIAL_OFFSET_POSITION - 0xBE22B26DD764C040 0xC59D4268

Vector3 GET_ANIM_INITIAL_OFFSET_POSITION(char* animDict, char* animName, float x, float y, float z, float xRot, float yRot, float zRot, float p8, int p9)



> GET_ANIM_INITIAL_OFFSET_ROTATION - 0x4B805E6046EE9E47 0x5F7789E6

Vector3 GET_ANIM_INITIAL_OFFSET_ROTATION(char* animDict, char* animName, float x, float y, float z, float xRot, float yRot, float zRot, float p8, int p9)



> GET_PED_DRAWABLE_VARIATION - 0x67F3780DD425D4FC 0x29850FE2

int GET_PED_DRAWABLE_VARIATION(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_NUMBER_OF_PED_DRAWABLE_VARIATIONS - 0x27561561732A7842 0x9754C27D

int GET_NUMBER_OF_PED_DRAWABLE_VARIATIONS(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_PED_TEXTURE_VARIATION - 0x04A355E041E004E6 0xC0A8590A

int GET_PED_TEXTURE_VARIATION(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_NUMBER_OF_PED_TEXTURE_VARIATIONS - 0x8F7156A3142A6BAD 0x83D9FBE7

int GET_NUMBER_OF_PED_TEXTURE_VARIATIONS(Ped ped, int componentId, int drawableId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_NUMBER_OF_PED_PROP_DRAWABLE_VARIATIONS - 0x5FAF9754E789FB47 0xC9780B95

int GET_NUMBER_OF_PED_PROP_DRAWABLE_VARIATIONS(Ped ped, int propId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_NUMBER_OF_PED_PROP_TEXTURE_VARIATIONS - 0xA6E7F1CEB523E171 0x4892B882

int GET_NUMBER_OF_PED_PROP_TEXTURE_VARIATIONS(Ped ped, int propId, int drawableId)

```
Need to check behavior when drawableId = -1

- Doofy.Ass
Why this function doesn't work and return nill value?
GET_NUMBER_OF_PED_PROP_TEXTURE_VARIATIONS(PLAYER.PLAYER_PED_ID(), 0, 5)

tick: scripts/addins/menu_execute.lua:51: attempt to call field 'GET_NUMBER_OF_PED_PROP_TEXTURE_VARIATIONS' (a nil value)


List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> GET_PED_PALETTE_VARIATION - 0xE3DD5F2A84B42281 0xEF1BC082

int GET_PED_PALETTE_VARIATION(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> 0x9E30E91FB03A2CAF 

BOOL 0x9E30E91FB03A2CAF(Any* p0, Any* p1)



> 0x1E77FA7A62EE6C4C 

Any 0x1E77FA7A62EE6C4C(Any p0)



> 0xF033419D1B81FAE8 

Any 0xF033419D1B81FAE8(Any p0)



> IS_PED_COMPONENT_VARIATION_VALID - 0xE825F6B6CEA7671D 0x952ABD9A

BOOL IS_PED_COMPONENT_VARIATION_VALID(Ped ped, int componentId, int drawableId, int textureId)

```
Checks if the component variation is valid, this works great for randomizing components using loops.

List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_COMPONENT_VARIATION - 0x262B14F48D29DE80 0xD4F7B05C

void SET_PED_COMPONENT_VARIATION(Ped ped, int componentId, int drawableId, int textureId, int paletteId)

```
paletteId/palletColor -  0 to 3. 
enum PedVariationData
{
	PED_VARIATION_FACE = 0,
	PED_VARIATION_HEAD = 1,
	PED_VARIATION_HAIR = 2,
	PED_VARIATION_TORSO = 3,
	PED_VARIATION_LEGS = 4,
	PED_VARIATION_HANDS = 5,
	PED_VARIATION_FEET = 6,
	PED_VARIATION_EYES = 7,
	PED_VARIATION_ACCESSORIES = 8,
	PED_VARIATION_TASKS = 9,
	PED_VARIATION_TEXTURES = 10,
	PED_VARIATION_TORSO2 = 11
};
Usage: 
SET_PED_COMPONENT_VARIATION(playerPed, PED_VARIATION_FACE, GET_NUMBER_OF_PED_DRAWABLE_VARIATIONS(playerPed, PED_VARIATION_FACE), GET_NUMBER_OF_PED_TEXTURE_VARIATIONS(playerPed, PED_VARIATION_FACE, 0), 2);

List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_RANDOM_COMPONENT_VARIATION - 0xC8A9481A01E63C28 0x4111BA46

void SET_PED_RANDOM_COMPONENT_VARIATION(Ped ped, BOOL p1)

```
p1 is always false in R* scripts.

Quick disassembly seems to indicate that p1 is unused.

List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_RANDOM_PROPS - 0xC44AA05345C992C6 0xE3318E0E

void SET_PED_RANDOM_PROPS(Ped ped)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_DEFAULT_COMPONENT_VARIATION - 0x45EEE61580806D63 0xC866A984

void SET_PED_DEFAULT_COMPONENT_VARIATION(Ped ped)

```
Sets Ped Default Clothes
```

> SET_PED_BLEND_FROM_PARENTS - 0x137BBD05230DB22D 0x837BD370

void SET_PED_BLEND_FROM_PARENTS(Ped ped, Any p1, Any p2, float p3, float p4)



> SET_PED_HEAD_BLEND_DATA - 0x9414E18B9434C2FE 0x60746B88

void SET_PED_HEAD_BLEND_DATA(Ped ped, int shapeFirstID, int shapeSecondID, int shapeThirdID, int skinFirstID, int skinSecondID, int skinThirdID, float shapeMix, float skinMix, float thirdMix, BOOL isParent)

```
The 'shape' parameters control the shape of the ped's face. The 'skin' parameters control the skin tone. ShapeMix and skinMix control how much the first and second IDs contribute,(typically mother and father.) ThirdMix overrides the others in favor of the third IDs. IsParent is set for 'children' of the player character's grandparents during old-gen character creation. It has unknown effect otherwise.

The IDs start at zero and go Male Non-DLC, Female Non-DLC, Male DLC, and Female DLC.

!!!Can someone add working example for this???

try this:
		headBlendData headData;
		_GET_PED_HEAD_BLEND_DATA(PLAYER_PED_ID(), &amp;headData);

		SET_PED_HEAD_BLEND_DATA(PLAYER_PED_ID(), headData.shapeFirst, headData.shapeSecond, headData.shapeThird, headData.skinFirst, headData.skinSecond
			, headData.skinThird, headData.shapeMix, headData.skinMix, headData.skinThird, 0);



THEAETIK: For more info please refer to this topic. 
gtaforums.com/topic/858970-all-gtao-face-ids-pedset-ped-head-blend-data-explained
```

> _GET_PED_HEAD_BLEND_DATA - 0x2746BD9D88C5C5D0 

BOOL _GET_PED_HEAD_BLEND_DATA(Ped ped, Any* headBlendData)

```
The pointer is to a padded struct that matches the arguments to SET_PED_HEAD_BLEND_DATA(...). There are 4 bytes of padding after each field.

(Edit) Console Hash: 0x44E1680C

pass this struct in the second parameter 
typedef struct
{
        int shapeFirst, shapeSecond, shapeThird; 
        int skinFirst, skinSecond, skinThird; 
	float shapeMix, skinMix, thirdMix;
} headBlendData;
```

> UPDATE_PED_HEAD_BLEND_DATA - 0x723538F61C647C5A 0x5CB76219

void UPDATE_PED_HEAD_BLEND_DATA(Ped ped, float shapeMix, float skinMix, float thirdMix)

```
See SET_PED_HEAD_BLEND_DATA().
```

> _SET_PED_EYE_COLOR - 0x50B56988B170AFDF 

void _SET_PED_EYE_COLOR(Ped ped, int index)

```
Used for freemode (online) characters.

For some reason, the scripts use a rounded float for the index.
```

> SET_PED_HEAD_OVERLAY - 0x48F44967FA05CC1E 0xD28DBA90

void SET_PED_HEAD_OVERLAY(Ped ped, int overlayID, int index, float opacity)

```
OverlayID ranges from 0 to 12, index from 0 to _GET_NUM_OVERLAY_VALUES(overlayID)-1, and opacity from 0.0 to 1.0. 

overlayID       Part                  Index, to disable
0               Blemishes             0 - 23, 255
1               Facial Hair           0 - 28, 255
2               Eyebrows              0 - 33, 255
3               Ageing                0 - 14, 255
4               Makeup                0 - 74, 255
5               Blush                 0 - 6, 255
6               Complexion            0 - 11, 255
7               Sun Damage            0 - 10, 255
8               Lipstick              0 - 9, 255
9               Moles/Freckles        0 - 17, 255
10              Chest Hair            0 - 16, 255
11              Body Blemishes        0 - 11, 255
12              Add Body Blemishes    0 - 1, 255
```

> _GET_PED_HEAD_OVERLAY_VALUE - 0xA60EF3B6461A4D43 

int _GET_PED_HEAD_OVERLAY_VALUE(Ped ped, int overlayID)

```
Likely a char, if that overlay is not set, e.i. 'None' option, returns 255;

```

> _GET_NUM_HEAD_OVERLAY_VALUES - 0xCF1CE768BB43480E 0xFF43C18D

int _GET_NUM_HEAD_OVERLAY_VALUES(int overlayID)

```
Used with freemode (online) characters.
```

> _SET_PED_HEAD_OVERLAY_COLOR - 0x497BF74A7B9CB952 

void _SET_PED_HEAD_OVERLAY_COLOR(Ped ped, int overlayID, int colorType, int colorID, int secondColorID)

```
Used for freemode (online) characters.

ColorType is 1 for eyebrows, beards, and chest hair; 2 for blush and lipstick; and 0 otherwise, though not called in those cases.

Called after SET_PED_HEAD_OVERLAY().
```

> _SET_PED_HAIR_COLOR - 0x4CFFC65454C93A49 

void _SET_PED_HAIR_COLOR(Ped ped, int colorID, int highlightColorID)

```
Used for freemode (online) characters.
```

> _GET_NUM_HAIR_COLORS - 0xE5C0CF872C2AD150 

int _GET_NUM_HAIR_COLORS()

```
Used for freemode (online) characters.
```

> _GET_NUM_MAKEUP_COLORS - 0xD1F7CA1535D22818 

int _GET_NUM_MAKEUP_COLORS()



> 0x4852FC386E2E1BB5 

void 0x4852FC386E2E1BB5(Any p0, Any* p1, Any* p2, Any* p3)



> 0x013E5CFC38CD5387 

void 0x013E5CFC38CD5387(Any p0, Any* p1, Any* p2, Any* p3)



> 0xED6D8E27A43B8CDE 

BOOL 0xED6D8E27A43B8CDE(Any p0)



> 0xEA9960D07DADCF10 

int 0xEA9960D07DADCF10(Any p0)



> 0x3E802F11FBE27674 

BOOL 0x3E802F11FBE27674(Any p0)



> 0xF41B5D290C99A3D6 

BOOL 0xF41B5D290C99A3D6(Any p0)



> _IS_A_VALID_HAIR_COLOR - 0xE0D36E5D9E99CC21 

BOOL _IS_A_VALID_HAIR_COLOR(int colorID)



> 0xAAA6A3698A69E048 

Any 0xAAA6A3698A69E048(Any p0)



> _IS_A_VALID_LIPSTICK_COLOR - 0x0525A2C2562F3CD4 

BOOL _IS_A_VALID_LIPSTICK_COLOR(int colorID)



> _IS_A_VALID_BLUSH_COLOR - 0x604E810189EE3A59 

BOOL _IS_A_VALID_BLUSH_COLOR(int colorID)



> 0xC56FBF2F228E1DAC 

Any 0xC56FBF2F228E1DAC(Any p0, Any p1, Any p2)



> _SET_PED_FACE_FEATURE - 0x71A5C1DBA060049E 

void _SET_PED_FACE_FEATURE(Ped ped, int index, float scale)

```
Sets the various freemode face features, e.g. nose length, chin shape. Scale ranges from -1.0 to 1.0.

Index can be 0 - 19
```

> HAS_PED_HEAD_BLEND_FINISHED - 0x654CD0A825161131 0x2B1BD9C5

BOOL HAS_PED_HEAD_BLEND_FINISHED(Ped ped)



> 0x4668D80430D6C299 0x894314A4

void 0x4668D80430D6C299(Ped ped)



> 0xCC9682B8951C5229 0x57E5B3F9

void 0xCC9682B8951C5229(Any p0, Any p1, Any p2, Any p3, Any p4)

```
p4 seems to vary from 0 to 3.
```

> 0xA21C118553BBDF02 0xC6F36292

void 0xA21C118553BBDF02(Any p0)



> _GET_FIRST_PARENT_ID_FOR_PED_TYPE - 0x68D353AB88B97E0C 0x211DEFEC

int _GET_FIRST_PARENT_ID_FOR_PED_TYPE(int type)

```
Type equals 0 for male non-dlc, 1 for female non-dlc, 2 for male dlc, and 3 for female dlc.

Used when calling SET_PED_HEAD_BLEND_DATA.
```

> _GET_NUM_PARENT_PEDS_OF_TYPE - 0x5EF37013A6539C9D 0x095D3BD8

int _GET_NUM_PARENT_PEDS_OF_TYPE(int type)

```
Type equals 0 for male non-dlc, 1 for female non-dlc, 2 for male dlc, and 3 for female dlc.
```

> 0x39D55A620FCB6A3A 0x45F3BDFB

Any 0x39D55A620FCB6A3A(Ped ped, int p1, int drawableId, int textureId)

```
from extreme3.c4
PED::_39D55A620FCB6A3A(PLAYER::PLAYER_PED_ID(), 8, PED::GET_PED_DRAWABLE_VARIATION(PLAYER::PLAYER_PED_ID(), 8), PED::GET_PED_TEXTURE_VARIATION(PLAYER::PLAYER_PED_ID(), 8));

p1 is probably componentId
```

> 0x66680A92700F43DF 0xC6517D52

BOOL 0x66680A92700F43DF(Ped p0)

```
Normally returns true. Returns false briefly whilst getting into a plane. This is probably a check to see if the ped model and all its components/drawables are properly loaded yet.
```

> 0x5AAB586FFEC0FD96 0x6435F67F

void 0x5AAB586FFEC0FD96(Any p0)



> _IS_PED_PROP_VALID - 0x2B16A3BFF1FBCE49 0xC0E23671

BOOL _IS_PED_PROP_VALID(Ped ped, int componentId, int drawableId, int TextureId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> 0x784002A632822099 0x3B0CA391

BOOL 0x784002A632822099(Ped ped)

```
Normally returns true. Returns false briefly whilst putting on a helmet after getting onto a motorbike. Not sure what that's about.
```

> 0xF79F9DEF0AADE61A 0xFD103BA7

void 0xF79F9DEF0AADE61A(Ped ped)



> GET_PED_PROP_INDEX - 0x898CC20EA75BACD8 0x746DDAC0

int GET_PED_PROP_INDEX(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_PROP_INDEX - 0x93376B65A266EB5F 0x0829F2E2

void SET_PED_PROP_INDEX(Ped ped, int componentId, int drawableId, int TextureId, BOOL attach)

```
ComponentId can be set to various things based on what category you're wanting to set
enum PedPropsData
{
	PED_PROP_HATS = 0,
	PED_PROP_GLASSES = 1,
	PED_PROP_EARS = 2,
};
Usage: SET_PED_PROP_INDEX(playerPed, PED_PROP_HATS, GET_NUMBER_OF_PED_PROP_DRAWABLE_VARIATIONS(playerPed, PED_PROP_HATS), GET_NUMBER_OF_PED_PROP_TEXTURE_VARIATIONS(playerPed, PED_PROP_HATS, 0), TRUE);

List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> KNOCK_OFF_PED_PROP - 0x6FD7816A36615F48 0x08D8B180

void KNOCK_OFF_PED_PROP(Ped ped, BOOL p1, BOOL p2, BOOL p3, BOOL p4)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> CLEAR_PED_PROP - 0x0943E5B8E078E76E 0x2D23D743

void CLEAR_PED_PROP(Ped ped, int propId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> CLEAR_ALL_PED_PROPS - 0xCD8A7537A9B52F06 0x81DF8B43

void CLEAR_ALL_PED_PROPS(Ped ped)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> 0xAFF4710E2A0A6C12 

void 0xAFF4710E2A0A6C12(Ped ped)



> GET_PED_PROP_TEXTURE_INDEX - 0xE131A28626F81AB2 0x922A6653

int GET_PED_PROP_TEXTURE_INDEX(Ped ped, int componentId)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> 0x1280804F7CFD2D6C 0x7BCD8991

void 0x1280804F7CFD2D6C(Any p0)



> 0x36C6984C3ED0C911 

void 0x36C6984C3ED0C911(Any p0)

```
when player character is used plays remove scuba gear animation
```

> 0xB50EB4CCB29704AC 0x080275EE

void 0xB50EB4CCB29704AC(Any p0)



> 0xFEC9A3B1820F3331 

BOOL 0xFEC9A3B1820F3331(Any p0)



> SET_BLOCKING_OF_NON_TEMPORARY_EVENTS - 0x9F8AA94D6D97DBF4 0xDFE34E4A

void SET_BLOCKING_OF_NON_TEMPORARY_EVENTS(Ped ped, BOOL toggle)

```
works with AI::TASK_SET_BLOCKING_OF_NON_TEMPORARY_EVENTS to make a ped completely oblivious to all events going on around him
```

> SET_PED_BOUNDS_ORIENTATION - 0x4F5F651ACCC9C4CF 0xCFA20D68

void SET_PED_BOUNDS_ORIENTATION(Ped ped, float p1, float p2, float p3, float p4, float p5)



> REGISTER_TARGET - 0x2F25D9AEFA34FBA2 0x50A95442

void REGISTER_TARGET(Ped ped, Ped target)

```
PED::REGISTER_TARGET(l_216, PLAYER::PLAYER_PED_ID()); from re_prisonbreak.txt.

l_216 = RECSBRobber1
```

> REGISTER_HATED_TARGETS_AROUND_PED - 0x9222F300BF8354FE 0x7F87559E

void REGISTER_HATED_TARGETS_AROUND_PED(Ped ped, float radius)

```
Based on TASK_COMBAT_HATED_TARGETS_AROUND_PED, the parameters are likely similar (PedHandle, and area to attack in).
```

> GET_RANDOM_PED_AT_COORD - 0x876046A8E3A4B71C 0xDC8239EB

Ped GET_RANDOM_PED_AT_COORD(float x, float y, float z, float xRadius, float yRadius, float zRadius, int pedType)

```
Gets a random ped in the x/y/zRadius near the x/y/z coordinates passed. 

Ped Types:
Any = -1
Player = 1
Male = 4 
Female = 5 
Cop = 6
Human = 26
SWAT = 27 
Animal = 28
Army = 29
```

> GET_CLOSEST_PED - 0xC33AB876A77F8164 0x8F6C1F55

BOOL GET_CLOSEST_PED(float x, float y, float z, float radius, BOOL p4, BOOL p5, Ped* outPed, BOOL p7, BOOL p8, int pedType)

```
Gets the closest ped in a radius.

Ped Types:
Any ped = -1
Player = 1
Male = 4 
Female = 5 
Cop = 6
Human = 26
SWAT = 27 
Animal = 28
Army = 29

------------------
P4 P5 P7 P8
1  0  x  x  = return nearest walking Ped
1  x  0  x  = return nearest walking Ped
x  1  1  x  = return Ped you are using
0  0  x  x  = no effect
0  x  0  x  = no effect

x = can be 1 or 0. Does not have any obvious changes.

This function does not return ped who is:
1. Standing still
2. Driving
3. Fleeing
4. Attacking

This function only work if the ped is:
1. walking normally.
2. waiting to cross a road.

Note: PED::GET_PED_NEARBY_PEDS works for more peds.
```

> SET_SCENARIO_PEDS_TO_BE_RETURNED_BY_NEXT_COMMAND - 0x14F19A8782C8071E 0x85615FD0

void SET_SCENARIO_PEDS_TO_BE_RETURNED_BY_NEXT_COMMAND(BOOL value)

```
Sets a value indicating whether scenario peds should be returned by the next call to a command that returns peds. Eg. GET_CLOSEST_PED.
```

> 0x03EA03AF85A85CB7 0x18DD76A1

BOOL 0x03EA03AF85A85CB7(Ped ped, BOOL p1, BOOL p2, BOOL p3, BOOL p4, BOOL p5, BOOL p6, BOOL p7, Any p8)



> 0xDED5AF5A0EA4B297 0x6D55B3B3

void 0xDED5AF5A0EA4B297(Ped driver, float p1)

```
Scripts use 0.2, 0.5 and 1.0.

SET_DRIVER_*
```

> SET_DRIVER_ABILITY - 0xB195FFA8042FC5C3 0xAAD4012C

void SET_DRIVER_ABILITY(Ped driver, float ability)

```
Decompiled scripts seem to use a range between 0.0 and 1.0, but tests confirm that 1.0 is not the limit.
*Both 10.0 and 100.0 allow the driver to avoid other vehicles better and have faster reaction times, but I don't know if 10.0 is the limit or is it 100.0. Didn't really notice differences.* (wrong)


MulleDK19: The above comment is either outdated, or just wrong from the start. The function specifically verifies the value is equal to, or less than 1.0f. If it is greater than 1.0f, the function does nothing at all.
```

> SET_DRIVER_AGGRESSIVENESS - 0xA731F608CA104E3C 0x8B02A8FB

void SET_DRIVER_AGGRESSIVENESS(Ped driver, float aggressiveness)

```
range 0.0f - 1.0f
```

> CAN_PED_RAGDOLL - 0x128F79EDCECE4FD5 0xC0EFB7A3

BOOL CAN_PED_RAGDOLL(Ped ped)

```
Prevents the ped from going limp.

[Example: Can prevent peds from falling when standing on moving vehicles.]

Edited by: Enumerator
```

> SET_PED_TO_RAGDOLL - 0xAE99FB955581844A 0x83CB5052

BOOL SET_PED_TO_RAGDOLL(Ped ped, int time1, int time2, int ragdollType, BOOL p4, BOOL p5, BOOL p6)

```
time1- Time Ped is in ragdoll mode(ms)

time2- time2 same as time1 but in mircoseconds (us)

ragdollType-
0 : Normal ragdoll
1 : Falls with stiff legs/body
2 : Narrow leg stumble(may not fall)
3 : Wide leg stumble(may not fall)

p4, p5, p6- No idea


EDIT 3/11/16: unclear what 'mircoseconds' mean-- a microsecond is 1000x a ms, so time2 must be 1000x time1?  more testing needed.  -sob
```

> SET_PED_TO_RAGDOLL_WITH_FALL - 0xD76632D99E4966C8 0xFA12E286

BOOL SET_PED_TO_RAGDOLL_WITH_FALL(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8, Any p9, Any p10, Any p11, Any p12, Any p13)



> SET_PED_RAGDOLL_ON_COLLISION - 0xF0A4F1BBF4FA7497 0x2654A0F4

void SET_PED_RAGDOLL_ON_COLLISION(Ped ped, BOOL toggle)

```
Causes Ped to ragdoll on collision with any object (e.g Running into trashcan). If applied to player you will sometimes trip on the sidewalk.
```

> IS_PED_RAGDOLL - 0x47E4E977581C5B55 0xC833BBE1

BOOL IS_PED_RAGDOLL(Ped ped)

```
If the ped handle passed through the parenthesis is in a ragdoll state this will return true.

-UNBOUND-
```

> IS_PED_RUNNING_RAGDOLL_TASK - 0xE3B6097CC25AA69E 0x44A153F2

BOOL IS_PED_RUNNING_RAGDOLL_TASK(Ped ped)



> SET_PED_RAGDOLL_FORCE_FALL - 0x01F6594B923B9251 0x20A5BDE0

Any SET_PED_RAGDOLL_FORCE_FALL(Ped ped)



> RESET_PED_RAGDOLL_TIMER - 0x9FA4664CF62E47E8 0xF2865370

void RESET_PED_RAGDOLL_TIMER(Ped ped)



> SET_PED_CAN_RAGDOLL - 0xB128377056A54E2A 0xCF1384C4

void SET_PED_CAN_RAGDOLL(Ped ped, BOOL toggle)



> 0xD1871251F3B5ACD7 

BOOL 0xD1871251F3B5ACD7(Ped ped)



> IS_PED_RUNNING_MOBILE_PHONE_TASK - 0x2AFE52F782F25775 0xFB2AFED1

BOOL IS_PED_RUNNING_MOBILE_PHONE_TASK(Ped ped)



> 0xA3F3564A5B3646C0 0x97353375

BOOL 0xA3F3564A5B3646C0(Ped ped)

```
Only called once in the scripts:

if (sub_1abd() &amp;&amp; (!PED::_A3F3564A5B3646C0(l_8C))) {
    if (sub_52e3('RESNA_CELLR', 0)) {
        PED::SET_PED_CAN_PLAY_GESTURE_ANIMS(l_8C, 1);
        PED::SET_PED_CAN_PLAY_AMBIENT_ANIMS(l_8C, 1);
        PED::SET_PED_CAN_PLAY_VISEME_ANIMS(l_8C, 1, 0);
        l_184 += 1;
    }
}
```

> _SET_PED_RAGDOLL_FLAG - 0x26695EC767728D84 0x9C8F830D

void _SET_PED_RAGDOLL_FLAG(Ped ped, int flag)

```
Works for both player and peds, but some flags don't seem to work for the player (1, for example)

1 - Blocks ragdolling when shot.
2 - Blocks ragdolling when hit by a vehicle. The ped still might play a falling animation.
4 - Blocks ragdolling when set on fire.

-----------------------------------------------------------------------

There seem to be 26 flags
```

> _SET_PED_RESET_RAGDOLL_FLAG - 0xD86D101FCFD00A4B 0x77CBA290

void _SET_PED_RESET_RAGDOLL_FLAG(Ped ped, int flag)

```
There seem to be 26 flags
```

> SET_PED_ANGLED_DEFENSIVE_AREA - 0xC7F76DF27A5045A1 0x3EFBDD9B

void SET_PED_ANGLED_DEFENSIVE_AREA(Ped ped, float p1, float p2, float p3, float p4, float p5, float p6, float p7, BOOL p8, BOOL p9)



> SET_PED_SPHERE_DEFENSIVE_AREA - 0x9D3151A373974804 0xBD96D8E8

void SET_PED_SPHERE_DEFENSIVE_AREA(Ped ped, float x, float y, float z, float radius, BOOL p5, BOOL p6)



> SET_PED_DEFENSIVE_SPHERE_ATTACHED_TO_PED - 0xF9B8F91AAD3B953E 0x40638BDC

void SET_PED_DEFENSIVE_SPHERE_ATTACHED_TO_PED(Ped ped, Any p1, float p2, float p3, float p4, float p5, BOOL p6)



> 0xE4723DB6E736CCFF 0x4763B2C6

void 0xE4723DB6E736CCFF(Ped ped, Any p1, float p2, float p3, float p4, float p5, BOOL p6)



> SET_PED_DEFENSIVE_AREA_ATTACHED_TO_PED - 0x4EF47FE21698A8B6 0x74BDA7CE

void SET_PED_DEFENSIVE_AREA_ATTACHED_TO_PED(Ped ped, Ped attachPed, float p2, float p3, float p4, float p5, float p6, float p7, float p8, BOOL p9, BOOL p10)



> SET_PED_DEFENSIVE_AREA_DIRECTION - 0x413C6C763A4AFFAD 0xB66B0C9A

void SET_PED_DEFENSIVE_AREA_DIRECTION(Ped ped, float p1, float p2, float p3, BOOL p4)



> REMOVE_PED_DEFENSIVE_AREA - 0x74D4E028107450A9 0x34AAAFA5

void REMOVE_PED_DEFENSIVE_AREA(Ped ped, BOOL toggle)

```
Ped will no longer get angry when you stay near him.
```

> GET_PED_DEFENSIVE_AREA_POSITION - 0x3C06B8786DD94CD1 0xCB65198D

Vector3 GET_PED_DEFENSIVE_AREA_POSITION(Ped ped, BOOL p1)



> 0xBA63D9FE45412247 

BOOL 0xBA63D9FE45412247(Ped ped, BOOL p1)



> SET_PED_PREFERRED_COVER_SET - 0x8421EB4DA7E391B9 0xF3B7EFBF

void SET_PED_PREFERRED_COVER_SET(Ped ped, Any itemSet)



> REMOVE_PED_PREFERRED_COVER_SET - 0xFDDB234CF74073D9 0xA0134498

void REMOVE_PED_PREFERRED_COVER_SET(Ped ped)



> REVIVE_INJURED_PED - 0x8D8ACD8388CD99CE 0x14D3E6E3

void REVIVE_INJURED_PED(Ped ped)

```
It will revive/cure the injured ped. The condition is ped must not be dead.

Upon setting and converting the health int, found, if health falls below 5, the ped will lay on the ground in pain(Maximum default health is 100).

This function is well suited there.
```

> RESURRECT_PED - 0x71BC8E838B9C6035 0xA4B82097

void RESURRECT_PED(Ped ped)

```
This function will simply bring the dead person back to life.

Try not to use it alone, since using this function alone, will make peds fall through ground in hell(well for the most of the times).

Instead, before calling this function, you may want to declare the position, where your Resurrected ped to be spawn at.(For instance, Around 2 floats of Player's current position.) 

Also, disabling any assigned task immediately helped in the number of scenarios, where If you want peds to perform certain decided tasks.
```

> SET_PED_NAME_DEBUG - 0x98EFA132A4117BE1 0x20D6273E

void SET_PED_NAME_DEBUG(Ped ped, char* name)

```
NOTE: Debugging functions are not present in the retail version of the game.

*untested but char *name could also be a hash for a localized string
```

> GET_PED_EXTRACTED_DISPLACEMENT - 0xE0AF41401ADF87E3 0x5231F901

Vector3 GET_PED_EXTRACTED_DISPLACEMENT(Ped ped, BOOL worldSpace)

```
Gets the offset the specified ped has moved since the previous tick.

If worldSpace is false, the returned offset is relative to the ped. That is, if the ped has moved 1 meter right and 5 meters forward, it'll return 1,5,0.

If worldSpace is true, the returned offset is relative to the world. That is, if the ped has moved 1 meter on the X axis and 5 meters on the Y axis, it'll return 1,5,0.
```

> SET_PED_DIES_WHEN_INJURED - 0x5BA7919BED300023 0xE94E24D4

Any SET_PED_DIES_WHEN_INJURED(Ped ped, BOOL toggle)



> SET_PED_ENABLE_WEAPON_BLOCKING - 0x97A790315D3831FD 0x4CAD1A4A

Any SET_PED_ENABLE_WEAPON_BLOCKING(Ped ped, BOOL toggle)



> 0xF9ACF4A08098EA25 0x141CC936

void 0xF9ACF4A08098EA25(Ped ped, BOOL p1)

```
p1 was always 1 (true).

Kicks the ped from the current vehicle and keeps the rendering-focus on this ped (also disables its collision). If doing this for your player ped, you'll still be able to drive the vehicle.
```

> RESET_PED_VISIBLE_DAMAGE - 0x3AC1F7B898F30C05 0xC4BC4841

Any RESET_PED_VISIBLE_DAMAGE(Ped ped)



> APPLY_PED_BLOOD_DAMAGE_BY_ZONE - 0x816F6981C60BF53B 0x1E54DB12

void APPLY_PED_BLOOD_DAMAGE_BY_ZONE(Ped ped, Any p1, float p2, float p3, Any p4)



> APPLY_PED_BLOOD - 0x83F7E01C7B769A26 0x376CE3C0

void APPLY_PED_BLOOD(Ped ped, int boneIndex, float xRot, float yRot, float zRot, char* woundType)

```
Found one occurence in re_crashrescue.c4

PED::APPLY_PED_BLOOD(l_4B, 3, 0.0, 0.0, 0.0, 'wound_sheet');

- winject


```

> APPLY_PED_BLOOD_BY_ZONE - 0x3311E47B91EDCBBC 0x8F3F3A9C

void APPLY_PED_BLOOD_BY_ZONE(Ped ped, Any p1, float p2, float p3, Any* p4)



> APPLY_PED_BLOOD_SPECIFIC - 0xEF0D582CBF2D9B0F 0xFC13CE80

void APPLY_PED_BLOOD_SPECIFIC(Ped ped, Any p1, float p2, float p3, float p4, float p5, Any p6, float p7, Any* p8)



> APPLY_PED_DAMAGE_DECAL - 0x397C38AA7B4A5F83 0x8A13A41F

void APPLY_PED_DAMAGE_DECAL(Ped ped, int p1, float p2, float p3, float p4, float p5, float p6, int p7, BOOL p8, char* p9)

```
APPLY_PED_DAMAGE_DECAL(ped, 1, 0.5f, 0.513f, 0f, 1f, unk, 0, 0, 'blushing');
```

> APPLY_PED_DAMAGE_PACK - 0x46DF918788CB093F 0x208D0CB8

void APPLY_PED_DAMAGE_PACK(Ped ped, char* damagePack, float damage, float mult)

```
Damage Packs:

'SCR_TrevorTreeBang'
'HOSPITAL_0'
'HOSPITAL_1'
'HOSPITAL_2'
'HOSPITAL_3'
'HOSPITAL_4'
'HOSPITAL_5'
'HOSPITAL_6'
'HOSPITAL_7'
'HOSPITAL_8'
'HOSPITAL_9'
'SCR_Dumpster'
'BigHitByVehicle'
'SCR_Finale_Michael_Face'
'SCR_Franklin_finb'
'SCR_Finale_Michael'
'SCR_Franklin_finb2'
'Explosion_Med'
'SCR_Torture'
'SCR_TracySplash'
'Skin_Melee_0'

Additional damage packs:

gist.github.com/alexguirre/f3f47f75ddcf617f416f3c8a55ae2227
```

> CLEAR_PED_BLOOD_DAMAGE - 0x8FE22675A5A45817 0xF7ADC960

void CLEAR_PED_BLOOD_DAMAGE(Ped ped)



> CLEAR_PED_BLOOD_DAMAGE_BY_ZONE - 0x56E3B78C5408D9F4 0xF210BE69

void CLEAR_PED_BLOOD_DAMAGE_BY_ZONE(Ped ped, int p1)

```
Somehow related to changing ped's clothes.
```

> HIDE_PED_BLOOD_DAMAGE_BY_ZONE - 0x62AB793144DE75DC 0x0CB6C4ED

void HIDE_PED_BLOOD_DAMAGE_BY_ZONE(Ped ped, Any p1, BOOL p2)



> CLEAR_PED_DAMAGE_DECAL_BY_ZONE - 0x523C79AEEFCC4A2A 0x70AA5B7D

void CLEAR_PED_DAMAGE_DECAL_BY_ZONE(Ped ped, int p1, char* p2)

```
p1: from 0 to 5 in the b617d scripts.
p2: 'blushing' and 'ALL' found in the b617d scripts.
```

> GET_PED_DECORATIONS_STATE - 0x71EAB450D86954A1 0x47187F7F

Any GET_PED_DECORATIONS_STATE(Ped ped)



> 0x2B694AFCF64E6994 

void 0x2B694AFCF64E6994(Ped ped, BOOL p1)



> CLEAR_PED_WETNESS - 0x9C720776DAA43E7E 0x629F15BD

Any CLEAR_PED_WETNESS(Ped ped)

```
It clears the wetness of the selected Ped/Player. Clothes have to be wet to notice the difference.
```

> SET_PED_WETNESS_HEIGHT - 0x44CB6447D2571AA0 0x7B33289A

Any SET_PED_WETNESS_HEIGHT(Ped ped, float height)

```
It adds the wetness level to the player clothing/outfit. As if player just got out from water surface.


```

> SET_PED_WETNESS_ENABLED_THIS_FRAME - 0xB5485E4907B53019 0xBDE749F7

void SET_PED_WETNESS_ENABLED_THIS_FRAME(Ped ped)

```
combined with PED::SET_PED_WETNESS_HEIGHT(), this native makes the ped drenched in water up to the height specified in the other function
```

> 0x6585D955A68452A5 0xA993915F

Any 0x6585D955A68452A5(Ped ped)

```
Something related to clearing the ped because always used with CLEAR_PED_WETNESS, CLEAR_PED_BLOOD_DAMAGE and RESET_PED_VISIBLE_DAMAGE.
```

> SET_PED_SWEAT - 0x27B0405F59637D1F 0x76A1DB9F

void SET_PED_SWEAT(Ped ped, float sweat)

```
Sweat is set to 100.0 or 0.0 in the decompiled scripts.
```

> _SET_PED_DECORATION - 0x5F5D1665E352A839 0x70559AC7

void _SET_PED_DECORATION(Ped ped, Hash collection, Hash overlay)

```
Applies an Item from a PedDecorationCollection to a ped. These include tattoos and shirt decals.

collection - PedDecorationCollection filename hash
overlay - Item name hash

Example:
Entry inside 'mpbeach_overlays.xml' -
&lt;Item&gt;
  &lt;uvPos x='0.500000' y='0.500000' /&gt;
  &lt;scale x='0.600000' y='0.500000' /&gt;
  &lt;rotation value='0.000000' /&gt;
  &lt;nameHash&gt;FM_Hair_Fuzz&lt;/nameHash&gt;
  &lt;txdHash&gt;mp_hair_fuzz&lt;/txdHash&gt;
  &lt;txtHash&gt;mp_hair_fuzz&lt;/txtHash&gt;
  &lt;zone&gt;ZONE_HEAD&lt;/zone&gt;
  &lt;type&gt;TYPE_TATTOO&lt;/type&gt;
  &lt;faction&gt;FM&lt;/faction&gt;
  &lt;garment&gt;All&lt;/garment&gt;
  &lt;gender&gt;GENDER_DONTCARE&lt;/gender&gt;
  &lt;award /&gt;
  &lt;awardLevel /&gt;
&lt;/Item&gt;

Code:
PED::_0x5F5D1665E352A839(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('mpbeach_overlays'), GAMEPLAY::GET_HASH_KEY('fm_hair_fuzz'))
```

> _SET_PED_FACIAL_DECORATION - 0x5619BFA07CFD7833 

void _SET_PED_FACIAL_DECORATION(Ped ped, Hash collection, Hash overlay)

```
Console Hash: 0x8CD3E487

```

> _GET_TATTOO_ZONE - 0x9FD452BFBE7A7A8B 0x3543019E

int _GET_TATTOO_ZONE(Hash collection, Hash overlay)

```
Returns the zoneID for the overlay if it is a member of collection.
enum TattooZoneData
{
	ZONE_TORSO = 0,
	ZONE_HEAD = 1,
	ZONE_LEFT_ARM = 2,
	ZONE_RIGHT_ARM = 3,
	ZONE_LEFT_LEG = 4,
	ZONE_RIGHT_LEG = 5,
	ZONE_UNKNOWN = 6,
	ZONE_NONE = 7,
};
```

> CLEAR_PED_DECORATIONS - 0x0E5173C163976E38 0xD4496BF3

void CLEAR_PED_DECORATIONS(Ped ped)



> _CLEAR_PED_FACIAL_DECORATIONS - 0xE3B27E70CEAB9F0C 0xEFD58EB9

void _CLEAR_PED_FACIAL_DECORATIONS(Ped ped)



> WAS_PED_SKELETON_UPDATED - 0x11B499C1E0FF8559 0xF7E2FBAD

BOOL WAS_PED_SKELETON_UPDATED(Ped ped)

```
MulleDK19: Despite this function's name, it simply returns whether the specified handle is a Ped.
```

> GET_PED_BONE_COORDS - 0x17C07FC640E86B4E 0x4579CAB1

Vector3 GET_PED_BONE_COORDS(Ped ped, int boneId, float offsetX, float offsetY, float offsetZ)

```
Gets the position of the specified bone of the specified ped.

ped: The ped to get the position of a bone from.
boneId: The ID of the bone to get the position from. This is NOT the index.
offsetX: The X-component of the offset to add to the position relative to the bone's rotation.
offsetY: The Y-component of the offset to add to the position relative to the bone's rotation.
offsetZ: The Z-component of the offset to add to the position relative to the bone's rotation.
```

> CREATE_NM_MESSAGE - 0x418EF2A1BCE56685 0x1CFBFD4B

void CREATE_NM_MESSAGE(BOOL startImmediately, int messageId)

```
MulleDK19: Creates a new NaturalMotion message.

startImmediately: If set to true, the character will perform the message the moment it receives it by GIVE_PED_NM_MESSAGE. If false, the Ped will get the message but won't perform it yet. While it's a boolean value, if negative, the message will not be initialized.
messageId: The ID of the NaturalMotion message.

If a message already exists, this function does nothing. A message exists until the point it has been successfully dispatched by GIVE_PED_NM_MESSAGE.
```

> GIVE_PED_NM_MESSAGE - 0xB158DFCCC56E5C5B 0x737C3689

void GIVE_PED_NM_MESSAGE(Ped ped)

```
MulleDK19: Sends the message that was created by a call to CREATE_NM_MESSAGE to the specified Ped.

If a message hasn't been created already, this function does nothing.
If the Ped is not ragdolled with Euphoria enabled, this function does nothing.
The following call can be used to ragdoll the Ped with Euphoria enabled: SET_PED_TO_RAGDOLL(ped, 4000, 5000, 1, 1, 1, 0);

Call order:
SET_PED_TO_RAGDOLL
CREATE_NM_MESSAGE
GIVE_PED_NM_MESSAGE

Multiple messages can be chained. Eg. to make the ped stagger and swing his arms around, the following calls can be made:
SET_PED_TO_RAGDOLL(ped, 4000, 5000, 1, 1, 1, 0);
CREATE_NM_MESSAGE(true, 0); // stopAllBehaviours - Stop all other behaviours, in case the Ped is already doing some Euphoria stuff.
GIVE_PED_NM_MESSAGE(ped); // Dispatch message to Ped.
CREATE_NM_MESSAGE(true, 1151); // staggerFall - Attempt to walk while falling.
GIVE_PED_NM_MESSAGE(ped); // Dispatch message to Ped.
CREATE_NM_MESSAGE(true, 372); // armsWindmill - Swing arms around.
GIVE_PED_NM_MESSAGE(ped); // Dispatch message to Ped.
```

> ADD_SCENARIO_BLOCKING_AREA - 0x1B5C85C612E5256E 0xA38C0234

Any ADD_SCENARIO_BLOCKING_AREA(float p0, float p1, float p2, float p3, float p4, float p5, BOOL p6, BOOL p7, BOOL p8, BOOL p9)



> REMOVE_SCENARIO_BLOCKING_AREAS - 0xD37401D78A929A49 0x4DDF845F

void REMOVE_SCENARIO_BLOCKING_AREAS()



> REMOVE_SCENARIO_BLOCKING_AREA - 0x31D16B74C6E29D66 0x4483EF06

void REMOVE_SCENARIO_BLOCKING_AREA(Any p0, BOOL p1)



> SET_SCENARIO_PEDS_SPAWN_IN_SPHERE_AREA - 0x28157D43CF600981 0x80EAD297

void SET_SCENARIO_PEDS_SPAWN_IN_SPHERE_AREA(Any p0, Any p1, Any p2, Any p3, Any p4)



> IS_PED_USING_SCENARIO - 0x1BF094736DD62C2E 0x0F65B0D4

BOOL IS_PED_USING_SCENARIO(Ped ped, char* scenario)



> IS_PED_USING_ANY_SCENARIO - 0x57AB4A3080F85143 0x195EF5B7

BOOL IS_PED_USING_ANY_SCENARIO(Ped ped)



> 0xFE07FF6495D52E2A 0x59DE73AC

Any 0xFE07FF6495D52E2A(Any p0, Any p1, Any p2, Any p3)



> 0x9A77DFD295E29B09 0xC08FE5F6

void 0x9A77DFD295E29B09(Any p0, BOOL p1)



> 0x25361A96E0F7E419 0x58C0F6CF

Any 0x25361A96E0F7E419(Any p0, Any p1, Any p2, Any p3)



> 0xEC6935EBE0847B90 0x761F8F48

Any 0xEC6935EBE0847B90(Any p0, Any p1, Any p2, Any p3)



> 0xA3A9299C4F2ADB98 0x033F43FA

void 0xA3A9299C4F2ADB98(Any p0)



> 0xF1C03A5352243A30 0x4C684C81

void 0xF1C03A5352243A30(Any p0)



> 0xEEED8FAFEC331A70 0x7B4C3E6F

Any 0xEEED8FAFEC331A70(Any p0, Any p1, Any p2, Any p3)



> 0x425AECF167663F48 0x5BC276AE

void 0x425AECF167663F48(Ped ped, BOOL p1)



> 0x5B6010B3CBC29095 

void 0x5B6010B3CBC29095(Any p0, BOOL p1)



> 0xCEDA60A74219D064 

void 0xCEDA60A74219D064(Any p0, BOOL p1)



> PLAY_FACIAL_ANIM - 0xE1E65CA8AC9C00ED 0x1F6CCDDE

void PLAY_FACIAL_ANIM(Ped ped, char* animName, char* animDict)



> SET_FACIAL_IDLE_ANIM_OVERRIDE - 0xFFC24B988B938B38 0x9BA19C13

void SET_FACIAL_IDLE_ANIM_OVERRIDE(Ped ped, char* animName, char* animDict)



> CLEAR_FACIAL_IDLE_ANIM_OVERRIDE - 0x726256CC1EEB182F 0x5244F4E2

void CLEAR_FACIAL_IDLE_ANIM_OVERRIDE(Ped ped)



> SET_PED_CAN_PLAY_GESTURE_ANIMS - 0xBAF20C5432058024 0xE131E3B3

void SET_PED_CAN_PLAY_GESTURE_ANIMS(Ped ped, BOOL toggle)



> SET_PED_CAN_PLAY_VISEME_ANIMS - 0xF833DDBA3B104D43 0xA2FDAF27

void SET_PED_CAN_PLAY_VISEME_ANIMS(Ped ped, BOOL p1, BOOL p2)



> 0x33A60D8BDD6E508C 0xADB2511A

void 0x33A60D8BDD6E508C(Any p0, BOOL p1)



> SET_PED_CAN_PLAY_AMBIENT_ANIMS - 0x6373D1349925A70E 0xF8053081

void SET_PED_CAN_PLAY_AMBIENT_ANIMS(Ped ped, BOOL toggle)



> SET_PED_CAN_PLAY_AMBIENT_BASE_ANIMS - 0x0EB0585D15254740 0x5720A5DD

void SET_PED_CAN_PLAY_AMBIENT_BASE_ANIMS(Ped ped, BOOL toggle)



> 0xC2EE020F5FB4DB53 0xB7CD0A49

void 0xC2EE020F5FB4DB53(Ped ped)



> SET_PED_CAN_ARM_IK - 0x6C3B4D6D13B4C841 0x343B4DE0

void SET_PED_CAN_ARM_IK(Ped ped, BOOL toggle)



> SET_PED_CAN_HEAD_IK - 0xC11C18092C5530DC 0xD3B04476

void SET_PED_CAN_HEAD_IK(Ped ped, BOOL toggle)



> SET_PED_CAN_LEG_IK - 0x73518ECE2485412B 0x9955BC6F

void SET_PED_CAN_LEG_IK(Ped ped, BOOL toggle)



> SET_PED_CAN_TORSO_IK - 0xF2B7106D37947CE0 0x8E5D4EAB

void SET_PED_CAN_TORSO_IK(Ped ped, BOOL toggle)



> 0xF5846EDB26A98A24 0x7B0040A8

void 0xF5846EDB26A98A24(Any p0, BOOL p1)



> 0x6647C5F6F5792496 0x0FDA62DE

void 0x6647C5F6F5792496(Any p0, BOOL p1)



> SET_PED_CAN_USE_AUTO_CONVERSATION_LOOKAT - 0xEC4686EC06434678 0x584C5178

void SET_PED_CAN_USE_AUTO_CONVERSATION_LOOKAT(Ped ped, BOOL toggle)



> IS_PED_HEADTRACKING_PED - 0x5CD3CB88A7F8850D 0x2A5DF721

BOOL IS_PED_HEADTRACKING_PED(Ped ped1, Ped ped2)



> IS_PED_HEADTRACKING_ENTITY - 0x813A0A7C9D2E831F 0x233C9ACF

BOOL IS_PED_HEADTRACKING_ENTITY(Ped ped, Entity entity)



> SET_PED_PRIMARY_LOOKAT - 0xCD17B554996A8D9E 0x6DEF6F1C

void SET_PED_PRIMARY_LOOKAT(Ped ped, Ped lookAt)

```
This is only called once in the scripts.

sub_1CD9(&amp;l_49, 0, getElem(3, &amp;l_34, 4), 'MICHAEL', 0, 1);
                    sub_1CA8('WORLD_HUMAN_SMOKING', 2);
                    PED::SET_PED_PRIMARY_LOOKAT(getElem(3, &amp;l_34, 4), PLAYER::PLAYER_PED_ID());
```

> 0x78C4E9961DB3EB5B 0xFC942D7C

void 0x78C4E9961DB3EB5B(Any p0, Any p1)



> 0x82A3D6D9CC2CB8E3 0x89EEE07B

void 0x82A3D6D9CC2CB8E3(Any p0, Any p1)



> 0xA660FAF550EB37E5 

void 0xA660FAF550EB37E5(Any p0, BOOL p1)



> SET_PED_CONFIG_FLAG - 0x1913FE4CBF41C463 0x9CFBE10D

void SET_PED_CONFIG_FLAG(Ped ped, int flagId, BOOL value)

```
Maximum value for flagId is 0x1AA (426) in b944.
ID 0xF0 (240) appears to be a special flag which is handled different compared to the others IDs.

-----------------------------------------------------------------------

enum PedConfigFlags
{
	PED_FLAG_CAN_FLY_THRU_WINDSCREEN = 32,
        PED_FLAG_DIES_BY_RAGDOLL = 33,
	PED_FLAG_NO_COLLISION = 52,
	PED_FLAG_NO_COLLIDE = 62,
	PED_FLAG_DEAD = 71,
        PED_FLAG_IS_SNIPER_SCOPE_ACTIVE = 72,
	PED_FLAG_SUPER_DEAD = 73,
	PED_FLAG_IS_AIMING = 78,
	PED_FLAG_DRUNK = 100,
        PED_FLAG_NO_PLAYER_MELEE = 122,
	PED_FLAG_NM_MESSAGE_466 = 125,
	PED_FLAG_INJURED_LIMP = 166,
	PED_FLAG_INJURED_LIMP_2 = 170,
	PED_FLAG_INJURED_DOWN = 187,
	PED_FLAG_SHRINK = 223,
        PED_FLAG_MELEE_COMBAT = 224,
	PED_FLAG_NO_WRITHE = 281,
	PED_FLAG_FREEZE = 292,
	PED_FLAG_IS_STILL = 301,
        PED_FLAG_NO_PED_MELEE = 314,
	PED_FLAG_ALPHA = 410,
};

When flagId is set to 33 and the bool value to true, peds will die by starting ragdoll, so you should set this flag to false when you resurrect a ped.
When flagId is set to 62 and the boolvalue to false this happens: Ped is taken out of vehicle and can't get back in when jacking their empty vehicle. If in a plane it falls from the sky and crashes. Sometimes peds vehicle continue to drive the route without its driver who's running after. 

Note: Using Menyoo on GTA V PC. It read PED_FLAG_COLLIDE - 62 as false. I attempted to toggle it to true and it caused the game to crash.

JUMPING CHANGES  60,61,104 TO FALSE
BEING ON WATER CHANGES 60,61 TO FALSE AND 65,66,168 TO TRUE
FALLING CHANGES 60,61,104,276 TO FALSE AND TO 76 TRUE
DYING CHANGES 60,61,104,276* TO FALSE AND (NONE) TO TRUE
DYING MAKES 60,61,104 TO FALSE
BEING IN A CAR CHANGES 60,79,104 TO FALSE AND 62 TO TRUE


--------------
can any see what flag 365 does. set it to 0
```

> SET_PED_RESET_FLAG - 0xC1E8A365BF3B29F2 0xCFF6FF66

void SET_PED_RESET_FLAG(Ped ped, int flagId, BOOL doReset)

```
PED::SET_PED_RESET_FLAG(PLAYER::PLAYER_PED_ID(), 240, 1);
```

> GET_PED_CONFIG_FLAG - 0x7EE53118C892B513 0xABE98267

BOOL GET_PED_CONFIG_FLAG(Ped ped, int flagId, BOOL p2)

```
p2 is always 1 in the scripts.

if (GET_PED_CONFIG_FLAG(ped, 78, 1))
= returns true if ped is aiming/shooting a gun
```

> GET_PED_RESET_FLAG - 0xAF9E59B1B1FBF2A0 0x2FC10D11

BOOL GET_PED_RESET_FLAG(Ped ped, int flagId)



> SET_PED_GROUP_MEMBER_PASSENGER_INDEX - 0x0BDDB8D9EC6BCF3C 0x2AB3670B

void SET_PED_GROUP_MEMBER_PASSENGER_INDEX(Ped ped, int index)



> SET_PED_CAN_EVASIVE_DIVE - 0x6B7A646C242A7059 0x542FEB4D

void SET_PED_CAN_EVASIVE_DIVE(Ped ped, BOOL toggle)



> IS_PED_EVASIVE_DIVING - 0x414641C26E105898 0xD82829DC

BOOL IS_PED_EVASIVE_DIVING(Ped ped, Entity* evadingEntity)

```
Presumably returns the Entity that the Ped is currently diving out of the way of.

var num3;
    if (PED::IS_PED_EVASIVE_DIVING(A_0, &amp;num3) != 0)
        if (ENTITY::IS_ENTITY_A_VEHICLE(num3) != 0)
```

> SET_PED_SHOOTS_AT_COORD - 0x96A05E4FB321B1BA 0xFD64EAE5

void SET_PED_SHOOTS_AT_COORD(Ped ped, float x, float y, float z, BOOL toggle)



> SET_PED_MODEL_IS_SUPPRESSED - 0xE163A4BCE4DE6F11 0x7820CA43

void SET_PED_MODEL_IS_SUPPRESSED(Ped ped, BOOL toggle)



> STOP_ANY_PED_MODEL_BEING_SUPPRESSED - 0xB47BD05FA66B40CF 0x5AD7DC55

void STOP_ANY_PED_MODEL_BEING_SUPPRESSED()



> SET_PED_CAN_BE_TARGETED_WHEN_INJURED - 0x638C03B0F9878F57 0x6FD9A7CD

void SET_PED_CAN_BE_TARGETED_WHEN_INJURED(Ped ped, BOOL toggle)



> SET_PED_GENERATES_DEAD_BODY_EVENTS - 0x7FB17BA2E7DECA5B 0xE9B97A2B

void SET_PED_GENERATES_DEAD_BODY_EVENTS(Ped ped, BOOL toggle)



> 0xE43A13C9E4CCCBCF 0xFF1F6AEB

void 0xE43A13C9E4CCCBCF(Ped ped, BOOL p1)



> SET_PED_CAN_RAGDOLL_FROM_PLAYER_IMPACT - 0xDF993EE5E90ABA25 0xE9BD733A

void SET_PED_CAN_RAGDOLL_FROM_PLAYER_IMPACT(Ped ped, BOOL toggle)



> GIVE_PED_HELMET - 0x54C7C4A94367717E 0x1862A461

void GIVE_PED_HELMET(Ped ped, BOOL cannotRemove, int helmetFlag, int textureIndex)

```
PoliceMotorcycleHelmet	1024	
RegularMotorcycleHelmet	4096	
FiremanHelmet	16384	
PilotHeadset	32768	
PilotHelmet	65536
--
p2 is generally 4096 or 16384 in the scripts. p1 varies between 1 and 0.
```

> REMOVE_PED_HELMET - 0xA7B2458D0AD6DED8 0x2086B1F0

void REMOVE_PED_HELMET(Ped ped, BOOL instantly)



> 0x14590DDBEDB1EC85 

BOOL 0x14590DDBEDB1EC85(Ped ped)



> SET_PED_HELMET - 0x560A43136EB58105 0xED366E53

void SET_PED_HELMET(Ped ped, BOOL canWearHelmet)



> SET_PED_HELMET_FLAG - 0xC0E78D5C2CE3EB25 0x12677780

void SET_PED_HELMET_FLAG(Ped ped, int helmetFlag)



> SET_PED_HELMET_PROP_INDEX - 0x26D83693ED99291C 0xA316D13F

void SET_PED_HELMET_PROP_INDEX(Ped ped, int propIndex)

```
List of component/props ID
gtaxscripting.blogspot.com/2016/04/gta-v-peds-component-and-props.html
```

> SET_PED_HELMET_TEXTURE_INDEX - 0xF1550C4BD22582E2 0x5F6C3328

void SET_PED_HELMET_TEXTURE_INDEX(Ped ped, int textureIndex)



> IS_PED_WEARING_HELMET - 0xF33BDFE19B309B19 0x0D680D49

BOOL IS_PED_WEARING_HELMET(Ped ped)

```
Returns true if the ped passed through the parenthesis is wearing a helmet.

-UNBOUND-
```

> 0x687C0B594907D2E8 0x24A1284E

void 0x687C0B594907D2E8(Any p0)



> 0x451294E859ECC018 0x8A3A3116

Any 0x451294E859ECC018(Any p0)



> 0x9D728C1E12BF5518 0x74EB662D

Any 0x9D728C1E12BF5518(Any p0)



> 0xF2385935BFFD4D92 0xFFF149FE

BOOL 0xF2385935BFFD4D92(Any p0)



> SET_PED_TO_LOAD_COVER - 0x332B562EEDA62399 0xCF94BA97

void SET_PED_TO_LOAD_COVER(Ped ped, BOOL toggle)



> SET_PED_CAN_COWER_IN_COVER - 0xCB7553CDCEF4A735 0x5194658B

void SET_PED_CAN_COWER_IN_COVER(Ped ped, BOOL toggle)

```
It simply makes the said ped to cower behind cover object(wall, desk, car)

Peds flee attributes must be set to not to flee, first. Else, most of the peds, will just flee from gunshot sounds or any other panic situations.

-YCSM
```

> SET_PED_CAN_PEEK_IN_COVER - 0xC514825C507E3736 0xC1DAE216

void SET_PED_CAN_PEEK_IN_COVER(Ped ped, BOOL toggle)



> SET_PED_PLAYS_HEAD_ON_HORN_ANIM_WHEN_DIES_IN_VEHICLE - 0x94D94BF1A75AED3D 0x7C563CD2

void SET_PED_PLAYS_HEAD_ON_HORN_ANIM_WHEN_DIES_IN_VEHICLE(Ped ped, BOOL toggle)

```
Points to the same function as for example GET_RANDOM_VEHICLE_MODEL_IN_MEMORY and it does absolutely nothing.
```

> SET_PED_LEG_IK_MODE - 0xC396F5B86FF9FEBD 0xFDDB042E

void SET_PED_LEG_IK_MODE(Ped ped, int mode)

```
'IK' stands for 'Inverse kinematics.' I assume this has something to do with how the ped uses his legs to balance. In the scripts, the second parameter is always an int with a value of 2, 0, or sometimes 1
```

> SET_PED_MOTION_BLUR - 0x0A986918B102B448 0xA211A128

void SET_PED_MOTION_BLUR(Ped ped, BOOL toggle)



> SET_PED_CAN_SWITCH_WEAPON - 0xED7F7EFE9FABF340 0xB5F8BA28

void SET_PED_CAN_SWITCH_WEAPON(Ped ped, BOOL toggle)



> SET_PED_DIES_INSTANTLY_IN_WATER - 0xEEB64139BA29A7CF 0xFE2554FC

void SET_PED_DIES_INSTANTLY_IN_WATER(Ped ped, BOOL toggle)



> 0x1A330D297AAC6BC1 0x77BB7CB8

void 0x1A330D297AAC6BC1(Ped ped, int p1)

```
Only appears in lamar1 script.
```

> STOP_PED_WEAPON_FIRING_WHEN_DROPPED - 0xC158D28142A34608 0x4AC3421E

void STOP_PED_WEAPON_FIRING_WHEN_DROPPED(Ped ped)



> SET_SCRIPTED_ANIM_SEAT_OFFSET - 0x5917BBA32D06C230 0x7CEFFA45

void SET_SCRIPTED_ANIM_SEAT_OFFSET(Ped ped, float p1)



> SET_PED_COMBAT_MOVEMENT - 0x4D9CA1009AFBD057 0x12E62F9E

void SET_PED_COMBAT_MOVEMENT(Ped ped, int combatMovement)

```
0 - Stationary (Will just stand in place)
1 - Defensive (Will try to find cover and very likely to blind fire)
2 - Offensive (Will attempt to charge at enemy but take cover as well)
3 - Suicidal Offensive (Will try to flank enemy in a suicidal attack)
```

> GET_PED_COMBAT_MOVEMENT - 0xDEA92412FCAEB3F5 0xF3E7730E

int GET_PED_COMBAT_MOVEMENT(Ped ped)



> SET_PED_COMBAT_ABILITY - 0xC7622C0D36B2FDA8 0x6C23D329

void SET_PED_COMBAT_ABILITY(Ped ped, int p1)

```
100 would equal attack
less then 50ish would mean run away

Only the values 0, 1 and 2 occur in the decompiled scripts. Most likely refers directly to the values also described in combatbehaviour.meta:
0: CA_Poor
1: CA_Average
2: CA_Professional

Tested this and got the same results as the first explanation here. Could not find any difference between 0, 1 and 2. 
```

> SET_PED_COMBAT_RANGE - 0x3C606747B23E497B 0x8818A959

void SET_PED_COMBAT_RANGE(Ped ped, int p1)

```
Only the values 0, 1 and 2 occur in the decompiled scripts. Most likely refers directly to the values also described as AttackRange in combatbehaviour.meta:
0: CR_Near
1: CR_Medium
2: CR_Far
```

> GET_PED_COMBAT_RANGE - 0xF9D9F7F2DB8E2FA0 0x9B9B7163

Any GET_PED_COMBAT_RANGE(Ped ped)



> SET_PED_COMBAT_ATTRIBUTES - 0x9F7794730795E019 0x81D64248

void SET_PED_COMBAT_ATTRIBUTES(Ped ped, int attributeIndex, BOOL enabled)

```
These combat attributes seem to be the same as the BehaviourFlags from combatbehaviour.meta.
So far, these are the equivalents found:
enum CombatAttributes
{
	BF_CanUseCover = 0,
	BF_CanUseVehicles = 1,
	BF_CanDoDrivebys = 2,
	BF_CanLeaveVehicle = 3,
	BF_CanFightArmedPedsWhenNotArmed = 5,
	BF_CanTauntInVehicle = 20,
	BF_AlwaysFight = 46,
	BF_IgnoreTrafficWhenDriving = 52,
        BF_FreezeMovement = 292,
        BF_PlayerCanUseFireingWeapons = 1424
};

Research thread: gtaforums.com/topic/833391-researchguide-combat-behaviour-flags/
```

> SET_PED_TARGET_LOSS_RESPONSE - 0x0703B9079823DA4A 0xCFA613FF

void SET_PED_TARGET_LOSS_RESPONSE(Ped ped, int responseType)

```
Only 1 and 2 appear in the scripts. combatbehaviour.meta seems to only have TLR_SearchForTarget for all peds, but we don't know if that's 1 or 2.
```

> 0xDCCA191DF9980FD7 0x139C0875

BOOL 0xDCCA191DF9980FD7(Ped ped)



> IS_PED_PERFORMING_STEALTH_KILL - 0xFD4CCDBCC59941B7 0x9ADD7B21

BOOL IS_PED_PERFORMING_STEALTH_KILL(Ped ped)



> 0xEBD0EDBA5BE957CF 0x9BE7C860

BOOL 0xEBD0EDBA5BE957CF(Ped ped)



> IS_PED_BEING_STEALTH_KILLED - 0x863B23EFDE9C5DF2 0xD044C8AF

BOOL IS_PED_BEING_STEALTH_KILLED(Ped ped)



> GET_MELEE_TARGET_FOR_PED - 0x18A3E9EE1297FD39 0xAFEC26A4

Ped GET_MELEE_TARGET_FOR_PED(Ped ped)



> WAS_PED_KILLED_BY_STEALTH - 0xF9800AA1A771B000 0x2EA4B54E

BOOL WAS_PED_KILLED_BY_STEALTH(Ped ped)



> WAS_PED_KILLED_BY_TAKEDOWN - 0x7F08E26039C7347C 0xBDD3CE69

BOOL WAS_PED_KILLED_BY_TAKEDOWN(Ped ped)



> 0x61767F73EACEED21 0x3993092B

BOOL 0x61767F73EACEED21(Ped ped)



> SET_PED_FLEE_ATTRIBUTES - 0x70A2D1137C8ED7C9 0xA717A875

void SET_PED_FLEE_ATTRIBUTES(Ped ped, int attributes, BOOL p2)

```
Bool probably has something to do with vehicles, maybe if the ped can use vehicle to flee?

Values used as attributes are those in sequence of powers of two, 1, 2, 4, 8, 16, 32, 64.... 65536.
```

> SET_PED_COWER_HASH - 0xA549131166868ED3 0x16F30DF4

void SET_PED_COWER_HASH(Ped ped, char* p1)

```
p1: Only 'CODE_HUMAN_STAND_COWER' found in the b617d scripts.
```

> 0x2016C603D6B8987C 0xA6F2C057

void 0x2016C603D6B8987C(Any p0, BOOL p1)



> SET_PED_STEERS_AROUND_PEDS - 0x46F2193B3AD1D891 0x797CAE4F

void SET_PED_STEERS_AROUND_PEDS(Ped ped, BOOL toggle)



> SET_PED_STEERS_AROUND_OBJECTS - 0x1509C089ADC208BF 0x3BD9B0A6

void SET_PED_STEERS_AROUND_OBJECTS(Ped ped, BOOL toggle)



> SET_PED_STEERS_AROUND_VEHICLES - 0xEB6FB9D48DDE23EC 0x533C0651

void SET_PED_STEERS_AROUND_VEHICLES(Ped ped, BOOL toggle)



> 0xA9B61A329BFDCBEA 0x2276DE0D

void 0xA9B61A329BFDCBEA(Any p0, BOOL p1)



> 0x570389D1C3DE3C6B 0x59C52BE6

void 0x570389D1C3DE3C6B(Any p0)



> 0x576594E8D64375E2 0x1D87DDC1

void 0x576594E8D64375E2(Any p0, BOOL p1)



> 0xA52D5247A4227E14 0xB52BA5F5

void 0xA52D5247A4227E14(Any p0)



> IS_ANY_PED_NEAR_POINT - 0x083961498679DC9F 0xFBD9B050

BOOL IS_ANY_PED_NEAR_POINT(float x, float y, float z, float radius)



> 0x2208438012482A1A 0x187B9070

void 0x2208438012482A1A(Ped ped, BOOL p1, BOOL p2)

```
Function.Call(Hash._0x2208438012482A1A, ped, 0, 0);

This makes the ped have faster animations
```

> 0xFCF37A457CB96DC0 0x45037B9B

BOOL 0xFCF37A457CB96DC0(Any p0, float p1, float p2, float p3, float p4)



> 0x7D7A2E43E74E2EB8 0x840D24D3

void 0x7D7A2E43E74E2EB8(Any p0)

```
i found this function just like VEHICLE::TRACK_VEHICLE_VISIBILITY 
example:
PED::_0x7D7A2E43E74E2EB8(ped);// TRACK_PED_VISIBILITY
if (PED::IS_TRACKED_PED_VISIBLE(ped))
{
    
}
```

> GET_PED_FLOOD_INVINCIBILITY - 0x2BC338A7B21F4608 0x31C31DAA

void GET_PED_FLOOD_INVINCIBILITY(Ped ped, BOOL p1)

```
hash collision???
```

> 0xCD018C591F94CB43 

void 0xCD018C591F94CB43(Any p0, BOOL p1)



> 0x75BA1CB3B7D40CAF 0x9194DB71

void 0x75BA1CB3B7D40CAF(Any p0, BOOL p1)



> IS_TRACKED_PED_VISIBLE - 0x91C8E617F64188AC 0x33248CC1

BOOL IS_TRACKED_PED_VISIBLE(Ped ped)

```
returns whether or not a ped is visible within your FOV, not this check auto's to false after a certain distance.

~ Lynxaa


Target needs to be tracked.. won't work otherwise.
-THEAETIK
```

> 0x511F1A683387C7E2 0x5B1B70AA

Any 0x511F1A683387C7E2(Any p0)



> IS_PED_TRACKED - 0x4C5E1F087CD10BB7 0x7EB613D9

BOOL IS_PED_TRACKED(Ped ped)



> HAS_PED_RECEIVED_EVENT - 0x8507BCB710FA6DC0 0xECD73DB0

BOOL HAS_PED_RECEIVED_EVENT(Any p0, Any p1)



> 0x6CD5A433374D4CFB 0x74A0F291

BOOL 0x6CD5A433374D4CFB(Any p0, Any p1)



> 0x9C6A6C19B6C0C496 

BOOL 0x9C6A6C19B6C0C496(Ped p0, Any* p1)



> GET_PED_BONE_INDEX - 0x3F428D08BE5AAE31 0x259C6BA2

int GET_PED_BONE_INDEX(Ped ped, int boneId)

```
no bone= -1
```

> GET_PED_RAGDOLL_BONE_INDEX - 0x2057EF813397A772 0x849F0716

int GET_PED_RAGDOLL_BONE_INDEX(Ped ped, int bone)



> SET_PED_ENVEFF_SCALE - 0xBF29516833893561 0xFC1CFC27

void SET_PED_ENVEFF_SCALE(Ped ped, float value)

```
Values look to be between 0.0 and 1.0
From decompiled scripts: 0.0, 0.6, 0.65, 0.8, 1.0

You are correct, just looked in IDA it breaks from the function if it's less than 0.0f or greater than 1.0f.
```

> GET_PED_ENVEFF_SCALE - 0x9C14D30395A51A3C 0xA3421E39

float GET_PED_ENVEFF_SCALE(Ped ped)



> SET_ENABLE_PED_ENVEFF_SCALE - 0xD2C5AA0C0E8D0F1E 0xC70F4A84

void SET_ENABLE_PED_ENVEFF_SCALE(Ped ped, BOOL toggle)



> 0x110F526AB784111F 0x3B882533

void 0x110F526AB784111F(Ped ped, float p1)

```
In agency_heist3b.c4, its like this 90% of the time:

PED::_110F526AB784111F(ped, 0.099);
PED::SET_PED_ENVEFF_SCALE(ped, 1.0);
PED::_D69411AA0CEBF9E9(ped, 87, 81, 68);
PED::SET_ENABLE_PED_ENVEFF_SCALE(ped, 1);

and its like this 10% of the time:

PED::_110F526AB784111F(ped, 0.2);
PED::SET_PED_ENVEFF_SCALE(ped, 0.65);
PED::_D69411AA0CEBF9E9(ped, 74, 69, 60);
PED::SET_ENABLE_PED_ENVEFF_SCALE(ped, 1);
```

> 0xD69411AA0CEBF9E9 0x87A0C174

void 0xD69411AA0CEBF9E9(Ped ped, int p1, int p2, int p3)

```
Something related to the environmental effects natives.
In the 'agency_heist3b' script, p1 - p3 are always under 100 - usually they are {87, 81, 68}. If SET_PED_ENVEFF_SCALE is set to 0.65 (instead of the usual 1.0), they use {74, 69, 60}
```

> 0x1216E0BFA72CC703 0x7BD26837

void 0x1216E0BFA72CC703(Any p0, Any p1)



> 0x2B5AA717A181FB4C 0x98E29ED0

void 0x2B5AA717A181FB4C(Any p0, BOOL p1)



> 0xB8B52E498014F5B0 

BOOL 0xB8B52E498014F5B0(Ped ped)

```
if (!$B8B52E498014F5B0(PLAYER::PLAYER_PED_ID())) {
```

> CREATE_SYNCHRONIZED_SCENE - 0x8C18E0F9080ADD73 0xFFDDF8FA

int CREATE_SYNCHRONIZED_SCENE(float x, float y, float z, float roll, float pitch, float yaw, int p6)

```
p6 always 2 (but it doesnt seem to matter...)

roll and pitch 0
yaw to Ped.rotation
```

> 0x62EC273D00187DCA 0xF3876894

int 0x62EC273D00187DCA(float x, float y, float z, float radius, Hash object)

```
returns sceneHandle
```

> IS_SYNCHRONIZED_SCENE_RUNNING - 0x25D39B935A038A26 0x57A282F1

BOOL IS_SYNCHRONIZED_SCENE_RUNNING(int sceneId)

```
Returns true if a synchronized scene is running
```

> SET_SYNCHRONIZED_SCENE_ORIGIN - 0x6ACF6B7225801CD7 0x2EC2A0B2

void SET_SYNCHRONIZED_SCENE_ORIGIN(int sceneID, float x, float y, float z, float roll, float pitch, float yaw, BOOL p7)



> SET_SYNCHRONIZED_SCENE_PHASE - 0x734292F4F0ABF6D0 0xF5AB0D98

void SET_SYNCHRONIZED_SCENE_PHASE(int sceneID, float phase)



> GET_SYNCHRONIZED_SCENE_PHASE - 0xE4A310B1D7FA73CC 0xB0B2C852

float GET_SYNCHRONIZED_SCENE_PHASE(int sceneID)



> SET_SYNCHRONIZED_SCENE_RATE - 0xB6C49F8A5E295A5D 0xF10112FD

void SET_SYNCHRONIZED_SCENE_RATE(int sceneID, float rate)



> GET_SYNCHRONIZED_SCENE_RATE - 0xD80932D577274D40 0x89365F0D

float GET_SYNCHRONIZED_SCENE_RATE(int sceneID)



> SET_SYNCHRONIZED_SCENE_LOOPED - 0xD9A897A4C6C2974F 0x32ED9F82

void SET_SYNCHRONIZED_SCENE_LOOPED(int sceneID, BOOL toggle)



> IS_SYNCHRONIZED_SCENE_LOOPED - 0x62522002E0C391BA 0x47D87A84

BOOL IS_SYNCHRONIZED_SCENE_LOOPED(int sceneID)



> 0x394B9CD12435C981 0x2DE48DA1

void 0x394B9CD12435C981(Any p0, BOOL p1)



> 0x7F2F4F13AC5257EF 0x72CF2514

BOOL 0x7F2F4F13AC5257EF(Any p0)



> ATTACH_SYNCHRONIZED_SCENE_TO_ENTITY - 0x272E4723B56A3B96 0xE9BA6189

void ATTACH_SYNCHRONIZED_SCENE_TO_ENTITY(int sceneID, Entity entity, int boneIndex)



> DETACH_SYNCHRONIZED_SCENE - 0x6D38F1F04CBB37EA 0x52A1CAB2

void DETACH_SYNCHRONIZED_SCENE(int sceneID)



> _DISPOSE_SYNCHRONIZED_SCENE - 0xCD9CC7E200A52A6F 0xBF7F9035

void _DISPOSE_SYNCHRONIZED_SCENE(int scene)



> FORCE_PED_MOTION_STATE - 0xF28965D04F570DCA 0x164DDEFF

BOOL FORCE_PED_MOTION_STATE(Ped ped, Hash motionStateHash, BOOL p2, BOOL p3, BOOL p4)

```
Some motionstate hashes are

0xec17e58 (standing idle), 0xbac0f10b (nothing?), 0x3f67c6af (aiming with pistol 2-h), 0x422d7a25 (stealth), 0xbd8817db, 0x916e828c

and those for the strings

'motionstate_idle', 'motionstate_walk', 'motionstate_run', 'motionstate_actionmode_idle', and 'motionstate_actionmode_walk'.

Regarding p2, p3 and p4: Most common is 0, 0, 0); followed by 0, 1, 0); and 1, 1, 0); in the scripts. p4 is very rarely something other than 0.

 
```

> 0xF60165E1D2C5370B 

BOOL 0xF60165E1D2C5370B(Ped ped, Any* p1, Any* p2)



> SET_PED_MAX_MOVE_BLEND_RATIO - 0x433083750C5E064A 0xEAD0269A

void SET_PED_MAX_MOVE_BLEND_RATIO(Ped ped, float value)



> SET_PED_MIN_MOVE_BLEND_RATIO - 0x01A898D26E2333DD 0x383EC364

void SET_PED_MIN_MOVE_BLEND_RATIO(Ped ped, float value)



> SET_PED_MOVE_RATE_OVERRIDE - 0x085BF80FA50A39D1 0x900008C6

void SET_PED_MOVE_RATE_OVERRIDE(Ped ped, float value)

```
Min: 0.00
Max: 10.00

Can be used in combo with fast run cheat.

When value is set to 10.00:
Sprinting without fast run cheat: 66 m/s
Sprinting with fast run cheat: 77 m/s

Does not need to be looped!

Note: According to IDA for the Xbox360 xex, when they check bgt they seem to have the min to 0.0f, but the max set to 1.15f not 10.0f.
```

> 0x46B05BCAE43856B0 0x79543043

BOOL 0x46B05BCAE43856B0(Ped ped, int flag)

```
Checks if the specified unknown flag is set in the ped's model.
The engine itself seems to exclusively check for flags 1 and 4 (Might be inlined code of the check that checks for other flags).
Game scripts exclusively check for flags 1 and 4.
```

> GET_PED_NEARBY_VEHICLES - 0xCFF869CBFA210D82 0xCB716F68

int GET_PED_NEARBY_VEHICLES(Ped ped, int* sizeAndVehs)

```
Returns size of array, passed into the second variable.

See below for usage information.

This function actually requires a struct, where the first value is the maximum number of elements to return.  Here is a sample of how I was able to get it to work correctly, without yet knowing the struct format.

//Setup the array
	const int numElements = 10;
	const int arrSize = numElements * 2 + 2;
	Any veh[arrSize];
	//0 index is the size of the array
	veh[0] = numElements;

	int count = PED::GET_PED_NEARBY_VEHICLES(PLAYER::PLAYER_PED_ID(), veh);

	if (veh != NULL)
	{
		//Simple loop to go through results
		for (int i = 0; i &lt; count; i++)
		{
			int offsettedID = i * 2 + 2;
			//Make sure it exists
			if (veh[offsettedID] != NULL &amp;&amp; ENTITY::DOES_ENTITY_EXIST(veh[offsettedID]))
			{
				//Do something
			}
		}
	}  
```

> GET_PED_NEARBY_PEDS - 0x23F8F5FC7E8C4A6B 0x4D3325F4

int GET_PED_NEARBY_PEDS(Ped ped, int* sizeAndPeds, int ignore)

```
sizeAndPeds - is a pointer to an array. The array is filled with peds found nearby the ped supplied to the first argument.
ignore - ped type to ignore

Return value is the number of peds found and added to the array passed.

-----------------------------------

To make this work in most menu bases at least in C++ do it like so,

 Formatted Example: pastebin.com/D8an9wwp

-----------------------------------

Example: gtaforums.com/topic/789788-function-args-to-pedget-ped-nearby-peds/?p=1067386687
```

> 0x7350823473013C02 0xF9FB4B71

BOOL 0x7350823473013C02(Ped ped)



> IS_PED_USING_ACTION_MODE - 0x00E73468D085F745 0x5AE7EDA2

BOOL IS_PED_USING_ACTION_MODE(Ped ped)



> SET_PED_USING_ACTION_MODE - 0xD75ACCF5E0FB5367 0x8802F696

void SET_PED_USING_ACTION_MODE(Ped ped, BOOL p1, Any p2, char* action)

```
p2 is usually -1 in the scripts. action is either 0 or 'DEFAULT_ACTION'.
```

> 0x781DE8FA214E87D2 

void 0x781DE8FA214E87D2(Ped ped, char* p1)

```
p1: 'MP_FEMALE_ACTION' found multiple times in the b617d scripts.

Console Hash: 0x83BAE814
```

> SET_PED_CAPSULE - 0x364DF566EC833DE2 0xB153E1B9

void SET_PED_CAPSULE(Ped ped, float value)

```
Overrides the ped's collision capsule radius for the current tick.
Must be called every tick to be effective.

Setting this to 0.001 will allow warping through some objects.
```

> REGISTER_PEDHEADSHOT - 0x4462658788425076 0xFFE2667B

Any REGISTER_PEDHEADSHOT(Ped ped)



> 0x953563CE563143AF 0x4DD03628

Any 0x953563CE563143AF(Any p0)



> UNREGISTER_PEDHEADSHOT - 0x96B1361D9B24C2FF 0x0879AE45

void UNREGISTER_PEDHEADSHOT(Ped ped)



> IS_PEDHEADSHOT_VALID - 0xA0A9668F158129A2 0x0B1080C4

int IS_PEDHEADSHOT_VALID(int handle)



> IS_PEDHEADSHOT_READY - 0x7085228842B13A67 0x761CD02E

BOOL IS_PEDHEADSHOT_READY(int handle)



> GET_PEDHEADSHOT_TXD_STRING - 0xDB4EACD4AD0A5D6B 0x76D28E96

char* GET_PEDHEADSHOT_TXD_STRING(int handle)



> 0xF0DAEF2F545BEE25 0x10F2C023

BOOL 0xF0DAEF2F545BEE25(Any p0)



> 0x5D517B27CF6ECD04 0x0DBB2FA7

void 0x5D517B27CF6ECD04(Any p0)



> 0xEBB376779A760AA8 0x810158F8

Any 0xEBB376779A760AA8()



> 0x876928DDDFCCC9CD 0x05023F8F

Any 0x876928DDDFCCC9CD()



> 0xE8A169E666CBC541 0xAA39FD6C

Any 0xE8A169E666CBC541()



> 0xC1F6EBF9A3D55538 0xEF9142DB

void 0xC1F6EBF9A3D55538(Any p0, Any p1)



> 0x600048C60D5C2C51 0x0688DE64

void 0x600048C60D5C2C51(Any p0)



> 0x2DF9038C90AD5264 0x909A1D76

void 0x2DF9038C90AD5264(float p0, float p1, float p2, float p3, float p4, int interiorFlags, float scale, int duration)



> 0xB2AFF10216DEFA2F 0x4AAD0ECB

void 0xB2AFF10216DEFA2F(float x, float y, float z, float p3, float p4, float p5, float p6, int interiorFlags, float scale, int duration)



> 0xFEE4A5459472A9F8 0x492C9E46

void 0xFEE4A5459472A9F8()



> 0x3C67506996001F5E 0x814A28F4

Any 0x3C67506996001F5E()



> 0xA586FBEB32A53DBB 0x0B60D2BA

Any 0xA586FBEB32A53DBB()



> 0xF445DE8DA80A1792 0x6B83ABDF

Any 0xF445DE8DA80A1792()



> 0xA635C11B8C44AFC2 0xF46B4DC8

Any 0xA635C11B8C44AFC2()



> 0x280C7E3AC7F56E90 0x36A4AC65

void 0x280C7E3AC7F56E90(Any p0, Any* p1, Any* p2, Any* p3)



> 0xB782F8238512BAD5 0xBA699DDF

void 0xB782F8238512BAD5(Any p0, Any* p1)



> SET_IK_TARGET - 0xC32779C16FCEECD9 0x6FE5218C

void SET_IK_TARGET(Ped ped, int p1, Ped targetPed, int boneLookAt, float x, float y, float z, Any p7, int duration, int duration1)



> 0xED3C76ADFA6D07C4 0xFB4000DC

void 0xED3C76ADFA6D07C4(Any p0)



> REQUEST_ACTION_MODE_ASSET - 0x290E2780BB7AA598 0x572BA553

void REQUEST_ACTION_MODE_ASSET(char* asset)



> HAS_ACTION_MODE_ASSET_LOADED - 0xE4B5F4BF2CB24E65 0xF7EB2BF1

BOOL HAS_ACTION_MODE_ASSET_LOADED(char* asset)



> REMOVE_ACTION_MODE_ASSET - 0x13E940F88470FA51 0x3F480F92

void REMOVE_ACTION_MODE_ASSET(char* asset)



> REQUEST_STEALTH_MODE_ASSET - 0x2A0A62FCDEE16D4F 0x280A004A

void REQUEST_STEALTH_MODE_ASSET(char* asset)



> HAS_STEALTH_MODE_ASSET_LOADED - 0xE977FC5B08AF3441 0x39245667

BOOL HAS_STEALTH_MODE_ASSET_LOADED(char* asset)



> REMOVE_STEALTH_MODE_ASSET - 0x9219857D21F0E842 0x8C0B243A

void REMOVE_STEALTH_MODE_ASSET(char* asset)



> SET_PED_LOD_MULTIPLIER - 0xDC2C5C242AAC342B 0x1D2B5C70

void SET_PED_LOD_MULTIPLIER(Ped ped, float multiplier)



> 0xE861D0B05C7662B8 0x2F9550C2

void 0xE861D0B05C7662B8(Any p0, BOOL p1, Any p2)



> 0x129466ED55140F8D 0x37DBC2AD

void 0x129466ED55140F8D(Ped ped, BOOL toggle)



> 0xCB968B53FC7F916D 0xC0F1BC91

void 0xCB968B53FC7F916D(Any p0, BOOL p1, Any p2, Any p3)



> 0x68772DB2B2526F9F 0x1A464167

BOOL 0x68772DB2B2526F9F(Ped ped, float x, float y, float z, float range)



> 0x06087579E7AA85A9 0xD0567D41

BOOL 0x06087579E7AA85A9(Any p0, Any p1, float p2, float p3, float p4, float p5)



> 0xD8C3BE3EE94CAF2D 0x4BBE5E2C

void 0xD8C3BE3EE94CAF2D(Any p0, Any p1, Any p2, Any p3, Any p4)



> 0xD33DAA36272177C4 0xA89A53F2

void 0xD33DAA36272177C4(Ped ped)



> 0x83A169EABCDB10A2 

void 0x83A169EABCDB10A2(Any p0, Any p1)



> 0x288DF530C92DAD6F 

void 0x288DF530C92DAD6F(Any p0, float p1)



