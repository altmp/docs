# Gameplay

> GET_ALLOCATED_STACK_SIZE - 0x8B3CA62B1EF19B62 0x4E9CA30A

int GET_ALLOCATED_STACK_SIZE()



> _GET_FREE_STACK_SLOTS_COUNT - 0xFEAD16FC8F9DFC0F 0x11A178B8

int _GET_FREE_STACK_SLOTS_COUNT(int stackSize)



> SET_RANDOM_SEED - 0x444D98F98C11F3EC 0xDB3FEB5C

void SET_RANDOM_SEED(int time)



> SET_TIME_SCALE - 0x1D408577D440E81E 0xA7F84694

void SET_TIME_SCALE(float time)

```
Maximum value is 1.
At a value of 0 the game will still run at a minimum time scale.

Slow Motion 1: 0.6
Slow Motion 2: 0.4
Slow Motion 3: 0.2
```

> SET_MISSION_FLAG - 0xC4301E5121A0ED73 0x57592D52

void SET_MISSION_FLAG(BOOL toggle)

```
If true, the player can't save the game. 


MulleDK19: If the parameter is true, sets the mission flag to true, if the parameter is false, the function does nothing at all.

^ also, if the mission flag is already set, the function does nothing at all
```

> GET_MISSION_FLAG - 0xA33CDCCDA663159E 0x95115F97

BOOL GET_MISSION_FLAG()



> SET_RANDOM_EVENT_FLAG - 0x971927086CFD2158 0xA77F31E8

void SET_RANDOM_EVENT_FLAG(BOOL p0)

```
MulleDK19: If the parameter is true, sets the random event flag to true, if the parameter is false, the function does nothing at all.
Does nothing if the mission flag is set.
```

> GET_RANDOM_EVENT_FLAG - 0xD2D57F1D764117B1 0x794CC92C

Any GET_RANDOM_EVENT_FLAG()



> _GET_EMPTY_STRING - 0x24DA7D7667FD7B09 

char* _GET_EMPTY_STRING()

```
Returns a global c-style string buffer that is used internally by the game 

sfink: nope, it returns a reference to an empty string, the same empty string that's used by 1687 internal gta functions.   if it was used in a script (and i cannot find an instance of it being used), it would be as the source for a StringCopy or somesuch.
```

> 0x4DCDF92BF64236CD 

void 0x4DCDF92BF64236CD(Any p0, Any p1)



> 0x31125FD509D9043F 

void 0x31125FD509D9043F(Any p0)



> 0xEBD3205A207939ED 

void 0xEBD3205A207939ED(Any p0)



> 0x97E7E2C04245115B 

void 0x97E7E2C04245115B(Any p0)



> 0xEB078CA2B5E82ADD 

void 0xEB078CA2B5E82ADD(Any p0, Any p1)



> 0x703CC7F60CBB2B57 

void 0x703CC7F60CBB2B57(Any p0)



> 0x8951EB9C6906D3C8 

void 0x8951EB9C6906D3C8()



> 0xBA4B8D83BDC75551 

void 0xBA4B8D83BDC75551(Any p0)



> 0xE8B9C0EC9E183F35 

Any 0xE8B9C0EC9E183F35()



> 0x65D2EBB47E1CEC21 

void 0x65D2EBB47E1CEC21(BOOL p0)



> 0x6F2135B6129620C1 0x8B2DE971

void 0x6F2135B6129620C1(BOOL p0)



> 0x8D74E26F54B4E5C3 0xE77199F7

void 0x8D74E26F54B4E5C3(char* p0)

```
GAMEPLAY::_8D74E26F54B4E5C3('');
```

> 0xB335F761606DB47C 

BOOL 0xB335F761606DB47C(Any* p0, Any* p1, Any p2, BOOL p3)

```
This line found 48 times in the scripts:

GAMEPLAY::_B335F761606DB47C(&amp;v_4, &amp;v_7, a_0, v_A);
```

> _GET_CURRENT_WEATHER_TYPE - 0x564B884A05EC45A3 0xA8171E9E

Hash _GET_CURRENT_WEATHER_TYPE()

```
Returns current weather name hash
```

> _GET_NEXT_WEATHER_TYPE - 0x711327CD09C8F162 0x353E8056

Hash _GET_NEXT_WEATHER_TYPE()

```
Returns weather name hash
```

> IS_PREV_WEATHER_TYPE - 0x44F28F86433B10A9 0x250ADA61

BOOL IS_PREV_WEATHER_TYPE(char* weatherType)



> IS_NEXT_WEATHER_TYPE - 0x2FAA3A30BEC0F25D 0x99CB167F

BOOL IS_NEXT_WEATHER_TYPE(char* weatherType)



> SET_WEATHER_TYPE_PERSIST - 0x704983DF373B198F 0xC6C04C75

void SET_WEATHER_TYPE_PERSIST(char* weatherType)

```
The following weatherTypes are used in the scripts:
'CLEAR'
'EXTRASUNNY'
'CLOUDS'
'OVERCAST'
'RAIN'
'CLEARING'
'THUNDER'
'SMOG'
'FOGGY'
'XMAS'
'SNOWLIGHT'
'BLIZZARD'
```

> SET_WEATHER_TYPE_NOW_PERSIST - 0xED712CA327900C8A 0xC869FE97

void SET_WEATHER_TYPE_NOW_PERSIST(char* weatherType)

```
The following weatherTypes are used in the scripts:
'CLEAR'
'EXTRASUNNY'
'CLOUDS'
'OVERCAST'
'RAIN'
'CLEARING'
'THUNDER'
'SMOG'
'FOGGY'
'XMAS'
'SNOWLIGHT'
'BLIZZARD'
```

> SET_WEATHER_TYPE_NOW - 0x29B487C359E19889 0x361E9EAC

void SET_WEATHER_TYPE_NOW(char* weatherType)

```
The following weatherTypes are used in the scripts:
'CLEAR'
'EXTRASUNNY'
'CLOUDS'
'OVERCAST'
'RAIN'
'CLEARING'
'THUNDER'
'SMOG'
'FOGGY'
'XMAS'
'SNOWLIGHT'
'BLIZZARD'
```

> _SET_WEATHER_TYPE_OVER_TIME - 0xFB5045B7C42B75BF 0x386F0D25

void _SET_WEATHER_TYPE_OVER_TIME(char* weatherType, float time)



> SET_RANDOM_WEATHER_TYPE - 0x8B05F884CF7E8020 0xE7AA1BC9

void SET_RANDOM_WEATHER_TYPE()



> CLEAR_WEATHER_TYPE_PERSIST - 0xCCC39339BEF76CF5 0x6AB757D8

void CLEAR_WEATHER_TYPE_PERSIST()



> _GET_WEATHER_TYPE_TRANSITION - 0xF3BBE884A14BB413 0x9A5C1D56

void _GET_WEATHER_TYPE_TRANSITION(Any* p0, Any* p1, float* progress_or_time)



> _SET_WEATHER_TYPE_TRANSITION - 0x578C752848ECFA0C 0x5CA74040

void _SET_WEATHER_TYPE_TRANSITION(Hash sourceWeather, Hash targetWeather, float transitionTime)

```
PNWParksFan 2017-02-18:

Mixes two weather types. If percentWeather2 is set to 0.0f, then the weather will be entirely of weatherType1, if it is set to 1.0f it will be entirely of weatherType2. If it's set somewhere in between, there will be a mixture of weather behaviors. To test, try this in the RPH console, and change the float to different values between 0 and 1:

execute 'NativeFunction.Natives.x578C752848ECFA0C(Game.GetHashKey(''RAIN''), Game.GetHashKey(''SMOG''), 0.50f);

Note that unlike most of the other weather natives, this native takes the hash of the weather name, not the plain string. These are the weather names and their hashes:

CLEAR	0x36A83D84
EXTRASUNNY	0x97AA0A79
CLOUDS	0x30FDAF5C
OVERCAST	0xBB898D2D
RAIN	0x54A69840
CLEARING	0x6DB1A50D
THUNDER	0xB677829F
SMOG	0x10DCF4B5
FOGGY	0xAE737644
XMAS	0xAAC9C895
SNOWLIGHT	0x23FB812B
BLIZZARD	0x27EA2814





/* OLD INVALID INFO BELOW */
Not tested. Based purely on disassembly. Instantly sets the weather to sourceWeather, then transitions to targetWeather over the specified transitionTime in seconds.

If an invalid hash is specified for sourceWeather, the current weather type will be used.
If an invalid hash is specified for targetWeather, the next weather type will be used.
If an invalid hash is specified for both sourceWeather and targetWeather, the function just changes the transition time of the current transition.
```

> SET_OVERRIDE_WEATHER - 0xA43D5C6FE51ADBEF 0xD9082BB5

void SET_OVERRIDE_WEATHER(char* weatherType)

```
Appears to have an optional bool parameter that is unused in the scripts.

If you pass true, something will be set to zero.
```

> CLEAR_OVERRIDE_WEATHER - 0x338D2E3477711050 0x7740EA4E

void CLEAR_OVERRIDE_WEATHER()



> 0xB8F87EAD7533B176 0x625181DC

void 0xB8F87EAD7533B176(float p0)



> 0xC3EAD29AB273ECE8 0xBEBBFDC8

