# Audio

> PLAY_PED_RINGTONE - 0xF9E56683CA8E11A5 0x1D530E47

void PLAY_PED_RINGTONE(char* ringtoneName, Ped ped, BOOL p2)

```
All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/RFb4GTny

AUDIO::PLAY_PED_RINGTONE('Remote_Ring', PLAYER::PLAYER_PED_ID(), 1);
AUDIO::PLAY_PED_RINGTONE('Dial_and_Remote_Ring', PLAYER::PLAYER_PED_ID(), 1);

```

> IS_PED_RINGTONE_PLAYING - 0x1E8E5E20937E3137 0xFE576EE4

BOOL IS_PED_RINGTONE_PLAYING(Ped ped)



> STOP_PED_RINGTONE - 0x6C5AE23EFA885092 0xFEEA107C

void STOP_PED_RINGTONE(Ped ped)



> IS_MOBILE_PHONE_CALL_ONGOING - 0x7497D2CE2C30D24C 0x4ED1400A

BOOL IS_MOBILE_PHONE_CALL_ONGOING()



> 0xC8B1B2425604CDD0 0x16FB88B5

Any 0xC8B1B2425604CDD0()



> CREATE_NEW_SCRIPTED_CONVERSATION - 0xD2C91A0B572AAE56 0xB2BC25F8

void CREATE_NEW_SCRIPTED_CONVERSATION()



> ADD_LINE_TO_CONVERSATION - 0xC5EF963405593646 0x96CD0513

void ADD_LINE_TO_CONVERSATION(Any p0, Any* p1, Any* p2, Any p3, Any p4, BOOL p5, BOOL p6, BOOL p7, BOOL p8, Any p9, BOOL p10, BOOL p11, BOOL p12)

```
NOTE: ones that are -1, 0 - 35 are determined by a function where it gets a TextLabel from a global then runs,
_GET_TEXT_SUBSTRING and depending on what the result is it goes in check order of 0 - 9 then A - Z then z (lowercase). So it will then return 0 - 35 or -1 if it's 'z'. The func to handle that ^^ is func_67 in dialog_handler.c atleast in TU27 Xbox360 scripts.

p0 is -1, 0 - 35
p1 is a char or string (whatever you wanna call it)
p2 is Global 10597 + i * 6. 'i' is a while(i &lt; 70) loop
p3 is again -1, 0 - 35 
p4 is again -1, 0 - 35 
p5 is either 0 or 1 (bool ?)
p6 is either 0 or 1 (The func to determine this is bool)
p7 is either 0 or 1 (The func to determine this is bool)
p8 is either 0 or 1 (The func to determine this is bool)
p9 is 0 - 3 (Determined by func_60 in dialogue_handler.c)
p10 is either 0 or 1 (The func to determine this is bool)
p11 is either 0 or 1 (The func to determine this is bool)
p12 is unknown as in TU27 X360 scripts it only goes to p11.
```

> ADD_PED_TO_CONVERSATION - 0x95D9F4BC443956E7 0xF8D5EB86

void ADD_PED_TO_CONVERSATION(Any p0, Any p1, char* p2)

```
4 calls in the b617d scripts. The only one with p0 and p2 in clear text:

AUDIO::ADD_PED_TO_CONVERSATION(5, l_AF, 'DINAPOLI');

=================================================
One of the 2 calls in dialogue_handler.c p0 is in a while-loop, and so is determined to also possibly be 0 - 15.
Based on it asking if does_entity_exist for the global I have determined that p1 is, in fact, the ped, but could be wrong.
```

> 0x33E3C6C6F2F0B506 0x73C6F979

void 0x33E3C6C6F2F0B506(Any p0, float p1, float p2, float p3)



> 0x892B6AB8F33606F5 0x88203DDA

void 0x892B6AB8F33606F5(Any p0, Any p1)



> SET_MICROPHONE_POSITION - 0xB6AE90EDDE95C762 0xAD7BB191

void SET_MICROPHONE_POSITION(BOOL p0, float x1, float y1, float z1, float x2, float y2, float z2, float x3, float y3, float z3)

```
If this is the correct name, what microphone? I know your TV isn't going to reach out and adjust your headset so..
```

> 0x0B568201DD99F0EB 0x1193ED6E

void 0x0B568201DD99F0EB(BOOL p0)



> 0x61631F5DF50D1C34 

void 0x61631F5DF50D1C34(BOOL p0)



> START_SCRIPT_PHONE_CONVERSATION - 0x252E5F915EABB675 0x38E42D07

void START_SCRIPT_PHONE_CONVERSATION(BOOL p0, BOOL p1)



> PRELOAD_SCRIPT_PHONE_CONVERSATION - 0x6004BCB0E226AAEA 0x9ACB213A

void PRELOAD_SCRIPT_PHONE_CONVERSATION(BOOL p0, BOOL p1)



> START_SCRIPT_CONVERSATION - 0x6B17C62C9635D2DC 0xE5DE7D9D

void START_SCRIPT_CONVERSATION(BOOL p0, BOOL p1, BOOL p2, BOOL p3)



> PRELOAD_SCRIPT_CONVERSATION - 0x3B3CAD6166916D87 0xDDF5C579

void PRELOAD_SCRIPT_CONVERSATION(BOOL p0, BOOL p1, BOOL p2, BOOL p3)



> START_PRELOADED_CONVERSATION - 0x23641AFE870AF385 0xA170261B

void START_PRELOADED_CONVERSATION()



> 0xE73364DB90778FFA 0x336F3D35

Any 0xE73364DB90778FFA()



> IS_SCRIPTED_CONVERSATION_ONGOING - 0x16754C556D2EDE3D 0xCB8FD96F

BOOL IS_SCRIPTED_CONVERSATION_ONGOING()



> IS_SCRIPTED_CONVERSATION_LOADED - 0xDF0D54BE7A776737 0xE1870EA9

BOOL IS_SCRIPTED_CONVERSATION_LOADED()



> GET_CURRENT_SCRIPTED_CONVERSATION_LINE - 0x480357EE890C295A 0x9620E41F

Any GET_CURRENT_SCRIPTED_CONVERSATION_LINE()



> PAUSE_SCRIPTED_CONVERSATION - 0x8530AD776CD72B12 0xE2C9C6F8

void PAUSE_SCRIPTED_CONVERSATION(BOOL p0)



> RESTART_SCRIPTED_CONVERSATION - 0x9AEB285D1818C9AC 0x6CB24B56

void RESTART_SCRIPTED_CONVERSATION()



> STOP_SCRIPTED_CONVERSATION - 0xD79DEEFB53455EBA 0xAB77DA7D

Any STOP_SCRIPTED_CONVERSATION(BOOL p0)



> SKIP_TO_NEXT_SCRIPTED_CONVERSATION_LINE - 0x9663FE6B7A61EB00 0x85C98304

void SKIP_TO_NEXT_SCRIPTED_CONVERSATION_LINE()



> INTERRUPT_CONVERSATION - 0xA018A12E5C5C2FA6 0xF3A67AF3

void INTERRUPT_CONVERSATION(Any p0, Any* p1, Any* p2)



> 0x8A694D7A68F8DC38 

void 0x8A694D7A68F8DC38(Ped p0, char* p1, char* p2)

```
One call found in the b617d scripts:

AUDIO::_8A694D7A68F8DC38(NETWORK::NET_TO_PED(l_3989._f26F[0/*1*/]), 'CONV_INTERRUPT_QUIT_IT', 'LESTER');
```

> 0xAA19F5572C38B564 0xB58B8FF3

Any 0xAA19F5572C38B564(Any* p0)



> 0xB542DE8C3D1CB210 0x789D8C6C

void 0xB542DE8C3D1CB210(BOOL p0)



> REGISTER_SCRIPT_WITH_AUDIO - 0xC6ED9D5092438D91 0xA6203643

void REGISTER_SCRIPT_WITH_AUDIO(Any p0)



> UNREGISTER_SCRIPT_WITH_AUDIO - 0xA8638BE228D4751A 0x66728EFE

void UNREGISTER_SCRIPT_WITH_AUDIO()



> REQUEST_MISSION_AUDIO_BANK - 0x7345BDD95E62E0F2 0x916E37CA

BOOL REQUEST_MISSION_AUDIO_BANK(char* p0, BOOL p1)

```
 All occurrences and usages found in b617d: pastebin.com/NzZZ2Tmm
 
```

> REQUEST_AMBIENT_AUDIO_BANK - 0xFE02FFBED8CA9D99 0x23C88BC7

BOOL REQUEST_AMBIENT_AUDIO_BANK(char* p0, BOOL p1)

```
All occurrences and usages found in b617d, sorted alphabetically and identical lines removed: pastebin.com/XZ1tmGEz
```

