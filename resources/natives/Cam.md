# Cam

> RENDER_SCRIPT_CAMS - 0x07E5B515DB0636FC 0x74337969

void RENDER_SCRIPT_CAMS(BOOL render, BOOL ease, int easeTime, BOOL p3, BOOL p4)

```
ease - smooth transition between the camera's positions
easeTime - Time in milliseconds for the transition to happen

If you have created a script (rendering) camera, and want to go back to the 
character (gameplay) camera, call this native with render set to 0.
Setting ease to 1 will smooth the transition.
```

> 0xC819F3CBB62BF692 0xD3C08183

void 0xC819F3CBB62BF692(Any p0, Any p1, Any p2)

```
This native makes the gameplay camera zoom into first person/third person with a special effect.

For example, if you were first person in a mission and after the cutscene ends, the camera would then zoom into the first person camera view.

if (CAM::GET_FOLLOW_PED_CAM_VIEW_MODE() != 4)
           CAM::_C819F3CBB62BF692(1, 0, 3, 0)

This makes the camera zoom in to first person.

- jedijosh920
--------------------------------------------
Thanks @jedijosh920 for the example, I hate to bring up last-gen, but seeing as that's what I develop on. For Xbox360 TU27 (Our last TU so far) This native only has 3 params not 4 like in your example.
Out of 166 hits in last-gen TU27 Decompiled Scripts.
1st Param Options: 0 or 1 (Changes quit often, toggle?)
2nd Param Options: 0, 0f, 1f, 3.8f, 10f, 20f (Mostly 0) 
3rd Param Options: 3, 2, 1 (Mostly 3);
Note for the 2nd param 10f (offroad_race.c) and 3rd param 20f (range_modern.c) are the only times those 2 high floats are called.
Note for the 3rd param 2 is only ever set in (franklin0.c), but it also sets it as 3. (0, 0, 3) ||(0, 0f, 2) || (0, 0, 3)

Final Note: I labeled the first param as a bool since it is only ever 1 or 0. Anybody can feel free to put it back and erase my final note. In my natives I just named this _RENDER_FIRST_PERSON_CAM
```

> CREATE_CAM - 0xC3981DCE61D9E13F 0xE9BF2A7D

Cam CREATE_CAM(char* camName, BOOL p1)

```
'DEFAULT_SCRIPTED_CAMERA'
'DEFAULT_ANIMATED_CAMERA'
'DEFAULT_SPLINE_CAMERA'
'DEFAULT_SCRIPTED_FLY_CAMERA'
'TIMED_SPLINE_CAMERA'
```

> CREATE_CAM_WITH_PARAMS - 0xB51194800B257161 0x23B02F15

Cam CREATE_CAM_WITH_PARAMS(char* camName, float posX, float posY, float posZ, float rotX, float rotY, float rotZ, float fov, BOOL p8, int p9)

```
camName is always set to 'DEFAULT_SCRIPTED_CAMERA' in Rockstar's scripts.
------------
Camera names found in the b617d scripts:
'DEFAULT_ANIMATED_CAMERA'
'DEFAULT_SCRIPTED_CAMERA'
'DEFAULT_SCRIPTED_FLY_CAMERA'
'DEFAULT_SPLINE_CAMERA'
------------
Side Note: It seems p8 is basically to represent what would be the bool p1 within CREATE_CAM native. As well as the p9 since it's always 2 in scripts seems to represent what would be the last param within SET_CAM_ROT native which normally would be 2.
```

> CREATE_CAMERA - 0x5E3CF89C6BCCA67D 0x5D6739AE

Cam CREATE_CAMERA(Hash camHash, BOOL p1)



> CREATE_CAMERA_WITH_PARAMS - 0x6ABFA3E16460F22D 0x0688BE9A

Cam CREATE_CAMERA_WITH_PARAMS(Hash camHash, float posX, float posY, float posZ, float rotX, float rotY, float rotZ, float fov, BOOL p8, Any p9)

```
CAM::_GET_GAMEPLAY_CAM_COORDS can be used instead of posX,Y,Z
CAM::_GET_GAMEPLAY_CAM_ROT can be used instead of rotX,Y,Z
CAM::_80EC114669DAEFF4() can be used instead of p7 (Possible p7 is FOV parameter. )
p8 ???
p9 uses 2 by default

```

> DESTROY_CAM - 0x865908C81A2C22E9 0xC39302BD

void DESTROY_CAM(Cam cam, BOOL destroy)

```
Removes the cam.
```

> DESTROY_ALL_CAMS - 0x8E5FB15663F79120 0x10C151CE

void DESTROY_ALL_CAMS(BOOL destroy)



> DOES_CAM_EXIST - 0xA7A932170592B50E 0x1EF89DC0

BOOL DOES_CAM_EXIST(Cam cam)

```
Returns whether or not the passed camera handle exists.
```

> SET_CAM_ACTIVE - 0x026FB97D0A425F84 0x064659C2

void SET_CAM_ACTIVE(Cam cam, BOOL active)

```
Set camera as active/inactive.
```

> IS_CAM_ACTIVE - 0xDFB2B516207D3534 0x4B58F177

BOOL IS_CAM_ACTIVE(Cam cam)

```
Returns whether or not the passed camera handle is active.
```

> IS_CAM_RENDERING - 0x02EC0AF5C5A49B7A 0x6EC6B5B2

BOOL IS_CAM_RENDERING(Cam cam)



> GET_RENDERING_CAM - 0x5234F9F10919EABA 0x0FCF4DF1

Cam GET_RENDERING_CAM()



> GET_CAM_COORD - 0xBAC038F7459AE5AE 0x7C40F09C

Vector3 GET_CAM_COORD(Cam cam)



> GET_CAM_ROT - 0x7D304C1C955E3E12 0xDAC84C9F

Vector3 GET_CAM_ROT(Cam cam, Any p1)

```
The last parameter, as in other 'ROT' methods, is usually 2.
```

> GET_CAM_FOV - 0xC3330A45CCCDB26A 0xD6E9FCF5

float GET_CAM_FOV(Cam cam)



> GET_CAM_NEAR_CLIP - 0xC520A34DAFBF24B1 0xCFCD35EE

float GET_CAM_NEAR_CLIP(Cam cam)



> GET_CAM_FAR_CLIP - 0xB60A9CFEB21CA6AA 0x09F119B8

