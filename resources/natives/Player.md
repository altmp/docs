# Player

> GET_PLAYER_PED - 0x43A66C31C68491C0 0x6E31E993

Ped GET_PLAYER_PED(Player player)



> GET_PLAYER_PED_SCRIPT_INDEX - 0x50FAC3A3E030A6E1 0x6AC64990

Ped GET_PLAYER_PED_SCRIPT_INDEX(Player player)

```
Same as GET_PLAYER_PED.
```

> SET_PLAYER_MODEL - 0x00A1CADD00108836 0x774A4C54

void SET_PLAYER_MODEL(Player player, Hash model)



> CHANGE_PLAYER_PED - 0x048189FAC643DEEE 0xBE515485

void CHANGE_PLAYER_PED(Player player, Ped ped, BOOL b2, BOOL b3)

```
b2 and/or b3 maybe got something to do with keeping values from the last ped. Both of them set to 1 works great. 

Examples from the decompiled scripts:

PLAYER::CHANGE_PLAYER_PED(PLAYER::PLAYER_ID(), l_5C0[4/*14*/], 0, 1);
PLAYER::CHANGE_PLAYER_PED(PLAYER::PLAYER_ID(), a_0[a_0._f7/*1*/], a_2, 0);


===========================================================
The only way I ever got this to work in GTA Online once is by setting both to 0, 0. However, when you switch from your online character to whomever, your character will start walking away 'as if you left the game.' If from there you attempt to call this native once more to switch back to you online ped. You will freeze or if you try changing to another ped. I've tried all posibilities so far.
1, 1 (Freeze), 0, 0(Works Once), 1, 0 &amp; 0, 1 (Freeze). Note of course trying to call this on another online player will crash. Anyone have any idea if implementing a blr within the xex itself on a possible check if it would prevent this freezing?
===========================================================
```

> GET_PLAYER_RGB_COLOUR - 0xE902EF951DCE178F 0x6EF43BBB

void GET_PLAYER_RGB_COLOUR(Player player, int* r, int* g, int* b)



> GET_NUMBER_OF_PLAYERS - 0x407C7F91DDB46C16 0x4C1B8867

int GET_NUMBER_OF_PLAYERS()

```
Gets the number of players in the current session.
If not multiplayer, always returns 1.
```

> GET_PLAYER_TEAM - 0x37039302F4E0A008 0x9873E404

int GET_PLAYER_TEAM(Player player)

```
Gets the player's team.
Does nothing in singleplayer.
```

> SET_PLAYER_TEAM - 0x0299FA38396A4940 0x725ADCF2

void SET_PLAYER_TEAM(Player player, int team)

```
Set player team on deathmatch and last team standing..
```

> GET_PLAYER_NAME - 0x6D0DE6A7B5DA71F8 0x406B4B20

char* GET_PLAYER_NAME(Player player)



> GET_WANTED_LEVEL_RADIUS - 0x085DEB493BE80812 0x1CF7D7DA

float GET_WANTED_LEVEL_RADIUS(Player player)

```
Remnant from GTA IV. Does nothing in GTA V.
```

> GET_PLAYER_WANTED_CENTRE_POSITION - 0x0C92BA89F1AF26F8 0x821F2D2C

Vector3 GET_PLAYER_WANTED_CENTRE_POSITION(Player player)



> SET_PLAYER_WANTED_CENTRE_POSITION - 0x520E541A97A13354 0xF261633A

void SET_PLAYER_WANTED_CENTRE_POSITION(Player player, float x, float y, float z)

```
# Predominant call signatures
PLAYER::SET_PLAYER_WANTED_CENTRE_POSITION(PLAYER::PLAYER_ID(), ENTITY::GET_ENTITY_COORDS(PLAYER::PLAYER_PED_ID(), 1));

# Parameter value ranges
P0: PLAYER::PLAYER_ID()
P1: ENTITY::GET_ENTITY_COORDS(PLAYER::PLAYER_PED_ID(), 1)
P2: Not set by any call
```

> GET_WANTED_LEVEL_THRESHOLD - 0xFDD179EAF45B556C 0xD9783F6B

int GET_WANTED_LEVEL_THRESHOLD(int wantedLevel)



> SET_PLAYER_WANTED_LEVEL - 0x39FF19C64EF7DA5B 0xB7A0914B

void SET_PLAYER_WANTED_LEVEL(Player player, int wantedLevel, BOOL disableNoMission)

```
Call SET_PLAYER_WANTED_LEVEL_NOW for immediate effect

wantedLevel is an integer value representing 0 to 5 stars even though the game supports the 6th wanted level but no police will appear since no definitions are present for it in the game files

disableNoMission-  Disables When Off Mission- appears to always be false

```

> SET_PLAYER_WANTED_LEVEL_NO_DROP - 0x340E61DE7F471565 0xED6F44F5

void SET_PLAYER_WANTED_LEVEL_NO_DROP(Player player, int wantedLevel, BOOL p2)

```
p2 is always false in R* scripts
```

> SET_PLAYER_WANTED_LEVEL_NOW - 0xE0A7D1E497FFCD6F 0xAF3AFD83

void SET_PLAYER_WANTED_LEVEL_NOW(Player player, BOOL p1)

```
Forces any pending wanted level to be applied to the specified player immediately.

Call SET_PLAYER_WANTED_LEVEL with the desired wanted level, followed by SET_PLAYER_WANTED_LEVEL_NOW.

Second parameter is unknown (always false).
```

> ARE_PLAYER_FLASHING_STARS_ABOUT_TO_DROP - 0xAFAF86043E5874E9 0xE13A71C7

BOOL ARE_PLAYER_FLASHING_STARS_ABOUT_TO_DROP(Player player)



> ARE_PLAYER_STARS_GREYED_OUT - 0x0A6EB355EE14A2DB 0x5E72AB72

BOOL ARE_PLAYER_STARS_GREYED_OUT(Player player)



> SET_DISPATCH_COPS_FOR_PLAYER - 0xDB172424876553F4 0x48A18913

void SET_DISPATCH_COPS_FOR_PLAYER(Player player, BOOL toggle)



> IS_PLAYER_WANTED_LEVEL_GREATER - 0x238DB2A2C23EE9EF 0x589A2661

BOOL IS_PLAYER_WANTED_LEVEL_GREATER(Player player, int wantedLevel)



> CLEAR_PLAYER_WANTED_LEVEL - 0xB302540597885499 0x54EA5BCC

void CLEAR_PLAYER_WANTED_LEVEL(Player player)

```
This executes at the same as speed as PLAYER::SET_PLAYER_WANTED_LEVEL(player, 0, false);

PLAYER::GET_PLAYER_WANTED_LEVEL(player); executes in less than half the time. Which means that it's worth first checking if the wanted level needs to be cleared before clearing. However, this is mostly about good code practice and can important in other situations. The difference in time in this example is negligible. 
```

> IS_PLAYER_DEAD - 0x424D4687FA1E5652 0x140CA5A8

BOOL IS_PLAYER_DEAD(Player player)



> IS_PLAYER_PRESSING_HORN - 0xFA1E2BF8B10598F9 0xED1D1662

BOOL IS_PLAYER_PRESSING_HORN(Player player)



> SET_PLAYER_CONTROL - 0x8D32347D6D4C40A2 0xD17AFCD8

void SET_PLAYER_CONTROL(Player player, BOOL toggle, int possiblyFlags)

```
Flags used in the scripts: 0,4,16,24,32,56,60,64,128,134,256,260,384,512,640,768,896,900,952,1024,1280,2048,2560

Note to people who needs this with camera mods, etc.: 
Flags(0, 4, 16, 24, 32, 56, 60, 64, 128, 134, 512, 640, 1024, 2048, 2560)
- Disables camera rotation as well.
Flags(256, 260, 384, 768, 896, 900, 952, 1280)
- Allows camera rotation.
```