> REQUEST_SCRIPT_AUDIO_BANK - 0x2F844A8B08D76685 0x21322887

BOOL REQUEST_SCRIPT_AUDIO_BANK(char* p0, BOOL p1)

```
All occurrences and usages found in b617d, sorted alphabetically and identical lines removed: pastebin.com/AkmDAVn6
```

> HINT_AMBIENT_AUDIO_BANK - 0x8F8C0E370AE62F5C 0xF1850DDC

Any HINT_AMBIENT_AUDIO_BANK(Any p0, Any p1)



> HINT_SCRIPT_AUDIO_BANK - 0xFB380A29641EC31A 0x41FA0E51

Any HINT_SCRIPT_AUDIO_BANK(Any p0, Any p1)



> RELEASE_MISSION_AUDIO_BANK - 0x0EC92A1BF0857187 0x8E8824C7

void RELEASE_MISSION_AUDIO_BANK()



> RELEASE_AMBIENT_AUDIO_BANK - 0x65475A218FFAA93D 0x8C938784

void RELEASE_AMBIENT_AUDIO_BANK()



> RELEASE_NAMED_SCRIPT_AUDIO_BANK - 0x77ED170667F50170 0x16707ABC

void RELEASE_NAMED_SCRIPT_AUDIO_BANK(char* audioBank)



> RELEASE_SCRIPT_AUDIO_BANK - 0x7A2D8AD0A9EB9C3F 0x22F865E5

void RELEASE_SCRIPT_AUDIO_BANK()



> 0x19AF7ED9B9D23058 0xA58BBF4F

void 0x19AF7ED9B9D23058()



> 0x9AC92EED5E4793AB 

void 0x9AC92EED5E4793AB()



> GET_SOUND_ID - 0x430386FE9BF80B45 0x6AE0AD56

int GET_SOUND_ID()



> RELEASE_SOUND_ID - 0x353FC880830B88FA 0x9C080899

void RELEASE_SOUND_ID(int soundId)



> PLAY_SOUND - 0x7FF4944CC209192D 0xB6E1917F

void PLAY_SOUND(int soundId, char* audioName, char* audioRef, BOOL p3, Any p4, BOOL p5)

```
All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/A8Ny8AHZ
```

> PLAY_SOUND_FRONTEND - 0x67C540AA08E4A6F5 0x2E458F74

void PLAY_SOUND_FRONTEND(int soundId, char* audioName, char* audioRef, BOOL p3)

```
list: pastebin.com/DCeRiaLJ

All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/0neZdsZ5
```

> 0xCADA5A0D0702381E 0xC70E6CFA

void 0xCADA5A0D0702381E(char* p0, char* soundset)

```
Only call found in the b617d scripts:

AUDIO::_CADA5A0D0702381E('BACK', 'HUD_FREEMODE_SOUNDSET');
```

> PLAY_SOUND_FROM_ENTITY - 0xE65F427EB70AB1ED 0x95AE00F8

void PLAY_SOUND_FROM_ENTITY(int soundId, char* audioName, Entity entity, char* audioRef, BOOL p4, Any p5)

```
All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/f2A7vTj0 
No changes made in b678d.

gtaforums.com/topic/795622-audio-for-mods

```

> PLAY_SOUND_FROM_COORD - 0x8D8686B622B88120 0xCAD3E2D5

void PLAY_SOUND_FROM_COORD(int soundId, char* audioName, float x, float y, float z, char* audioRef, BOOL p6, Any p7, BOOL p8)

```
All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/eeFc5DiW

gtaforums.com/topic/795622-audio-for-mods
```

> STOP_SOUND - 0xA3B0C41BA5CC0BB5 0xCD7F4030

void STOP_SOUND(int soundId)



> GET_NETWORK_ID_FROM_SOUND_ID - 0x2DE3F0A134FFBC0D 0x2576F610

int GET_NETWORK_ID_FROM_SOUND_ID(int soundId)

```
Could this be used alongside either, 
SET_NETWORK_ID_EXISTS_ON_ALL_MACHINES or _SET_NETWORK_ID_SYNC_TO_PLAYER to make it so other players can hear the sound while online? It'd be a bit troll-fun to be able to play the Zancudo UFO creepy sounds globally.
```

> GET_SOUND_ID_FROM_NETWORK_ID - 0x75262FD12D0A1C84 0xD064D4DC

int GET_SOUND_ID_FROM_NETWORK_ID(int netId)



> SET_VARIABLE_ON_SOUND - 0xAD6B3148A78AE9B6 0x606EE5FA

void SET_VARIABLE_ON_SOUND(int soundId, Any* p1, float p2)



> SET_VARIABLE_ON_STREAM - 0x2F9D3834AEB9EF79 0xF67BB44C

void SET_VARIABLE_ON_STREAM(char* p0, float p1)

```
From the scripts, p0:

'ArmWrestlingIntensity',
'INOUT',
'Monkey_Stream',
'ZoomLevel'
```

> OVERRIDE_UNDERWATER_STREAM - 0xF2A9CDABCEA04BD6 0x9A083B7E

void OVERRIDE_UNDERWATER_STREAM(Any* p0, BOOL p1)



> 0x733ADF241531E5C2 0x62D026BE

void 0x733ADF241531E5C2(Any* p0, float p1)

```
AUDIO::_733ADF241531E5C2('inTunnel', 1.0);
AUDIO::_733ADF241531E5C2('inTunnel', 0.0);

I do not know as of yet what this does, but this was found in the scripts.

- jedijosh920
```

> HAS_SOUND_FINISHED - 0xFCBDCE714A7C88E5 0xE85AEC2E

BOOL HAS_SOUND_FINISHED(int soundId)



> _PLAY_AMBIENT_SPEECH1 - 0x8E04FEDD28D42462 0x5C57B85D

void _PLAY_AMBIENT_SPEECH1(Ped ped, char* speechName, char* speechParam)

```
Plays ambient speech. See also _0x444180DB.

ped: The ped to play the ambient speech.
speechName: Name of the speech to play, eg. 'GENERIC_HI'.
speechParam: Can be one of the following:
SPEECH_PARAMS_STANDARD
SPEECH_PARAMS_ALLOW_REPEAT
SPEECH_PARAMS_BEAT
SPEECH_PARAMS_FORCE
SPEECH_PARAMS_FORCE_FRONTEND
SPEECH_PARAMS_FORCE_NO_REPEAT_FRONTEND
SPEECH_PARAMS_FORCE_NORMAL
SPEECH_PARAMS_FORCE_NORMAL_CLEAR
SPEECH_PARAMS_FORCE_NORMAL_CRITICAL
SPEECH_PARAMS_FORCE_SHOUTED
SPEECH_PARAMS_FORCE_SHOUTED_CLEAR
SPEECH_PARAMS_FORCE_SHOUTED_CRITICAL
SPEECH_PARAMS_FORCE_PRELOAD_ONLY
SPEECH_PARAMS_MEGAPHONE
SPEECH_PARAMS_HELI
SPEECH_PARAMS_FORCE_MEGAPHONE
SPEECH_PARAMS_FORCE_HELI
SPEECH_PARAMS_INTERRUPT
SPEECH_PARAMS_INTERRUPT_SHOUTED
SPEECH_PARAMS_INTERRUPT_SHOUTED_CLEAR
SPEECH_PARAMS_INTERRUPT_SHOUTED_CRITICAL
SPEECH_PARAMS_INTERRUPT_NO_FORCE
SPEECH_PARAMS_INTERRUPT_FRONTEND
SPEECH_PARAMS_INTERRUPT_NO_FORCE_FRONTEND
SPEECH_PARAMS_ADD_BLIP
SPEECH_PARAMS_ADD_BLIP_ALLOW_REPEAT
SPEECH_PARAMS_ADD_BLIP_FORCE
SPEECH_PARAMS_ADD_BLIP_SHOUTED
SPEECH_PARAMS_ADD_BLIP_SHOUTED_FORCE
SPEECH_PARAMS_ADD_BLIP_INTERRUPT
SPEECH_PARAMS_ADD_BLIP_INTERRUPT_FORCE
SPEECH_PARAMS_FORCE_PRELOAD_ONLY_SHOUTED
SPEECH_PARAMS_FORCE_PRELOAD_ONLY_SHOUTED_CLEAR
SPEECH_PARAMS_FORCE_PRELOAD_ONLY_SHOUTED_CRITICAL
SPEECH_PARAMS_SHOUTED
SPEECH_PARAMS_SHOUTED_CLEAR
SPEECH_PARAMS_SHOUTED_CRITICAL

Note: A list of Name and Parameters can be found here pastebin.com/1GZS5dCL

Full list of speeches and voices names by alexguirre: gist.github.com/alexguirre/0af600eb3d4c91ad4f900120a63b8992
```