float GET_CAM_FAR_CLIP(Cam cam)



> GET_CAM_FAR_DOF - 0x255F8DAFD540D397 0x98C5CCE9

float GET_CAM_FAR_DOF(Cam cam)



> SET_CAM_PARAMS - 0xBFD8727AEA3CCEBA 0x2167CEBF

void SET_CAM_PARAMS(Cam cam, float p1, float p2, float p3, float p4, float p5, float p6, float p7, Any p8, Any p9, Any p10, Any p11)



> SET_CAM_COORD - 0x4D41783FB745E42E 0x7A8053AF

void SET_CAM_COORD(Cam cam, float posX, float posY, float posZ)

```
Sets the position of the cam.
```

> SET_CAM_ROT - 0x85973643155D0B07 0xEE38B3C1

void SET_CAM_ROT(Cam cam, float rotX, float rotY, float rotZ, int p4)

```
Sets the rotation of the cam.
Last parameter unknown.

Last parameter seems to always be set to 2.
```

> SET_CAM_FOV - 0xB13C14F66A00D047 0xD3D5D74F

void SET_CAM_FOV(Cam cam, float fieldOfView)

```
Sets the field of view of the cam.
---------------------------------------------
Min: 1.0f
Max: 130.0f
```

> SET_CAM_NEAR_CLIP - 0xC7848EFCCC545182 0x46DB13B1

void SET_CAM_NEAR_CLIP(Cam cam, float nearClip)



> SET_CAM_FAR_CLIP - 0xAE306F2A904BF86E 0x0D23E381

void SET_CAM_FAR_CLIP(Cam cam, float farClip)



> SET_CAM_MOTION_BLUR_STRENGTH - 0x6F0F77FBA9A8F2E6 0xFD6E0D67

void SET_CAM_MOTION_BLUR_STRENGTH(Cam cam, float strength)



> SET_CAM_NEAR_DOF - 0x3FA4BF0A7AB7DE2C 0xF28254DF

void SET_CAM_NEAR_DOF(Cam cam, float nearDOF)



> SET_CAM_FAR_DOF - 0xEDD91296CD01AEE0 0x58515E8E

void SET_CAM_FAR_DOF(Cam cam, float farDOF)



> SET_CAM_DOF_STRENGTH - 0x5EE29B4D7D5DF897 0x3CC4EB3F

void SET_CAM_DOF_STRENGTH(Cam cam, float dofStrength)



> SET_CAM_DOF_PLANES - 0x3CF48F6F96E749DC 0xAD6C2B8F

void SET_CAM_DOF_PLANES(Cam cam, float p1, float p2, float p3, float p4)



> SET_CAM_USE_SHALLOW_DOF_MODE - 0x16A96863A17552BB 0x8306C256

void SET_CAM_USE_SHALLOW_DOF_MODE(Cam cam, BOOL toggle)



> SET_USE_HI_DOF - 0xA13B0222F3D94A94 0x8BBF2950

void SET_USE_HI_DOF()



> 0xF55E4046F6F831DC 

void 0xF55E4046F6F831DC(Any p0, float p1)



> 0xE111A7C0D200CBC5 

void 0xE111A7C0D200CBC5(Any p0, float p1)



> _SET_CAM_DOF_FNUMBER_OF_LENS - 0x7DD234D6F3914C5B 

void _SET_CAM_DOF_FNUMBER_OF_LENS(Cam camera, float p1)

```
This native has its name defined inside its code

~Zorg93


```

> _SET_CAM_DOF_FOCUS_DISTANCE_BIAS - 0xC669EEA5D031B7DE 

void _SET_CAM_DOF_FOCUS_DISTANCE_BIAS(Cam camera, float p1)

```
This native has a name defined inside its code

~Zorg93
```

> _SET_CAM_DOF_MAX_NEAR_IN_FOCUS_DISTANCE - 0xC3654A441402562D 

void _SET_CAM_DOF_MAX_NEAR_IN_FOCUS_DISTANCE(Cam camera, float p1)

```
This native has a name defined inside its code

~Zorg93
```

> _SET_CAM_DOF_MAX_NEAR_IN_FOCUS_DISTANCE_BLEND_LEVEL - 0x2C654B4943BDDF7C 

void _SET_CAM_DOF_MAX_NEAR_IN_FOCUS_DISTANCE_BLEND_LEVEL(Cam camera, float p1)

```
This native has a name defined inside its code

~Zorg93
```

> ATTACH_CAM_TO_ENTITY - 0xFEDB7D269E8C60E3 0xAD7C45F6

void ATTACH_CAM_TO_ENTITY(Cam cam, Entity entity, float xOffset, float yOffset, float zOffset, BOOL isRelative)

```
*JulioNIB:
Last param determines if its relative to the Entity
```

> ATTACH_CAM_TO_PED_BONE - 0x61A3DBA14AB7F411 0x506BB35C

void ATTACH_CAM_TO_PED_BONE(Cam cam, Ped ped, int boneIndex, float x, float y, float z, BOOL heading)



> DETACH_CAM - 0xA2FABBE87F4BAD82 0xF4FBF14A

void DETACH_CAM(Cam cam)



> SET_CAM_INHERIT_ROLL_VEHICLE - 0x45F1DE9C34B93AE6 0xE4BD5342

void SET_CAM_INHERIT_ROLL_VEHICLE(Cam cam, BOOL p1)

```
The native seems to only be called once.

The native is used as so,
CAM::SET_CAM_INHERIT_ROLL_VEHICLE(l_544, getElem(2, &amp;l_525, 4));
In the exile1 script.
```

> POINT_CAM_AT_COORD - 0xF75497BB865F0803 0x914BC21A

void POINT_CAM_AT_COORD(Cam cam, float x, float y, float z)



> POINT_CAM_AT_ENTITY - 0x5640BFF86B16E8DC 0x7597A0F7

void POINT_CAM_AT_ENTITY(Cam cam, Entity entity, float p2, float p3, float p4, BOOL p5)

```
p5 always seems to be 1 i.e TRUE
```

> POINT_CAM_AT_PED_BONE - 0x68B2B5F33BA63C41 0x09F47049

void POINT_CAM_AT_PED_BONE(Cam cam, int ped, int boneIndex, float x, float y, float z, BOOL p6)

```
Parameters p0-p5 seems correct. The bool p6 is unknown, but through every X360 script it's always 1. Please correct p0-p5 if any prove to be wrong. 
```