> GET_PLAYER_WANTED_LEVEL - 0xE28E54788CE8F12D 0xBDCDD163

int GET_PLAYER_WANTED_LEVEL(Player player)



> SET_MAX_WANTED_LEVEL - 0xAA5F02DB48D704B9 0x665A06F5

void SET_MAX_WANTED_LEVEL(int maxWantedLevel)



> SET_POLICE_RADAR_BLIPS - 0x43286D561B72B8BF 0x8E114B10

void SET_POLICE_RADAR_BLIPS(BOOL toggle)



> SET_POLICE_IGNORE_PLAYER - 0x32C62AA929C2DA6A 0xE6DE71B7

void SET_POLICE_IGNORE_PLAYER(Player player, BOOL toggle)



> IS_PLAYER_PLAYING - 0x5E9564D8246B909A 0xE15D777F

BOOL IS_PLAYER_PLAYING(Player player)

```
Checks whether the specified player has a Ped, the Ped is not dead, is not injured and is not arrested.
```

> SET_EVERYONE_IGNORE_PLAYER - 0x8EEDA153AD141BA4 0xC915285E

void SET_EVERYONE_IGNORE_PLAYER(Player player, BOOL toggle)



> SET_ALL_RANDOM_PEDS_FLEE - 0x056E0FE8534C2949 0x49EAE968

void SET_ALL_RANDOM_PEDS_FLEE(Player player, BOOL toggle)



> SET_ALL_RANDOM_PEDS_FLEE_THIS_FRAME - 0x471D2FF42A94B4F2 0xBF974891

void SET_ALL_RANDOM_PEDS_FLEE_THIS_FRAME(Player player)



> SET_HUD_ANIM_STOP_LEVEL - 0xDE45D1A1EF45EE61 0x274631FE

void SET_HUD_ANIM_STOP_LEVEL(Player player, BOOL toggle)

```
hash collision
```

> SET_AREAS_GENERATOR_ORIENTATION - 0xC3376F42B1FACCC6 0x02DF7AF4

void SET_AREAS_GENERATOR_ORIENTATION(Player player)

```
- This is called after SET_ALL_RANDOM_PEDS_FLEE_THIS_FRAME
hash collision
```

> SET_IGNORE_LOW_PRIORITY_SHOCKING_EVENTS - 0x596976B02B6B5700 0xA3D675ED

void SET_IGNORE_LOW_PRIORITY_SHOCKING_EVENTS(Player player, BOOL toggle)



> SET_WANTED_LEVEL_MULTIPLIER - 0x020E5F00CDA207BA 0x1359292F

void SET_WANTED_LEVEL_MULTIPLIER(float multiplier)



> SET_WANTED_LEVEL_DIFFICULTY - 0x9B0BB33B04405E7A 0xB552626C

void SET_WANTED_LEVEL_DIFFICULTY(Player player, float difficulty)

```
Max value is 1.0
```

> RESET_WANTED_LEVEL_DIFFICULTY - 0xB9D0DD990DC141DD 0xA64C378D

void RESET_WANTED_LEVEL_DIFFICULTY(Player player)



> START_FIRING_AMNESTY - 0xBF9BD71691857E48 0x5F8A22A6

void START_FIRING_AMNESTY(int duration)



> REPORT_CRIME - 0xE9B09589827545E7 0xD8EB3A44

void REPORT_CRIME(Player player, int crimeType, int wantedLvlThresh)

```
PLAYER::REPORT_CRIME(PLAYER::PLAYER_ID(), 37, PLAYER::GET_WANTED_LEVEL_THRESHOLD(1));

From am_armybase.ysc.c4:

PLAYER::REPORT_CRIME(PLAYER::PLAYER_ID(4), 36, PLAYER::GET_WANTED_LEVEL_THRESHOLD(4));

-----

This was taken from the GTAV.exe v1.334. The function is called sub_140592CE8. For a full decompilation of the function, see here: pastebin.com/09qSMsN7 

-----
crimeType:
1: Firearms possession
2: Person running a red light ('5-0-5')
3: Reckless driver
4: Speeding vehicle (a '5-10')
5: Traffic violation (a '5-0-5')
6: Motorcycle rider without a helmet
7: Vehicle theft (a '5-0-3')
8: Grand Theft Auto
9: ???
10: ???
11: Assault on a civilian (a '2-40')
12: Assault on an officer
13: Assault with a deadly weapon (a '2-45')
14: Officer shot (a '2-45')
15: Pedestrian struck by a vehicle
16: Officer struck by a vehicle
17: Helicopter down (an 'AC'?)
18: Civilian on fire (a '2-40')
19: Officer set on fire (a '10-99')
20: Car on fire
21: Air unit down (an 'AC'?)
22: An explosion (a '9-96')
23: A stabbing (a '2-45') (also something else I couldn't understand)
24: Officer stabbed (also something else I couldn't understand)
25: Attack on a vehicle ('MDV'?)
26: Damage to property
27: Suspect threatening officer with a firearm
28: Shots fired
29: ???
30: ???
31: ???
32: ???
33: ???
34: A '2-45'
35: ???
36: A '9-25'
37: ???
38: ???
39: ???
40: ???
41: ???
42: ???
43: Possible disturbance
44: Civilian in need of assistance
45: ???
46: ???
```

> RESERVE_ENTITY_EXPLODES_ON_HIGH_EXPLOSION_COMBO - 0x9A987297ED8BD838 0x59B5C2A2

void RESERVE_ENTITY_EXPLODES_ON_HIGH_EXPLOSION_COMBO(Player player, int p1)

```
This was previously named as 'RESERVE_ENTITY_EXPLODES_ON_HIGH_EXPLOSION_COMBO'
which is obviously incorrect.

Seems to only appear in scripts used in Singleplayer. p1 ranges from 2 - 46.


I assume this switches the crime type
```

> 0xBC9490CA15AEA8FB 0x6B34A160

void 0xBC9490CA15AEA8FB(Player player)

```
Seems to only appear in scripts used in Singleplayer.

AI_PHONE_ARGS is a hash collision!!!
```

> 0x4669B3ED80F24B4E 0xB9FB142F

Any 0x4669B3ED80F24B4E(Player player)

```
This has been found in use in the decompiled files.
```

> 0xAD73CE5A09E42D12 0x85725848

Any 0xAD73CE5A09E42D12(Player player)

```
This has been found in use in the decompiled files.
```

> 0x36F1B38855F2A8DF 0x3A7E5FB6

void 0x36F1B38855F2A8DF(Player player)



> 0xDC64D2C53493ED12 0xD15C4B1C

Any 0xDC64D2C53493ED12(Player player)

```
Has something to do with police.
```

> 0xB45EFF719D8427A6 0xBF6993C7

void 0xB45EFF719D8427A6(float p0)

```
PLAYER::0xBF6993C7(rPtr((&amp;l_122) + 71)); // Found in decompilation

***

In 'am_hold_up.ysc' used once:

l_8d._f47 = GAMEPLAY::GET_RANDOM_FLOAT_IN_RANGE(18.0, 28.0);
PLAYER::_B45EFF719D8427A6((l_8d._f47));
```

> 0x0032A6DBA562C518 0x47CAB814

void 0x0032A6DBA562C518()

```
2 matches in 1 script - am_hold_up
```

> CAN_PLAYER_START_MISSION - 0xDE7465A27D403C06 0x39E3CB3F

BOOL CAN_PLAYER_START_MISSION(Player player)



> IS_PLAYER_READY_FOR_CUTSCENE - 0x908CBECC2CAA3690 0xBB77E9CD

BOOL IS_PLAYER_READY_FOR_CUTSCENE(Player player)