void 0xC3EAD29AB273ECE8(float p0)



> 0xA7A1127490312C36 0x6926AB03

void 0xA7A1127490312C36(float p0)



> 0x31727907B2C43C55 0xD447439D

void 0x31727907B2C43C55(float p0)



> 0x405591EC8FD9096D 0x584E9C59

void 0x405591EC8FD9096D(float p0)



> 0xF751B16FB32ABC1D 0x5656D578

void 0xF751B16FB32ABC1D(float p0)



> 0xB3E6360DDE733E82 0x0DE40C28

void 0xB3E6360DDE733E82(float p0)



> 0x7C9C0B1EEB1F9072 0x98C9138B

void 0x7C9C0B1EEB1F9072(float p0)



> 0x6216B116083A7CB4 0xFB1A9CDE

void 0x6216B116083A7CB4(float p0)



> 0x9F5E6BB6B34540DA 0x1C0CAE89

void 0x9F5E6BB6B34540DA(float p0)



> 0xB9854DFDE0D833D6 0x4671AC2E

void 0xB9854DFDE0D833D6(float p0)



> 0xC54A08C85AE4D410 0xDA02F415

void 0xC54A08C85AE4D410(float p0)



> 0xA8434F1DFF41D6E7 0x5F3DDEC0

void 0xA8434F1DFF41D6E7(float p0)



> 0xC3C221ADDDE31A11 0x63A89684

void 0xC3C221ADDDE31A11(float p0)



> SET_WIND - 0xAC3A74E8384A9919 0xC6294698

void SET_WIND(float p0)

```
Sets the the raw wind speed value.
```

> SET_WIND_SPEED - 0xEE09ECEDBABE47FC 0x45705F94

void SET_WIND_SPEED(float speed)

```
Using this native will clamp the wind speed value to a range of 0.0- 12.0. Using SET_WIND sets the same value but without the restriction.
```

> GET_WIND_SPEED - 0xA8CF1CC0AFCD3F12 0x098F0F3C

float GET_WIND_SPEED()



> SET_WIND_DIRECTION - 0xEB0F4468467B4528 0x381AEEE9

void SET_WIND_DIRECTION(float direction)



> GET_WIND_DIRECTION - 0x1F400FEF721170DA 0x89499A0D

Vector3 GET_WIND_DIRECTION()



> _SET_RAIN_FX_INTENSITY - 0x643E26EA6E024D92 

void _SET_RAIN_FX_INTENSITY(float intensity)

```
puddles, rain fx on ground/buildings/puddles, rain sound
```

> GET_RAIN_LEVEL - 0x96695E368AD855F3 0xC9F67F28

Any GET_RAIN_LEVEL()



> GET_SNOW_LEVEL - 0xC5868A966E5BE3AE 0x1B09184F

Any GET_SNOW_LEVEL()



> _CREATE_LIGHTNING_THUNDER - 0xF6062E089251C898 0xDF38165E

void _CREATE_LIGHTNING_THUNDER()

```
creates single lightning+thunder at random position
```

> 0x02DEAAC8F8EA7FE7 

void 0x02DEAAC8F8EA7FE7(char* p0)

```
Found in the scripts:

GAMEPLAY::_02DEAAC8F8EA7FE7('');
```

> 0x11B56FBBF7224868 0x8727A4C5

void 0x11B56FBBF7224868(char* p0)

```
Found in the scripts:

GAMEPLAY::_11B56FBBF7224868('CONTRAILS');
```

> _SET_CLOUD_HAT_TRANSITION - 0xFC4842A34657BFCB 0xED88FC61

void _SET_CLOUD_HAT_TRANSITION(char* type, float transitionTime)



> 0xA74802FB8D0B7814 0xC9FA6E07

void 0xA74802FB8D0B7814(char* p0, float p1)

```
Called 4 times in the b617d scripts:
GAMEPLAY::_A74802FB8D0B7814('CONTRAILS', 0);
```

> _CLEAR_CLOUD_HAT - 0x957E790EA1727B64 0x2D7787BC

void _CLEAR_CLOUD_HAT()



> 0xF36199225D6D8C86 

void 0xF36199225D6D8C86(float p0)

```
(MsQ) Sets opacity of skybox clouds overlay 'SET_SKYBOX_CLOUD_OPACITY'
0.0 = Fully transparent
1.0 = Fully opaque

Value can be set below 0.0 (inverts texture) and above 1.0 (overexposure) but will look weird.
```

> 0x20AC25E781AE4A84 

float 0x20AC25E781AE4A84()

```
(MsQ) Gets opacity of skybox clouds overlay 'GET_SKYBOX_CLOUD_OPACITY'
```

> GET_GAME_TIMER - 0x9CD27B0045628463 0xA4EA0691

int GET_GAME_TIMER()



> GET_FRAME_TIME - 0x15C40837039FFAF7 0x96374262

float GET_FRAME_TIME()



> 0xE599A503B3837E1B 

float 0xE599A503B3837E1B()



> GET_FRAME_COUNT - 0xFC8202EFC642E6F2 0xB477A015

int GET_FRAME_COUNT()



> GET_RANDOM_FLOAT_IN_RANGE - 0x313CE5879CEB6FCD 0x0562C4D0

float GET_RANDOM_FLOAT_IN_RANGE(float startRange, float endRange)



> GET_RANDOM_INT_IN_RANGE - 0xD53343AA4FB7DD28 0x4051115B

int GET_RANDOM_INT_IN_RANGE(int startRange, int endRange)

```
Another extremely useful native.

You can use it simply like:
if (GAMEPLAY::GET_RANDOM_INT_IN_RANGE(0, 2))

and the if-statement will count it as false only if the random int is 0. That means there is a one in three chance of it being false. Put a '!' in front and it means there is a one in three chance of it being true.
```

> GET_GROUND_Z_FOR_3D_COORD - 0xC906A7DAB05C8D2B 0xA1BFD5E0

BOOL GET_GROUND_Z_FOR_3D_COORD(float x, float y, float z, float* groundZ, BOOL unk)

```
Gets the ground elevation at the specified position. Note that if the specified position is below ground level, the function will output zero!

x: Position on the X-axis to get ground elevation at.
y: Position on the Y-axis to get ground elevation at.
z: Position on the Z-axis to get ground elevation at.
groundZ: The ground elevation at the specified position.
unk: Nearly always 0, very rarely 1 in the scripts.
```

> 0x8BDC7BFC57A81E76 0x64D91CED

BOOL 0x8BDC7BFC57A81E76(float x, float y, float z, float* p3, Vector3* p4)

```
only documented to be continued...

Vector3 func_164(Vector3 vParam0, Vector3 vParam1)
{
	return vParam0.y * vParam1.z - vParam0.z * vParam1.y, vParam0.z * vParam1.x - vParam0.x * vParam1.z, vParam0.x * vParam1.y - vParam0.y * vParam1.x;
}
float func_67(vector3 vParam0, vector3 vParam1)
{
	return vParam0.x * vParam1.x + vParam0.y * vParam1.y + vParam0.z * vParam1.z;
}
float p3; Vector3 p4;
_0x64D91CED(coords0to.x, coords0to.y, coords0to.z, &amp;p3, &amp;p4);
```

> ASIN - 0xC843060B5765DCE7 0x998E5CAD

float ASIN(float p0)



> ACOS - 0x1D08B970013C34B6 0xF4038776

float ACOS(float p0)



> TAN - 0x632106CC96E82E91 0xD320CE5E

float TAN(float p0)



> ATAN - 0xA9D1795CD5043663 0x7A03CC8E

float ATAN(float p0)



> ATAN2 - 0x8927CBF9D22261A4 0x2508AC81

float ATAN2(float p0, float p1)



> GET_DISTANCE_BETWEEN_COORDS - 0xF1B760881820C952 0xF698765E

float GET_DISTANCE_BETWEEN_COORDS(float x1, float y1, float z1, float x2, float y2, float z2, BOOL useZ)

```
If useZ is false, only the 2D plane (X-Y) will be considered for calculating the distance.

Consider using this faster native instead: SYSTEM::VDIST - DVIST always takes in consideration the 3D coordinates.
```

> GET_ANGLE_BETWEEN_2D_VECTORS - 0x186FC4BE848E1C92 0xDBF75E58

float GET_ANGLE_BETWEEN_2D_VECTORS(float x1, float y1, float x2, float y2)



> GET_HEADING_FROM_VECTOR_2D - 0x2FFB6B224F4B2926 0xD209D52B

float GET_HEADING_FROM_VECTOR_2D(float dx, float dy)

```
dx = x1 - x2
dy = y1 - y2
```

> 0x7F8F6405F4777AF6 0x89459F0A

float 0x7F8F6405F4777AF6(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, BOOL p9)



> 0x21C235BC64831E5A 0xCAECF37E

Vector3 0x21C235BC64831E5A(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, BOOL p9)



> 0xF56DFB7B61BE7276 0xC6CC812C

BOOL 0xF56DFB7B61BE7276(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, Any* p12)



> SET_BIT - 0x933D6A9EEC1BACD0 0x4EFE7E6B

void SET_BIT(int* address, int offset)