> STOP_CAM_POINTING - 0xF33AB75780BA57DE 0x5435F6A5

void STOP_CAM_POINTING(Cam cam)



> SET_CAM_AFFECTS_AIMING - 0x8C1DC7770C51DC8D 0x0C74F9AF

void SET_CAM_AFFECTS_AIMING(Cam cam, BOOL toggle)

```
Allows you to aim and shoot at the direction the camera is facing.
```

> 0x661B5C8654ADD825 0xE1A0B2F1

void 0x661B5C8654ADD825(Any p0, BOOL p1)



> 0xA2767257A320FC82 

void 0xA2767257A320FC82(Any p0, BOOL p1)



> 0x271017B9BA825366 0x43220969

void 0x271017B9BA825366(Any p0, BOOL p1)



> SET_CAM_DEBUG_NAME - 0x1B93E0107865DD40 0x9B00DF3F

void SET_CAM_DEBUG_NAME(Cam camera, char* name)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> ADD_CAM_SPLINE_NODE - 0x8609C75EC438FB3B 0xAD3C7EAA

void ADD_CAM_SPLINE_NODE(int camera, float x, float y, float z, float xRot, float yRot, float zRot, int length, int p8, int p9)

```
I filled p1-p6 (the floats) as they are as other natives with 6 floats in a row are similar and I see no other method. So if a test from anyone proves them wrong please correct.

p7 (length) determines the length of the spline, affects camera path and duration of transition between previous node and this one

p8 big values ~100 will slow down the camera movement before reaching this node

p9 != 0 seems to override the rotation/pitch (bool?)
```

> 0x0A9F2A468B328E74 0x30510511

void 0x0A9F2A468B328E74(Any p0, Any p1, Any p2, Any p3)



> 0x0FB82563989CF4FB 0xBA6C085B

void 0x0FB82563989CF4FB(Any p0, Any p1, Any p2, Any p3)



> 0x609278246A29CA34 0xB4737F03

void 0x609278246A29CA34(Any p0, Any p1, Any p2)



> SET_CAM_SPLINE_PHASE - 0x242B5874F0A4E052 0xF0AED233

void SET_CAM_SPLINE_PHASE(int cam, float p1)



> GET_CAM_SPLINE_PHASE - 0xB5349E36C546509A 0x39784DD9

float GET_CAM_SPLINE_PHASE(Cam cam)

```
Can use this with SET_CAM_SPLINE_PHASE to set the float it this native returns.

(returns 1.0f when no nodes has been added, reached end of non existing spline)
```

> GET_CAM_SPLINE_NODE_PHASE - 0xD9D0E694C8282C96 0x7B9522F6

float GET_CAM_SPLINE_NODE_PHASE(Any p0)

```
I'm pretty sure the parameter is the camera as usual, but I am not certain so I'm going to leave it as is.
```

> SET_CAM_SPLINE_DURATION - 0x1381539FEE034CDA 0x3E91FC8A

void SET_CAM_SPLINE_DURATION(int cam, int timeDuration)

```
I named p1 as timeDuration as it is obvious. I'm assuming tho it is ran in ms(Milliseconds) as usual.
```

> 0xD1B0F412F109EA5D 0x15E141CE

void 0xD1B0F412F109EA5D(Any p0, Any p1)



> GET_CAM_SPLINE_NODE_INDEX - 0xB22B17DF858716A6 0xF8AEB6BD

BOOL GET_CAM_SPLINE_NODE_INDEX(int cam)

```
I named the beginning from Any to BOOL as this native is used in an if statement as well. 
```

> 0x83B8201ED82A9A2D 0x21D275DA

void 0x83B8201ED82A9A2D(Any p0, Any p1, Any p2, float p3)



> 0xA6385DEB180F319F 0xA3BD9E94

void 0xA6385DEB180F319F(Any p0, Any p1, float p2)



> OVERRIDE_CAM_SPLINE_VELOCITY - 0x40B62FA033EB0346 0x326A17E2

void OVERRIDE_CAM_SPLINE_VELOCITY(int cam, int p1, float p2, float p3)



> OVERRIDE_CAM_SPLINE_MOTION_BLUR - 0x7DCF7C708D292D55 0x633179E6

void OVERRIDE_CAM_SPLINE_MOTION_BLUR(Any p0, Any p1, float p2, float p3)

```
Max value for p1 is 15.
```

> 0x7BF1A54AE67AC070 0xC90B2DDC

void 0x7BF1A54AE67AC070(Any p0, Any p1, Any p2)



> IS_CAM_SPLINE_PAUSED - 0x0290F35C0AD97864 0x60B34FF5

BOOL IS_CAM_SPLINE_PAUSED(Any p0)



> SET_CAM_ACTIVE_WITH_INTERP - 0x9FBDA379383A52A4 0x7983E7F0

void SET_CAM_ACTIVE_WITH_INTERP(Cam camTo, Cam camFrom, int duration, int easeLocation, int easeRotation)

```
Previous declaration void SET_CAM_ACTIVE_WITH_INTERP(Cam camTo, Cam camFrom, int duration, BOOL easeLocation, BOOL easeRotation) is completely wrong. The last two params are integers not BOOLs...

```

> IS_CAM_INTERPOLATING - 0x036F97C908C2B52C 0x7159CB5D

BOOL IS_CAM_INTERPOLATING(Cam cam)



> SHAKE_CAM - 0x6A25241C340D3822 0x1D4211B0

void SHAKE_CAM(Cam cam, char* type, float amplitude)

```
Possible shake types (updated b617d):

DEATH_FAIL_IN_EFFECT_SHAKE
DRUNK_SHAKE
FAMILY5_DRUG_TRIP_SHAKE
HAND_SHAKE
JOLT_SHAKE
LARGE_EXPLOSION_SHAKE
MEDIUM_EXPLOSION_SHAKE
SMALL_EXPLOSION_SHAKE
ROAD_VIBRATION_SHAKE
SKY_DIVING_SHAKE
VIBRATE_SHAKE
```

> ANIMATED_SHAKE_CAM - 0xA2746EEAE3E577CD 0xE1168767

void ANIMATED_SHAKE_CAM(Cam cam, char* p1, char* p2, char* p3, float amplitude)