> IS_PLAYER_TARGETTING_ENTITY - 0x7912F7FC4F6264B6 0xF3240B77

BOOL IS_PLAYER_TARGETTING_ENTITY(Player player, Entity entity)



> GET_PLAYER_TARGET_ENTITY - 0x13EDE1A5DBF797C9 0xF6AAA2D7

BOOL GET_PLAYER_TARGET_ENTITY(Player player, Entity* entity)

```
Assigns the handle of locked-on melee target to *entity that you pass it.
Returns false if no entity found.
```

> IS_PLAYER_FREE_AIMING - 0x2E397FD2ECD37C87 0x1DEC67B7

BOOL IS_PLAYER_FREE_AIMING(Player player)

```
Gets a value indicating whether the specified player is currently aiming freely.
```

> IS_PLAYER_FREE_AIMING_AT_ENTITY - 0x3C06B5C839B38F7B 0x7D80EEAA

BOOL IS_PLAYER_FREE_AIMING_AT_ENTITY(Player player, Entity entity)

```
Gets a value indicating whether the specified player is currently aiming freely at the specified entity.
```

> GET_ENTITY_PLAYER_IS_FREE_AIMING_AT - 0x2975C866E6713290 0x8866D9D0

BOOL GET_ENTITY_PLAYER_IS_FREE_AIMING_AT(Player player, Entity* entity)

```
Returns TRUE if it found an entity in your crosshair within range of your weapon. Assigns the handle of the target to the *entity that you pass it.
Returns false if no entity found.
```

> SET_PLAYER_LOCKON_RANGE_OVERRIDE - 0x29961D490E5814FD 0x74D42C03

void SET_PLAYER_LOCKON_RANGE_OVERRIDE(Player player, float range)

```
Affects the range of auto aim target.
```

> SET_PLAYER_CAN_DO_DRIVE_BY - 0x6E8834B52EC20C77 0xF4D99685

void SET_PLAYER_CAN_DO_DRIVE_BY(Player player, BOOL toggle)

```
Set whether this player should be able to do drive-bys.

'A drive-by is when a ped is aiming/shooting from vehicle. This includes middle finger taunts. By setting this value to false I confirm the player is unable to do all that. Tested on tick.' - THEAETIK

```

> SET_PLAYER_CAN_BE_HASSLED_BY_GANGS - 0xD5E460AD7020A246 0x71B305BB

void SET_PLAYER_CAN_BE_HASSLED_BY_GANGS(Player player, BOOL toggle)

```
Sets whether this player can be hassled by gangs.
```

> SET_PLAYER_CAN_USE_COVER - 0xD465A8599DFF6814 0x13CAFAFA

Any SET_PLAYER_CAN_USE_COVER(Player player, BOOL toggle)

```
Sets whether this player can take cover.
```

> GET_MAX_WANTED_LEVEL - 0x462E0DB9B137DC5F 0x457F1E44

int GET_MAX_WANTED_LEVEL()

```
Gets the maximum wanted level the player can get.
Ranges from 0 to 5.
```

> IS_PLAYER_TARGETTING_ANYTHING - 0x78CFE51896B6B8A4 0x456DB50D

BOOL IS_PLAYER_TARGETTING_ANYTHING(Player player)



> SET_PLAYER_SPRINT - 0xA01B8075D8B92DF4 0x7DD7900C

void SET_PLAYER_SPRINT(Player player, BOOL toggle)



> RESET_PLAYER_STAMINA - 0xA6F312FCCE9C1DFE 0xC0445A9C

void RESET_PLAYER_STAMINA(Player player)



> RESTORE_PLAYER_STAMINA - 0xA352C1B864CAFD33 0x62A93608

void RESTORE_PLAYER_STAMINA(Player player, float p1)



> GET_PLAYER_SPRINT_STAMINA_REMAINING - 0x3F9F16F8E65A7ED7 0x47017C90

float GET_PLAYER_SPRINT_STAMINA_REMAINING(Player player)



> GET_PLAYER_SPRINT_TIME_REMAINING - 0x1885BC9B108B4C99 0x40E80543

float GET_PLAYER_SPRINT_TIME_REMAINING(Player player)



> GET_PLAYER_UNDERWATER_TIME_REMAINING - 0xA1FCF8E6AF40B731 0x1317125A

float GET_PLAYER_UNDERWATER_TIME_REMAINING(Player player)



> GET_PLAYER_GROUP - 0x0D127585F77030AF 0xA5EDCDE8

int GET_PLAYER_GROUP(Player player)

```
Returns the group ID the player is member of.
```

> GET_PLAYER_MAX_ARMOUR - 0x92659B4CE1863CB3 0x02A50657

int GET_PLAYER_MAX_ARMOUR(Player player)



> IS_PLAYER_CONTROL_ON - 0x49C32D60007AFA47 0x618857F2

BOOL IS_PLAYER_CONTROL_ON(Player player)

```
Can the player control himself, used to disable controls for player for things like a cutscene.

---

You can't disable controls with this, use SET_PLAYER_CONTROL(...) for this. 
```

> _IS_PLAYER_CAM_CONTROL_DISABLED - 0x7C814D2FB49F40C0 

BOOL _IS_PLAYER_CAM_CONTROL_DISABLED()

```
Returns true when the player is not able to control the cam i.e. when running a benchmark test, switching the player or viewing a cutscene.

Note: I am not 100% sure if the native actually checks if the cam control is disabled but it seems promising.
```

> IS_PLAYER_SCRIPT_CONTROL_ON - 0x8A876A65283DD7D7 0x61B00A84

BOOL IS_PLAYER_SCRIPT_CONTROL_ON(Player player)



> IS_PLAYER_CLIMBING - 0x95E8F73DC65EFB9C 0x4A9E9AE0

BOOL IS_PLAYER_CLIMBING(Player player)



> IS_PLAYER_BEING_ARRESTED - 0x388A47C51ABDAC8E 0x7F6A60D3

BOOL IS_PLAYER_BEING_ARRESTED(Player player, BOOL atArresting)

```
Return true while player is being arrested / busted.

If atArresting is set to 1, this function will return 1 when player is being arrested (while player is putting his hand up, but still have control)

If atArresting is set to 0, this function will return 1 only when the busted screen is shown.
```

> RESET_PLAYER_ARREST_STATE - 0x2D03E13C460760D6 0x453C7CAB

void RESET_PLAYER_ARREST_STATE(Player player)



> GET_PLAYERS_LAST_VEHICLE - 0xB6997A7EB3F5C8C0 0xE2757AC1

Vehicle GET_PLAYERS_LAST_VEHICLE()

```
Alternative: GET_VEHICLE_PED_IS_IN(PLAYER_PED_ID(), 1);
```

> GET_PLAYER_INDEX - 0xA5EDC40EF369B48D 0x309BBDC1

Player GET_PLAYER_INDEX()

```
Returns the same as PLAYER_ID and NETWORK_PLAYER_ID_TO_INT
```

> INT_TO_PLAYERINDEX - 0x41BD2A6B006AF756 0x98DD98F1

Player INT_TO_PLAYERINDEX(int value)

```
Simply returns whatever is passed to it (Regardless of whether the handle is valid or not).
```

> INT_TO_PARTICIPANTINDEX - 0x9EC6603812C24710 0x98F3B274

int INT_TO_PARTICIPANTINDEX(int value)

```
Simply returns whatever is passed to it (Regardless of whether the handle is valid or not).
--------------------------------------------------------
if (NETWORK::NETWORK_IS_PARTICIPANT_ACTIVE(PLAYER::INT_TO_PARTICIPANTINDEX(i)))

```

> GET_TIME_SINCE_PLAYER_HIT_VEHICLE - 0x5D35ECF3A81A0EE0 0x6E9B8B9E