```
This sets bit [offset] of [address] to on.

The offsets used are different bits to be toggled on and off, typically there is only one address used in a script.

Example:
GAMEPLAY::SET_BIT(&amp;bitAddress, 1);

To check if this bit has been enabled:
GAMEPLAY::IS_BIT_SET(bitAddress, 1); // will return 1 afterwards

Please note, this method may assign a value to [address] when used.
```

> CLEAR_BIT - 0xE80492A9AC099A93 0x8BC9E618

void CLEAR_BIT(int* address, int offset)

```
This sets bit [offset] of [address] to off.

Example:
GAMEPLAY::CLEAR_BIT(&amp;bitAddress, 1);

To check if this bit has been enabled:
GAMEPLAY::IS_BIT_SET(bitAddress, 1); // will return 0 afterwards
```

> GET_HASH_KEY - 0xD24D37CC275948CC 0x98EFF6F1

Hash GET_HASH_KEY(char* value)

```
This native converts its past string to hash. It is hashed using jenkins one at a time method.
```

> 0xF2F6A2FA49278625 0x87B92190

void 0xF2F6A2FA49278625(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, Any* p9, Any* p10, Any* p11, Any* p12)



> IS_AREA_OCCUPIED - 0xA61B4DF533DCB56E 0xC013972F

BOOL IS_AREA_OCCUPIED(float p0, float p1, float p2, float p3, float p4, float p5, BOOL p6, BOOL p7, BOOL p8, BOOL p9, BOOL p10, Any p11, BOOL p12)



> IS_POSITION_OCCUPIED - 0xADCDE75E1C60F32D 0x452E8D9E

BOOL IS_POSITION_OCCUPIED(float p0, float p1, float p2, float p3, BOOL p4, BOOL p5, BOOL p6, BOOL p7, BOOL p8, Any p9, BOOL p10)



> IS_POINT_OBSCURED_BY_A_MISSION_ENTITY - 0xE54E209C35FFA18D 0xC161558D

BOOL IS_POINT_OBSCURED_BY_A_MISSION_ENTITY(float p0, float p1, float p2, float p3, float p4, float p5, Any p6)



> CLEAR_AREA - 0xA56F01F3765B93A0 0x854E9AB8

void CLEAR_AREA(float X, float Y, float Z, float radius, BOOL p4, BOOL ignoreCopCars, BOOL ignoreObjects, BOOL p7)

```
Example: CLEAR_AREA(0, 0, 0, 30, true, false, false, false);
```

> _CLEAR_AREA_OF_EVERYTHING - 0x957838AAF91BD12D 0x20E4FFD9

void _CLEAR_AREA_OF_EVERYTHING(float x, float y, float z, float radius, BOOL p4, BOOL p5, BOOL p6, BOOL p7)

```
GAMEPLAY::_0x957838AAF91BD12D(x, y, z, radius, false, false, false, false); seem to make all objects go away, peds, vehicles etc. All booleans set to true doesn't seem to change anything. 
```

> CLEAR_AREA_OF_VEHICLES - 0x01C7B9B38428AEB6 0x63320F3C

void CLEAR_AREA_OF_VEHICLES(float x, float y, float z, float radius, BOOL p4, BOOL p5, BOOL p6, BOOL p7, BOOL p8)

```
Example: 		CLEAR_AREA_OF_VEHICLES(0, 0, 0, 10000, false, false, false, false, false);
```

> CLEAR_ANGLED_AREA_OF_VEHICLES - 0x11DB3500F042A8AA 0xF11A3018

void CLEAR_ANGLED_AREA_OF_VEHICLES(float p0, float p1, float p2, float p3, float p4, float p5, float p6, BOOL p7, BOOL p8, BOOL p9, BOOL p10, BOOL p11)



> CLEAR_AREA_OF_OBJECTS - 0xDD9B9B385AAC7F5B 0xBB720FE7

void CLEAR_AREA_OF_OBJECTS(float x, float y, float z, float radius, int flags)

```
I looked through the PC scripts that this site provides you with a link to find. It shows the last param mainly uses, (0, 2, 6, 16, and 17) so I am going to assume it is a type of flag. 
```

> CLEAR_AREA_OF_PEDS - 0xBE31FD6CE464AC59 0x25BE7FA8

void CLEAR_AREA_OF_PEDS(float x, float y, float z, float radius, int flags)

```
Example: 		CLEAR_AREA_OF_PEDS(0, 0, 0, 10000, 1);
```

> CLEAR_AREA_OF_COPS - 0x04F8FC8FCF58F88D 0x95C53824

void CLEAR_AREA_OF_COPS(float x, float y, float z, float radius, int flags)

```
flags appears to always be 0
```

> CLEAR_AREA_OF_PROJECTILES - 0x0A1CB9094635D1A6 0x18DB5434

void CLEAR_AREA_OF_PROJECTILES(float x, float y, float z, float radius, int flags)

```
flags is usually 0 in the scripts.
```

> 0x7EC6F9A478A6A512 

void 0x7EC6F9A478A6A512()



> SET_SAVE_MENU_ACTIVE - 0xC9BF75D28165FF77 0xF5CCF164

void SET_SAVE_MENU_ACTIVE(BOOL unk)

```
The bool is not a toggle!!!
```

> 0x397BAA01068BAA96 0x39771F21

int 0x397BAA01068BAA96()



> SET_CREDITS_ACTIVE - 0xB938B7E6D3C0620C 0xEC2A0ECF

void SET_CREDITS_ACTIVE(BOOL toggle)



> 0xB51B9AB9EF81868C 0x75B06B5A

void 0xB51B9AB9EF81868C(BOOL toggle)



> 0x075F1D57402C93BA 0x2569C9A7

Any 0x075F1D57402C93BA()



> TERMINATE_ALL_SCRIPTS_WITH_THIS_NAME - 0x9DC711BC69C548DF 0x9F861FD4

void TERMINATE_ALL_SCRIPTS_WITH_THIS_NAME(char* scriptName)

```
For a full list, see here: pastebin.com/yLNWicUi
```

> NETWORK_SET_SCRIPT_IS_SAFE_FOR_NETWORK_GAME - 0x9243BAC96D64C050 0x878486CE

void NETWORK_SET_SCRIPT_IS_SAFE_FOR_NETWORK_GAME()



> ADD_HOSPITAL_RESTART - 0x1F464EF988465A81 0x4F3E3104

int ADD_HOSPITAL_RESTART(float x, float y, float z, float p3, Any p4)

```
Returns the index of the newly created hospital spawn point.

p3 might be radius?

- mlgthatsme
```

> DISABLE_HOSPITAL_RESTART - 0xC8535819C450EBA8 0x09F49C72

void DISABLE_HOSPITAL_RESTART(int hospitalIndex, BOOL toggle)

```
The game by default has 5 hospital respawn points. Disabling them all will cause the player to respawn at the last position they were.

- mlgthatsme

---------------------

Doesn't work....
```

> ADD_POLICE_RESTART - 0x452736765B31FC4B 0xE96C29FE

Any ADD_POLICE_RESTART(float p0, float p1, float p2, float p3, Any p4)



> DISABLE_POLICE_RESTART - 0x23285DED6EBD7EA3 0x0A280324

void DISABLE_POLICE_RESTART(int policeIndex, BOOL toggle)

```
Disables the spawn point at the police house on the specified index.

policeIndex: The police house index.
toggle: true to enable the spawn point, false to disable.

- Nacorpio
```

> 0x706B5EDCAA7FA663 

void 0x706B5EDCAA7FA663(float x, float y, float z, float heading)

```
Specifies a custom respawn position to be used in conjunction with _SET_NEXT_RESPAWN_TO_CUSTOM
```

> 0xA2716D40842EAF79 

void 0xA2716D40842EAF79()

```
Sets the next spawn location to the position supplied to _SET_CUSTOM_RESPAWN_POSITION. 
```

> _DISABLE_AUTOMATIC_RESPAWN - 0x2C2B3493FBF51C71 0x296574AE

void _DISABLE_AUTOMATIC_RESPAWN(BOOL disableRespawn)



> IGNORE_NEXT_RESTART - 0x21FFB63D8C615361 0xDA13A4B6

void IGNORE_NEXT_RESTART(BOOL toggle)



> SET_FADE_OUT_AFTER_DEATH - 0x4A18E01DF2C87B86 0xC9F6F0BC

void SET_FADE_OUT_AFTER_DEATH(BOOL toggle)

```
Sets whether the game should fade out after the player dies.
```

> SET_FADE_OUT_AFTER_ARREST - 0x1E0B4DC0D990A4E7 0xCB074B9D

void SET_FADE_OUT_AFTER_ARREST(BOOL toggle)

```
Sets whether the game should fade out after the player is arrested.
```

> SET_FADE_IN_AFTER_DEATH_ARREST - 0xDA66D2796BA33F12 0xACDE6985

void SET_FADE_IN_AFTER_DEATH_ARREST(BOOL toggle)

```
Sets whether the game should fade in after the player dies or is arrested.
```

> SET_FADE_IN_AFTER_LOAD - 0xF3D78F59DFE18D79 0x6E00EB0B

void SET_FADE_IN_AFTER_LOAD(BOOL toggle)



> REGISTER_SAVE_HOUSE - 0xC0714D0A7EEECA54 0x39C1849A