```
Example from michael2 script.

CAM::ANIMATED_SHAKE_CAM(l_5069, 'shake_cam_all@', 'light', '', 1f);
```

> IS_CAM_SHAKING - 0x6B24BFE83A2BE47B 0x0961FD9B

BOOL IS_CAM_SHAKING(Cam cam)



> SET_CAM_SHAKE_AMPLITUDE - 0xD93DB43B82BC0D00 0x60FF6382

void SET_CAM_SHAKE_AMPLITUDE(Cam cam, float amplitude)



> STOP_CAM_SHAKING - 0xBDECF64367884AC3 0x40D0EB87

void STOP_CAM_SHAKING(Cam cam, BOOL p1)



> 0xF4C8CF9E353AFECA 0x2B0F05CD

void 0xF4C8CF9E353AFECA(char* p0, float p1)

```
Something to do with shake:
CAM::_F4C8CF9E353AFECA('HAND_SHAKE', 0.2);
```

> 0xC2EAE3FB8CDBED31 0xCB75BD9C

void 0xC2EAE3FB8CDBED31(char* p0, char* p1, char* p2, float p3)

```
CAM::_C2EAE3FB8CDBED31('SHAKE_CAM_medium', 'medium', '', 0.5f);
```

> 0xC912AF078AF19212 0x6AEFE6A5

BOOL 0xC912AF078AF19212()

```
In drunk_controller.c4, sub_309
if (CAM::_C912AF078AF19212()) {
    CAM::_1C9D7949FA533490(0);
}

What does 'IS_SCRIPT_GLOBAL_SHAKING' mean..? :/ Is this a hash collision?
```

> 0x1C9D7949FA533490 0x26FCFB96

void 0x1C9D7949FA533490(BOOL p0)

```
In drunk_controller.c4, sub_309
if (CAM::_C912AF078AF19212()) {
    CAM::_1C9D7949FA533490(0);
}
```

> PLAY_CAM_ANIM - 0x9A2D0FB2E7852392 0xBCEFB87E

BOOL PLAY_CAM_ANIM(Cam cam, char* animName, char* animDictionary, float x, float y, float z, float xRot, float yRot, float zRot, BOOL p9, int p10)

```
Atleast one time in a script for the zRot Rockstar uses GET_ENTITY_HEADING to help fill the parameter.

p9 is unknown at this time.
p10 throughout all the X360 Scripts is always 2.

Animations List : www.ls-multiplayer.com/dev/index.php?section=3
```

> IS_CAM_PLAYING_ANIM - 0xC90621D8A0CEECF2 0xB998CB49

BOOL IS_CAM_PLAYING_ANIM(Cam cam, char* animName, char* animDictionary)



> SET_CAM_ANIM_CURRENT_PHASE - 0x4145A4C44FF3B5A6 0x3CB1D17F

void SET_CAM_ANIM_CURRENT_PHASE(Cam cam, float phase)



> GET_CAM_ANIM_CURRENT_PHASE - 0xA10B2DB49E92A6B0 0x345F72D0

float GET_CAM_ANIM_CURRENT_PHASE(Cam cam)



> PLAY_SYNCHRONIZED_CAM_ANIM - 0xE32EFE9AB4A9AA0C 0x9458459E

BOOL PLAY_SYNCHRONIZED_CAM_ANIM(Any p0, Any p1, char* animName, char* animDictionary)

```
Examples:

CAM::PLAY_SYNCHRONIZED_CAM_ANIM(l_2734, NETWORK::_02C40BF885C567B6(l_2739), 'PLAYER_EXIT_L_CAM', 'mp_doorbell');

CAM::PLAY_SYNCHRONIZED_CAM_ANIM(l_F0D[7/*1*/], l_F4D[15/*1*/], 'ah3b_attackheli_cam2', 'missheistfbi3b_helicrash');
```

> 0x503F5920162365B2 0x56F9ED27

void 0x503F5920162365B2(Any p0, float p1, float p2, float p3)



> 0xF9D02130ECDD1D77 0x71570DBA

void 0xF9D02130ECDD1D77(Any p0, float p1)



> 0xC91C6C55199308CA 0x60B345DE

void 0xC91C6C55199308CA(Any p0, float p1, float p2, float p3)



> 0xC8B5C4A79CC18B94 0x44473EFC

void 0xC8B5C4A79CC18B94(Cam p0)



> 0x5C48A1D6E3B33179 0xDA931D65

BOOL 0x5C48A1D6E3B33179(Any p0)



> IS_SCREEN_FADED_OUT - 0xB16FCE9DDC7BA182 0x9CAA05FA

BOOL IS_SCREEN_FADED_OUT()



> IS_SCREEN_FADED_IN - 0x5A859503B0C08678 0x4F37276D

BOOL IS_SCREEN_FADED_IN()



> IS_SCREEN_FADING_OUT - 0x797AC7CB535BA28F 0x79275A57

BOOL IS_SCREEN_FADING_OUT()



> IS_SCREEN_FADING_IN - 0x5C544BC6C57AC575 0xC7C82800

BOOL IS_SCREEN_FADING_IN()



> DO_SCREEN_FADE_IN - 0xD4E8E24955024033 0x66C1BDEE

void DO_SCREEN_FADE_IN(int duration)

```
Fades the screen in.

duration: The time the fade should take, in milliseconds.
```

> DO_SCREEN_FADE_OUT - 0x891B5B39AC6302AF 0x89D01805

void DO_SCREEN_FADE_OUT(int duration)

```
Fades the screen out.

duration: The time the fade should take, in milliseconds.
```

> SET_WIDESCREEN_BORDERS - 0xDCD4EA924F42D01A 0x1A75DC9A

Any SET_WIDESCREEN_BORDERS(BOOL p0, int p1)



> GET_GAMEPLAY_CAM_COORD - 0x14D6F5678D8F1B37 0x9388CF79

Vector3 GET_GAMEPLAY_CAM_COORD()



> GET_GAMEPLAY_CAM_ROT - 0x837765A25378F0BB 0x13A010B5

Vector3 GET_GAMEPLAY_CAM_ROT(int p0)

```
p0 dosen't seem to change much, I tried it with 0, 1, 2:
0-Pitch(X): -70.000092
0-Roll(Y): -0.000001
0-Yaw(Z): -43.886459
1-Pitch(X): -70.000092
1-Roll(Y): -0.000001
1-Yaw(Z): -43.886463
2-Pitch(X): -70.000092
2-Roll(Y): -0.000002
2-Yaw(Z): -43.886467
```