> _PLAY_AMBIENT_SPEECH2 - 0xC6941B4A3A8FBBB9 0x444180DB

void _PLAY_AMBIENT_SPEECH2(Ped ped, char* speechName, char* speechParam)

```
Plays ambient speech. See also _0x5C57B85D.

See _PLAY_AMBIENT_SPEECH1 for parameter specifications.

Full list of speeches and voices names by alexguirre: gist.github.com/alexguirre/0af600eb3d4c91ad4f900120a63b8992
```

> _PLAY_AMBIENT_SPEECH_WITH_VOICE - 0x3523634255FC3318 0x8386AE28

void _PLAY_AMBIENT_SPEECH_WITH_VOICE(Ped p0, char* speechName, char* voiceName, char* speechParam, BOOL p4)

```
This is the same as _PLAY_AMBIENT_SPEECH1 and _PLAY_AMBIENT_SPEECH2 but it will allow you to play a speech file from a specific voice file. It works on players and all peds, even animals.

EX (C#):
GTA.Native.Function.Call(Hash._0x3523634255FC3318, Game.Player.Character, 'GENERIC_INSULT_HIGH', 's_m_y_sheriff_01_white_full_01', 'SPEECH_PARAMS_FORCE_SHOUTED', 0);

The first param is the ped you want to play it on, the second is the speech name, the third is the voice name, the fourth is the speech param, and the last param is usually always 0.

Full list of speeches and voices names by alexguirre: gist.github.com/alexguirre/0af600eb3d4c91ad4f900120a63b8992
```

> _PLAY_AMBIENT_SPEECH_AT_COORDS - 0xED640017ED337E45 0xA1A1402E

void _PLAY_AMBIENT_SPEECH_AT_COORDS(char* p0, char* p1, float p2, float p3, float p4, char* p5)



> OVERRIDE_TREVOR_RAGE - 0x13AD665062541A7E 0x05B9B5CF

void OVERRIDE_TREVOR_RAGE(Any* p0)



> RESET_TREVOR_RAGE - 0xE78503B10C4314E0 0xE80CF0D4

void RESET_TREVOR_RAGE()



> SET_PLAYER_ANGRY - 0xEA241BB04110F091 0x782CA58D

void SET_PLAYER_ANGRY(Ped playerPed, BOOL disabled)

```
MulleDK19: Hash collision! Disables speech.
```

> PLAY_PAIN - 0xBC9AE166038A5CEC 0x874BD6CB

void PLAY_PAIN(int painID, float p1, int p2)

```
Last 2 parameters always seem to be 0.

EX: Function.Call(Hash.PLAY_PAIN, TestPed, 6, 0, 0);

Known Pain IDs
________________________

1 - CRASHES GAME (DON'T USE) - (EDIT from someone else: Does NOT crash in 1.0.617.1 for me)
6 - Scream (Short)
7 - Scared Scream (Kinda Long)
8 - On Fire

- jedijosh920

Needs another parameter [int p2]. The signature is PED::PLAY_PAIN(Ped ped, int painID, int p1, int p2);

- sollaholla
```

> 0xD01005D2BA2EB778 0x59A3A17D

void 0xD01005D2BA2EB778(Any* p0)



> 0xDDC635D5B3262C56 0x0E387BFE

void 0xDDC635D5B3262C56(Any* p0)



> SET_AMBIENT_VOICE_NAME - 0x6C8065A3B780185B 0xBD2EA1A1

void SET_AMBIENT_VOICE_NAME(Ped ped, char* name)

```
Edit by @AmeyBanaye

Audio List
gtaforums.com/topic/795622-audio-for-mods/

All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/FTeAj4yZ
```

> 0x40CF0D12D142A9E8 

void 0x40CF0D12D142A9E8(Ped ped)

```
MulleDK19: Assigns some ambient voice to the ped.
```

> 0x7CDC8C3B89F661B3 

void 0x7CDC8C3B89F661B3(Any p0, Any p1)

```
From the scripts:

AUDIO::_7CDC8C3B89F661B3(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('PAIGE_PVG'));
                AUDIO::_7CDC8C3B89F661B3(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('TALINA_PVG'));
            AUDIO::_7CDC8C3B89F661B3(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('FEMALE_LOST_BLACK_PVG'));
            AUDIO::_7CDC8C3B89F661B3(PLAYER::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('FEMALE_LOST_WHITE_PVG'));

```

> 0xA5342D390CDA41D6 

void 0xA5342D390CDA41D6(Any p0, BOOL p1)



> 0x7A73D05A607734C7 

void 0x7A73D05A607734C7(Ped ped)

```
MulleDK19: Stops speech.
```

> STOP_CURRENT_PLAYING_AMBIENT_SPEECH - 0xB8BEC0CA6F0EDB0F 0xBB8E64BF

void STOP_CURRENT_PLAYING_AMBIENT_SPEECH(Ped p0)

```
Needs to be called every frame. 
```

> IS_AMBIENT_SPEECH_PLAYING - 0x9072C8B49907BFAD 0x1972E8AA

BOOL IS_AMBIENT_SPEECH_PLAYING(Ped p0)



> IS_SCRIPTED_SPEECH_PLAYING - 0xCC9AA18DCC7084F4 0x2C653904

BOOL IS_SCRIPTED_SPEECH_PLAYING(Any p0)



> IS_ANY_SPEECH_PLAYING - 0x729072355FA39EC9 0x2B74A6D6

BOOL IS_ANY_SPEECH_PLAYING(Ped ped)



> 0x49B99BF3FDA89A7A 0x8BD5F11E

BOOL 0x49B99BF3FDA89A7A(Any p0, Any* p1, BOOL p2)

```
jedijosh920: Checks if the ped can play the speech or has the speech file, last parameter is usually 0
```

> IS_PED_IN_CURRENT_CONVERSATION - 0x049E937F18F4020C 0x7B2F0743

BOOL IS_PED_IN_CURRENT_CONVERSATION(Ped ped)



> SET_PED_IS_DRUNK - 0x95D2D383D5396B8A 0xD2EA77A3

void SET_PED_IS_DRUNK(Ped ped, BOOL toggle)

```
Sets the ped drunk sounds.  Only works with PLAYER_PED_ID

====================================================

As mentioned above, this only sets the drunk sound to ped/player.

To give the Ped a drunk effect with drunk walking animation try using SET_PED_MOVEMENT_CLIPSET

Below is an example

if (!Function.Call&lt;bool&gt;(Hash.HAS_ANIM_SET_LOADED, 'move_m@drunk@verydrunk'))
                {
                    Function.Call(Hash.REQUEST_ANIM_SET, 'move_m@drunk@verydrunk');
                }
                Function.Call(Hash.SET_PED_MOVEMENT_CLIPSET, Ped.Handle, 'move_m@drunk@verydrunk', 0x3E800000);



And to stop the effect use
RESET_PED_MOVEMENT_CLIPSET
-YCSM
```

> 0xEE066C7006C49C0A 0x498849F3

void 0xEE066C7006C49C0A(Any p0, Any p1, Any* p2)



> 0xC265DF9FB44A9FBD 0x0CBAF2EF

BOOL 0xC265DF9FB44A9FBD(Any p0)



> SET_ANIMAL_MOOD - 0xCC97B29285B1DC3B 0x3EA7C6CB

void SET_ANIMAL_MOOD(Any p0, Any p1)

```
mood can be 0 or 1 (it's not a boolean value!). Effects audio of the animal.
```

> IS_MOBILE_PHONE_RADIO_ACTIVE - 0xB35CE999E8EF317E 0x6E502A5B

BOOL IS_MOBILE_PHONE_RADIO_ACTIVE()



> SET_MOBILE_PHONE_RADIO_STATE - 0xBF286C554784F3DF 0xE1E0ED34

void SET_MOBILE_PHONE_RADIO_STATE(BOOL state)



> GET_PLAYER_RADIO_STATION_INDEX - 0xE8AF77C4C06ADC93 0x1C4946AC

int GET_PLAYER_RADIO_STATION_INDEX()

```
Returns 255 (radio off index) if the function fails.
```

> GET_PLAYER_RADIO_STATION_NAME - 0xF6D733C32076AD03 0xD909C107

char* GET_PLAYER_RADIO_STATION_NAME()

```
Returns active radio station name
```

> GET_RADIO_STATION_NAME - 0xB28ECA15046CA8B9 0x3DF493BC

char* GET_RADIO_STATION_NAME(int radioStation)

```
Returns String with radio station name.
```

> GET_PLAYER_RADIO_STATION_GENRE - 0xA571991A7FE6CCEB 0x872CF0EA

Any GET_PLAYER_RADIO_STATION_GENRE()



> IS_RADIO_RETUNING - 0xA151A7394A214E65 0xCF29097B

BOOL IS_RADIO_RETUNING()



> 0x0626A247D2405330 