Any REGISTER_SAVE_HOUSE(float p0, float p1, float p2, float p3, Any* p4, Any p5, Any p6)



> SET_SAVE_HOUSE - 0x4F548CABEAE553BC 0xC3240BB4

void SET_SAVE_HOUSE(Any p0, BOOL p1, BOOL p2)

```
Both p1 &amp; p2 were always true in scripts. - Kryptus
 --&gt; I don't think this is correct.

Both p1 &amp; p2 were always true in scripts. - Kryptus
```

> OVERRIDE_SAVE_HOUSE - 0x1162EA8AE9D24EEA 0x47436C12

BOOL OVERRIDE_SAVE_HOUSE(BOOL p0, float p1, float p2, float p3, float p4, BOOL p5, float p6, float p7)



> 0xA4A0065E39C9F25C 0xC4D71AB4

Any 0xA4A0065E39C9F25C(Any p0, Any p1, Any p2, Any p3)



> DO_AUTO_SAVE - 0x50EEAAD86232EE55 0x54C44B1A

void DO_AUTO_SAVE()



> 0x6E04F06094C87047 0xA8546914

Any 0x6E04F06094C87047()



> IS_AUTO_SAVE_IN_PROGRESS - 0x69240733738C19A0 0x36F75399

BOOL IS_AUTO_SAVE_IN_PROGRESS()



> 0x2107A3773771186D 0x78350773

Any 0x2107A3773771186D()



> 0x06462A961E94B67C 0x5A45B11A

void 0x06462A961E94B67C()



> BEGIN_REPLAY_STATS - 0xE0E500246FF73D66 0x17F4F44D

void BEGIN_REPLAY_STATS(Any p0, Any p1)



> 0x69FE6DC87BD2A5E9 0x81216EE0

void 0x69FE6DC87BD2A5E9(Any p0)



> END_REPLAY_STATS - 0xA23E821FBDF8A5F2 0xCB570185

void END_REPLAY_STATS()



> 0xD642319C54AADEB6 0xC58250F1

Any 0xD642319C54AADEB6()



> 0x5B1F2E327B6B6FE1 0x50C39926

Any 0x5B1F2E327B6B6FE1()



> 0x2B626A0150E4D449 0x710E5D1E

Any 0x2B626A0150E4D449()



> 0xDC9274A7EF6B2867 0xC7BD1AF0

Any 0xDC9274A7EF6B2867()



> 0x8098C8D6597AAE18 0x22BE2423

Any 0x8098C8D6597AAE18(Any p0)



> CLEAR_REPLAY_STATS - 0x1B1AB132A16FDA55 0xC47DFF02

void CLEAR_REPLAY_STATS()



> 0x72DE52178C291CB5 0xF62B3C48

Any 0x72DE52178C291CB5()



> 0x44A0BDC559B35F6E 0x3589452B

Any 0x44A0BDC559B35F6E()



> 0xEB2104E905C6F2E9 

Any 0xEB2104E905C6F2E9()



> 0x2B5E102E4A42F2BF 0x144AAF22

Any 0x2B5E102E4A42F2BF()



> IS_MEMORY_CARD_IN_USE - 0x8A75CE2956274ADD 0x40CE4DFD

BOOL IS_MEMORY_CARD_IN_USE()



> SHOOT_SINGLE_BULLET_BETWEEN_COORDS - 0x867654CBC7606F2C 0xCB7415AC

void SHOOT_SINGLE_BULLET_BETWEEN_COORDS(float x1, float y1, float z1, float x2, float y2, float z2, int damage, BOOL p7, Hash weaponHash, Ped ownerPed, BOOL isAudible, BOOL isInvisible, float speed)



> 0xE3A7742E0B7A2F8B 0x52ACCB7B

void 0xE3A7742E0B7A2F8B(float x1, float y1, float z1, float x2, float y2, float z2, int damage, BOOL p7, Hash weaponHash, Ped ownerPed, BOOL isAudible, BOOL isInvisible, float speed, Entity entity)

```
only documented to be continued...
```

> 0xBFE5756E7407064A 

void 0xBFE5756E7407064A(float x1, float y1, float z1, float x2, float y2, float z2, int damage, BOOL p7, Hash weaponHash, Ped ownerPed, BOOL isAudible, BOOL isInvisible, float speed, Entity entity, BOOL p14, BOOL p15, BOOL p16, BOOL p17)

```
Since latest patches has 18 parameters.

Console Hash: 0xCCDC33CC

only documented to be continued...
```

> GET_MODEL_DIMENSIONS - 0x03E8D3D5F549087A 0x91ABB8E0

void GET_MODEL_DIMENSIONS(Hash modelHash, Vector3* minimum, Vector3* maximum)

```
Gets the dimensions of a model.

Calculate (maximum - minimum) to get the size, in which case, Y will be how long the model is.

Example from the scripts: GAMEPLAY::GET_MODEL_DIMENSIONS(ENTITY::GET_ENTITY_MODEL(PLAYER::PLAYER_PED_ID()), &amp;v_1A, &amp;v_17);
```

> SET_FAKE_WANTED_LEVEL - 0x1454F2448DE30163 0x85B1C9FA

void SET_FAKE_WANTED_LEVEL(int fakeWantedLevel)

```
Sets a visually fake wanted level on the user interface. Used by Rockstar's scripts to 'override' regular wanted levels and make custom ones while the real wanted level and multipliers are ignored.

Max is 5, anything above this makes it just 5. Also the mini-map gets the red &amp; blue flashing effect. I wish I could use this to fake I had 6 stars like a few of the old GTAs'
```

> GET_FAKE_WANTED_LEVEL - 0x4C9296CBCD1B971E 0x0022A430

int GET_FAKE_WANTED_LEVEL()



> IS_BIT_SET - 0xA921AA820C25702F 0x902E26AC

BOOL IS_BIT_SET(int address, int offset)

```
Returns bit's boolean state from [offset] of [address].

Example:
GAMEPLAY::IS_BIT_SET(bitAddress, 1);

To enable and disable bits, see:
GAMEPLAY::SET_BIT(&amp;bitAddress, 1);   // enable
GAMEPLAY::CLEAR_BIT(&amp;bitAddress, 1); // disable
```

> USING_MISSION_CREATOR - 0xF14878FC50BEC6EE 0x20AB0B6B

void USING_MISSION_CREATOR(BOOL toggle)

```
Hash collision
```

> 0xDEA36202FC3382DF 0x082BA6F2

void 0xDEA36202FC3382DF(BOOL p0)



> SET_MINIGAME_IN_PROGRESS - 0x19E00D7322C6F85B 0x348B9046

void SET_MINIGAME_IN_PROGRESS(BOOL toggle)



> IS_MINIGAME_IN_PROGRESS - 0x2B4A15E44DE0F478 0x53A95E13

BOOL IS_MINIGAME_IN_PROGRESS()



> IS_THIS_A_MINIGAME_SCRIPT - 0x7B30F65D7B710098 0x7605EF6F

BOOL IS_THIS_A_MINIGAME_SCRIPT()



> IS_SNIPER_INVERTED - 0x61A23B7EDA9BDA24 0x5C3BF51B

BOOL IS_SNIPER_INVERTED()

```
MulleDK19: This function is hard-coded to always return 0.
```

> 0xD3D15555431AB793 0xBAF17315

Any 0xD3D15555431AB793()



> GET_PROFILE_SETTING - 0xC488FF2356EA7791 0xD374BEBC

int GET_PROFILE_SETTING(int profileSetting)

```
anyone have a settingid dump?
```

> ARE_STRINGS_EQUAL - 0x0C515FAB3FF9EA92 0x877C0BC5

BOOL ARE_STRINGS_EQUAL(char* string1, char* string2)

```
is this like strcmp??
```

> COMPARE_STRINGS - 0x1E34710ECD4AB0EB 0xFE25A58F

int COMPARE_STRINGS(char* str1, char* str2, BOOL matchCase, int maxLength)

```
Compares two strings up to a specified number of characters.

Parameters:
str1 - String to be compared.
str2 - String to be compared.
matchCase - Comparison will be case-sensitive.
maxLength - Maximum number of characters to compare. A value of -1 indicates an infinite length.

Returns:
A value indicating the relationship between the strings:
&lt;0 - The first non-matching character in 'str1' is less than the one in 'str2'. (e.g. 'A' &lt; 'B', so result = -1)
0 - The contents of both strings are equal.
&gt;0 - The first non-matching character in 'str1' is less than the one in 'str2'. (e.g. 'B' &gt; 'A', so result = 1)

Examples:
GAMEPLAY::COMPARE_STRINGS('STRING', 'string', false, -1); // 0; equal
GAMEPLAY::COMPARE_STRINGS('TESTING', 'test', false, 4); // 0; equal
GAMEPLAY::COMPARE_STRINGS('R2D2', 'R2xx', false, 2); // 0; equal
GAMEPLAY::COMPARE_STRINGS('foo', 'bar', false, -1); // 4; 'f' &gt; 'b'
GAMEPLAY::COMPARE_STRINGS('A', 'A', true, 1); // 0; equal

When comparing case-sensitive strings, lower-case characters are greater than upper-case characters:
GAMEPLAY::COMPARE_STRINGS('A', 'a', true, 1); // -1; 'A' &lt; 'a'
GAMEPLAY::COMPARE_STRINGS('a', 'A', true, 1); // 1; 'a' &gt; 'A'
```

