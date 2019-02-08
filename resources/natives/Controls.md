# Controls

> IS_CONTROL_ENABLED - 0x1CEA6BFDF248E5D9 0x9174AF84

BOOL IS_CONTROL_ENABLED(int inputGroup, int control)

```
Control Groups:

enum InputGroups
{
	INPUTGROUP_MOVE = 0,
	INPUTGROUP_LOOK = 1,
	INPUTGROUP_WHEEL = 2,
	INPUTGROUP_CELLPHONE_NAVIGATE = 3,
	INPUTGROUP_CELLPHONE_NAVIGATE_UD = 4,
	INPUTGROUP_CELLPHONE_NAVIGATE_LR = 5,
	INPUTGROUP_FRONTEND_DPAD_ALL = 6,
	INPUTGROUP_FRONTEND_DPAD_UD = 7,
	INPUTGROUP_FRONTEND_DPAD_LR = 8,
	INPUTGROUP_FRONTEND_LSTICK_ALL = 9,
	INPUTGROUP_FRONTEND_RSTICK_ALL = 10,
	INPUTGROUP_FRONTEND_GENERIC_UD = 11,
	INPUTGROUP_FRONTEND_GENERIC_LR = 12,
	INPUTGROUP_FRONTEND_GENERIC_ALL = 13,
	INPUTGROUP_FRONTEND_BUMPERS = 14,
	INPUTGROUP_FRONTEND_TRIGGERS = 15,
	INPUTGROUP_FRONTEND_STICKS = 16,
	INPUTGROUP_SCRIPT_DPAD_ALL = 17,
	INPUTGROUP_SCRIPT_DPAD_UD = 18,
	INPUTGROUP_SCRIPT_DPAD_LR = 19,
	INPUTGROUP_SCRIPT_LSTICK_ALL = 20,
	INPUTGROUP_SCRIPT_RSTICK_ALL = 21,
	INPUTGROUP_SCRIPT_BUMPERS = 22,
	INPUTGROUP_SCRIPT_TRIGGERS = 23,
	INPUTGROUP_WEAPON_WHEEL_CYCLE = 24,
	INPUTGROUP_FLY = 25,
	INPUTGROUP_SUB = 26,
	INPUTGROUP_VEH_MOVE_ALL = 27,
	INPUTGROUP_CURSOR = 28,
	INPUTGROUP_CURSOR_SCROLL = 29,
	INPUTGROUP_SNIPER_ZOOM_SECONDARY = 30,
	INPUTGROUP_VEH_HYDRAULICS_CONTROL = 31,
	MAX_INPUTGROUPS = 32,
	INPUTGROUP_INVALID = 33
};
0, 1 and 2 used in the scripts.
```

> IS_CONTROL_PRESSED - 0xF3A21BCD95725A4A 0x517A4384

BOOL IS_CONTROL_PRESSED(int inputGroup, int control)

```
index always is 2 for xbox 360 controller and razerblade

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> IS_CONTROL_RELEASED - 0x648EE3E7F38877DD 0x1F91A06E

BOOL IS_CONTROL_RELEASED(int inputGroup, int control)

```
0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> IS_CONTROL_JUST_PRESSED - 0x580417101DDB492F 0x4487F579

BOOL IS_CONTROL_JUST_PRESSED(int inputGroup, int control)



> IS_CONTROL_JUST_RELEASED - 0x50F940259D3841E6 0x2314444B

BOOL IS_CONTROL_JUST_RELEASED(int inputGroup, int control)



> GET_CONTROL_VALUE - 0xD95E79E8686D2C27 0xC526F3C6

int GET_CONTROL_VALUE(int inputGroup, int control)

```


0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> GET_CONTROL_NORMAL - 0xEC3C9B8D5327B563 0x5DE226A5

float GET_CONTROL_NORMAL(int inputGroup, int control)

```
Returns the value of CONTROLS::GET_CONTROL_VALUE Normalized (ie a real number value between -1 and 1)

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0x5B73C77D9EB66E24 

void 0x5B73C77D9EB66E24(BOOL p0)



> 0x5B84D09CEC5209C5 0xC49343BB

float 0x5B84D09CEC5209C5(int inputGroup, int control)