> GET_GAMEPLAY_CAM_FOV - 0x65019750A0324133 0x4D6B3BFA

float GET_GAMEPLAY_CAM_FOV()



> 0x487A82C650EB7799 0xA6E73135

void 0x487A82C650EB7799(float p0)

```
some camera effect that is used in the drunk-cheat, and turned off (by setting it to 0.0) along with the shaking effects once the drunk cheat is disabled.
```

> 0x0225778816FDC28C 0x1126E37C

void 0x0225778816FDC28C(float p0)

```
some camera effect that is (also) used in the drunk-cheat, and turned off (by setting it to 0.0) along with the shaking effects once the drunk cheat is disabled. Possibly a cinematic or script-cam version of _0x487A82C650EB7799
```

> GET_GAMEPLAY_CAM_RELATIVE_HEADING - 0x743607648ADD4587 0xCAF839C2

float GET_GAMEPLAY_CAM_RELATIVE_HEADING()



> SET_GAMEPLAY_CAM_RELATIVE_HEADING - 0xB4EC2312F4E5B1F1 0x20C6217C

void SET_GAMEPLAY_CAM_RELATIVE_HEADING(float heading)

```
Sets the camera position relative to heading in float from -360 to +360.

Heading is alwyas 0 in aiming camera.
```

> GET_GAMEPLAY_CAM_RELATIVE_PITCH - 0x3A6867B4845BEDA2 0xFC5A4946

float GET_GAMEPLAY_CAM_RELATIVE_PITCH()



> SET_GAMEPLAY_CAM_RELATIVE_PITCH - 0x6D0858B8EDFD2B7D 0x6381B963

Any SET_GAMEPLAY_CAM_RELATIVE_PITCH(float x, float Value2)

```
Sets the camera pitch.

Parameters:
x = pitches the camera on the x axis.
Value2 = always seems to be hex 0x3F800000 (1.000000 float).
```

> _SET_GAMEPLAY_CAM_RAW_YAW - 0x103991D4A307D472 

void _SET_GAMEPLAY_CAM_RAW_YAW(float yaw)

```
Does nothing
```

> _SET_GAMEPLAY_CAM_RAW_PITCH - 0x759E13EBC1C15C5A 

void _SET_GAMEPLAY_CAM_RAW_PITCH(float pitch)



> 0x469F2ECDEC046337 

void 0x469F2ECDEC046337(BOOL p0)



> SHAKE_GAMEPLAY_CAM - 0xFD55E49555E017CF 0xF2EFE660

void SHAKE_GAMEPLAY_CAM(char* shakeName, float intensity)

```
Possible shake types (updated b617d):

DEATH_FAIL_IN_EFFECT_SHAKE
DRUNK_SHAKE
FAMILY5_DRUG_TRIP_SHAKE
HAND_SHAKE
JOLT_SHAKE
LARGE_EXPLOSION_SHAKE
MEDIUM_EXPLOSION_SHAKE
SMALL_EXPLOSION_SHAKE
ROAD_VIBRATION_SHAKE
SKY_DIVING_SHAKE
VIBRATE_SHAKE
```

> IS_GAMEPLAY_CAM_SHAKING - 0x016C090630DF1F89 0x3457D681

BOOL IS_GAMEPLAY_CAM_SHAKING()



> SET_GAMEPLAY_CAM_SHAKE_AMPLITUDE - 0xA87E00932DB4D85D 0x9219D44A

void SET_GAMEPLAY_CAM_SHAKE_AMPLITUDE(float amplitude)

```
Sets the amplitude for the gameplay (i.e. 3rd or 1st) camera to shake. Used in script 'drunk_controller.ysc.c4' to simulate making the player drunk.

- Shawn
```

> STOP_GAMEPLAY_CAM_SHAKING - 0x0EF93E9F3D08C178 0xFD569E4E

void STOP_GAMEPLAY_CAM_SHAKING(BOOL p0)



> 0x8BBACBF51DA047A8 0x7D3007A2

void 0x8BBACBF51DA047A8(Any p0)



> IS_GAMEPLAY_CAM_RENDERING - 0x39B5D1B10383F0C8 0x0EF276DA

BOOL IS_GAMEPLAY_CAM_RENDERING()

```
Examples when this function will return 0 are:
- During busted screen.
- When player is coming out from a hospital.
- When player is coming out from a police station.
- When player is buying gun from AmmuNation.
```

> 0x3044240D2E0FA842 0xC0B00C20

BOOL 0x3044240D2E0FA842()



> 0x705A276EBFF3133D 0x60C23785

BOOL 0x705A276EBFF3133D()



> 0xDB90C6CCA48940F1 0x20BFF6E5

void 0xDB90C6CCA48940F1(BOOL p0)



> _ENABLE_CROSSHAIR_THIS_FRAME - 0xEA7F0AD7E9BA676F 0xA61FF9AC

void _ENABLE_CROSSHAIR_THIS_FRAME()

```
Shows the crosshair even if it wouldn't show normally. Only works for one frame, so make sure to call it repeatedly.
```

> IS_GAMEPLAY_CAM_LOOKING_BEHIND - 0x70FDA869F3317EA9 0x33C83F17

BOOL IS_GAMEPLAY_CAM_LOOKING_BEHIND()



> 0x2AED6301F67007D5 0x2701A9AD

void 0x2AED6301F67007D5(Entity p0)

```
                if (ENTITY::DOES_ENTITY_EXIST(l_228)) {
                    CAM::_2AED6301F67007D5(l_228);
```

> 0x49482F9FCD825AAA 0xC4736ED3

void 0x49482F9FCD825AAA(Any p0)



> 0xFD3151CD37EA2245 

void 0xFD3151CD37EA2245(Any p0)



> 0xDD79DF9F4D26E1C9 0x6B0E9D57

void 0xDD79DF9F4D26E1C9()



> IS_SPHERE_VISIBLE - 0xE33D59DA70B58FDF 0xDD1329E2

BOOL IS_SPHERE_VISIBLE(float x, float y, float z, float radius)



> IS_FOLLOW_PED_CAM_ACTIVE - 0xC6D3D26810C8E0F9 0x9F9E856C

BOOL IS_FOLLOW_PED_CAM_ACTIVE()