> ABSI - 0xF0D31AD191A74F87 0xB44677C5

int ABSI(int value)



> ABSF - 0x73D57CFFDD12C355 0xAF6F6E0B

float ABSF(float value)



> IS_SNIPER_BULLET_IN_AREA - 0xFEFCF11B01287125 0x0483715C

BOOL IS_SNIPER_BULLET_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2)

```
Determines whether there is a sniper bullet within the specified coordinates. The coordinates form a rectangle.

- Nacorpio
```

> IS_PROJECTILE_IN_AREA - 0x5270A8FBC098C3F8 0x78E1A557

BOOL IS_PROJECTILE_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, BOOL ownedByPlayer)

```
Determines whether there is a projectile within the specified coordinates. The coordinates form a rectangle.

- Nacorpio


ownedByPlayer = only projectiles fired by the player will be detected.
```

> IS_PROJECTILE_TYPE_IN_AREA - 0x2E0DC353342C4A6D 0x2B73BCF6

BOOL IS_PROJECTILE_TYPE_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, int type, BOOL p7)

```
Determines whether there is a projectile of a specific type within the specified coordinates. The coordinates form a rectangle.

Note: This native hasn't been tested yet.

- Nacorpio
```

> IS_PROJECTILE_TYPE_IN_ANGLED_AREA - 0xF0BC12401061DEA0 0xD1AE2681

BOOL IS_PROJECTILE_TYPE_IN_ANGLED_AREA(float p0, float p1, float p2, float p3, float p4, float p5, float p6, Any p7, BOOL p8)



> 0x34318593248C8FB2 0xBE81F1E2

BOOL 0x34318593248C8FB2(float p0, float p1, float p2, Any p3, float p4, BOOL p5)



> 0x8D7A43EC6A5FEA45 0x1A40454B

Any 0x8D7A43EC6A5FEA45(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8)



> 0xDFB4138EEFED7B81 0x6BDE5CE4

Any 0xDFB4138EEFED7B81(Any p0, Any p1, Any p2, Any p3, Any p4)

```
From a quick disassembly I can say that this has something to do with weapons.

Added params according to what I could see in IDA.
```

> 0x82FDE6A57EE4EE44 0x507BC6F7

Any 0x82FDE6A57EE4EE44(Ped ped, Hash weaponhash, float p2, float p3, float p4, float p5)

```
only documented to be continued...
```

> IS_BULLET_IN_ANGLED_AREA - 0x1A8B5F3C01E2B477 0xE2DB58F7

BOOL IS_BULLET_IN_ANGLED_AREA(float p0, float p1, float p2, float p3, float p4, float p5, float p6, BOOL p7)



> IS_BULLET_IN_AREA - 0x3F2023999AD51C1F 0xB54F46CA

BOOL IS_BULLET_IN_AREA(float p0, float p1, float p2, float p3, BOOL p4)



> IS_BULLET_IN_BOX - 0xDE0F6D7450D37351 0xAB73ED26

BOOL IS_BULLET_IN_BOX(float p0, float p1, float p2, float p3, float p4, float p5, BOOL p6)



> HAS_BULLET_IMPACTED_IN_AREA - 0x9870ACFB89A90995 0x902BC7D9

BOOL HAS_BULLET_IMPACTED_IN_AREA(float p0, float p1, float p2, float p3, BOOL p4, BOOL p5)

```
p3 - possibly radius?
```

> HAS_BULLET_IMPACTED_IN_BOX - 0xDC8C5D7CFEAB8394 0x2C2618CC

BOOL HAS_BULLET_IMPACTED_IN_BOX(float p0, float p1, float p2, float p3, float p4, float p5, BOOL p6, BOOL p7)



> IS_ORBIS_VERSION - 0xA72BC0B675B1519E 0x40282018

BOOL IS_ORBIS_VERSION()

```
PS4

MulleDK19: This function is hard-coded to always return 0.

Force67: I patched return result and got this : i.imgur.com/hUn7zSj.jpg

translate please?
```

> IS_DURANGO_VERSION - 0x4D982ADB1978442D 0x46FB06A5

BOOL IS_DURANGO_VERSION()

```
XBOX ONE

MulleDK19: This function is hard-coded to always return 0.
```

> IS_XBOX360_VERSION - 0xF6201B4DAF662A9D 0x24005CC8

BOOL IS_XBOX360_VERSION()

```
XBOX 360

MulleDK19: This function is hard-coded to always return 0.
```

> IS_PS3_VERSION - 0xCCA1072C29D096C2 0x4C0D5303

BOOL IS_PS3_VERSION()

```
PS3

MulleDK19: This function is hard-coded to always return 0.
```

> IS_PC_VERSION - 0x48AF36444B965238 0x4D5D9EE3

BOOL IS_PC_VERSION()

```
PC

MulleDK19: This function is hard-coded to always return 1.
```

> IS_AUSSIE_VERSION - 0x9F1935CA1F724008 0x944BA1DC

BOOL IS_AUSSIE_VERSION()

```
if (GAMEPLAY::IS_AUSSIE_VERSION()) {
    sub_127a9(&amp;l_31, 1024); // l_31 |= 1024
    l_129 = 3;
    sub_129d2('AUSSIE VERSION IS TRUE!?!?!'); // DEBUG
}

Used to block some of the prostitute stuff due to laws in Australia.
```

> IS_STRING_NULL - 0xF22B6C47C6EAB066 0x8E71E00F

BOOL IS_STRING_NULL(char* string)



> IS_STRING_NULL_OR_EMPTY - 0xCA042B6957743895 0x42E9F2CA

BOOL IS_STRING_NULL_OR_EMPTY(char* string)



> STRING_TO_INT - 0x5A5F40FE637EB584 0x590A8160

BOOL STRING_TO_INT(char* string, int* outInteger)

```
Basically the same as std::stoi.
```

> SET_BITS_IN_RANGE - 0x8EF07E15701D61ED 0x32094719

void SET_BITS_IN_RANGE(int* var, int rangeStart, int rangeEnd, int p3)



> GET_BITS_IN_RANGE - 0x53158863FCC0893A 0xCA03A1E5

int GET_BITS_IN_RANGE(int var, int rangeStart, int rangeEnd)



> ADD_STUNT_JUMP - 0x1A992DA297A4630C 0xB630E5FF

int ADD_STUNT_JUMP(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, float p12, float p13, float p14, Any p15, Any p16)



> ADD_STUNT_JUMP_ANGLED - 0xBBE5D803A5360CBF 0xB9B7E777

int ADD_STUNT_JUMP_ANGLED(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, float p12, float p13, float p14, float p15, float p16, Any p17, Any p18)



> DELETE_STUNT_JUMP - 0xDC518000E39DAE1F 0x840CB5DA

void DELETE_STUNT_JUMP(int p0)



> ENABLE_STUNT_JUMP_SET - 0xE369A5783B866016 0x9D1E7785

void ENABLE_STUNT_JUMP_SET(int p0)



> DISABLE_STUNT_JUMP_SET - 0xA5272EBEDD4747F6 0x644C9FA4

void DISABLE_STUNT_JUMP_SET(int p0)



> 0xD79185689F8FD5DF 0x3C806A2D

void 0xD79185689F8FD5DF(BOOL p0)



> IS_STUNT_JUMP_IN_PROGRESS - 0x7A3F19700A4D0525 0xF477D0B1

BOOL IS_STUNT_JUMP_IN_PROGRESS()



> 0x2272B0A1343129F4 0x021636EE

BOOL 0x2272B0A1343129F4()



> 0x996DD1E1E02F1008 0x006F9BA2

Any 0x996DD1E1E02F1008()



> 0x6856EC3D35C81EA4 

Any 0x6856EC3D35C81EA4()



> CANCEL_STUNT_JUMP - 0xE6B7B0ACD4E4B75E 0xF43D9821

void CANCEL_STUNT_JUMP()



> SET_GAME_PAUSED - 0x577D1284D6873711 0x8230FF6C

void SET_GAME_PAUSED(BOOL toggle)

```
Make sure to call this from the correct thread if you're using multiple threads because all other threads except the one which is calling SET_GAME_PAUSED will be paused which means you will lose control and the game remains in paused mode until you exit GTA5.exe
```

> SET_THIS_SCRIPT_CAN_BE_PAUSED - 0xAA391C728106F7AF 0xA0C3CE29

void SET_THIS_SCRIPT_CAN_BE_PAUSED(BOOL toggle)



> SET_THIS_SCRIPT_CAN_REMOVE_BLIPS_CREATED_BY_ANY_SCRIPT - 0xB98236CAAECEF897 0xD06F1720

void SET_THIS_SCRIPT_CAN_REMOVE_BLIPS_CREATED_BY_ANY_SCRIPT(BOOL toggle)



> _HAS_BUTTON_COMBINATION_JUST_BEEN_ENTERED - 0x071E2A839DE82D90 0xFF6191E1

BOOL _HAS_BUTTON_COMBINATION_JUST_BEEN_ENTERED(Hash hash, int amount)