Any 0x0626A247D2405330()



> 0xFF266D1D0EB1195D 0x53DB6994

void 0xFF266D1D0EB1195D()

```
Tune Forward... ?
```

> 0xDD6BCF9E94425DF9 0xD70ECC80

void 0xDD6BCF9E94425DF9()

```
Tune Backwards... ?
```

> SET_RADIO_TO_STATION_NAME - 0xC69EDA28699D5107 0x7B36E35E

void SET_RADIO_TO_STATION_NAME(char* stationName)

```
For a full list, see here: pastebin.com/Kj9t38KF
```

> SET_VEH_RADIO_STATION - 0x1B9C0099CB942AC6 0xE391F55F

void SET_VEH_RADIO_STATION(Vehicle vehicle, char* radioStation)

```
For a full list, see here: pastebin.com/Kj9t38KF
```

> 0xC1805D05E6D4FE10 0x7ABB89D2

void 0xC1805D05E6D4FE10(Vehicle vehicle)



> SET_EMITTER_RADIO_STATION - 0xACF57305B12AF907 0x87431585

void SET_EMITTER_RADIO_STATION(char* emitterName, char* radioStation)



> SET_STATIC_EMITTER_ENABLED - 0x399D2D3B33F1B8EB 0x91F72E92

void SET_STATIC_EMITTER_ENABLED(char* emitterName, BOOL toggle)

```
Example:
AUDIO::SET_STATIC_EMITTER_ENABLED((Any*)'LOS_SANTOS_VANILLA_UNICORN_01_STAGE', false);	AUDIO::SET_STATIC_EMITTER_ENABLED((Any*)'LOS_SANTOS_VANILLA_UNICORN_02_MAIN_ROOM', false);	AUDIO::SET_STATIC_EMITTER_ENABLED((Any*)'LOS_SANTOS_VANILLA_UNICORN_03_BACK_ROOM', false);

This turns off surrounding sounds not connected directly to peds. 


```

> SET_RADIO_TO_STATION_INDEX - 0xA619B168B8A8570F 0x1D82766D

void SET_RADIO_TO_STATION_INDEX(int radioStation)

```
Sets radio station by index.
```

> SET_FRONTEND_RADIO_ACTIVE - 0xF7F26C6E9CC9EBB8 0xB1172075

void SET_FRONTEND_RADIO_ACTIVE(BOOL active)



> UNLOCK_MISSION_NEWS_STORY - 0xB165AB7C248B2DC1 0xCCD9ABE4

void UNLOCK_MISSION_NEWS_STORY(int newsStory)

```
I see this as a native that would of been used back in GTA III when you finally unlocked the bridge to the next island and such.
```

> GET_NUMBER_OF_PASSENGER_VOICE_VARIATIONS - 0x66E49BF55B4B1874 0x27305D37

int GET_NUMBER_OF_PASSENGER_VOICE_VARIATIONS(Any p0)



> GET_AUDIBLE_MUSIC_TRACK_TEXT_ID - 0x50B196FC9ED6545B 0xA2B88CA7

int GET_AUDIBLE_MUSIC_TRACK_TEXT_ID()



> PLAY_END_CREDITS_MUSIC - 0xCD536C4D33DCC900 0x8E88B3CC

void PLAY_END_CREDITS_MUSIC(BOOL play)



> SKIP_RADIO_FORWARD - 0x6DDBBDD98E2E9C25 0x10D36630

void SKIP_RADIO_FORWARD()



> FREEZE_RADIO_STATION - 0x344F393B027E38C3 0x286BF543

void FREEZE_RADIO_STATION(char* radioStation)



> UNFREEZE_RADIO_STATION - 0xFC00454CF60B91DD 0x4D46202C

void UNFREEZE_RADIO_STATION(char* radioStation)



> SET_RADIO_AUTO_UNFREEZE - 0xC1AA9F53CE982990 0xA40196BF

void SET_RADIO_AUTO_UNFREEZE(BOOL p0)



> SET_INITIAL_PLAYER_STATION - 0x88795F13FACDA88D 0x9B069233

void SET_INITIAL_PLAYER_STATION(char* radioStation)



> SET_USER_RADIO_CONTROL_ENABLED - 0x19F21E63AE6EAE4E 0x52E054CE

void SET_USER_RADIO_CONTROL_ENABLED(BOOL p0)



> SET_RADIO_TRACK - 0xB39786F201FEE30B 0x76E96212

void SET_RADIO_TRACK(char* radioStation, char* radioTrack)

```
Only found this one in the decompiled scripts:

AUDIO::SET_RADIO_TRACK('RADIO_03_HIPHOP_NEW', 'ARM1_RADIO_STARTS');

```

> SET_VEHICLE_RADIO_LOUD - 0xBB6F1CAEC68B0BCE 0x8D9EDD99

void SET_VEHICLE_RADIO_LOUD(Vehicle vehicle, BOOL toggle)



> _IS_VEHICLE_RADIO_LOUD - 0x032A116663A4D5AC 0xCBA99F4A

BOOL _IS_VEHICLE_RADIO_LOUD(Vehicle vehicle)



> SET_MOBILE_RADIO_ENABLED_DURING_GAMEPLAY - 0x1098355A16064BB3 0x990085F0

void SET_MOBILE_RADIO_ENABLED_DURING_GAMEPLAY(BOOL Toggle)

```
Enables Radio on phone.
```

> 0x109697E2FFBAC8A1 0x46B0C696

BOOL 0x109697E2FFBAC8A1()

```
MulleDK19: Not sure what this function does, but it's related to the audio of the local player's vehicle (Considering the surrounding natives, it's probably radio related).
```

> 0x5F43D83FD6738741 0x2A3E5E8B

BOOL 0x5F43D83FD6738741()



> SET_VEHICLE_RADIO_ENABLED - 0x3B988190C0AA6C0B 0x6F812CAB

void SET_VEHICLE_RADIO_ENABLED(Vehicle vehicle, BOOL toggle)

```
can't seem to enable radio on cop cars etc
```

> 0x4E404A9361F75BB2 0x128C3873

void 0x4E404A9361F75BB2(char* radioStation, char* p1, BOOL p2)

```
Examples:

AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'END_CREDITS_KILL_MICHAEL', 1);
AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'END_CREDITS_KILL_MICHAEL', 1);
AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'END_CREDITS_KILL_TREVOR', 1);
AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'END_CREDITS_SAVE_MICHAEL_TREVOR', 1);
AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'OFF_ROAD_RADIO_ROCK_LIST', 1);
AUDIO::_4E404A9361F75BB2('RADIO_06_COUNTRY', 'MAGDEMO2_RADIO_DINGHY', 1);
AUDIO::_4E404A9361F75BB2('RADIO_16_SILVERLAKE', 'SEA_RACE_RADIO_PLAYLIST', 1);
AUDIO::_4E404A9361F75BB2('RADIO_01_CLASS_ROCK', 'OFF_ROAD_RADIO_ROCK_LIST', 1);
```

> 0x1654F24A88A8E3FE 0x1D766976

void 0x1654F24A88A8E3FE(char* radioStation)

```
3 calls in the b617d scripts, removed duplicate.

AUDIO::_1654F24A88A8E3FE('RADIO_16_SILVERLAKE');
AUDIO::_1654F24A88A8E3FE('RADIO_01_CLASS_ROCK');
```

> _MAX_RADIO_STATION_INDEX - 0xF1620ECB50E01DE7 0xCC91FCF5

int _MAX_RADIO_STATION_INDEX()



> FIND_RADIO_STATION_INDEX - 0x8D67489793FF428B 0xECA1512F

int FIND_RADIO_STATION_INDEX(int station)



> 0x774BD811F656A122 0xB1FF7137

void 0x774BD811F656A122(char* radioStation, BOOL p1)

```
6 calls in the b617d scripts, removed identical lines:

AUDIO::_774BD811F656A122('RADIO_01_CLASS_ROCK', 1);
AUDIO::_774BD811F656A122(AUDIO::GET_RADIO_STATION_NAME(10), 0);
AUDIO::_774BD811F656A122(AUDIO::GET_RADIO_STATION_NAME(10), 1);
```

> 0x2C96CDB04FCA358E 0xC8B514E2

void 0x2C96CDB04FCA358E(float p0)



> 0x031ACB6ABA18C729 0xBE998184

void 0x031ACB6ABA18C729(char* radioStation, char* p1)

```
2 calls in the b617d scripts. This line is called 2 times:
AUDIO::_031ACB6ABA18C729('RADIO_16_SILVERLAKE', 'MIRRORPARK_LOCKED');

Note: Another name for RADIO_16_SILVERLAKE is RADIO MIRROR PARK
```

> 0xF3365489E0DD50F9 0x8AFC488D