int GET_TIME_SINCE_PLAYER_HIT_VEHICLE(Player player)



> GET_TIME_SINCE_PLAYER_HIT_PED - 0xE36A25322DC35F42 0xB6209195

int GET_TIME_SINCE_PLAYER_HIT_PED(Player player)



> GET_TIME_SINCE_PLAYER_DROVE_ON_PAVEMENT - 0xD559D2BE9E37853B 0x8836E732

int GET_TIME_SINCE_PLAYER_DROVE_ON_PAVEMENT(Player player)



> GET_TIME_SINCE_PLAYER_DROVE_AGAINST_TRAFFIC - 0xDB89591E290D9182 0x9F27D00E

int GET_TIME_SINCE_PLAYER_DROVE_AGAINST_TRAFFIC(Player player)



> IS_PLAYER_FREE_FOR_AMBIENT_TASK - 0xDCCFD3F106C36AB4 0x85C7E232

BOOL IS_PLAYER_FREE_FOR_AMBIENT_TASK(Player player)



> PLAYER_ID - 0x4F8644AF03D0E0D6 0x8AEA886C

Player PLAYER_ID()

```
This returns YOUR 'identity' as a Player type.

Always returns 0 in story mode.
```

> PLAYER_PED_ID - 0xD80958FC74E988A6 0xFA92E226

Ped PLAYER_PED_ID()

```
Returns current player ped
```

> NETWORK_PLAYER_ID_TO_INT - 0xEE68096F9F37341E 0x8DD5B838

int NETWORK_PLAYER_ID_TO_INT()

```
Does exactly the same thing as PLAYER_ID()
```

> HAS_FORCE_CLEANUP_OCCURRED - 0xC968670BFACE42D9 0x4B37333C

BOOL HAS_FORCE_CLEANUP_OCCURRED(int cleanupFlags)



> FORCE_CLEANUP - 0xBC8983F38F78ED51 0xFDAAEA2B

void FORCE_CLEANUP(int cleanupFlags)

```
used with 1,2,8,64,128 in the scripts
```

> FORCE_CLEANUP_FOR_ALL_THREADS_WITH_THIS_NAME - 0x4C68DDDDF0097317 0x04256C73

void FORCE_CLEANUP_FOR_ALL_THREADS_WITH_THIS_NAME(char* name, int cleanupFlags)

```
PLAYER::FORCE_CLEANUP_FOR_ALL_THREADS_WITH_THIS_NAME('pb_prostitute', 1); // Found in decompilation
```

> FORCE_CLEANUP_FOR_THREAD_WITH_THIS_ID - 0xF745B37630DF176B 0x882D3EB3

void FORCE_CLEANUP_FOR_THREAD_WITH_THIS_ID(int id, int cleanupFlags)



> GET_CAUSE_OF_MOST_RECENT_FORCE_CLEANUP - 0x9A41CF4674A12272 0x39AA9FC8

int GET_CAUSE_OF_MOST_RECENT_FORCE_CLEANUP()



> SET_PLAYER_MAY_ONLY_ENTER_THIS_VEHICLE - 0x8026FF78F208978A 0xA454DD29

void SET_PLAYER_MAY_ONLY_ENTER_THIS_VEHICLE(Player player, Vehicle vehicle)



> SET_PLAYER_MAY_NOT_ENTER_ANY_VEHICLE - 0x1DE37BBF9E9CC14A 0xAF7AFCC4

void SET_PLAYER_MAY_NOT_ENTER_ANY_VEHICLE(Player player)



> GIVE_ACHIEVEMENT_TO_PLAYER - 0xBEC7076D64130195 0x822BC992

BOOL GIVE_ACHIEVEMENT_TO_PLAYER(int achievement)

```
Achievements from 0-57


more achievements came with update 1.29 (freemode events update), I'd say that they now go to 60, but I'll need to check.
```

> 0xC2AFFFDABBDC2C5C 

BOOL 0xC2AFFFDABBDC2C5C(Any p0, Any p1)

```
This seems to be related to Steam achievements.
```

> 0x1C186837D0619335 

Cam 0x1C186837D0619335(Any p0)



> HAS_ACHIEVEMENT_BEEN_PASSED - 0x867365E111A3B6EB 0x136A5BE9

BOOL HAS_ACHIEVEMENT_BEEN_PASSED(int achievement)



> IS_PLAYER_ONLINE - 0xF25D331DC2627BBC 0x9FAB6729

BOOL IS_PLAYER_ONLINE()

```
Returns TRUE if the game is in online mode and FALSE if in offline mode.

This is an alias for NETWORK_IS_SIGNED_ONLINE.
```

> IS_PLAYER_LOGGING_IN_NP - 0x74556E1420867ECA 0x8F72FAD0

BOOL IS_PLAYER_LOGGING_IN_NP()

```
MulleDK19: This function is hard-coded to always return 0.
```

> DISPLAY_SYSTEM_SIGNIN_UI - 0x94DD7888C10A979E 0x4264CED2

void DISPLAY_SYSTEM_SIGNIN_UI(BOOL unk)

```
Purpose of the BOOL currently unknown.
Both, true and false, work
```

> IS_SYSTEM_UI_BEING_DISPLAYED - 0x5D511E3867C87139 0xE495B6DA

BOOL IS_SYSTEM_UI_BEING_DISPLAYED()



> SET_PLAYER_INVINCIBLE - 0x239528EACDC3E7DE 0xDFB9A2A2

void SET_PLAYER_INVINCIBLE(Player player, BOOL toggle)

```
Simply sets you as invincible (Health will not deplete).

Use 0x733A643B5B0C53C1 instead if you want Ragdoll enabled, which is equal to:
*(DWORD *)(playerPedAddress + 0x188) |= (1 &lt;&lt; 9);
```

> GET_PLAYER_INVINCIBLE - 0xB721981B2B939E07 0x680C90EE

BOOL GET_PLAYER_INVINCIBLE(Player player)

```
Returns the Player's Invincible status.

This function will always return false if 0x733A643B5B0C53C1 is used to set the invincibility status. To always get the correct result, use this:

	bool IsPlayerInvincible(Player player)
	{
		auto addr = getScriptHandleBaseAddress(GET_PLAYER_PED(player));	

		if (addr)
		{
			DWORD flag = *(DWORD *)(addr + 0x188);
			return ((flag &amp; (1 &lt;&lt; 8)) != 0) || ((flag &amp; (1 &lt;&lt; 9)) != 0);
		}

		return false;
	}


```

> 0xCAC57395B151135F 0x00563E0D

void 0xCAC57395B151135F(Player player, BOOL p1)



> REMOVE_PLAYER_HELMET - 0xF3AC26D3CC576528 0x6255F3B4

Any REMOVE_PLAYER_HELMET(Player player, BOOL p2)



> GIVE_PLAYER_RAGDOLL_CONTROL - 0x3C49C870E66F0A28 0xC7B4D7AC

void GIVE_PLAYER_RAGDOLL_CONTROL(Player player, BOOL toggle)



> SET_PLAYER_LOCKON - 0x5C8B2F450EE4328E 0x0B270E0F

void SET_PLAYER_LOCKON(Player player, BOOL toggle)

```
Example from fm_mission_controler.ysc.c4:

PLAYER::SET_PLAYER_LOCKON(PLAYER::PLAYER_ID(), 1);

All other decompiled scripts using this seem to be using the player id as the first parameter, so I feel the need to confirm it as so.
```

> SET_PLAYER_TARGETING_MODE - 0xB1906895227793F3 0x61CAE253

void SET_PLAYER_TARGETING_MODE(int targetMode)