```
This native appears on the cheat_controller script and tracks a combination of buttons, which may be used to toggle cheats in-game. Credits to ThreeSocks for the info. The hash contains the combination, while the 'amount' represents the amount of buttons used in a combination. The following page can be used to make a button combination: gta5offset.com/ts/hash/

INT_SCORES_SCORTED was a hash collision
```

> _HAS_CHEAT_STRING_JUST_BEEN_ENTERED - 0x557E43C447E700A8 

BOOL _HAS_CHEAT_STRING_JUST_BEEN_ENTERED(Hash hash)

```
Get inputted 'Cheat code', for example:

while (TRUE)
{
    if (GAMEPLAY::_557E43C447E700A8(${fugitive}))
    {
       // Do something.
    }
    SYSTEM::WAIT(0);
}

Calling this will also set the last saved string hash to zero.

```

> _ENABLE_MP_DLC_MAPS - 0x9BAE5AD2508DF078 0x721B2492

void _ENABLE_MP_DLC_MAPS(BOOL toggle)

```
Formerly known as _LOWER_MAP_PROP_DENSITY and wrongly due to idiots as _ENABLE_MP_DLC_MAPS.
Sets the maximum prop density and changes a loading screen flag from 'loading story mode' to 'loading GTA Online'. Does not touch DLC map data at all.

In fact, I doubt this changes the flag whatsoever, that's the OTHER native idiots use together with this that does so, this one only causes a loading screen to show as it reloads map data.
```

> _SET_UNK_MAP_FLAG - 0xC5F0A8EBD3F361CE 0xE202879D

void _SET_UNK_MAP_FLAG(int flag)

```
Sets an unknown flag used by CScene in determining which entities from CMapData scene nodes to draw, similar to 9BAE5AD2508DF078.

Documented by NTAuthority (http://fivem.net/).
```

> IS_FRONTEND_FADING - 0x7EA2B6AF97ECA6ED 0x8FF6232C

BOOL IS_FRONTEND_FADING()

```
MulleDK19: This function is hard-coded to always return 0.
```

> POPULATE_NOW - 0x7472BB270D7B4F3E 0x72C20700

void POPULATE_NOW()

```
spawns a few distant/out-of-sight peds, vehicles, animals etc each time it is called
```

> GET_INDEX_OF_CURRENT_LEVEL - 0xCBAD6729F7B1F4FC 0x6F203C6E

int GET_INDEX_OF_CURRENT_LEVEL()



> SET_GRAVITY_LEVEL - 0x740E14FAD5842351 0x2D833F4A

void SET_GRAVITY_LEVEL(int level)

```
level can be from 0 to 3
0: 9.8 - normal
1: 2.4 - low
2: 0.1 - very low
3: 0.0 - off

//SuckMyCoke
```

> START_SAVE_DATA - 0xA9575F812C6A7997 0x881A694D

void START_SAVE_DATA(Any* p0, Any p1, BOOL p2)



> STOP_SAVE_DATA - 0x74E20C9145FB66FD 0x3B1C07C8

void STOP_SAVE_DATA()



> 0xA09F896CE912481F 0x9EF0BC64

Any 0xA09F896CE912481F(BOOL p0)



> REGISTER_INT_TO_SAVE - 0x34C9EE5986258415 0xB930956F

void REGISTER_INT_TO_SAVE(Any* p0, char* name)



> 0xA735353C77334EA0 

void 0xA735353C77334EA0(Any* p0, Any* p1)



> REGISTER_ENUM_TO_SAVE - 0x10C2FA78D0E128A1 0x9B38374A

void REGISTER_ENUM_TO_SAVE(Any* p0, char* name)



> REGISTER_FLOAT_TO_SAVE - 0x7CAEC29ECB5DFEBB 0xDB06F7AD

void REGISTER_FLOAT_TO_SAVE(Any* p0, char* name)



> REGISTER_BOOL_TO_SAVE - 0xC8F4131414C835A1 0x5417E0E0

void REGISTER_BOOL_TO_SAVE(Any* p0, char* name)



> REGISTER_TEXT_LABEL_TO_SAVE - 0xEDB1232C5BEAE62F 0x284352C4

void REGISTER_TEXT_LABEL_TO_SAVE(Any* p0, char* name)



> 0x6F7794F28C6B2535 0xE2089749

void 0x6F7794F28C6B2535(Any* p0, char* name)

```
Seems to have the same functionality as REGISTER_TEXT_LABEL_TO_SAVE?

GAMEPLAY::_6F7794F28C6B2535(&amp;a_0._f1, 'tlPlateText');
GAMEPLAY::_6F7794F28C6B2535(&amp;a_0._f1C, 'tlPlateText_pending');
GAMEPLAY::_6F7794F28C6B2535(&amp;a_0._f10B, 'tlCarAppPlateText');

'tl' prefix sounds like 'Text Label'. ~Fireboyd78
```

> 0x48F069265A0E4BEC 0xF91B8C33

void 0x48F069265A0E4BEC(Any* p0, char* name)

```
Only found 3 times in decompiled scripts. Not a whole lot to go off of.

GAMEPLAY::_48F069265A0E4BEC(a_0, 'Movie_Name_For_This_Player');
GAMEPLAY::_48F069265A0E4BEC(&amp;a_0._fB, 'Ringtone_For_This_Player');
GAMEPLAY::_48F069265A0E4BEC(&amp;a_0._f1EC4._f12[v_A/*6*/], &amp;v_13); // where v_13 is 'MPATMLOGSCRS0' thru 'MPATMLOGSCRS15'
```

> 0x8269816F6CFD40F8 0x74E8FAD9

void 0x8269816F6CFD40F8(Any* p0, char* name)

```
Only found 2 times in decompiled scripts. Not a whole lot to go off of.

GAMEPLAY::_8269816F6CFD40F8(&amp;a_0._f1F5A._f6[0/*8*/], 'TEMPSTAT_LABEL'); // gets saved in a struct called 'g_SaveData_STRING_ScriptSaves'
GAMEPLAY::_8269816F6CFD40F8(&amp;a_0._f4B4[v_1A/*8*/], &amp;v_5); // where v_5 is 'Name0' thru 'Name9', gets saved in a struct called 'OUTFIT_Name'
```

> 0xFAA457EF263E8763 0x6B4335DD

void 0xFAA457EF263E8763(Any* p0, char* name)

```
Another unknown label type...

GAMEPLAY::_FAA457EF263E8763(a_0, 'Thumb_label');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f10, 'Photo_label');
GAMEPLAY::_FAA457EF263E8763(a_0, 'GXTlabel');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f21, 'StringComp');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f43, 'SecondStringComp');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f53, 'ThirdStringComp');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f32, 'SenderStringComp');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f726[v_1A/*16*/], &amp;v_20); // where v_20 is 'LastJobTL_0_1' thru 'LastJobTL_2_1', gets saved in a struct called 'LAST_JobGamer_TL'
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f4B, 'PAID_PLAYER');
GAMEPLAY::_FAA457EF263E8763(&amp;a_0._f5B, 'RADIO_STATION');
```

> _START_SAVE_STRUCT - 0xBF737600CDDBEADD 0xFB45728E

void _START_SAVE_STRUCT(Any* p0, int p1, char* structName)

```
Second parameter might be length.
```

> STOP_SAVE_STRUCT - 0xEB1774DF12BB9F12 0xC2624A28

void STOP_SAVE_STRUCT()



> _START_SAVE_ARRAY - 0x60FE567DF1B1AF9D 0x893A342C

void _START_SAVE_ARRAY(Any* p0, int p1, char* arrayName)

```
Second parameter might be length.
```

> STOP_SAVE_ARRAY - 0x04456F95153C6BE4 0x0CAD8217

void STOP_SAVE_ARRAY()



> ENABLE_DISPATCH_SERVICE - 0xDC0F817884CDD856 0x0B710A51

void ENABLE_DISPATCH_SERVICE(int dispatchType, BOOL toggle)

```
dispatchType:
Police Automobile = 1
Police Helicopter = 2
Swat Helicopter = 3
Fire Department = 4
Swat Automobile = 5
Ambulance Department = 6
Gangs = 7
Police Riders = 8
Police Vehicle Request = 9
Police Road Block = 10
Police Boat = 11
Army Vehicle = 12

By making toggle false it disables the dispatch (for 7, it will disable gangs.)

curious if this is what they used when you toggled on and off cops in a GTA IV freemode you hosted. Sad they got rid of the option to make a private session without cops.
Also on x360 seems with or without neverWanted on, setting these to all false in SP of course doesn't seem to work. I would understand getting stars, but cops are still dispatched and combat you.
```

> 0x9B2BD3773123EA2F 0xE0F0684F

void 0x9B2BD3773123EA2F(Any p0, Any p1)



> 0xEB4A0C2D56441717 0x3CE5BF6B

int 0xEB4A0C2D56441717(int p0)



> CREATE_INCIDENT - 0x3F892CAF67444AE7 0xFC5FF7B3

BOOL CREATE_INCIDENT(int p0, float p2, float p3, float p4, int p5, float p6, int* outIncident)