void 0xF3365489E0DD50F9(Any p0, BOOL p1)



> SET_AMBIENT_ZONE_STATE - 0xBDA07E5950085E46 0x2849CAC9

void SET_AMBIENT_ZONE_STATE(Any* p0, BOOL p1, BOOL p2)



> CLEAR_AMBIENT_ZONE_STATE - 0x218DD44AAAC964FF 0xCDFF3C82

void CLEAR_AMBIENT_ZONE_STATE(Any* p0, BOOL p1)

```
This function also has a p2, unknown. Signature AUDIO::CLEAR_AMBIENT_ZONE_STATE(char* zoneName, bool p1, Any p2);

Still needs more research. 

Here are the names I've found: pastebin.com/AfA0Qjyv

- Sollaholla
```

> SET_AMBIENT_ZONE_LIST_STATE - 0x9748FA4DE50CCE3E 0xBF80B412

void SET_AMBIENT_ZONE_LIST_STATE(Any* p0, BOOL p1, BOOL p2)



> CLEAR_AMBIENT_ZONE_LIST_STATE - 0x120C48C614909FA4 0x38B9B8D4

void CLEAR_AMBIENT_ZONE_LIST_STATE(Any* p0, BOOL p1)



> SET_AMBIENT_ZONE_STATE_PERSISTENT - 0x1D6650420CEC9D3B 0xC1FFB672

void SET_AMBIENT_ZONE_STATE_PERSISTENT(char* ambientZone, BOOL p1, BOOL p2)

```
 All occurrences found in b617d, sorted alphabetically and identical lines removed: pastebin.com/jYvw7N1S
```

> SET_AMBIENT_ZONE_LIST_STATE_PERSISTENT - 0xF3638DAE8C4045E1 0x5F5A2605

void SET_AMBIENT_ZONE_LIST_STATE_PERSISTENT(char* ambientZone, BOOL p1, BOOL p2)

```
All occurrences found in b617d, sorted alphabetically and identical lines removed: pastebin.com/WkXDGgQL
```

> IS_AMBIENT_ZONE_ENABLED - 0x01E2817A479A7F9B 0xBFABD872

BOOL IS_AMBIENT_ZONE_ENABLED(char* ambientZone)



> SET_CUTSCENE_AUDIO_OVERRIDE - 0x3B4BF5F0859204D9 0xCE1332B7

void SET_CUTSCENE_AUDIO_OVERRIDE(char* p0)

```
All occurrences found in b617d, sorted alphabetically and identical lines removed: 

AUDIO::SET_CUTSCENE_AUDIO_OVERRIDE('_AK');
AUDIO::SET_CUTSCENE_AUDIO_OVERRIDE('_CUSTOM');
AUDIO::SET_CUTSCENE_AUDIO_OVERRIDE('_TOOTHLESS');
```

> GET_PLAYER_HEADSET_SOUND_ALTERNATE - 0xBCC29F935ED07688 0xD63CF33A

void GET_PLAYER_HEADSET_SOUND_ALTERNATE(char* p0, float p1)

```
Called 5 times in the scripts. All occurrences found in b617d, sorted alphabetically and identical lines removed: 

AUDIO::GET_PLAYER_HEADSET_SOUND_ALTERNATE('INOUT', 0.0);
AUDIO::GET_PLAYER_HEADSET_SOUND_ALTERNATE('INOUT', 1.0);
```

> PLAY_POLICE_REPORT - 0xDFEBD56D9BD1EB16 0x3F277B62

Any PLAY_POLICE_REPORT(char* name, float p1)

```
Please change to void. (Does not return anything!)

Plays the given police radio message.

All found occurrences in b617d, sorted alphabetically and identical lines removed: pastebin.com/GBnsQ5hr
```

> _DISABLE_POLICE_REPORTS - 0xB4F90FAF7670B16F 

void _DISABLE_POLICE_REPORTS()



> BLIP_SIREN - 0x1B9025BDA76822B6 0xC0EB6924

void BLIP_SIREN(Vehicle vehicle)

```
Plays the siren sound of a vehicle which is otherwise activated when fastly double-pressing the horn key.
Only works on vehicles with a police siren.
```

> OVERRIDE_VEH_HORN - 0x3CDC1E622CCE0356 0x2ACAB783

void OVERRIDE_VEH_HORN(Vehicle vehicle, BOOL mute, int p2)

```
vehicle - the vehicle whose horn should be overwritten
mute - p1 seems to be an option for muting the horn
p2 - maybe a horn id, since the function AUDIO::GET_VEHICLE_DEFAULT_HORN(veh) exists?
```

> IS_HORN_ACTIVE - 0x9D6BFC12B05C6121 0x20E2BDD0

BOOL IS_HORN_ACTIVE(Vehicle vehicle)

```
Checks whether the horn of a vehicle is currently played.
```

> SET_AGGRESSIVE_HORNS - 0x395BF71085D1B1D9 0x01D6EABE

void SET_AGGRESSIVE_HORNS(BOOL toggle)

```
Makes pedestrians sound their horn longer, faster and more agressive when they use their horn.
```

> 0x02E93C796ABD3A97 0x3C395AEE

void 0x02E93C796ABD3A97(Any p0)



> 0x58BB377BEC7CD5F4 0x8CE63FA1

void 0x58BB377BEC7CD5F4(BOOL p0, BOOL p1)



> IS_STREAM_PLAYING - 0xD11FA52EB849D978 0xF1F51A14

BOOL IS_STREAM_PLAYING()



> GET_STREAM_PLAY_TIME - 0x4E72BBDBCA58A3DB 0xB4F0AD56

int GET_STREAM_PLAY_TIME()



> LOAD_STREAM - 0x1F1F957154EC51DF 0x0D89599D

BOOL LOAD_STREAM(char* streamName, char* soundSet)

```
Example:
AUDIO::LOAD_STREAM('CAR_STEAL_1_PASSBY', 'CAR_STEAL_1_SOUNDSET');

All found occurrences in the b678d decompiled scripts: pastebin.com/3rma6w5w

Stream names often ends with '_MASTER', '_SMALL' or '_STREAM'. Also '_IN', '_OUT' and numbers.   

soundSet is often set to 0 in the scripts. These are common to end the soundSets: '_SOUNDS', '_SOUNDSET' and numbers. 
```

> LOAD_STREAM_WITH_START_OFFSET - 0x59C16B79F53B3712 0xE5B5745C

BOOL LOAD_STREAM_WITH_START_OFFSET(char* streamName, int startOffset, char* soundSet)

```
Example:
AUDIO::LOAD_STREAM_WITH_START_OFFSET('STASH_TOXIN_STREAM', 2400, 'FBI_05_SOUNDS');

Only called a few times in the scripts. 
```

> PLAY_STREAM_FROM_PED - 0x89049DD63C08B5D1 0xA1D7FABE

void PLAY_STREAM_FROM_PED(Ped ped)



> PLAY_STREAM_FROM_VEHICLE - 0xB70374A758007DFA 0xF8E4BDA2

void PLAY_STREAM_FROM_VEHICLE(Vehicle vehicle)



> PLAY_STREAM_FROM_OBJECT - 0xEBAA9B64D76356FD 0xC5266BF7

void PLAY_STREAM_FROM_OBJECT(Object object)

```
Used with AUDIO::LOAD_STREAM

Example from finale_heist2b.c4:
AI::TASK_SYNCHRONIZED_SCENE(l_4C8[2/*14*/], l_4C8[2/*14*/]._f7, l_30A, 'push_out_vault_l', 4.0, -1.5, 5, 713, 4.0, 0);
                    PED::SET_SYNCHRONIZED_SCENE_PHASE(l_4C8[2/*14*/]._f7, 0.0);
                    PED::_2208438012482A1A(l_4C8[2/*14*/], 0, 0);
                    PED::SET_PED_COMBAT_ATTRIBUTES(l_4C8[2/*14*/], 38, 1);
                    PED::SET_BLOCKING_OF_NON_TEMPORARY_EVENTS(l_4C8[2/*14*/], 1);
                    if (AUDIO::LOAD_STREAM('Gold_Cart_Push_Anim_01', 'BIG_SCORE_3B_SOUNDS')) {
                        AUDIO::PLAY_STREAM_FROM_OBJECT(l_36F[0/*1*/]);
                    }
```

> PLAY_STREAM_FRONTEND - 0x58FCE43488F9F5F4 0x2C2A16BC

void PLAY_STREAM_FRONTEND()



> SPECIAL_FRONTEND_EQUAL - 0x21442F412E8DE56B 0x6FE5D865

void SPECIAL_FRONTEND_EQUAL(float x, float y, float z)

```
Hash collision!!! PLAY_STREAM_FROM_POSITION is the correct name!
```

> STOP_STREAM - 0xA4718A1419D18151 0xD1E364DE