> SET_FOLLOW_PED_CAM_CUTSCENE_CHAT - 0x44A113DD6FFC48D1 0x1425F6AC

BOOL SET_FOLLOW_PED_CAM_CUTSCENE_CHAT(char* p0, int p1)

```
From the b617d scripts:

CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_ATTACHED_TO_ROPE_CAMERA', 0);
 CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_ON_EXILE1_LADDER_CAMERA', 1500);
 CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_SKY_DIVING_CAMERA', 0);
 CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_SKY_DIVING_CAMERA', 3000);
 CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_SKY_DIVING_FAMILY5_CAMERA', 0);
CAM::SET_FOLLOW_PED_CAM_CUTSCENE_CHAT('FOLLOW_PED_SKY_DIVING_CAMERA', 0);
```

> 0x271401846BD26E92 0x8DC53629

void 0x271401846BD26E92(BOOL p0, BOOL p1)



> 0xC8391C309684595A 0x1F9DE6E4

void 0xC8391C309684595A()



> _CLAMP_GAMEPLAY_CAM_YAW - 0x8F993D26E0CA5E8E 0x749909AC

Any _CLAMP_GAMEPLAY_CAM_YAW(float minimum, float maximum)

```
minimum: Degrees between -180f and 180f.
maximum: Degrees between -180f and 180f.

Clamps the gameplay camera's current yaw.

Eg. _CLAMP_GAMEPLAY_CAM_YAW(0.0f, 0.0f) will set the horizontal angle directly behind the player.
```

> _CLAMP_GAMEPLAY_CAM_PITCH - 0xA516C198B7DCA1E1 0xFA3A16E7

Any _CLAMP_GAMEPLAY_CAM_PITCH(float minimum, float maximum)

```
minimum: Degrees between -90f and 90f.
maximum: Degrees between -90f and 90f.

Clamps the gameplay camera's current pitch.

Eg. _CLAMP_GAMEPLAY_CAM_PITCH(0.0f, 0.0f) will set the vertical angle directly behind the player.
```

> _ANIMATE_GAMEPLAY_CAM_ZOOM - 0xDF2E1F7742402E81 0x77340650

void _ANIMATE_GAMEPLAY_CAM_ZOOM(float p0, float distance)

```
Seems to animate the gameplay camera zoom.

Eg. _ANIMATE_GAMEPLAY_CAM_ZOOM(1f, 1000f);
will animate the camera zooming in from 1000 meters away.

Game scripts use it like this:

// Setting this to 1 prevents V key from changing zoom
PLAYER::SET_PLAYER_FORCED_ZOOM(PLAYER::PLAYER_ID(), 1);

// These restrict how far you can move cam up/down left/right
CAM::_CLAMP_GAMEPLAY_CAM_YAW(-20f, 50f);
CAM::_CLAMP_GAMEPLAY_CAM_PITCH(-60f, 0f);

CAM::_ANIMATE_GAMEPLAY_CAM_ZOOM(1f, 1f);
```

> 0xE9EA16D6E54CDCA4 0x4B22C5CB

Any 0xE9EA16D6E54CDCA4(Vehicle p0, int p1)



> _DISABLE_FIRST_PERSON_CAM_THIS_FRAME - 0xDE2EF5DA284CC8DF 

void _DISABLE_FIRST_PERSON_CAM_THIS_FRAME()

```
Disables first person camera for the current frame.

Found in decompiled scripts:
GRAPHICS::DRAW_DEBUG_TEXT_2D('Disabling First Person Cam', 0.5, 0.8, 0.0, 0, 0, 255, 255);
CAM::_DE2EF5DA284CC8DF();
```

> 0x59424BD75174C9B1 

void 0x59424BD75174C9B1()



> GET_FOLLOW_PED_CAM_ZOOM_LEVEL - 0x33E6C8EFD0CD93E9 0x57583DF1

int GET_FOLLOW_PED_CAM_ZOOM_LEVEL()



> GET_FOLLOW_PED_CAM_VIEW_MODE - 0x8D4D46230B2C353A 0xA65FF946

int GET_FOLLOW_PED_CAM_VIEW_MODE()

```
Returns
0 - Third Person Close
1 - Third Person Mid
2 - Third Person Far
4 - First Person
```

> SET_FOLLOW_PED_CAM_VIEW_MODE - 0x5A4F9EDF1673F704 0x495DBE8D

void SET_FOLLOW_PED_CAM_VIEW_MODE(int viewMode)

```
Sets the type of Player camera:

0 - Third Person Close
1 - Third Person Mid
2 - Third Person Far
4 - First Person
```

> IS_FOLLOW_VEHICLE_CAM_ACTIVE - 0xCBBDE6D335D6D496 0x8DD49B77

BOOL IS_FOLLOW_VEHICLE_CAM_ACTIVE()



> 0x91EF6EE6419E5B97 0x9DB5D391

void 0x91EF6EE6419E5B97(BOOL p0)



> SET_TIME_IDLE_DROP - 0x9DFE13ECDC1EC196 0x92302899

void SET_TIME_IDLE_DROP(BOOL p0, BOOL p1)

```
hash collision?
```

> GET_FOLLOW_VEHICLE_CAM_ZOOM_LEVEL - 0xEE82280AB767B690 0x8CD67DE3

int GET_FOLLOW_VEHICLE_CAM_ZOOM_LEVEL()



> SET_FOLLOW_VEHICLE_CAM_ZOOM_LEVEL - 0x19464CB6E4078C8A 0x8F55EBBE

void SET_FOLLOW_VEHICLE_CAM_ZOOM_LEVEL(int zoomLevel)



> GET_FOLLOW_VEHICLE_CAM_VIEW_MODE - 0xA4FF579AC0E3AAAE 0xA4B4DB03

int GET_FOLLOW_VEHICLE_CAM_VIEW_MODE()

```
Returns the type of camera:

0 - Third Person Close
1 - Third Person Mid
2 - Third Person Far
4 - First Person
```

> SET_FOLLOW_VEHICLE_CAM_VIEW_MODE - 0xAC253D7842768F48 0xC4FBBBD3

void SET_FOLLOW_VEHICLE_CAM_VIEW_MODE(int viewMode)

```
Sets the type of Player camera in vehicles:

0 - Third Person Close
1 - Third Person Mid
2 - Third Person Far
4 - First Person
```