```
p0 could be type

=====================================================
enum IncidentTypes{
    FireDepartment = 3,
    Paramedics = 5,
    Police = 7,
    PedsInCavalcades = 11, 
    Merryweather = 14
};

As for the 'police' incident, it will call police cars to you, but unlike PedsInCavalcades &amp; Merryweather they won't start shooting at you unless you shoot first or shoot at them. The top 2 however seem to cancel theirselves if there is noone dead around you or a fire. I only figured them out as I found out the 3rd param is definately the amountOfPeople and they called incident 3 in scripts with 4 people (which the firetruck has) and incident 5 with 2 people (which the ambulence has). The 4 param I cant say is radius, but for the pedsInCavalcades and Merryweather R* uses 0.0f and for the top 3 (Emergency Services) they use 3.0f. 

Side Note: It seems calling the pedsInCavalcades or Merryweather then removing it seems to break you from calling the EmergencyEvents and I also believe pedsInCavalcades. (The V cavalcades of course not IV).

Side Note 2: I say it breaks as if you call this proper,
if(CREATE_INCIDENT) etc it will return false if you do as I said above.
=====================================================
```

> CREATE_INCIDENT_WITH_ENTITY - 0x05983472F0494E60 0xBBC35B03

BOOL CREATE_INCIDENT_WITH_ENTITY(int p0, Entity p1, int p2, float p3, int* outIncident)

```
p0 could be type (valueused in scripts: 14, 7, 5, 3, 11)
p1 is a return from get_player_ped() in am_gang_call.c, but player_ped_id() in other (non am) scripts.
p3 is usually 0f or 3f

=====================================================
enum IncidentTypes{
    FireDepartment = 3,
    Paramedics = 5,
    Police = 7,
    PedsInCavalcades = 11, 
    Merryweather = 14
};

As for the 'police' incident, it will call police cars to you, but unlike PedsInCavalcades &amp; Merryweather they won't start shooting at you unless you shoot first or shoot at them. The top 2 however seem to cancel theirselves if there is noone dead around you or a fire. I only figured them out as I found out the 3rd param is definately the amountOfPeople and they called incident 3 in scripts with 4 people (which the firetruck has) and incident 5 with 2 people (which the ambulence has). The 4 param I cant say is radius, but for the pedsInCavalcades and Merryweather R* uses 0.0f and for the top 3 (Emergency Services) they use 3.0f. 

Side Note: It seems calling the pedsInCavalcades or Merryweather then removing it seems to break you from calling the EmergencyEvents and I also believe pedsInCavalcades. (The V cavalcades of course not IV).

Side Note 2: I say it breaks as if you call this proper,
if(CREATE_INCIDENT) etc it will return false if you do as I said above.
=====================================================
```

> DELETE_INCIDENT - 0x556C1AA270D5A207 0x212BD0DC

void DELETE_INCIDENT(int* incidentId)

```
Delete an incident with a given id.

=======================================================
Correction, I have change this to int, instead of int*
as it doesn't use a pointer to the createdIncident.
If you try it you will crash (or) freeze.
=======================================================
```

> IS_INCIDENT_VALID - 0xC8BC6461E629BEAA 0x31FD0BA4

BOOL IS_INCIDENT_VALID(int* incidentId)

```
=======================================================
Correction, I have change this to int, instead of int*
as it doesn't use a pointer to the createdIncident.
If you try it you will crash (or) freeze.
=======================================================
```

> 0xB08B85D860E7BA3C 0x0242D88E

void 0xB08B85D860E7BA3C(Any p0, Any p1, Any p2)



> 0xD261BA3E7E998072 0x1F38102E

void 0xD261BA3E7E998072(Any p0, float p1)



> FIND_SPAWN_POINT_IN_DIRECTION - 0x6874E2190B0C1972 0x71AEFD77

BOOL FIND_SPAWN_POINT_IN_DIRECTION(float x1, float y1, float z1, float x2, float y2, float z2, float distance, Vector3* spawnPoint)

```
Finds a position ahead of the player by predicting the players next actions.
The positions match path finding node positions.
When roads diverge, the position may rapidly change between two or more positions. This is due to the engine not being certain of which path the player will take.

=======================================================
I may sort this with alter research, but if someone
already knows please tell what the difference in 
X2, Y2, Z2 is. I doubt it's rotation. Is it like 
checkpoints where X1, Y1, Z1 is your/a position and
X2, Y2, Z2 is a given position ahead of that position?
=======================================================
```

> 0x67F6413D3220E18D 0x42BF09B3

Any 0x67F6413D3220E18D(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8)



> 0x1327E2FE9746BAEE 

BOOL 0x1327E2FE9746BAEE(Any p0)



> 0xB129E447A2EDA4BF 0xFBDBE374

void 0xB129E447A2EDA4BF(Any p0, BOOL p1)



> 0x32C7A7E8C43A1F80 

Any 0x32C7A7E8C43A1F80(float p0, float p1, float p2, float p3, float p4, float p5, BOOL p6, BOOL p7)



> 0xE6869BECDD8F2403 

void 0xE6869BECDD8F2403(Any p0, BOOL p1)



> ENABLE_TENNIS_MODE - 0x28A04B411933F8A6 0x0BD3F9EC

void ENABLE_TENNIS_MODE(Ped ped, BOOL toggle, BOOL p2)

```
Makes the ped jump around like they're in a tennis match
```

> IS_TENNIS_MODE - 0x5D5479D115290C3F 0x04A947BA

BOOL IS_TENNIS_MODE(Ped ped)

```
Return whether tennis mode is active or not.
```

> 0xE266ED23311F24D4 0xC20A7D2B

void 0xE266ED23311F24D4(Any p0, Any* p1, Any* p2, float p3, float p4, BOOL p5)



> 0x17DF68D720AA77F8 0x8501E727

BOOL 0x17DF68D720AA77F8(Any p0)



> 0x19BFED045C647C49 0x1A332D2D

BOOL 0x19BFED045C647C49(Any p0)



> 0xE95B0C7D5BA3B96B 

BOOL 0xE95B0C7D5BA3B96B(Any p0)



> 0x8FA9C42FC5D7C64B 0x0C8865DF

void 0x8FA9C42FC5D7C64B(Any p0, Any p1, float p2, float p3, float p4, BOOL p5)



> 0x54F157E0336A3822 0x49F977A9

void 0x54F157E0336A3822(Any p0, char* p1, float p2)

```
From the scripts:

GAMEPLAY::_54F157E0336A3822(sub_aa49(a_0), 'ForcedStopDirection', v_E);
```

> 0xD10F442036302D50 0x6F009E33

void 0xD10F442036302D50(Any p0, Any p1, Any p2)



> RESET_DISPATCH_IDEAL_SPAWN_DISTANCE - 0x77A84429DD9F0A15 0xDA65ECAA

void RESET_DISPATCH_IDEAL_SPAWN_DISTANCE()



> SET_DISPATCH_IDEAL_SPAWN_DISTANCE - 0x6FE601A64180D423 0x6283BE32

void SET_DISPATCH_IDEAL_SPAWN_DISTANCE(float p0)



> SET_DISPATCH_TIME_BETWEEN_SPAWN_ATTEMPTS - 0x44F7CBC1BEB3327D 0xABADB709

void SET_DISPATCH_TIME_BETWEEN_SPAWN_ATTEMPTS(Any p0, float p1)



> SET_DISPATCH_TIME_BETWEEN_SPAWN_ATTEMPTS_MULTIPLIER - 0x48838ED9937A15D1 0x1C996BCD

void SET_DISPATCH_TIME_BETWEEN_SPAWN_ATTEMPTS_MULTIPLIER(Any p0, float p1)



> 0x918C7B2D2FF3928B 0xF557BAF9

Any 0x918C7B2D2FF3928B(float p0, float p1, float p2, float p3, float p4, float p5, float p6)



> 0x2D4259F1FEB81DA9 

Any 0x2D4259F1FEB81DA9(float p0, float p1, float p2, float p3)



> REMOVE_DISPATCH_SPAWN_BLOCKING_AREA - 0x264AC28B01B353A5 0xA8D2FB92

void REMOVE_DISPATCH_SPAWN_BLOCKING_AREA(Any p0)



> RESET_DISPATCH_SPAWN_BLOCKING_AREAS - 0xAC7BFD5C1D83EA75 0x9A17F835

void RESET_DISPATCH_SPAWN_BLOCKING_AREAS()



> 0xD9F692D349249528 0xE0C9307E

void 0xD9F692D349249528()



> 0xE532EC1A63231B4F 0xA0D8C749

void 0xE532EC1A63231B4F(Any p0, Any p1)



> 0xB8721407EE9C3FF6 0x24A4E0B2

void 0xB8721407EE9C3FF6(Any p0, Any p1, Any p2)



> 0xB3CD58CCA6CDA852 0x66C3C59C

void 0xB3CD58CCA6CDA852()



> 0x2587A48BC88DFADF 0xD9660339

void 0x2587A48BC88DFADF(BOOL p0)



> 0xCA78CFA0366592FE 0xD2688412

void 0xCA78CFA0366592FE(int p0, char* windowTitle, Any* p2, char* defaultText, char* defaultConcat1, char* defaultConcat2, char* defaultConcat3, char* defaultConcat4, char* defaultConcat5, char* defaultConcat6, char* defaultConcat7, int maxInputLength)

```
only documented to be continued...
```

> DISPLAY_ONSCREEN_KEYBOARD - 0x00DC833F2568DBF6 0xAD99F2CE