void STOP_STREAM()



> STOP_PED_SPEAKING - 0x9D64D7405520E3D3 0xFF92B49D

void STOP_PED_SPEAKING(Ped ped, BOOL shaking)



> DISABLE_PED_PAIN_AUDIO - 0xA9A41C1E940FB0E8 0x3B8E2D5F

void DISABLE_PED_PAIN_AUDIO(Ped ped, BOOL toggle)



> IS_AMBIENT_SPEECH_DISABLED - 0x932C2D096A2C3FFF 0x109D1F89

BOOL IS_AMBIENT_SPEECH_DISABLED(Ped ped)

```
Common in the scripts:
AUDIO::IS_AMBIENT_SPEECH_DISABLED(PLAYER::PLAYER_PED_ID());
```

> SET_SIREN_WITH_NO_DRIVER - 0x1FEF0683B96EBCF2 0x77182D58

void SET_SIREN_WITH_NO_DRIVER(Vehicle vehicle, BOOL set)



> _SOUND_VEHICLE_HORN_THIS_FRAME - 0x9C11908013EA4715 0xDE8BA3CD

void _SOUND_VEHICLE_HORN_THIS_FRAME(Vehicle vehicle)



> SET_HORN_ENABLED - 0x76D683C108594D0E 0x6EB92D05

void SET_HORN_ENABLED(Vehicle vehicle, BOOL toggle)



> SET_AUDIO_VEHICLE_PRIORITY - 0xE5564483E407F914 0x271A9766

void SET_AUDIO_VEHICLE_PRIORITY(Vehicle vehicle, Any p1)



> 0x9D3AF56E94C9AE98 0x2F0A16D1

void 0x9D3AF56E94C9AE98(Any p0, float p1)



> USE_SIREN_AS_HORN - 0xFA932DE350266EF8 0xC6BC16F3

void USE_SIREN_AS_HORN(Vehicle vehicle, BOOL toggle)



> _SET_VEHICLE_AUDIO - 0x4F0C413926060B38 0x33B0B007

void _SET_VEHICLE_AUDIO(Vehicle vehicle, char* audioName)

```
This native sets the audio of the specified vehicle to the audioName (p1).

Use the audioNameHash found in vehicles.meta

Example:
_SET_VEHICLE_AUDIO(veh, 'ADDER');
The selected vehicle will now have the audio of the Adder.

FORCE_VEHICLE_???
```

> 0xF1F8157B8C3F171C 0x1C0C5E4C

void 0xF1F8157B8C3F171C(Any p0, char* p1, char* p2)

```
2 calls found in the b617d scripts:

AUDIO::_F1F8157B8C3F171C(l_A42, 'Franklin_Bike_Rev', 'BIG_SCORE_3A_SOUNDS');
AUDIO::_F1F8157B8C3F171C(l_166, 'Trevor_Revs_Off', 'PALETO_SCORE_SETUP_SOUNDS');
```

> 0xD2DCCD8E16E20997 

void 0xD2DCCD8E16E20997(Any p0)



> 0x5DB8010EE71FDEF2 0x6E660D3F

BOOL 0x5DB8010EE71FDEF2(Any p0)



> 0x59E7B488451F4D3A 0x23BE6432

void 0x59E7B488451F4D3A(Any p0, float p1)



> 0x01BB4D577D38BD9E 0xE81FAC68

void 0x01BB4D577D38BD9E(Any p0, float p1)



> 0x1C073274E065C6D2 0x9365E042

void 0x1C073274E065C6D2(Any p0, BOOL p1)



> 0x2BE4BC731D039D5A 0x2A60A90E

void 0x2BE4BC731D039D5A(Any p0, BOOL p1)



> SET_VEHICLE_BOOST_ACTIVE - 0x4A04DE7CAB2739A1 0x072F15F2

void SET_VEHICLE_BOOST_ACTIVE(Vehicle vehicle, BOOL Toggle)

```
SET_VEHICLE_BOOST_ACTIVE(vehicle, 1, 0);
SET_VEHICLE_BOOST_ACTIVE(vehicle, 0, 0); 

Will give a boost-soundeffect.
```

> 0x6FDDAD856E36988A 0x934BE749

void 0x6FDDAD856E36988A(Any p0, BOOL p1)



> 0x06C0023BED16DD6B 0xE61110A2

void 0x06C0023BED16DD6B(Any p0, BOOL p1)



> PLAY_VEHICLE_DOOR_OPEN_SOUND - 0x3A539D52857EA82D 0x84930330

void PLAY_VEHICLE_DOOR_OPEN_SOUND(Vehicle vehicle, int p1)

```
p1 appears to only be '0' or '3'. I personally use '0' as p1.
-xNITEMAREx
```

> PLAY_VEHICLE_DOOR_CLOSE_SOUND - 0x62A456AA4769EF34 0xBA2CF407

void PLAY_VEHICLE_DOOR_CLOSE_SOUND(Vehicle vehicle, int p1)

```
This native only comes up once. And in that one instance, p1 is '1'.
-xNITEMAREx
```

> 0xC15907D667F7CFB2 0x563B635D

void 0xC15907D667F7CFB2(Vehicle vehicle, BOOL toggle)



> IS_GAME_IN_CONTROL_OF_MUSIC - 0x6D28DC1671E334FD 0x7643170D

BOOL IS_GAME_IN_CONTROL_OF_MUSIC()

```
Hardcoded to return 1
```

> SET_GPS_ACTIVE - 0x3BD3F52BA9B1E4E8 0x0FC3379A

void SET_GPS_ACTIVE(BOOL active)



> PLAY_MISSION_COMPLETE_AUDIO - 0xB138AAB8A70D3C69 0x3033EA1D

void PLAY_MISSION_COMPLETE_AUDIO(char* audioName)

```
 Called 38 times in the scripts. There are 5 different audioNames used. 
 One unknown removed below. 

 AUDIO::PLAY_MISSION_COMPLETE_AUDIO('DEAD');
 AUDIO::PLAY_MISSION_COMPLETE_AUDIO('FRANKLIN_BIG_01');
 AUDIO::PLAY_MISSION_COMPLETE_AUDIO('GENERIC_FAILED');
 AUDIO::PLAY_MISSION_COMPLETE_AUDIO('TREVOR_SMALL_01');
```

> IS_MISSION_COMPLETE_PLAYING - 0x19A30C23F5827F8A 0x939982A1

BOOL IS_MISSION_COMPLETE_PLAYING()



> 0x6F259F82D873B8B8 0xCBE09AEC

Any 0x6F259F82D873B8B8()



> 0xF154B8D1775B2DEC 0xD2858D8A

void 0xF154B8D1775B2DEC(BOOL p0)



> START_AUDIO_SCENE - 0x013A80FC08F6E4F2 0xE48D757B

BOOL START_AUDIO_SCENE(char* sceneName)

```
Used to prepare a scene where the surrounding sound is muted or a bit changed. This does not play any sound.

List of all usable scene names found in b617d. Sorted alphabetically and identical names removed: pastebin.com/MtM9N9CC
```

> STOP_AUDIO_SCENE - 0xDFE8422B3B94E688 0xA08D8C58

void STOP_AUDIO_SCENE(char* scene)



> STOP_AUDIO_SCENES - 0xBAC7FC81A75EC1A1 0xF6C7342A

void STOP_AUDIO_SCENES()

```
??
```

> IS_AUDIO_SCENE_ACTIVE - 0xB65B60556E2A9225 0xACBED05C

BOOL IS_AUDIO_SCENE_ACTIVE(char* scene)



> SET_AUDIO_SCENE_VARIABLE - 0xEF21A9EF089A2668 0x19BB3CE8

void SET_AUDIO_SCENE_VARIABLE(Any* p0, Any* p1, float p2)



> 0xA5F377B175A699C5 0xE812925D

void 0xA5F377B175A699C5(Any p0)



> 0x153973AB99FE8980 0x2BC93264

void 0x153973AB99FE8980(Entity p0, char* p1, float p2)

```
All found occurrences in b678d:
pastebin.com/ceu67jz8

Still not sure on the functionality of this native but it has something to do with dynamic mixer groups defined in dynamix.dat15
```

> 0x18EB48CFC41F2EA0 0x308ED0EC

void 0x18EB48CFC41F2EA0(Any p0, float p1)



> AUDIO_IS_SCRIPTED_MUSIC_PLAYING - 0x845FFC3A4FEEFA3E 0x86E995D1

Any AUDIO_IS_SCRIPTED_MUSIC_PLAYING()



> PREPARE_MUSIC_EVENT - 0x1E5185B72EF5158A 0x534A5C1C

BOOL PREPARE_MUSIC_EVENT(char* eventName)

```
All music event names found in the b617d scripts: pastebin.com/GnYt0R3P
```