> 0xEE778F8C7E1142E2 0xF3B148A6

Any 0xEE778F8C7E1142E2(Any p0)

```
interprets the result of CAM::_0x19CAFA3C87F7C2FF()

example: // checks if you're currently in first person
if ((CAM::_EE778F8C7E1142E2(CAM::_19CAFA3C87F7C2FF()) == 4) &amp;&amp; (!__463_$28ED382849B17AFC())) {
UI::_FDEC055AB549E328();
UI::_SET_NOTIFICATION_TEXT_ENTRY('REC_FEED_WAR');
l_CE[0/*1*/] = UI::_DRAW_NOTIFICATION(0, 1);
}

- Luucky

```

> 0x2A2173E46DAECD12 0x1DEBCB45

void 0x2A2173E46DAECD12(Any p0, Any p1)



> 0x19CAFA3C87F7C2FF 

Any 0x19CAFA3C87F7C2FF()

```
Seems to return the current type of view
example: // checks if you're currently in first person
if ((CAM::_EE778F8C7E1142E2(CAM::_19CAFA3C87F7C2FF()) == 4) &amp;&amp; (!__463_$28ED382849B17AFC())) {
    UI::_FDEC055AB549E328();
    UI::_SET_NOTIFICATION_TEXT_ENTRY('REC_FEED_WAR');
    l_CE[0/*1*/] = UI::_DRAW_NOTIFICATION(0, 1);
}

- Luucky
```

> IS_AIM_CAM_ACTIVE - 0x68EDDA28A5976D07 0xC24B4F6F

BOOL IS_AIM_CAM_ACTIVE()



> 0x74BD83EA840F6BC9 0x8F320DE4

Any 0x74BD83EA840F6BC9()



> IS_FIRST_PERSON_AIM_CAM_ACTIVE - 0x5E346D934122613F 0xD6280468

BOOL IS_FIRST_PERSON_AIM_CAM_ACTIVE()



> DISABLE_AIM_CAM_THIS_UPDATE - 0x1A31FE0049E542F6 0x1BAA7182

void DISABLE_AIM_CAM_THIS_UPDATE()



> _GET_GAMEPLAY_CAM_ZOOM - 0x7EC52CC40597D170 0x33951005

float _GET_GAMEPLAY_CAM_ZOOM()



> 0x70894BD0915C5BCA 0x9F4AF763

Any 0x70894BD0915C5BCA(float p0)



> 0xCED08CBE8EBB97C7 0x68BA0730

void 0xCED08CBE8EBB97C7(float p0, float p1)



> 0x2F7F2B26DD3F18EE 0x2F29F0D5

void 0x2F7F2B26DD3F18EE(float p0, float p1)



> 0xBCFC632DB7673BF0 0x76DAC96C

void 0xBCFC632DB7673BF0(float p0, float p1)



> 0x0AF7B437918103B3 0x0E21069D

void 0x0AF7B437918103B3(float p0)

```
Appear to have something to do with the clipping at close range.
```

> 0x42156508606DE65E 0x71E9C63E

void 0x42156508606DE65E(float p0)



> 0x4008EDF7D6E48175 0xD1EEBC45

void 0x4008EDF7D6E48175(BOOL p0)



> _GET_GAMEPLAY_CAM_COORDS - 0xA200EB1EE790F448 0x9C84BDA0

Vector3 _GET_GAMEPLAY_CAM_COORDS()



> _GET_GAMEPLAY_CAM_ROT - 0x5B4E4C817FCC2DFB 0x1FFBEFC5

Vector3 _GET_GAMEPLAY_CAM_ROT(int p0)

```
p0 seems to consistently be 2 across scripts

Function is called faily often by CAM::CREATE_CAM_WITH_PARAMS
```

> 0x26903D9CD1175F2C 0xACADF916

int 0x26903D9CD1175F2C(Any p0, Any p1)



> 0x80EC114669DAEFF4 0x721B763B

Any 0x80EC114669DAEFF4()

```
Believe something to do with a Scripted Cam's FOV
```

> 0x5F35F6732C3FBBA0 0x23E3F106

float 0x5F35F6732C3FBBA0(Any p0)



> 0xD0082607100D7193 0x457AE195

Any 0xD0082607100D7193()



> 0xDFC8CBC606FDB0FC 0x46CB3A49

Any 0xDFC8CBC606FDB0FC()



> 0xA03502FC581F7D9B 0x19297A7A

Any 0xA03502FC581F7D9B()



> 0x9780F32BCAF72431 0xF24777CA

Any 0x9780F32BCAF72431()



> 0x162F9D995753DC19 0x38992E83

Any 0x162F9D995753DC19()



> SET_GAMEPLAY_COORD_HINT - 0xD51ADCD2D8BC0FB3 0xF27483C9

void SET_GAMEPLAY_COORD_HINT(float p0, float p1, float p2, Any p3, Any p4, Any p5, Any p6)



> SET_GAMEPLAY_PED_HINT - 0x2B486269ACD548D3 0x7C27343E

void SET_GAMEPLAY_PED_HINT(Ped p0, float x1, float y1, float z1, BOOL p4, Any p5, Any p6, Any p7)



> SET_GAMEPLAY_VEHICLE_HINT - 0xA2297E18F3E71C2E 0x2C9A11D8

void SET_GAMEPLAY_VEHICLE_HINT(Any p0, float p1, float p2, float p3, BOOL p4, Any p5, Any p6, Any p7)



> SET_GAMEPLAY_OBJECT_HINT - 0x83E87508A2CA2AC6 0x2ED5E2F8

void SET_GAMEPLAY_OBJECT_HINT(Any p0, float p1, float p2, float p3, BOOL p4, Any p5, Any p6, Any p7)



> SET_GAMEPLAY_ENTITY_HINT - 0x189E955A8313E298 0x66C32306

void SET_GAMEPLAY_ENTITY_HINT(Any p0, float p1, float p2, float p3, BOOL p4, Any p5, Any p6, Any p7, Any p8)

```
p6 &amp; p7 - possibly length or time
```

> IS_GAMEPLAY_HINT_ACTIVE - 0xE520FF1AD2785B40 0xAD8DA205

BOOL IS_GAMEPLAY_HINT_ACTIVE()



> STOP_GAMEPLAY_HINT - 0xF46C581C61718916 0x1BC28B7B

void STOP_GAMEPLAY_HINT(BOOL p0)