```
Seems to return values between -1 and 1 for controls like gas and steering.

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> _SET_CONTROL_NORMAL - 0xE8A25867FBA3B05E 

BOOL _SET_CONTROL_NORMAL(int inputGroup, int control, float amount)

```
This is for simulating player input.
amount is a float value from 0 - 1

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> IS_DISABLED_CONTROL_PRESSED - 0xE2587F8CBBD87B1D 0x32A93544

BOOL IS_DISABLED_CONTROL_PRESSED(int inputGroup, int control)

```
0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> IS_DISABLED_CONTROL_JUST_PRESSED - 0x91AEF906BCA88877 0xEE6ABD32

BOOL IS_DISABLED_CONTROL_JUST_PRESSED(int inputGroup, int control)

```
0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> IS_DISABLED_CONTROL_JUST_RELEASED - 0x305C8DCD79DA8B0F 0xD6A679E1

BOOL IS_DISABLED_CONTROL_JUST_RELEASED(int inputGroup, int control)

```
0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> GET_DISABLED_CONTROL_NORMAL - 0x11E65974A982637C 0x66FF4FAA

float GET_DISABLED_CONTROL_NORMAL(int inputGroup, int control)

```
control - c# works with (int)GTA.Control.CursorY / (int)GTA.Control.CursorX and returns the mouse movement (additive).


0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0x4F8A26A890FD62FB 0xF2A65A4C

float 0x4F8A26A890FD62FB(int inputGroup, int control)

```
The 'disabled' variant of _0x5B84D09CEC5209C5.

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0xD7D22F5592AED8BA 0x0E8EF929

int 0xD7D22F5592AED8BA(int p0)



> _IS_INPUT_DISABLED - 0xA571D46727E2B718 

BOOL _IS_INPUT_DISABLED(int inputGroup)

```
Seems to return true if the input is currently disabled. '_GET_LAST_INPUT_METHOD' didn't seem very accurate, but I've left the original description below.

--

index usually 2

returns true if the last input method was made with mouse + keyboard, false if it was made with a gamepad

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> _IS_INPUT_JUST_DISABLED - 0x13337B38DB572509 

BOOL _IS_INPUT_JUST_DISABLED(int inputGroup)

```
I may be wrong with this one, but from the looks of the scripts, it sets keyboard related stuff as soon as this returns true.

0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0xFC695459D4D0E219 

BOOL 0xFC695459D4D0E219(float p0, float p1)

```
Renamed to SET_CURSOR_LOCATION (I previously named it _SET_CURSOR_POSTION) which is the correct name as far as I can tell.
```

> 0x23F09EADC01449D6 

BOOL 0x23F09EADC01449D6(Any p0)



> 0x6CD79468A1E595C6 

BOOL 0x6CD79468A1E595C6(int inputGroup)



> _GET_CONTROL_ACTION_NAME - 0x0499D7B09FC9B407 0x3551727A

char* _GET_CONTROL_ACTION_NAME(int inputGroup, int control, BOOL p2)

```
formerly called _GET_CONTROL_ACTION_NAME incorrectly

p2 appears to always be true.
p2 is unused variable in function.

EG:
_GET_CONTROL_ACTION_NAME(2, 201, 1) /*INPUT_FRONTEND_ACCEPT (e.g. Enter button)*/
_GET_CONTROL_ACTION_NAME(2, 202, 1) /*INPUT_FRONTEND_CANCEL (e.g. ESC button)*/
_GET_CONTROL_ACTION_NAME(2, 51, 1) /*INPUT_CONTEXT (e.g. E button)*/

gtaforums.com/topic/819070-c-draw-instructional-buttons-scaleform-movie/#entry1068197378


0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0x80C2FD58D720C801 0x3EE71F6A

char* 0x80C2FD58D720C801(int inputGroup, int control, BOOL p2)

```
0, 1 and 2 used in the scripts. 0 is by far the most common of them.
```

> 0x8290252FFF36ACB5 

void 0x8290252FFF36ACB5(int p0, int red, int green, int blue)

```
HUD_COLOUR_CONTROLLER_CHOP = 174;

UI::GET_HUD_COLOUR(174, &amp;v_6, &amp;v_7, &amp;v_8, &amp;v_9);
CONTROLS::_8290252FFF36ACB5(0, v_6, v_7, v_8);
```