> CANCEL_MUSIC_EVENT - 0x5B17A90291133DA5 0x89FF942D

BOOL CANCEL_MUSIC_EVENT(char* eventName)

```
All music event names found in the b617d scripts: pastebin.com/GnYt0R3P
```

> TRIGGER_MUSIC_EVENT - 0x706D57B0F50DA710 0xB6094948

BOOL TRIGGER_MUSIC_EVENT(char* eventName)

```
List of all usable event names found in b617d used with this native. Sorted alphabetically and identical names removed: pastebin.com/RzDFmB1W

All music event names found in the b617d scripts: pastebin.com/GnYt0R3P
```

> 0xA097AB275061FB21 0x2705C4D5

Any 0xA097AB275061FB21()



> GET_MUSIC_PLAYTIME - 0xE7A0D23DC414507B 0xD633C809

Any GET_MUSIC_PLAYTIME()



> 0xFBE20329593DEC9D 0x53FC3FEC

void 0xFBE20329593DEC9D(Any p0, Any p1, Any p2, Any p3)



> CLEAR_ALL_BROKEN_GLASS - 0xB32209EFFDC04913 0xE6B033BF

Any CLEAR_ALL_BROKEN_GLASS()



> 0x70B8EC8FC108A634 0x95050CAD

void 0x70B8EC8FC108A634(BOOL p0, Any p1)



> 0x149AEE66F0CB3A99 0xE64F97A0

void 0x149AEE66F0CB3A99(float p0, float p1)



> 0x8BF907833BE275DE 

void 0x8BF907833BE275DE(float p0, float p1)



> 0x062D5EAD4DA2FA6A 0xD87AF337

void 0x062D5EAD4DA2FA6A()



> PREPARE_ALARM - 0x9D74AE343DB65533 0x084932E8

BOOL PREPARE_ALARM(char* alarmName)

```
Example:

bool prepareAlarm = AUDIO::PREPARE_ALARM('PORT_OF_LS_HEIST_FORT_ZANCUDO_ALARMS');

~Zerovv
```

> START_ALARM - 0x0355EF116C4C97B2 0x703F524B

void START_ALARM(char* alarmName, BOOL p2)

```
Example:

This will start the alarm at Fort Zancudo.

AUDIO::START_ALARM('PORT_OF_LS_HEIST_FORT_ZANCUDO_ALARMS', 1);

First parameter (char) is the name of the alarm.
Second parameter (bool) is unknown, it does not seem to make a difference if this one is 0 or 1.

~Zerovv

----------

It DOES make a difference but it has to do with the duration or something I dunno yet

----------

 Found in the b617d scripts:

 AUDIO::START_ALARM('AGENCY_HEIST_FIB_TOWER_ALARMS', 0);
 AUDIO::START_ALARM('AGENCY_HEIST_FIB_TOWER_ALARMS_UPPER', 1);
 AUDIO::START_ALARM('AGENCY_HEIST_FIB_TOWER_ALARMS_UPPER_B', 0);
 AUDIO::START_ALARM('BIG_SCORE_HEIST_VAULT_ALARMS', a_0);
 AUDIO::START_ALARM('FBI_01_MORGUE_ALARMS', 1);
 AUDIO::START_ALARM('FIB_05_BIOTECH_LAB_ALARMS', 0);
 AUDIO::START_ALARM('JEWEL_STORE_HEIST_ALARMS', 0);
 AUDIO::START_ALARM('PALETO_BAY_SCORE_ALARM', 1);
 AUDIO::START_ALARM('PALETO_BAY_SCORE_CHICKEN_FACTORY_ALARM', 0);
 AUDIO::START_ALARM('PORT_OF_LS_HEIST_FORT_ZANCUDO_ALARMS', 1);
 AUDIO::START_ALARM('PORT_OF_LS_HEIST_SHIP_ALARMS', 0);
 AUDIO::START_ALARM('PRISON_ALARMS', 0);
 AUDIO::START_ALARM('PROLOGUE_VAULT_ALARMS', 0);
```

> STOP_ALARM - 0xA1CADDCD98415A41 0xF987BE8C

void STOP_ALARM(char* alarmName, BOOL toggle)

```
Example:

This will stop the alarm at Fort Zancudo.

AUDIO::STOP_ALARM('PORT_OF_LS_HEIST_FORT_ZANCUDO_ALARMS', 1);

First parameter (char) is the name of the alarm.
Second parameter (bool) has to be true (1) to have any effect.

~Zerovv
```

> STOP_ALL_ALARMS - 0x2F794A877ADD4C92 0xC3CB9DC6

void STOP_ALL_ALARMS(BOOL stop)



> IS_ALARM_PLAYING - 0x226435CB96CCFC8C 0x9D8E1D23

BOOL IS_ALARM_PLAYING(char* alarmName)

```
Example:

bool playing = AUDIO::IS_ALARM_PLAYING('PORT_OF_LS_HEIST_FORT_ZANCUDO_ALARMS');

~Zerovv
```

> GET_VEHICLE_DEFAULT_HORN - 0x02165D55000219AC 0xE84ABC19

Hash GET_VEHICLE_DEFAULT_HORN(Vehicle veh)

```
Returns hash of default vehicle horn

Hash is stored in audVehicleAudioEntity
```

> 0xACB5DCCA1EC76840 0xFD4B5B3B

Any 0xACB5DCCA1EC76840(Any p0)

```
Seems to get the hash of the vehicle's currently installed horn? -Fireboyd78
```

> RESET_PED_AUDIO_FLAGS - 0xF54BB7B61036F335 0xDF720C86

void RESET_PED_AUDIO_FLAGS(Any p0)



> 0xD2CC78CD3D0B50F9 0xC307D531

void 0xD2CC78CD3D0B50F9(Any p0, BOOL p1)



> 0xBF4DC1784BE94DFA 

void 0xBF4DC1784BE94DFA(Any p0, BOOL p1, Any p2)



> 0x75773E11BA459E90 

void 0x75773E11BA459E90(Any p0, BOOL p1)



> 0xD57AAAE0E2214D11 

void 0xD57AAAE0E2214D11()



> 0x552369F549563AD5 0x13EB5861

void 0x552369F549563AD5(BOOL p0)

```
if value is set to true, and ambient siren sound will be played.

-------------------------------------------------------------------------

Appears to enable/disable an audio flag.
```

> 0x43FA0DFC5DF87815 0x7BED1872

void 0x43FA0DFC5DF87815(Any p0, BOOL p1)



> SET_AUDIO_FLAG - 0xB9EFD5C25018725A 0x1C09C9E0

void SET_AUDIO_FLAG(char* flagName, BOOL toggle)