> 0xCCD078C2665D2973 0xCAFEE798

void 0xCCD078C2665D2973(BOOL p0)



> 0x247ACBC4ABBC9D1C 

void 0x247ACBC4ABBC9D1C(BOOL p0)



> 0xBF72910D0F26F025 

Any 0xBF72910D0F26F025()



> SET_GAMEPLAY_HINT_FOV - 0x513403FB9C56211F 0x96FD173B

void SET_GAMEPLAY_HINT_FOV(float FOV)



> 0xF8BDBF3D573049A1 0x72E8CD3A

void 0xF8BDBF3D573049A1(float p0)



> 0xD1F8363DFAD03848 0x79472AE3

void 0xD1F8363DFAD03848(float p0)



> 0x5D7B620DAE436138 0xFC7464A0

void 0x5D7B620DAE436138(float p0)



> 0xC92717EF615B6704 0x3554AA0E

void 0xC92717EF615B6704(float p0)



> GET_IS_MULTIPLAYER_BRIEF - 0xE3433EADAAF7EE40 0x2F0CE859

void GET_IS_MULTIPLAYER_BRIEF(BOOL p0)

```
Hash collision
```

> SET_CINEMATIC_BUTTON_ACTIVE - 0x51669F7D1FB53D9F 0x3FBC5D00

void SET_CINEMATIC_BUTTON_ACTIVE(BOOL p0)



> IS_CINEMATIC_CAM_RENDERING - 0xB15162CB5826E9E8 0x80471AD9

BOOL IS_CINEMATIC_CAM_RENDERING()



> SHAKE_CINEMATIC_CAM - 0xDCE214D9ED58F3CF 0x61815F31

void SHAKE_CINEMATIC_CAM(char* p0, float p1)

```
p0 argument found in the b617d scripts: 'DRUNK_SHAKE' 
```

> IS_CINEMATIC_CAM_SHAKING - 0xBBC08F6B4CB8FF0A 0x8376D939

BOOL IS_CINEMATIC_CAM_SHAKING()



> SET_CINEMATIC_CAM_SHAKE_AMPLITUDE - 0xC724C701C30B2FE7 0x67510C4B

void SET_CINEMATIC_CAM_SHAKE_AMPLITUDE(float p0)



> STOP_CINEMATIC_CAM_SHAKING - 0x2238E588E588A6D7 0x71C12904

void STOP_CINEMATIC_CAM_SHAKING(BOOL p0)



> _DISABLE_VEHICLE_FIRST_PERSON_CAM_THIS_FRAME - 0xADFF1B2A555F5FBA 0x5AC6DAC9

void _DISABLE_VEHICLE_FIRST_PERSON_CAM_THIS_FRAME()



> 0x62ECFCFDEE7885D6 0x837F8581

void 0x62ECFCFDEE7885D6()



> 0x9E4CFFF989258472 0x65DDE8AF

void 0x9E4CFFF989258472()



> 0xF4F2C0D4EE209E20 0xD75CDD75

void 0xF4F2C0D4EE209E20()



> 0xCA9D2AA3E326D720 0x96A07066

Any 0xCA9D2AA3E326D720()



> 0x4F32C0D5A90A9B40 

Any 0x4F32C0D5A90A9B40()



> CREATE_CINEMATIC_SHOT - 0x741B0129D4560F31 0xAC494E35

void CREATE_CINEMATIC_SHOT(Any p0, int p1, Any p2, Entity entity)



> IS_CINEMATIC_SHOT_ACTIVE - 0xCC9F3371A7C28BC9 0xA4049042

BOOL IS_CINEMATIC_SHOT_ACTIVE(Any p0)



> STOP_CINEMATIC_SHOT - 0x7660C6E75D3A078E 0xD78358C5

void STOP_CINEMATIC_SHOT(Any p0)



> 0xA41BCD7213805AAC 0xFBB85E02

void 0xA41BCD7213805AAC(BOOL p0)



> 0xDC9DA9E8789F5246 0x4938C82F

void 0xDC9DA9E8789F5246()



> SET_CINEMATIC_MODE_ACTIVE - 0xDCF0754AC3D6FD4E 0x2009E747

void SET_CINEMATIC_MODE_ACTIVE(BOOL p0)

```
p0 = 0/1 or true/false

It doesn't seems to work
```

> 0x1F2300CB7FA7B7F6 0x6739AD55

Any 0x1F2300CB7FA7B7F6()



> 0x17FCA7199A530203 

Any 0x17FCA7199A530203()



> STOP_CUTSCENE_CAM_SHAKING - 0xDB629FFD9285FA06 0xF07D603D

void STOP_CUTSCENE_CAM_SHAKING()



> 0x12DED8CA53D47EA5 0x067BA6F5

void 0x12DED8CA53D47EA5(float p0)



> 0x89215EC747DF244A 0xFD99BE2B

Any 0x89215EC747DF244A(float p0, Any p1, float p2, float p3, float p4, float p5, float p6, Any p7, Any p8)



> 0x5A43C76F7FC7BA5F 0xE206C450

void 0x5A43C76F7FC7BA5F()



> _SET_CAM_EFFECT - 0x80C8B1846639BB19 0xB06CCD38

void _SET_CAM_EFFECT(int p0)

```
if p0 is 0, effect is cancelled

if p0 is 1, effect zooms in, gradually tilts cam clockwise apx 30 degrees, wobbles slowly. Motion blur is active until cancelled.

if p0 is 2, effect immediately tilts cam clockwise apx 30 degrees, begins to wobble slowly, then gradually tilts cam back to normal. The wobbling will continue until the effect is cancelled.
```

> 0x5C41E6BABC9E2112 

void 0x5C41E6BABC9E2112(Any p0)



> 0x21E253A7F8DA5DFB 

void 0x21E253A7F8DA5DFB(char* vehicleName)

```
From b617 scripts:

CAM::_21E253A7F8DA5DFB('DINGHY');
CAM::_21E253A7F8DA5DFB('ISSI2');
CAM::_21E253A7F8DA5DFB('SPEEDO');
```

> 0x11FA5D3479C7DD47 

void 0x11FA5D3479C7DD47(Any p0)



> 0xEAF0FA793D05C592 

Any 0xEAF0FA793D05C592()



> 0x8BFCEB5EA1B161B6 

Any 0x8BFCEB5EA1B161B6()