> 0xCB0360EFEFB2580D 

void 0xCB0360EFEFB2580D(Any p0)



> SET_PAD_SHAKE - 0x48B3886C1358D0D5 0x5D38BD2F

void SET_PAD_SHAKE(int p0, int duration, int frequency)

```
p0 always seems to be 0
duration in milliseconds 
frequency should range from about 10 (slow vibration) to 255 (very fast)
appears to be a hash collision, though it does do what it says

example:
SET_PAD_SHAKE(0, 100, 200);
```

> 0x14D29BB12D47F68C 

void 0x14D29BB12D47F68C(Any p0, Any p1, Any p2, Any p3, Any p4)



> STOP_PAD_SHAKE - 0x38C16A305E8CDC8D 0x8F75657E

void STOP_PAD_SHAKE(Any p0)



> 0xF239400E16C23E08 0x7D65EB6E

void 0xF239400E16C23E08(Any p0, Any p1)



> 0xA0CEFCEA390AAB9B 

void 0xA0CEFCEA390AAB9B(Any p0)



> IS_LOOK_INVERTED - 0x77B612531280010D 0x313434B2

BOOL IS_LOOK_INVERTED()



> 0xE1615EC03B3BB4FD 

BOOL 0xE1615EC03B3BB4FD()

```
Used with IS_LOOK_INVERTED() and negates its affect.

--

Not sure how the person above got that description, but here's an actual example:

if (CONTROLS::_GET_LAST_INPUT_METHOD(2)) {
    if (a_5) {
        if (CONTROLS::IS_LOOK_INVERTED()) {
            a_3 *= -1;
        }
        if (CONTROLS::_E1615EC03B3BB4FD()) {
            a_3 *= -1;
        }
    }
}
```

> GET_LOCAL_PLAYER_AIM_STATE - 0xBB41AFBBBC0A0287 0x81802053

int GET_LOCAL_PLAYER_AIM_STATE()



> 0x59B9A7AF4C95133C 

Any 0x59B9A7AF4C95133C()

```
Same behavior as GET_LOCAL_PLAYER_AIM_STATE but only used on the PC version.
```

> 0x0F70731BACCFBB96 

BOOL 0x0F70731BACCFBB96()



> 0xFC859E2374407556 

BOOL 0xFC859E2374407556()



> SET_PLAYERPAD_SHAKES_WHEN_CONTROLLER_DISABLED - 0x798FDEB5B1575088 0xA86BD91F

void SET_PLAYERPAD_SHAKES_WHEN_CONTROLLER_DISABLED(BOOL toggle)



> SET_INPUT_EXCLUSIVE - 0xEDE476E5EE29EDB1 0x4E8E29E6

void SET_INPUT_EXCLUSIVE(int inputGroup, int control)



> DISABLE_CONTROL_ACTION - 0xFE99B66D079CF6BC 0x3800C0DC

void DISABLE_CONTROL_ACTION(int inputGroup, int control, BOOL disable)

```
control values and meaning: github.com/crosire/scripthookvdotnet/blob/dev/source/scripting/Controls.hpp

0, 1 and 2 used in the scripts. 0 is by far the most common of them.

Control values from the decompiled scripts: 0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,
28,29,30,31,32,33,34,35,36,37,38,39,40,41,42,43,44,45,46,47,48,49,50,51,53,5
4,55,56,57,58,59,60,61,62,63,64,65,66,67,68,69,70,71,72,73,74,75,76,77,78,
79,80,81,82,85,86,87,88,89,90,91,92,93,95,96,97,98,99,100,101,102,103,105,
107,108,109,110,111,112,113,114,115,116,117,118,119,123,126,129,130,131,132,
133,134,136,137,138,139,140,141,142,143,144,145,146,147,148,149,150,151,152,
153,154,155,156,157,158,159,160,161,162,163,164,165,166,167,168,169,171,172
,177,187,188,189,190,195,196,199,200,201,202,203,205,207,208,209,211,212,213, 217,219,220,221,225,226,230,234,235,236,237,238,239,240,241,242,243,244,257,
261,262,263,264,265,270,271,272,273,274,278,279,280,281,282,283,284,285,286,
287,288,289,337.

Example: CONTROLS::DISABLE_CONTROL_ACTION(2, 19, true) disables the switching UI from appearing both when using a keyboard and Xbox 360 controller. Needs to be looped. 
 
Control group 1 and 0 gives the same results as 2. Same results for all players. 
```