```
Possible flag names:
(updated from b393d scripts - MoMadenU - 8/23/15)

'ActivateSwitchWheelAudio'
'AllowAmbientSpeechInSlowMo'
'AllowCutsceneOverScreenFade'
'AllowForceRadioAfterRetune'
'AllowPainAndAmbientSpeechToPlayDuringCutscene'
'AllowPlayerAIOnMission'
'AllowPoliceScannerWhenPlayerHasNoControl'
'AllowRadioDuringSwitch'
'AllowRadioOverScreenFade'
'AllowScoreAndRadio'
'AllowScriptedSpeechInSlowMo'
'AvoidMissionCompleteDelay'
'DisableAbortConversationForDeathAndInjury'
'DisableAbortConversationForRagdoll'
'DisableBarks'
'DisableFlightMusic'
'DisableReplayScriptStreamRecording'
'EnableHeadsetBeep'
'ForceConversationInterrupt'
'ForceSeamlessRadioSwitch'
'ForceSniperAudio'
'FrontendRadioDisabled'
'HoldMissionCompleteWhenPrepared'
'IsDirectorModeActive'
'IsPlayerOnMissionForSpeech'
'ListenerReverbDisabled'
'LoadMPData'
'MobileRadioInGame'
'OnlyAllowScriptTriggerPoliceScanner'
'PlayMenuMusic'
'PoliceScannerDisabled'
'ScriptedConvListenerMaySpeak'
'SpeechDucksScore'
'SuppressPlayerScubaBreathing'
'WantedMusicDisabled'
'WantedMusicOnMission'

-------------------------------
No added flag names between b393d and b573d, including b573d.

#######################################################################

'IsDirectorModeActive' is an audio flag which will allow you to play speech infinitely without any pauses like in Director Mode.

- jedijosh920

-----------------------------------------------------------------------

All flag IDs and hashes:

ID: 01 | Hash: 0x20A7858F
ID: 02 | Hash: 0xA11C2259
ID: 03 | Hash: 0x08DE4700
ID: 04 | Hash: 0x989F652F
ID: 05 | Hash: 0x3C9E76BA
ID: 06 | Hash: 0xA805FEB0
ID: 07 | Hash: 0x4B94EA26
ID: 08 | Hash: 0x803ACD34
ID: 09 | Hash: 0x7C741226
ID: 10 | Hash: 0x31DB9EBD
ID: 11 | Hash: 0xDF386F18
ID: 12 | Hash: 0x669CED42
ID: 13 | Hash: 0x51F22743
ID: 14 | Hash: 0x2052B35C
ID: 15 | Hash: 0x071472DC
ID: 16 | Hash: 0xF9928BCC
ID: 17 | Hash: 0x7ADBDD48
ID: 18 | Hash: 0xA959BA1A
ID: 19 | Hash: 0xBBE89B60
ID: 20 | Hash: 0x87A08871
ID: 21 | Hash: 0xED1057CE
ID: 22 | Hash: 0x1584AD7A
ID: 23 | Hash: 0x8582CFCB
ID: 24 | Hash: 0x7E5E2FB0
ID: 25 | Hash: 0xAE4F72DB
ID: 26 | Hash: 0x5D16D1FA
ID: 27 | Hash: 0x06B2F4B8
ID: 28 | Hash: 0x5D4CDC96
ID: 29 | Hash: 0x8B5A48BA
ID: 30 | Hash: 0x98FBD539
ID: 31 | Hash: 0xD8CB0473
ID: 32 | Hash: 0x5CBB4874
ID: 33 | Hash: 0x2E9F93A9
ID: 34 | Hash: 0xD93BEA86
ID: 35 | Hash: 0x92109B7D
ID: 36 | Hash: 0xB7EC9E4D
ID: 37 | Hash: 0xCABDBB1D
ID: 38 | Hash: 0xB3FD4A52
ID: 39 | Hash: 0x370D94E5
ID: 40 | Hash: 0xA0F7938F
ID: 41 | Hash: 0xCBE1CE81
ID: 42 | Hash: 0xC27F1271
ID: 43 | Hash: 0x9E3258EB
ID: 44 | Hash: 0x551CDA5B
ID: 45 | Hash: 0xCB6D663C
ID: 46 | Hash: 0x7DACE87F
ID: 47 | Hash: 0xF9DE416F
ID: 48 | Hash: 0x882E6E9E
ID: 49 | Hash: 0x16B447E7
ID: 50 | Hash: 0xBD867739
ID: 51 | Hash: 0xA3A58604
ID: 52 | Hash: 0x7E046BBC
ID: 53 | Hash: 0xD95FDB98
ID: 54 | Hash: 0x5842C0ED
ID: 55 | Hash: 0x285FECC6
ID: 56 | Hash: 0x9351AC43
ID: 57 | Hash: 0x50032E75
ID: 58 | Hash: 0xAE6D0D59
ID: 59 | Hash: 0xD6351785
ID: 60 | Hash: 0xD25D71BC
ID: 61 | Hash: 0x1F7F6423
ID: 62 | Hash: 0xE24C3AA6
ID: 63 | Hash: 0xBFFDD2B7
```

> PREPARE_SYNCHRONIZED_AUDIO_EVENT - 0xC7ABCACA4985A766 0xE1D91FD0

Any PREPARE_SYNCHRONIZED_AUDIO_EVENT(char* p0, Any p1)



> PREPARE_SYNCHRONIZED_AUDIO_EVENT_FOR_SCENE - 0x029FE7CD1B7E2E75 0x7652DD49

BOOL PREPARE_SYNCHRONIZED_AUDIO_EVENT_FOR_SCENE(Any p0, Any* p1)



> PLAY_SYNCHRONIZED_AUDIO_EVENT - 0x8B2FD4560E55DD2D 0x507F3241

BOOL PLAY_SYNCHRONIZED_AUDIO_EVENT(Any p0)



> STOP_SYNCHRONIZED_AUDIO_EVENT - 0x92D6A88E64A94430 0xADEED2B4

BOOL STOP_SYNCHRONIZED_AUDIO_EVENT(Any p0)



> 0xC8EDE9BDBCCBA6D4 0x55A21772

void 0xC8EDE9BDBCCBA6D4(Any* p0, float p1, float p2, float p3)



> _SET_SYNCHRONIZED_AUDIO_EVENT_POSITION_THIS_FRAME - 0x950A154B8DAB6185 0xA17F9AB0

void _SET_SYNCHRONIZED_AUDIO_EVENT_POSITION_THIS_FRAME(char* p0, Entity p1)

```
Sets the position of the audio event to the entity's position for one frame(?)

if (l_8C3 == 0) {
    sub_27fd1(0, -1, 1);
    if (PED::IS_SYNCHRONIZED_SCENE_RUNNING(l_87D)) {
        AUDIO::STOP_SYNCHRONIZED_AUDIO_EVENT(l_87D);
    }
    if (sub_7dd(l_A00)) {
        AUDIO::_950A154B8DAB6185('PAP2_IG1_POPPYSEX', l_A00);
    }
    sub_91c('TK************ SETTING SYNCH SCENE AUDIO POSITION THIS FRAME ************TK');
    l_8C3 = 1;
}

--

Found in the b617d scripts, duplicates removed: 

AUDIO::_950A154B8DAB6185('CAR_5_IG_6', l_7FE[1/*1*/]);
AUDIO::_950A154B8DAB6185('EX03_TRAIN_BIKE_LAND',   PLAYER::PLAYER_PED_ID());
AUDIO::_950A154B8DAB6185('FBI_2_MCS_1_LeadIn', l_40[2/*1*/]);
AUDIO::_950A154B8DAB6185('FIN_C2_MCS_1', l_24C[0/*1*/]);
AUDIO::_950A154B8DAB6185('MNT_DNC', l_5F);
AUDIO::_950A154B8DAB6185('PAP2_IG1_POPPYSEX', l_A00);
```

> 0x12561FCBB62D5B9C 0x62B43677

void 0x12561FCBB62D5B9C(Any p0)

```
p0 is usually 0. sometimes 2. Not sure what this does.
```

> 0x044DBAD7A7FA2BE5 0x8AD670EC

void 0x044DBAD7A7FA2BE5(char* p0, char* p1)

```
Found in the b617d scripts, duplicates removed:  

AUDIO::_044DBAD7A7FA2BE5('V_CARSHOWROOM_PS_WINDOW_UNBROKEN', 'V_CARSHOWROOM_PS_WINDOW_BROKEN');

 AUDIO::_044DBAD7A7FA2BE5('V_CIA_PS_WINDOW_UNBROKEN', 'V_CIA_PS_WINDOW_BROKEN');

 AUDIO::_044DBAD7A7FA2BE5('V_DLC_HEIST_APARTMENT_DOOR_CLOSED', 'V_DLC_HEIST_APARTMENT_DOOR_OPEN');

 AUDIO::_044DBAD7A7FA2BE5('V_FINALEBANK_PS_VAULT_INTACT', 'V_FINALEBANK_PS_VAULT_BLOWN');

 AUDIO::_044DBAD7A7FA2BE5('V_MICHAEL_PS_BATHROOM_WITH_WINDOW', 'V_MICHAEL_PS_BATHROOM_WITHOUT_WINDOW');
```

> 0xB4BBFD9CD8B3922B 0xD24B4D0C

void 0xB4BBFD9CD8B3922B(char* p0)

```
 Found in the b617d scripts, duplicates removed: 

 AUDIO::_B4BBFD9CD8B3922B('V_CARSHOWROOM_PS_WINDOW_UNBROKEN');
 AUDIO::_B4BBFD9CD8B3922B('V_CIA_PS_WINDOW_UNBROKEN');
 AUDIO::_B4BBFD9CD8B3922B('V_DLC_HEIST_APARTMENT_DOOR_CLOSED');
 AUDIO::_B4BBFD9CD8B3922B('V_FINALEBANK_PS_VAULT_INTACT');
 AUDIO::_B4BBFD9CD8B3922B('V_MICHAEL_PS_BATHROOM_WITH_WINDOW');
```

> 0xE4E6DD5566D28C82 0x7262B5BA

void 0xE4E6DD5566D28C82()



> 0x3A48AB4445D499BE 0x93A44A1F

Any 0x3A48AB4445D499BE()



> 0x4ADA3F19BE4A6047 0x13777A0B

void 0x4ADA3F19BE4A6047(Ped ped)

```
MulleDK19: Speech related.
```

> 0x0150B6FF25A9E2E5 0x1134F68B

void 0x0150B6FF25A9E2E5()



> 0xBEF34B1D9624D5DD 0xE0047BFD

void 0xBEF34B1D9624D5DD(BOOL p0)



> 0x806058BBDC136E06 

void 0x806058BBDC136E06()



> 0x544810ED9DB6BBE6 

Any 0x544810ED9DB6BBE6()



> 0x5B50ABB1FE3746F4 

Any 0x5B50ABB1FE3746F4()