```
I don't know which number is which mode I'm sure it can easily be found with testing, but scripts showed it's not player. They ask a function which returns this Global (Global_2404048) on in the Xbox360 scripts, then sets the param to either, (0, 1, 2, or 3).
```

> 0x5702B917B99DB1CD 

void 0x5702B917B99DB1CD(Any p0)

```
Jenkins hash: 0x772DA539
```

> 0xB9CF1F793A9F1BF1 

Any 0xB9CF1F793A9F1BF1()



> CLEAR_PLAYER_HAS_DAMAGED_AT_LEAST_ONE_PED - 0xF0B67A4DE6AB5F98 0x1D31CBBD

void CLEAR_PLAYER_HAS_DAMAGED_AT_LEAST_ONE_PED(Player player)



> HAS_PLAYER_DAMAGED_AT_LEAST_ONE_PED - 0x20CE80B0C2BF4ACC 0x14F52453

BOOL HAS_PLAYER_DAMAGED_AT_LEAST_ONE_PED(Player player)



> CLEAR_PLAYER_HAS_DAMAGED_AT_LEAST_ONE_NON_ANIMAL_PED - 0x4AACB96203D11A31 0x7E3BFBC5

void CLEAR_PLAYER_HAS_DAMAGED_AT_LEAST_ONE_NON_ANIMAL_PED(Player player)



> HAS_PLAYER_DAMAGED_AT_LEAST_ONE_NON_ANIMAL_PED - 0xE4B90F367BD81752 0xA3707DFC

BOOL HAS_PLAYER_DAMAGED_AT_LEAST_ONE_NON_ANIMAL_PED(Player player)



> SET_AIR_DRAG_MULTIPLIER_FOR_PLAYERS_VEHICLE - 0xCA7DC8329F0A1E9E 0xF20F72E5

void SET_AIR_DRAG_MULTIPLIER_FOR_PLAYERS_VEHICLE(Player player, float multiplier)

```
This can be between 1.0f - 14.9f 

You can change the max in IDA from 15.0. I say 15.0 as the function blrs if what you input is greater than or equal to 15.0 hence why it's 14.9 max default.


```

> SET_SWIM_MULTIPLIER_FOR_PLAYER - 0xA91C6F0FF7D16A13 0xB986FF47

void SET_SWIM_MULTIPLIER_FOR_PLAYER(Player player, float multiplier)

```
Swim speed multiplier.
Multiplier goes up to 1.49

Just call it one time, it is not required to be called once every tick. - Note copied from below native.

Note: At least the IDA method if you change the max float multiplier from 1.5 it will change it for both this and RUN_SPRINT below. I say 1.5 as the function blrs if what you input is greater than or equal to 1.5 hence why it's 1.49 max default.
```

> SET_RUN_SPRINT_MULTIPLIER_FOR_PLAYER - 0x6DB47AA77FD94E09 0x825423C2

void SET_RUN_SPRINT_MULTIPLIER_FOR_PLAYER(Player player, float multiplier)

```
Multiplier goes up to 1.49 any value above will be completely overruled by the game and the multiplier will not take effect, this can be edited in memory however.

Just call it one time, it is not required to be called once every tick.

Note: At least the IDA method if you change the max float multiplier from 1.5 it will change it for both this and SWIM above. I say 1.5 as the function blrs if what you input is greater than or equal to 1.5 hence why it's 1.49 max default.
```

> GET_TIME_SINCE_LAST_ARREST - 0x5063F92F07C2A316 0x62824EF4

int GET_TIME_SINCE_LAST_ARREST()

```
Returns the time since the character was arrested in (ms) milliseconds.

example

var time = Function.call&lt;int&gt;(Hash.GET_TIME_SINCE_LAST_ARREST();

UI.DrawSubtitle(time.ToString());

if player has not been arrested, the int returned will be -1.
```

> GET_TIME_SINCE_LAST_DEATH - 0xC7034807558DDFCA 0x24BC5AC0

int GET_TIME_SINCE_LAST_DEATH()

```
Returns the time since the character died in (ms) milliseconds.

example

var time = Function.call&lt;int&gt;(Hash.GET_TIME_SINCE_LAST_DEATH();

UI.DrawSubtitle(time.ToString());

if player has not died, the int returned will be -1.
```

> ASSISTED_MOVEMENT_CLOSE_ROUTE - 0xAEBF081FFC0A0E5E 0xF23277F3

void ASSISTED_MOVEMENT_CLOSE_ROUTE()



> ASSISTED_MOVEMENT_FLUSH_ROUTE - 0x8621390F0CDCFE1F 0xD04568B9

void ASSISTED_MOVEMENT_FLUSH_ROUTE()

```
hELP
```

> SET_PLAYER_FORCED_AIM - 0x0FEE4F80AC44A726 0x94E42E2E

void SET_PLAYER_FORCED_AIM(Player player, BOOL toggle)



> SET_PLAYER_FORCED_ZOOM - 0x75E7D505F2B15902 0xB0C576CB

void SET_PLAYER_FORCED_ZOOM(Player player, BOOL toggle)



> SET_PLAYER_FORCE_SKIP_AIM_INTRO - 0x7651BC64AE59E128 0x374F42F0

void SET_PLAYER_FORCE_SKIP_AIM_INTRO(Player player, BOOL toggle)



> DISABLE_PLAYER_FIRING - 0x5E6CC07646BBEAB8 0x30CB28CB

void DISABLE_PLAYER_FIRING(Player player, BOOL toggle)

```
Inhibits the player from using any method of combat including melee and firearms.

NOTE: Only disables the firing for one frame
```

> 0xB885852C39CC265D 

void 0xB885852C39CC265D()

```
Old Gen: 0x47D6004E

Disables something. Used only once in R* scripts (freemode.ysc).
```

> SET_DISABLE_AMBIENT_MELEE_MOVE - 0x2E8AABFA40A84F8C 0xCCD937E7

void SET_DISABLE_AMBIENT_MELEE_MOVE(Player player, BOOL toggle)



> SET_PLAYER_MAX_ARMOUR - 0x77DFCCF5948B8C71 0xC6C3C53B

void SET_PLAYER_MAX_ARMOUR(Player player, int value)

```
Default is 100. Use player id and not ped id. For instance: PLAYER::SET_PLAYER_MAX_ARMOUR(PLAYER::PLAYER_ID(), 100); // main_persistent.ct4
```

> SPECIAL_ABILITY_DEACTIVATE - 0xD6A953C6D1492057 0x80C2AB09

void SPECIAL_ABILITY_DEACTIVATE(Player player)



> SPECIAL_ABILITY_DEACTIVATE_FAST - 0x9CB5CE07A3968D5A 0x0751908A

void SPECIAL_ABILITY_DEACTIVATE_FAST(Player player)



> SPECIAL_ABILITY_RESET - 0x375F0E738F861A94 0xA7D8BCD3

void SPECIAL_ABILITY_RESET(Player player)



> 0xC9A763D8FE87436A 0x4136829A

void 0xC9A763D8FE87436A(Player player)

```
Seems to be called before SPECIAL_ABILITY_DEACTIVATE. Needs more research.

SPECIAL_ABILITY_CHARGE_*
```

> SPECIAL_ABILITY_CHARGE_SMALL - 0x2E7B9B683481687D 0x6F463F56

void SPECIAL_ABILITY_CHARGE_SMALL(Player player, BOOL p1, BOOL p2)

```
Every occurrence of p1 &amp; p2 were both true.
```

> SPECIAL_ABILITY_CHARGE_MEDIUM - 0xF113E3AA9BC54613 0xAB55D8F3

void SPECIAL_ABILITY_CHARGE_MEDIUM(Player player, BOOL p1, BOOL p2)

```
Only 1 match. Both p1 &amp; p2 were true.
```

> SPECIAL_ABILITY_CHARGE_LARGE - 0xF733F45FA4497D93 0xF440C04D