> ENABLE_CONTROL_ACTION - 0x351220255D64C155 0xD2753551

void ENABLE_CONTROL_ACTION(int inputGroup, int control, BOOL enable)

```
control values and meaning: github.com/crosire/scripthookvdotnet/blob/dev/source/scripting/Controls.hpp

0, 1 and 2 used in the scripts.

Control values from the decompiled scripts: 
0,1,2,3,4,5,6,8,9,10,11,14,15,16,17,19,21,22,24,25,26,30,31,32,33,34,35,36,
37,44,46,47,59,60,65,68,69,70,71,72,73,74,75,76,79,80,81,82,86,95,98,99,100
,101,114,140,141,143,172,173,174,175,176,177,178,179,180,181,187,188,189,19
0,195,196,197,198,199,201,202,203,204,205,206,207,208,209,210,217,218,219,2
20,221,225,228,229,230,231,234,235,236,237,238,239,240,241,242,245,246,257,
261,262,263,264,286,287,288,289,337,338,339,340,341,342,343

INPUTGROUP_MOVE
INPUTGROUP_LOOK
INPUTGROUP_WHEEL
INPUTGROUP_CELLPHONE_NAVIGATE
INPUTGROUP_CELLPHONE_NAVIGATE_UD
INPUTGROUP_CELLPHONE_NAVIGATE_LR
INPUTGROUP_FRONTEND_DPAD_ALL
INPUTGROUP_FRONTEND_DPAD_UD
INPUTGROUP_FRONTEND_DPAD_LR
INPUTGROUP_FRONTEND_LSTICK_ALL
INPUTGROUP_FRONTEND_RSTICK_ALL
INPUTGROUP_FRONTEND_GENERIC_UD
INPUTGROUP_FRONTEND_GENERIC_LR
INPUTGROUP_FRONTEND_GENERIC_ALL
INPUTGROUP_FRONTEND_BUMPERS
INPUTGROUP_FRONTEND_TRIGGERS
INPUTGROUP_FRONTEND_STICKS
INPUTGROUP_SCRIPT_DPAD_ALL
INPUTGROUP_SCRIPT_DPAD_UD
INPUTGROUP_SCRIPT_DPAD_LR
INPUTGROUP_SCRIPT_LSTICK_ALL
INPUTGROUP_SCRIPT_RSTICK_ALL
INPUTGROUP_SCRIPT_BUMPERS
INPUTGROUP_SCRIPT_TRIGGERS
INPUTGROUP_WEAPON_WHEEL_CYCLE
INPUTGROUP_FLY
INPUTGROUP_SUB
INPUTGROUP_VEH_MOVE_ALL
INPUTGROUP_CURSOR
INPUTGROUP_CURSOR_SCROLL
INPUTGROUP_SNIPER_ZOOM_SECONDARY
INPUTGROUP_VEH_HYDRAULICS_CONTROL


Took those in IDA Pro.Not sure in which order they go
```

> DISABLE_ALL_CONTROL_ACTIONS - 0x5F4B6931816E599B 0x16753CF4

void DISABLE_ALL_CONTROL_ACTIONS(int inputGroup)



> ENABLE_ALL_CONTROL_ACTIONS - 0xA5FFE9B05F199DE7 0xFC2F119F

void ENABLE_ALL_CONTROL_ACTIONS(int inputGroup)



> 0x3D42B92563939375 0xD2C80B2E

BOOL 0x3D42B92563939375(char* p0)

```
Used in carsteal3 script with p0 = 'Carsteal4_spycar'.
```

> 0x4683149ED1DDE7A1 0xBBFC9050

BOOL 0x4683149ED1DDE7A1(char* p0)



> 0x643ED62D5EA3BEBD 0x42140FF9

void 0x643ED62D5EA3BEBD()



> 0x7F4724035FDCA1DD 0x2CEDE6C5

void 0x7F4724035FDCA1DD(int inputGroup)