void DISPLAY_ONSCREEN_KEYBOARD(int p0, char* windowTitle, char* p2, char* defaultText, char* defaultConcat1, char* defaultConcat2, char* defaultConcat3, int maxInputLength)

```
sfink: note, p0 is set to 6 for PC platform in at least 1 script, or to `unk::_get_ui_language_id() == 0` otherwise.

NOTE: windowTitle uses text labels, and an invalid value will display nothing.

www.gtaforums.com/topic/788343-vrel-script-hook-v/?p=1067380474

windowTitle's
-----------------
CELL_EMAIL_BOD	=	'Enter your Eyefind message'
CELL_EMAIL_BODE	=	'Message too long. Try again'
CELL_EMAIL_BODF	=	'Forbidden message. Try again'
CELL_EMAIL_SOD	=	'Enter your Eyefind subject'
CELL_EMAIL_SODE	=	'Subject too long. Try again'
CELL_EMAIL_SODF	=	'Forbidden text. Try again'
CELL_EMASH_BOD	=	'Enter your Eyefind message'
CELL_EMASH_BODE	=	'Message too long. Try again'
CELL_EMASH_BODF	=	'Forbidden message. Try again'
CELL_EMASH_SOD	=	'Enter your Eyefind subject'
CELL_EMASH_SODE	=	'Subject too long. Try again'
CELL_EMASH_SODF	=	'Forbidden Text. Try again'
FMMC_KEY_TIP10	=	'Enter Synopsis'
FMMC_KEY_TIP12	=	'Enter Custom Team Name'
FMMC_KEY_TIP12F	=	'Forbidden Text. Try again'
FMMC_KEY_TIP12N	=	'Custom Team Name'
FMMC_KEY_TIP8	=	'Enter Message'
FMMC_KEY_TIP8F	=	'Forbidden Text. Try again'
FMMC_KEY_TIP8FS	=	'Invalid Message. Try again'
FMMC_KEY_TIP8S	=	'Enter Message'
FMMC_KEY_TIP9	=	'Enter Outfit Name'
FMMC_KEY_TIP9F	=	'Invalid Outfit Name. Try again'
FMMC_KEY_TIP9N	=	'Outfit Name'
PM_NAME_CHALL	=	'Enter Challenge Name'
```

> UPDATE_ONSCREEN_KEYBOARD - 0x0CF2B696BBF945AE 0x23D0A1CE

int UPDATE_ONSCREEN_KEYBOARD()

```
Returns the current status of the onscreen keyboard, and updates the output.

Status Codes:

0 - User still editing
1 - User has finished editing
2 - User has canceled editing
3 - Keyboard isn't active
```

> GET_ONSCREEN_KEYBOARD_RESULT - 0x8362B09B91893647 0x44828FB3

char* GET_ONSCREEN_KEYBOARD_RESULT()

```
Returns NULL unless UPDATE_ONSCREEN_KEYBOARD() returns 1 in the same tick.
```

> 0x3ED1438C1F5C6612 0x3301EA47

void 0x3ED1438C1F5C6612(int p0)

```
p0 was always 2 in R* scripts.
Called before calling DISPLAY_ONSCREEN_KEYBOARD if the input needs to be saved.
```

> 0xA6A12939F16D85BE 0x42B484ED

void 0xA6A12939F16D85BE(Hash hash, BOOL p1)

```
Appears to remove stealth kill action from memory
```

> 0x1EAE0A6E978894A2 0x8F60366E

void 0x1EAE0A6E978894A2(int p0, BOOL p1)

```
Unsure about the use of this native but here's an example:

void sub_8709() {
    GAMEPLAY::_1EAE0A6E978894A2(0, 1);
    GAMEPLAY::_1EAE0A6E978894A2(1, 1);
    GAMEPLAY::_1EAE0A6E978894A2(2, 1);
    GAMEPLAY::_1EAE0A6E978894A2(3, 1);
    GAMEPLAY::_1EAE0A6E978894A2(4, 1);
    GAMEPLAY::_1EAE0A6E978894A2(5, 1);
    GAMEPLAY::_1EAE0A6E978894A2(6, 1);
    GAMEPLAY::_1EAE0A6E978894A2(7, 1);
    GAMEPLAY::_1EAE0A6E978894A2(8, 1);
}

So it appears that p0 ranges from 0 to 8.

ENABLE_DISPATCH_SERVICE, seems to have a similar layout.
```

> SET_EXPLOSIVE_AMMO_THIS_FRAME - 0xA66C71C98D5F2CFB 0x2EAFA1D1

Any SET_EXPLOSIVE_AMMO_THIS_FRAME(Player player)



> SET_FIRE_AMMO_THIS_FRAME - 0x11879CDD803D30F4 0x7C18FC8A

Any SET_FIRE_AMMO_THIS_FRAME(Player player)



> SET_EXPLOSIVE_MELEE_THIS_FRAME - 0xFF1BED81BFDC0FE0 0x96663D56

Any SET_EXPLOSIVE_MELEE_THIS_FRAME(Player player)



> SET_SUPER_JUMP_THIS_FRAME - 0x57FFF03E423A4C0B 0x86745EF3

Any SET_SUPER_JUMP_THIS_FRAME(Player player)



> 0x6FDDF453C0C756EC 0xC3C10FCC

BOOL 0x6FDDF453C0C756EC()

```
- if (GAMEPLAY::_6FDDF453C0C756EC() || GAMEPLAY::IS_PC_VERSION()) {

- if (((!g_1) &amp;&amp; (!GAMEPLAY::IS_PC_VERSION())) &amp;&amp; GAMEPLAY::_6FDDF453C0C756EC()) {

```

> 0xFB00CA71DA386228 0x054EC103

void 0xFB00CA71DA386228()



> 0x5AA3BEFA29F03AD4 0x46B5A15C

Any 0x5AA3BEFA29F03AD4()



> 0xE3D969D2785FFB5E 

void 0xE3D969D2785FFB5E()

```
sets something to 1
```

> _RESET_LOCALPLAYER_STATE - 0xC0AA53F866B3134D 0x5D209F25

void _RESET_LOCALPLAYER_STATE()

```
Sets the localplayer playerinfo state back to playing (State 0)

States are:
-1: 'Invalid'
0: 'Playing'
1: 'Died'
2: 'Arrested'
3: 'Failed Mission'
4: 'Left Game'
5: 'Respawn'
6: 'In MP Cutscene'
```

> 0x0A60017F841A54F2 0x2D33F15A

void 0x0A60017F841A54F2(Any p0, Any p1, Any p2, Any p3)



> 0x1FF6BF9A63E5757F 0xDF99925C

void 0x1FF6BF9A63E5757F()



> 0x1BB299305C3E8C13 0xA27F4472

void 0x1BB299305C3E8C13(Any p0, Any p1, Any p2, Any p3)



> 0x8EF5573A1F801A5C 0x07FF553F

BOOL 0x8EF5573A1F801A5C(Any p0, Any* p1, Any* p2)



> 0x92790862E36C2ADA 

void 0x92790862E36C2ADA()

```
I can 100% confirm this is some kind of START_* native.

Next character in the name is either C, D or E.

Used only once in the scripts (benchmark.ysc).
```

> 0xC7DB36C24634F52B 

void 0xC7DB36C24634F52B()



> 0x437138B6A830166A 

void 0x437138B6A830166A()



> 0x37DEB0AA183FB6D8 

void 0x37DEB0AA183FB6D8()



> 0xEA2F2061875EED90 

Any 0xEA2F2061875EED90()



> 0x3BBBD13E5041A79E 

Any 0x3BBBD13E5041A79E()



> 0xA049A5BE0F04F2F8 

Any 0xA049A5BE0F04F2F8()



> 0x4750FC27570311EC 

Any 0x4750FC27570311EC()



> 0x1B2366C3F2A5C8DF 

Any 0x1B2366C3F2A5C8DF()



> _FORCE_SOCIAL_CLUB_UPDATE - 0xEB6891F03362FB12 

void _FORCE_SOCIAL_CLUB_UPDATE()

```
Exits the game and downloads a fresh social club update on next restart.
```

> 0x14832BF2ABA53FC5 

Any 0x14832BF2ABA53FC5()



> 0xC79AE21974B01FB2 

void 0xC79AE21974B01FB2()



> 0x684A41975F077262 

BOOL 0x684A41975F077262()

```
example:

 if (GAMEPLAY::_684A41975F077262()) {
        (a_0) = GAMEPLAY::_ABB2FA71C83A1B72();
    } else { 
        (a_0) = -1;
    }
```

> 0xABB2FA71C83A1B72 

Any 0xABB2FA71C83A1B72()



> 0x4EBB7E87AA0DBED4 

void 0x4EBB7E87AA0DBED4(BOOL p0)

```
If toggle is true, the ped's head is shown in the pause menu
If toggle is false, the ped's head is not shown in the pause menu
```

> 0x9689123E3F213AA5 

BOOL 0x9689123E3F213AA5()



> 0x9D8D44ADBBA61EF2 

void 0x9D8D44ADBBA61EF2(BOOL p0)



> 0x23227DF0B2115469 

void 0x23227DF0B2115469()



> 0xD10282B6E3751BA0 

Any 0xD10282B6E3751BA0()