void SPECIAL_ABILITY_CHARGE_LARGE(Player player, BOOL p1, BOOL p2)

```
2 matches. p1 was always true.
```

> SPECIAL_ABILITY_CHARGE_CONTINUOUS - 0xED481732DFF7E997 0x5FEE98A2

void SPECIAL_ABILITY_CHARGE_CONTINUOUS(Player player, BOOL p1)

```
p1 appears to always be 1 (only comes up twice)
```

> SPECIAL_ABILITY_CHARGE_ABSOLUTE - 0xB7B0870EB531D08D 0x72429998

void SPECIAL_ABILITY_CHARGE_ABSOLUTE(Player player, int p1, BOOL p2)

```
p1 appears as 5, 10, 15, 25, or 30. p2 is always true.
```

> SPECIAL_ABILITY_CHARGE_NORMALIZED - 0xA0696A65F009EE18 0x8C7E68C1

void SPECIAL_ABILITY_CHARGE_NORMALIZED(Player player, float normalizedValue, BOOL p2)

```

normalizedValue is from 0.0 - 1.0
p2 is always 1
```

> SPECIAL_ABILITY_FILL_METER - 0x3DACA8DDC6FD4980 0xB71589DA

void SPECIAL_ABILITY_FILL_METER(Player player, BOOL p1)

```
Also known as _RECHARGE_SPECIAL_ABILITY
```

> SPECIAL_ABILITY_DEPLETE_METER - 0x1D506DBBBC51E64B 0x9F80F6DF

void SPECIAL_ABILITY_DEPLETE_METER(Player player, BOOL p1)

```
p1 was always true.
```

> SPECIAL_ABILITY_LOCK - 0x6A09D0D590A47D13 0x1B7BB388

void SPECIAL_ABILITY_LOCK(Hash playerModel)



> SPECIAL_ABILITY_UNLOCK - 0xF145F3BE2EFA9A3B 0x1FDB2919

void SPECIAL_ABILITY_UNLOCK(Hash playerModel)



> IS_SPECIAL_ABILITY_UNLOCKED - 0xC6017F6A6CDFA694 0xC9C75E82

BOOL IS_SPECIAL_ABILITY_UNLOCKED(Hash playerModel)



> IS_SPECIAL_ABILITY_ACTIVE - 0x3E5F7FC85D854E15 0x1B17E334

BOOL IS_SPECIAL_ABILITY_ACTIVE(Player player)



> IS_SPECIAL_ABILITY_METER_FULL - 0x05A1FE504B7F2587 0x2E19D7F6

BOOL IS_SPECIAL_ABILITY_METER_FULL(Player player)



> ENABLE_SPECIAL_ABILITY - 0x181EC197DAEFE121 0xC86C1B4E

void ENABLE_SPECIAL_ABILITY(Player player, BOOL toggle)



> IS_SPECIAL_ABILITY_ENABLED - 0xB1D200FE26AEF3CB 0xC01238CC

BOOL IS_SPECIAL_ABILITY_ENABLED(Player player)



> SET_SPECIAL_ABILITY_MULTIPLIER - 0xA49C426ED0CA4AB7 0xFF1BC556

void SET_SPECIAL_ABILITY_MULTIPLIER(float multiplier)



> 0xFFEE8FA29AB9A18E 0x5D0FE25B

void 0xFFEE8FA29AB9A18E(Player player)



> 0x5FC472C501CCADB3 0x46E7E31D

BOOL 0x5FC472C501CCADB3(Player player)



> 0xF10B44FD479D69F3 0x1E359CC8

BOOL 0xF10B44FD479D69F3(Player player, int p1)

```
Only 1 occurrence. p1 was 2.
```

> 0xDD2620B7B9D16FF1 0x8CB53C9F

BOOL 0xDD2620B7B9D16FF1(Player player, float p1)

```
2 occurrences in agency_heist3a. p1 was 0.7f then 0.4f.
```

> START_PLAYER_TELEPORT - 0xAD15F075A4DA0FDE 0xC552E06C

void START_PLAYER_TELEPORT(Player player, float x, float y, float z, float heading, BOOL p5, BOOL p6, BOOL p7)



> _HAS_PLAYER_TELEPORT_FINISHED - 0xE23D5873C2394C61 

BOOL _HAS_PLAYER_TELEPORT_FINISHED(Player player)



> STOP_PLAYER_TELEPORT - 0xC449EDED9D73009C 0x86AB8DBB

void STOP_PLAYER_TELEPORT()

```
Disables the player's teleportation
```

> IS_PLAYER_TELEPORT_ACTIVE - 0x02B15662D7F8886F 0x3A11D118

BOOL IS_PLAYER_TELEPORT_ACTIVE()



> GET_PLAYER_CURRENT_STEALTH_NOISE - 0x2F395D61F3A1F877 0xC3B02362

float GET_PLAYER_CURRENT_STEALTH_NOISE(Player player)



> SET_PLAYER_HEALTH_RECHARGE_MULTIPLIER - 0x5DB660B38DD98A31 0x45514731

void SET_PLAYER_HEALTH_RECHARGE_MULTIPLIER(Player player, float regenRate)



> SET_PLAYER_WEAPON_DAMAGE_MODIFIER - 0xCE07B9F7817AADA3 0xB02C2F39

void SET_PLAYER_WEAPON_DAMAGE_MODIFIER(Player player, float damageAmount)

```
This modifies the damage value of your weapon. Whether it is a multiplier or base damage is unknown. 

Based on tests, it is unlikely to be a multiplier.
```

> SET_PLAYER_WEAPON_DEFENSE_MODIFIER - 0x2D83BC011CA14A3C 0xAE446344

void SET_PLAYER_WEAPON_DEFENSE_MODIFIER(Player player, float modifier)



> SET_PLAYER_MELEE_WEAPON_DAMAGE_MODIFIER - 0x4A3DC7ECCC321032 0x362E69AD

void SET_PLAYER_MELEE_WEAPON_DAMAGE_MODIFIER(Player player, float modifier)



> SET_PLAYER_MELEE_WEAPON_DEFENSE_MODIFIER - 0xAE540335B4ABC4E2 0x9F3D577F

void SET_PLAYER_MELEE_WEAPON_DEFENSE_MODIFIER(Player player, float modifier)



> SET_PLAYER_VEHICLE_DAMAGE_MODIFIER - 0xA50E117CDDF82F0C 0x823ECA63

void SET_PLAYER_VEHICLE_DAMAGE_MODIFIER(Player player, float damageAmount)



> SET_PLAYER_VEHICLE_DEFENSE_MODIFIER - 0x4C60E6EFDAFF2462 0xA16626C7

void SET_PLAYER_VEHICLE_DEFENSE_MODIFIER(Player player, float modifier)



> SET_PLAYER_PARACHUTE_TINT_INDEX - 0xA3D0E54541D9A5E5 0x8EA12EDB

void SET_PLAYER_PARACHUTE_TINT_INDEX(Player player, int tintIndex)

```
Tints:
	None = -1,
	Rainbow = 0,
	Red = 1,
	SeasideStripes = 2,
	WidowMaker = 3,
	Patriot = 4,
	Blue = 5,
	Black = 6,
	Hornet = 7,
	AirFocce = 8,
	Desert = 9,
	Shadow = 10,
	HighAltitude = 11,
	Airbone = 12,
	Sunrise = 13,

```

> GET_PLAYER_PARACHUTE_TINT_INDEX - 0x75D3F7A1B0D9B145 0x432B0509

void GET_PLAYER_PARACHUTE_TINT_INDEX(Player player, int* tintIndex)

```
Tints:
	None = -1,
	Rainbow = 0,
	Red = 1,
	SeasideStripes = 2,
	WidowMaker = 3,
	Patriot = 4,
	Blue = 5,
	Black = 6,
	Hornet = 7,
	AirFocce = 8,
	Desert = 9,
	Shadow = 10,
	HighAltitude = 11,
	Airbone = 12,
	Sunrise = 13,
```

> SET_PLAYER_RESERVE_PARACHUTE_TINT_INDEX - 0xAF04C87F5DC1DF38 0x70689638

void SET_PLAYER_RESERVE_PARACHUTE_TINT_INDEX(Player player, int index)

```
Tints:
	None = -1,
	Rainbow = 0,
	Red = 1,
	SeasideStripes = 2,
	WidowMaker = 3,
	Patriot = 4,
	Blue = 5,
	Black = 6,
	Hornet = 7,
	AirFocce = 8,
	Desert = 9,
	Shadow = 10,
	HighAltitude = 11,
	Airbone = 12,
	Sunrise = 13,
```

> GET_PLAYER_RESERVE_PARACHUTE_TINT_INDEX - 0xD5A016BC3C09CF40 0x77B8EF01

void GET_PLAYER_RESERVE_PARACHUTE_TINT_INDEX(Player player, int* index)

```
Tints:
	None = -1,
	Rainbow = 0,
	Red = 1,
	SeasideStripes = 2,
	WidowMaker = 3,
	Patriot = 4,
	Blue = 5,
	Black = 6,
	Hornet = 7,
	AirFocce = 8,
	Desert = 9,
	Shadow = 10,
	HighAltitude = 11,
	Airbone = 12,
	Sunrise = 13,
```

> SET_PLAYER_PARACHUTE_PACK_TINT_INDEX - 0x93B0FB27C9A04060 0xD79D5D1B

void SET_PLAYER_PARACHUTE_PACK_TINT_INDEX(Player player, int tintIndex)

```
tints 0- 13
0 - unkown
1 - unkown
2 - unkown
3 - unkown
4 - unkown
```

> GET_PLAYER_PARACHUTE_PACK_TINT_INDEX - 0x6E9C742F340CE5A2 0x4E418E13

void GET_PLAYER_PARACHUTE_PACK_TINT_INDEX(Player player, int* tintIndex)



> SET_PLAYER_HAS_RESERVE_PARACHUTE - 0x7DDAB28D31FAC363 0xA3E4798E

void SET_PLAYER_HAS_RESERVE_PARACHUTE(Player player)



> GET_PLAYER_HAS_RESERVE_PARACHUTE - 0x5DDFE2FF727F3CA3 0x30DA1DA1

BOOL GET_PLAYER_HAS_RESERVE_PARACHUTE(Player player)



> SET_PLAYER_CAN_LEAVE_PARACHUTE_SMOKE_TRAIL - 0xF401B182DBA8AF53 0x832DEB7A

void SET_PLAYER_CAN_LEAVE_PARACHUTE_SMOKE_TRAIL(Player player, BOOL enabled)



> SET_PLAYER_PARACHUTE_SMOKE_TRAIL_COLOR - 0x8217FD371A4625CF 0x14FE9264

void SET_PLAYER_PARACHUTE_SMOKE_TRAIL_COLOR(Player player, int r, int g, int b)



> GET_PLAYER_PARACHUTE_SMOKE_TRAIL_COLOR - 0xEF56DBABD3CD4887 0xF66E5CDD

void GET_PLAYER_PARACHUTE_SMOKE_TRAIL_COLOR(Player player, int* r, int* g, int* b)



> SET_PLAYER_RESET_FLAG_PREFER_REAR_SEATS - 0x11D5F725F0E780E0 0x725C6174

void SET_PLAYER_RESET_FLAG_PREFER_REAR_SEATS(Player player, int flags)

```
example:

flags: 0-6

PLAYER::SET_PLAYER_RESET_FLAG_PREFER_REAR_SEATS(PLAYER::PLAYER_ID(), 6);

wouldnt the flag be the seatIndex?
```

> SET_PLAYER_NOISE_MULTIPLIER - 0xDB89EF50FF25FCE9 0x15786DD1

void SET_PLAYER_NOISE_MULTIPLIER(Player player, float multiplier)



> SET_PLAYER_SNEAKING_NOISE_MULTIPLIER - 0xB2C1A29588A9F47C 0x8D2D89C4

void SET_PLAYER_SNEAKING_NOISE_MULTIPLIER(Player player, float multiplier)

```
Values around 1.0f to 2.0f used in game scripts.
```

> CAN_PED_HEAR_PLAYER - 0xF297383AA91DCA29 0x1C70B2EB

BOOL CAN_PED_HEAR_PLAYER(Player player, Ped ped)



> SIMULATE_PLAYER_INPUT_GAIT - 0x477D5D63E63ECA5D 0x0D77CC34

void SIMULATE_PLAYER_INPUT_GAIT(Player player, float amount, int gaitType, float speed, BOOL p4, BOOL p5)

```
This is to make the player walk without accepting input from INPUT.

gaitType is in increments of 100s. 2000, 500, 300, 200, etc.

p4 is always 1 and p5 is always 0.

C# Example :

Function.Call(Hash.SIMULATE_PLAYER_INPUT_GAIT, Game.Player, 1.0f, 100, 1.0f, 1, 0); //Player will go forward for 100ms
```

> RESET_PLAYER_INPUT_GAIT - 0x19531C47A2ABD691 0x4A701EE1

void RESET_PLAYER_INPUT_GAIT(Player player)



> SET_AUTO_GIVE_PARACHUTE_WHEN_ENTER_PLANE - 0x9F343285A00B4BB6 0xA97C2059

void SET_AUTO_GIVE_PARACHUTE_WHEN_ENTER_PLANE(Player player, BOOL toggle)



> 0xD2B315B6689D537D 0xA25D767E

void 0xD2B315B6689D537D(Player player, BOOL p1)

```
1.0.335.2, 1.0.350.1/2, 1.0.372.2, 1.0.393.2, 1.0.393.4, 1.0.463.1;
```

> SET_PLAYER_STEALTH_PERCEPTION_MODIFIER - 0x4E9021C1FCDD507A 0x3D26105F

void SET_PLAYER_STEALTH_PERCEPTION_MODIFIER(Player player, float value)



> 0x690A61A6D13583F6 0x1D371529

BOOL 0x690A61A6D13583F6(Any p0)



> 0x9EDD76E87D5D51BA 0xE30A64DC

void 0x9EDD76E87D5D51BA(Player player)



> SET_PLAYER_SIMULATE_AIMING - 0xC54C95DA968EC5B5 0xF1E0CAFC

void SET_PLAYER_SIMULATE_AIMING(Player player, BOOL toggle)



> SET_PLAYER_CLOTH_PIN_FRAMES - 0x749FADDF97DFE930 0xF7A0F00F

void SET_PLAYER_CLOTH_PIN_FRAMES(Player player, BOOL toggle)

```
Every occurrence of p1 I found was true.1.0.335.2, 1.0.350.1/2, 1.0.372.2, 1.0.393.2, 1.0.393.4, 1.0.463.1;
```

> SET_PLAYER_CLOTH_PACKAGE_INDEX - 0x9F7BBA2EA6372500 0xB8209F16

void SET_PLAYER_CLOTH_PACKAGE_INDEX(int index)

```
Every occurrence was either 0 or 2.
```

> SET_PLAYER_CLOTH_LOCK_COUNTER - 0x14D913B777DFF5DA 0x8D9FD4D1

void SET_PLAYER_CLOTH_LOCK_COUNTER(int value)

```
6 matches across 4 scripts. 5 occurrences were 240. The other was 255.
```

> PLAYER_ATTACH_VIRTUAL_BOUND - 0xED51733DC73AED51 0xECD12E60

void PLAYER_ATTACH_VIRTUAL_BOUND(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7)

```
Only 1 match. ob_sofa_michael.

PLAYER::PLAYER_ATTACH_VIRTUAL_BOUND(-804.5928f, 173.1801f, 71.68436f, 0f, 0f, 0.590625f, 1f, 0.7f);1.0.335.2, 1.0.350.1/2, 1.0.372.2, 1.0.393.2, 1.0.393.4, 1.0.463.1;
```

> PLAYER_DETACH_VIRTUAL_BOUND - 0x1DD5897E2FA6E7C9 0x96100EA4

void PLAYER_DETACH_VIRTUAL_BOUND()

```
1.0.335.2, 1.0.350.1/2, 1.0.372.2, 1.0.393.2, 1.0.393.4, 1.0.463.1;
```

> HAS_PLAYER_BEEN_SPOTTED_IN_STOLEN_VEHICLE - 0xD705740BB0A1CF4C 0x4A01B76A

BOOL HAS_PLAYER_BEEN_SPOTTED_IN_STOLEN_VEHICLE(Player player)



> 0x38D28DA81E4E9BF9 0x013B4F72

BOOL 0x38D28DA81E4E9BF9(Player player)

```
Returns true if an unk value is greater than 0.0f
```

> 0xBC0753C9CA14B506 0x9DF75B2A

BOOL 0xBC0753C9CA14B506(Player player, int p1, BOOL p2)

```
Assuming p0 is Player, not sure.
p1 was always 100.
p2 was always false.
- Kryptus

Edit from someone else: p0 is definately a player.
.xsc:
var num3 = PLAYER::GET_PLAYER_PED(l_2171); // proof l_2171 is a player

var num17 = PLAYER::0x9DF75B2A(l_2171, 100, 0); // l_2171

.ysc:
    if (PLAYER::GET_PLAYER_WANTED_LEVEL(l_6EF) &lt; v_4) { // l_6EF is a player
        PLAYER::SET_PLAYER_WANTED_LEVEL(l_6EF, v_4, 0); // l_6EF
        PLAYER::SET_PLAYER_WANTED_LEVEL_NOW(l_6EF, 0); // l_6EF
    } else { 
        PLAYER::_4669B3ED80F24B4E(l_6EF); // l_6EF
        UI::_BA8D65C1C65702E5(1);
        a_0 = 1;
    }

        if (l_4B24[l_6F2/*156*/]._f8C != PLAYER::_BC0753C9CA14B506(l_6EF, 100, 0)) { // l_6EF
            l_4B24[l_6F2/*156*/]._f8C = PLAYER::_BC0753C9CA14B506(l_6EF, 100, 0); // l_6EF
        }

Both was taken from fm_mission_controller

GET_PLAYER_*
```

> 0x5006D96C995A5827 

void 0x5006D96C995A5827(float x, float y, float z)

```
Appears only 3 times in the scripts, more specifically in michael1.ysc

Console hash: 0x64ddb07d
```

> IS_PLAYER_RIDING_TRAIN - 0x4EC12697209F2196 0x9765E71D

BOOL IS_PLAYER_RIDING_TRAIN(Player player)

```
Returns true if the player is riding a train.
```

> HAS_PLAYER_LEFT_THE_WORLD - 0xD55DDFB47991A294 0xFEA40B6C

BOOL HAS_PLAYER_LEFT_THE_WORLD(Player player)

```
Gets the player's info and calls a function that checks the player's ped position.

Here's the decompiled function that checks the position: pastebin.com/ZdHG2E7n
```

> 0xFF300C7649724A0B 0xAD8383FA

void 0xFF300C7649724A0B(Player player, BOOL p1)

```
gets byte at offset 0x862 in the specified players data (ped data + 0xbd0) and stores the bool p1 in it.
lwz       r3, 0xBD0(r3) ;r3 is player data
lbz       r4, 0x862(r3) ;r4 is now the byte
insrwi    r4, r31, 1,28 ;stores p1 as a bit in place 28 idk
stb       r4, 0x862(r3) ; puts the newly modified one back in

SET_PLAYER_*
```

> SET_PLAYER_PARACHUTE_VARIATION_OVERRIDE - 0xD9284A8C0D48352C 0x9254249D

void SET_PLAYER_PARACHUTE_VARIATION_OVERRIDE(Player player, int p1, Any p2, Any p3, BOOL p4)

```
p1 was always 5.
p4 was always false.
```

> CLEAR_PLAYER_PARACHUTE_VARIATION_OVERRIDE - 0x0F4CC924CF8C7B21 0xFD60F5AB

void CLEAR_PLAYER_PARACHUTE_VARIATION_OVERRIDE(Player player)



> SET_PLAYER_PARACHUTE_MODEL_OVERRIDE - 0x977DB4641F6FC3DB 0x5D382498

void SET_PLAYER_PARACHUTE_MODEL_OVERRIDE(Player player, Hash model)

```
example:

PLAYER::SET_PLAYER_PARACHUTE_MODEL_OVERRIDE(PLAYER::PLAYER_ID(), 0x73268708);
```

> CLEAR_PLAYER_PARACHUTE_MODEL_OVERRIDE - 0x8753997EB5F6EE3F 0x6FF034BB

void CLEAR_PLAYER_PARACHUTE_MODEL_OVERRIDE(Player player)



> SET_PLAYER_PARACHUTE_PACK_MODEL_OVERRIDE - 0xDC80A4C2F18A2B64 0xA877FF5E

void SET_PLAYER_PARACHUTE_PACK_MODEL_OVERRIDE(Player player, Hash model)



> CLEAR_PLAYER_PARACHUTE_PACK_MODEL_OVERRIDE - 0x10C54E4389C12B42 0xBB62AAC5

void CLEAR_PLAYER_PARACHUTE_PACK_MODEL_OVERRIDE(Player player)



> DISABLE_PLAYER_VEHICLE_REWARDS - 0xC142BE3BB9CE125F 0x8C6E611D

void DISABLE_PLAYER_VEHICLE_REWARDS(Player player)



> 0x2F7CEB6520288061 0x2849D4B2

void 0x2F7CEB6520288061(BOOL p0)

```
Used with radios:

void sub_cf383(auto _a0) {
    if ((a_0)==1) {
        if (GAMEPLAY::IS_BIT_SET((g_240005._f1), 3)) {
            PLAYER::_2F7CEB6520288061(0);
            AUDIO::SET_AUDIO_FLAG('AllowRadioDuringSwitch', 0);
            AUDIO::SET_MOBILE_PHONE_RADIO_STATE(0);
            AUDIO::SET_AUDIO_FLAG('MobileRadioInGame', 0);
        }
        sub_cf3f6(1);
    } else { 
        if (GAMEPLAY::IS_BIT_SET((g_240005._f1), 3)) {
            PLAYER::_2F7CEB6520288061(1);
            AUDIO::SET_AUDIO_FLAG('AllowRadioDuringSwitch', 1);
            AUDIO::SET_MOBILE_PHONE_RADIO_STATE(1);
            AUDIO::SET_AUDIO_FLAG('MobileRadioInGame', 1);
        }
        sub_cf3f6(0);
    }
}

SET_PLAYER_S*
```

> 0x5DC40A8869C22141 

void 0x5DC40A8869C22141(BOOL p0, ScrHandle p1)



> 0x65FAEE425DE637B0 

BOOL 0x65FAEE425DE637B0(Player p0)

```
IS_PLAYER_*
```

> 0x5501B7A5CDB79D37 

void 0x5501B7A5CDB79D37(Any p0)

```
DISABLE_*
```

> 0x56105E599CAB0EFA 

Player 0x56105E599CAB0EFA(int* p0)

```
GET_PLAYER_*
```

