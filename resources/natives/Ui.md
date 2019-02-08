# Ui

> _SET_LOADING_PROMPT_TEXT_ENTRY - 0xABA17D7CE615ADBF 0xCB7C8994

void _SET_LOADING_PROMPT_TEXT_ENTRY(char* string)

```
Initializes the text entry for the the text next to a loading prompt. All natives for for building UI texts can be used here


e.g
void StartLoadingMessage(char *text, int spinnerType = 3)
	{
		_SET_LOADING_PROMPT_TEXT_ENTRY('STRING');
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		_SHOW_LOADING_PROMPT(spinnerType);
	}
/*OR*/
	void ShowLoadingMessage(char *text, int spinnerType = 3, int timeMs = 10000)
	{
		_SET_LOADING_PROMPT_TEXT_ENTRY('STRING');
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		_SHOW_LOADING_PROMPT(spinnerType);
		WAIT(timeMs);
		_REMOVE_LOADING_PROMPT();
	}


These are some localized strings used in the loading spinner.
'PM_WAIT'                   = Please Wait
'CELEB_WPLYRS'              = Waiting For Players.
'CELL_SPINNER2'             = Scanning storage.
'ERROR_CHECKYACHTNAME' = Registering your yacht's name. Please wait.
'ERROR_CHECKPROFANITY'   = Checking your text for profanity. Please wait.
'FM_COR_AUTOD'                        = Just spinner no text
'FM_IHELP_WAT2'                        = Waiting for other players
'FM_JIP_WAITO'                            = Game options are being set
'FMMC_DOWNLOAD'                    = Downloading
'FMMC_PLYLOAD'                         = Loading
'FMMC_STARTTRAN'                    = Launching session
'HUD_QUITTING'                           =  Quiting session
'KILL_STRIP_IDM'                         = Waiting for to accept
'MP_SPINLOADING'                      = Loading
```

> _SHOW_LOADING_PROMPT - 0xBD12F8228410D9B4 0x903F5EE4

void _SHOW_LOADING_PROMPT(int busySpinnerType)

```
This does NOT get called per frame. Call it once to show, then use UI::_REMOVE_LOADING_PROMPT to remove it

Changes the the above native's (UI::_SET_LOADING_PROMPT_TEXT_ENTRY) spinning circle type.

Types:
enum LoadingPromptTypes
{
	LOADING_PROMPT_LEFT,
	LOADING_PROMPT_LEFT_2,
	LOADING_PROMPT_LEFT_3,
	SAVE_PROMPT_LEFT,
	LOADING_PROMPT_RIGHT,
};
```

> _REMOVE_LOADING_PROMPT - 0x10D373323E5B9C0D 0x94119534

void _REMOVE_LOADING_PROMPT()

```
Removes the loading prompt at the bottom right of the screen, created by the UI::_SHOW_LOADING_PROMPT native.
```

> 0xC65AB383CD91DF98 0x71077FBD

void 0xC65AB383CD91DF98()

```
Often called after _REMOVE_LOADING_PROMPT. Unsure what exactly it does, but It references busy_spinner, I can only guess its freeing the busy_spinner scaleform from memory
```

> _IS_LOADING_PROMPT_BEING_DISPLAYED - 0xD422FCC5F239A915 0xB8B3A5D0

BOOL _IS_LOADING_PROMPT_BEING_DISPLAYED()



> 0xB2A592B04648A9CB 

Any 0xB2A592B04648A9CB()



> 0x9245E81072704B8A 

void 0x9245E81072704B8A(BOOL p0)



> _SHOW_CURSOR_THIS_FRAME - 0xAAE7CE1D63167423 

void _SHOW_CURSOR_THIS_FRAME()

```
Shows the cursor on screen for the frame its called.
```

> _SET_CURSOR_SPRITE - 0x8DB8CFFD58B62552 

void _SET_CURSOR_SPRITE(int spriteId)

```
Changes the mouse cursor's sprite. 
1 = Normal
6 = Left Arrow
7 = Right Arrow
```

> 0x98215325A695E78A 

void 0x98215325A695E78A(BOOL p0)



> 0x3D9ACB1EB139E702 

Any 0x3D9ACB1EB139E702()



> 0x632B2940C67F4EA9 

BOOL 0x632B2940C67F4EA9(int scaleformHandle, Any* p1, Any* p2, Any* p3)



> 0x6F1554B0CC2089FA 0xA7C8594B

void 0x6F1554B0CC2089FA(BOOL p0)



> 0x55598D21339CB998 0x1DA7E41A

void 0x55598D21339CB998(float p0)



> 0x25F87B30C382FCA7 0x1E63088A

void 0x25F87B30C382FCA7()



> 0xA8FDB297A8D25FBA 0x5205C6F5

void 0xA8FDB297A8D25FBA()



> _REMOVE_NOTIFICATION - 0xBE4390CB40B3E627 0xECA8ACB9

void _REMOVE_NOTIFICATION(int notifactionId)

```
Removes a notification instantly instead of waiting for it to disappear
```

> 0xA13C11E1B5C06BFC 0x520FCB6D

void 0xA13C11E1B5C06BFC()



> 0x583049884A2EEE3C 0xC8BAB2F2

void 0x583049884A2EEE3C()



> 0xFDB423997FA30340 0x4D0449C6

void 0xFDB423997FA30340()



> 0xE1CD1E48E025E661 0xD3F40140

void 0xE1CD1E48E025E661()



> 0xA9CBFD40B3FA3010 0xC5223796

Any 0xA9CBFD40B3FA3010()



> 0xD4438C0564490E63 0x709B4BCB

void 0xD4438C0564490E63()



> 0xB695E2CD0A2DA9EE 0x4A4A40A4

void 0xB695E2CD0A2DA9EE()



> _GET_CURRENT_NOTIFICATION - 0x82352748437638CA 0x294405D4

int _GET_CURRENT_NOTIFICATION()

```
Returns the handle for the notification currently displayed on the screen.
```

> 0x56C8B608CFD49854 0xF881AB87

void 0x56C8B608CFD49854()



> 0xADED7F5748ACAFE6 0x1D6859CA

void 0xADED7F5748ACAFE6()



> 0x92F0DA1E27DB96DC 

void 0x92F0DA1E27DB96DC(int p0)

```
From the decompiled scripts:
UI::_92F0DA1E27DB96DC(6);
UI::_92F0DA1E27DB96DC(184);
UI::_92F0DA1E27DB96DC(190);

sets background color for the next notification
6 = red
184 = green
190 = yellow
```

> _SET_NOTIFICATION_FLASH_COLOR - 0x17430B918701C342 0xCF14D7F2

void _SET_NOTIFICATION_FLASH_COLOR(int red, int green, int blue, int alpha)

```
sets color for notification flash
```

> 0x17AD8C9706BDD88A 0x24A97AF8

void 0x17AD8C9706BDD88A(Any p0)



> 0x4A0C7C9BB10ABB36 0x44018EDB

void 0x4A0C7C9BB10ABB36(BOOL p0)



> 0xFDD85225B2DEA55E 0xA4524B23

void 0xFDD85225B2DEA55E()



> 0xFDEC055AB549E328 0xAFA1148B

void 0xFDEC055AB549E328()



> 0x80FE4F3AB4E1B62A 0x3CD4307C

void 0x80FE4F3AB4E1B62A()



> 0xBAE4F9B97CD43B30 

void 0xBAE4F9B97CD43B30(BOOL p0)



> 0x317EBA71D7543F52 

void 0x317EBA71D7543F52(Any* p0, Any* p1, Any* p2, Any* p3)

```
From the decompiled scripts, called 61 times:
UI::_317EBA71D7543F52(&amp;v_13, &amp;v_13, &amp;v_3, &amp;v_3);
```

> _SET_NOTIFICATION_TEXT_ENTRY - 0x202709F4C58A0424 0x574EE85C

void _SET_NOTIFICATION_TEXT_ENTRY(char* type)

```
Declares the entry type of a notification, for example 'STRING'.
```

> 0x2B7E9A4EAAA93C89 0xED130FA1

int 0x2B7E9A4EAAA93C89(char* p0, int p1, int p2, int p3, BOOL p4, char* picName1, char* picName2)



> _SET_NOTIFICATION_MESSAGE - 0x1CCD9A37359072CF 0xE7E3C98B

int _SET_NOTIFICATION_MESSAGE(char* picName1, char* picName2, BOOL flash, int iconType, char* sender, char* subject)

```
picName1 &amp; picName2 must match. Possibilities: 'CHAR_SIMEON', 'CHAR_DEFAULT', 'CHAR_FACEBOOK', 'CHAR_SOCIAL_CLUB', 'CHAR_BLOCKED', 'CHAR_ALL_PLAYERS_CONF'


flash is a bool for fading in.
iconTypes:
1 : Chat Box
2 : Email
3 : Add Friend Request
4 : Nothing
5 : Nothing
6 : Nothing
7 : Right Jumping Arrow
8 : RP Icon
9 : $ Icon

'sender' is the very top header. This can be any old string.
'subject' is the header under the sender.
```

> 0xC6F580E4C94926AC 

int 0xC6F580E4C94926AC(char* picName1, char* picName2, BOOL p2, Any p3, char* p4, char* p5)

```
Needs more research.

Only one type of usage in the scripts:

UI::_C6F580E4C94926AC('CHAR_ACTING_UP', 'CHAR_ACTING_UP', 0, 0, 'DI_FEED_CHAR', a_0);
```

> 0x1E6611149DB3DB6B 0x0EB382B7

int 0x1E6611149DB3DB6B(char* picName1, char* picName2, BOOL flash, int iconType, char* sender, char* subject, float duration)

```
NOTE: 'duration' is a multiplier, so 1.0 is normal, 2.0 is twice as long (very slow), and 0.5 is half as long.

Example, only occurrence in the scripts:
v_8 = UI::_1E6611149DB3DB6B('CHAR_SOCIAL_CLUB', 'CHAR_SOCIAL_CLUB', 0, 0, &amp;v_9, '', a_5);
```

> _SET_NOTIFICATION_MESSAGE_CLAN_TAG - 0x5CBF7BADE20DB93E 0x3E807FE3

int _SET_NOTIFICATION_MESSAGE_CLAN_TAG(char* picName1, char* picName2, BOOL flash, int iconType, char* sender, char* subject, float duration, char* clanTag)

```
picName1 &amp; picName2 must match. Possibilities: 'CHAR_DEFAULT', 'CHAR_FACEBOOK', 'CHAR_SOCIAL_CLUB'.
List of picNames pastebin.com/XdpJVbHz
flash is a bool for fading in.
iconTypes:
1 : Chat Box
2 : Email
3 : Add Friend Request
4 : Nothing
5 : Nothing
6 : Nothing
7 : Right Jumping Arrow
8 : RP Icon
9 : $ Icon

'sender' is the very top header. This can be any old string.
'subject' is the header under the sender.
'duration' is a multiplier, so 1.0 is normal, 2.0 is twice as long (very slow), and 0.5 is half as long.
'clanTag' shows a crew tag in the 'sender' header, after the text. You need to use 3 underscores as padding. Maximum length of this field seems to be 7. (e.g. 'MK' becomes '___MK', 'ACE' becomes '___ACE', etc.)
```

> _SET_NOTIFICATION_MESSAGE_CLAN_TAG_2 - 0x531B84E7DA981FB6 0xDEB491C8

int _SET_NOTIFICATION_MESSAGE_CLAN_TAG_2(char* picName1, char* picName2, BOOL flash, int iconType1, char* sender, char* subject, float duration, char* clanTag, int iconType2, int p9)

```
picName1 &amp; picName2 must match. Possibilities: 'CHAR_DEFAULT', 'CHAR_FACEBOOK', 'CHAR_SOCIAL_CLUB'.
flash is a bool for fading in.
iconTypes:
1 : Chat Box
2 : Email
3 : Add Friend Request
4 : Nothing
5 : Nothing
6 : Nothing
7 : Right Jumping Arrow
8 : RP Icon
9 : $ Icon

'sender' is the very top header. This can be any old string.
'subject' is the header under the sender.
'duration' is a multiplier, so 1.0 is normal, 2.0 is twice as long (very slow), and 0.5 is half as long.
'clanTag' shows a crew tag in the 'sender' header, after the text. You need to use 3 underscores as padding. Maximum length of this field seems to be 7. (e.g. 'MK' becomes '___MK', 'ACE' becomes '___ACE', etc.)
iconType2 is a mirror of iconType. It shows in the 'subject' line, right under the original iconType.
```

> _DRAW_NOTIFICATION - 0x2ED7843F8F801023 0x08F7AF78

int _DRAW_NOTIFICATION(BOOL blink, BOOL p1)

```
Draws a notification above the map and returns the notifications handle

Color syntax:
~r~ = Red
~b~ = Blue
~g~ = Green
~y~ = Yellow
~p~ = Purple
~o~ = Orange
~c~ = Grey
~m~ = Darker Grey
~u~ = Black
~n~ = New Line
~s~ = Default White
~w~ = White
~h~ = Bold Text
~nrt~ = ???

Special characters:
� = Rockstar Verified Icon (U+00A6:Broken Bar - Alt+0166)
? = Rockstar Icon (U+00F7:Division Sign - Alt+0247)
? = Rockstar Icon 2 (U+2211:N-Ary Summation)

Example C#:
            Function.Call(Hash._ADD_TEXT_COMPONENT_STRING3, 'Now I need you to bring the ~b~vehicle~w~ back to me!');
```

> _DRAW_NOTIFICATION_2 - 0x44FA03975424A0EE 0x57B8D0D4

int _DRAW_NOTIFICATION_2(BOOL blink, BOOL p1)



> _DRAW_NOTIFICATION_3 - 0x378E809BF61EC840 0x02BCAF9B

int _DRAW_NOTIFICATION_3(BOOL blink, BOOL p1)



> 0xAA295B6F28BD587D 0x02DED2B8

int 0xAA295B6F28BD587D(char* p0, char* p1, int p2, int p3, char* p4)

```
Example:

UI::_SET_NOTIFICATION_TEXT_ENTRY('HUNT');
UI::_0xAA295B6F28BD587D('Hunting', 'Hunting_Gold_128', 0, 109, 'HUD_MED_UNLKED');
```

> 0x97C9E4E7024A8F2C 0xA9CCEF66

Any 0x97C9E4E7024A8F2C(BOOL p0, BOOL p1, Any* p2, Any p3, BOOL p4, BOOL p5, Any p6, Any p7, Any p8, Any p9)

```
This function and the one below it are for after you receive an invite, not sending it.

p0 = 1 or 0

nothin doin. 
int invite(Player player)
	{
		int iVar2, iVar3;
		networkHandleMgr handle;
		NETWORK_HANDLE_FROM_PLAYER(player, &amp;handle.netHandle, 13);
		networkClanMgr clan;

		char *playerName = GET_PLAYER_NAME(player);
		_SET_NOTIFICATION_TEXT_ENTRY('STRING');
		_SET_NOTIFACTION_COLOR_NEXT(0);
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(playerName);
		if (NETWORK_CLAN_PLAYER_GET_DESC(&amp;clan, 35, &amp;handle.netHandle))
		{
			iVar2 = 0;
			if (ARE_STRINGS_EQUAL(clan.unk22, 'Leader') &amp;&amp; clan.unk30 == 0)
			{
				iVar2 = 1;
			}
			if (clan.unk21 &gt; 0)
			{
				iVar3 = 0;
			}
			else
			{
				iVar3 = 1;
			}
			BOOL unused = _0x54E79E9C(&amp;clan.clanHandle, 35);
			return _NOTIFICATION_SEND_APARTMENT_INVITE(iVar3, 0 /*unused*/, &amp;clan.unk17, clan.unk30, iVar2, 0, clan.clanHandle, 0, 0, 0);
		}
	}
```

> 0x137BC35589E34E1E 0x88B9B909

int 0x137BC35589E34E1E(BOOL p0, BOOL p1, Any* p2, Any p3, BOOL p4, BOOL unk0, Any p6, char* playerName, Any p8, Any p9, Any p10)

```
p0 = 1 or 0

crashes my game...
this is for sending invites to network players - jobs/apartment/ect... 
return notification handle

int invite(Player player)
	{
		networkHandleMgr netHandle;
		networkClanMgr clan;
		char *playerName = GET_PLAYER_NAME(player);
		_SET_NOTIFICATION_TEXT_ENTRY('STRING');
		_SET_NOTIFACTION_COLOR_NEXT(1);
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(playerName);
		NETWORK_HANDLE_FROM_PLAYER(player, &amp;netHandle.netHandle, 13);
		if (NETWORK_CLAN_PLAYER_IS_ACTIVE(&amp;netHandle.netHandle))
		{
			NETWORK_CLAN_PLAYER_GET_DESC(&amp;clan.clanHandle, 35, &amp;netHandle.netHandle);
			_NOTIFICATION_SEND_CLAN_INVITE(0, _0x54E79E9C(&amp;clan.clanHandle, 35), &amp;clan.unk17, clan.isLeader, 0, 0, clan.clanHandle, playerName, 0, 0, 0);
		}
	}
```

> 0x33EE12743CCD6343 0xE05E7052

Any 0x33EE12743CCD6343(Any p0, Any p1, Any p2)



> 0xC8F3AAF93D0600BF 0x4FA43BA4

Any 0xC8F3AAF93D0600BF(Any p0, Any p1, Any p2, Any p3)



> 0x7AE0589093A2E088 0x8C90D22F

Any 0x7AE0589093A2E088(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)



> _DRAW_NOTIFICATION_4 - 0xF020C96915705B3A 0x8E319AB8

int _DRAW_NOTIFICATION_4(BOOL blink, BOOL p1)



> 0x8EFCCF6EC66D85E4 

Any 0x8EFCCF6EC66D85E4(Any* p0, Any* p1, Any* p2, BOOL p3, BOOL p4)

```
Example, only occurrence in the scripts:
UI::_8EFCCF6EC66D85E4(&amp;v_23, &amp;v_13, &amp;v_13, 1, v_34);
```

> 0xB6871B0555B02996 0x5E93FBFA

Any 0xB6871B0555B02996(Any* p0, Any* p1, Any p2, Any* p3, Any* p4, Any p5)



> 0xD202B92CBF1D816F 

Any 0xD202B92CBF1D816F(int type, int image, char* text)

```
returns a notification handle, prints out a notification like below:
type range: 0 - 2
if you set type to 1, image goes from 0 - 39 - Xbox you can add text to

example: 
UI::_0xD202B92CBF1D816F(1, 20, 'Who you trynna get crazy with, ese? Don't you know I'm LOCO?!');
- imgur.com/lGBPCz3
```

> 0xDD6CB2CCE7C2735C 

Any 0xDD6CB2CCE7C2735C(int type, char* button, char* text)

```
returns a notification handle, prints out a notification like below:
type range: 0 - 2
if you set type to 1, button accepts '~INPUT_SOMETHING~'

example:
UI::_0xDD6CB2CCE7C2735C(1, '~INPUT_TALK~', 'Who you trynna get crazy with, ese? Don't you know I'm LOCO?!');
- imgur.com/UPy0Ial


Examples from the scripts:
l_D1[1/*1*/]=UI::_DD6CB2CCE7C2735C(1,'~INPUT_REPLAY_START_STOP_RECORDING~','');
l_D1[2/*1*/]=UI::_DD6CB2CCE7C2735C(1,'~INPUT_SAVE_REPLAY_CLIP~','');
l_D1[1/*1*/]=UI::_DD6CB2CCE7C2735C(1,'~INPUT_REPLAY_START_STOP_RECORDING~','');
l_D1[2/*1*/]=UI::_DD6CB2CCE7C2735C(1,'~INPUT_REPLAY_START_STOP_RECORDING_SECONDARY~','');

```

> _SET_TEXT_ENTRY_2 - 0xB87A37EEB7FAA67D 0xF42C43C7

void _SET_TEXT_ENTRY_2(char* p0)

```
Used to be known as _SET_TEXT_ENTRY_2
```

> _DRAW_SUBTITLE_TIMED - 0x9D77056A530643F6 0x38F82261

void _DRAW_SUBTITLE_TIMED(int time, BOOL p1)

```
Draws the subtitle at middle center of the screen.

int duration = time in milliseconds to show text on screen before disappearing

drawImmediately = If true, the text will be drawn immediately, if false, the text will be drawn after the previous subtitle has finished

Used to be known as _DRAW_SUBTITLE_TIMED
```

> 0x853648FD1063A213 0xDD524A11

void 0x853648FD1063A213(Any* p0)

```
nothin doin. 

void Message(char* text)
	{
		_SET_TEXT_ENTRY_CONDITIONAL('STRING');
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		_IS_CONDITIONAL_TEXT_ENTRY_DISPLAYED();
	}
```

> 0x8A9BA1AB3E237613 0x672EFB45

BOOL 0x8A9BA1AB3E237613()



> _SET_TEXT_ENTRY - 0x25FBB336DF1804CB 0x3E35563E

void _SET_TEXT_ENTRY(char* text)

```
The following were found in the decompiled script files:
STRING, TWOSTRINGS, NUMBER, PERCENTAGE, FO_TWO_NUM, ESMINDOLLA, ESDOLLA, MTPHPER_XPNO, AHD_DIST, CMOD_STAT_0, CMOD_STAT_1, CMOD_STAT_2, CMOD_STAT_3, DFLT_MNU_OPT, F3A_TRAFDEST, ES_HELP_SOC3

ESDOLLA - cash
ESMINDOLLA - cash (negative)

Used to be known as _SET_TEXT_ENTRY
```

> _DRAW_TEXT - 0xCD015E5BB0D96A57 0x6F8350CE

void _DRAW_TEXT(float x, float y)

```
After applying the properties to the text (See UI::SET_TEXT_), this will draw the text in the applied position. Also 0.0f &lt; x, y &lt; 1.0f, percentage of the axis.

Used to be known as _DRAW_TEXT
```

> _SET_TEXT_ENTRY_FOR_WIDTH - 0x54CE8AC98E120CAB 0x51E7A037

void _SET_TEXT_ENTRY_FOR_WIDTH(char* text)

```
Used for setting text entry and then getting the text width via _GET_TEXT_SCREEN_WIDTH.

Example:
_SET_TEXT_ENTRY_FOR_WIDTH('NUMBER');
ADD_TEXT_COMPONENT_FLOAT(69.420f, 2);
FLOAT width = _GET_TEXT_SCREEN_WIDTH(1);

// YOU CANNOT DRAW TEXT WITH THIS. USE _SET_TEXT_ENTRY FOR THAT
```

> _GET_TEXT_SCREEN_WIDTH - 0x85F061DA64ED2F67 0xD12A643A

float _GET_TEXT_SCREEN_WIDTH(BOOL p0)

```
In scripts font most of the time is passed as 1.
Use _SET_TEXT_ENTRY_FOR_WIDTH

param is not font from what i've tested
```

> _SET_TEXT_GXT_ENTRY - 0x521FB041D93DD0E4 0x94B82066

void _SET_TEXT_GXT_ENTRY(char* entry)

```
get's line count


int GetLineCount(char *text, float x, float y)
	{
		_SET_TEXT_ENTRY_FOR_LINE_COUNT('STRING');
                ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		return _GET_TEXT_SCREEN_LINE_COUNT(x, y);
	}
```

> 0x9040DFB09BE75706 0xAA318785

int 0x9040DFB09BE75706(float p0, float p1)

```
Determines how many lines the text string will use when drawn on screen. 
Must use 0x521FB041D93DD0E4 for setting up
```

> _SET_TEXT_COMPONENT_FORMAT - 0x8509B634FBE7DA11 0xB245FC10

void _SET_TEXT_COMPONENT_FORMAT(char* inputType)

```
Used to be known as _SET_TEXT_COMPONENT_FORMAT
```

> _DISPLAY_HELP_TEXT_FROM_STRING_LABEL - 0x238FFE5C7B0498A6 0xB59B530D

void _DISPLAY_HELP_TEXT_FROM_STRING_LABEL(Any p0, BOOL loop, BOOL beep, int shape)

```
shape goes from -1 to 50 (may be more).
p0 is always 0.

Example:
void FloatingHelpText1(char* text)
{
	BEGIN_TEXT_COMMAND_DISPLAY_HELP('STRING');
	ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
	END_TEXT_COMMAND_DISPLAY_HELP (0, 0, 1, -1);
}

Image:
- imgbin.org/images/26209.jpg

more inputs/icons: (scroll to line 377 and below)
- pastebin.com/nqNYWMSB

Used to be known as _DISPLAY_HELP_TEXT_FROM_STRING_LABEL
```

> 0x0A24DA3A41B718F5 0x00E20F2D

void 0x0A24DA3A41B718F5(char* p0)

```
BOOL IsContextActive(char *ctx)
	{
		BEGIN_TEXT_COMMAND_IS_THIS_HELP_MESSAGE_BEING_DISPLAYED(ctx);
		return END_TEXT_COMMAND_IS_THIS_HELP_MESSAGE_BEING_DISPLAYED(0);
	}
```

> 0x10BDDBFC529428DD 0xF63A13EC

BOOL 0x10BDDBFC529428DD(int p0)



> BEGIN_TEXT_COMMAND_SET_BLIP_NAME - 0xF9113A30DE5C6670 0xF4C211F6

void BEGIN_TEXT_COMMAND_SET_BLIP_NAME(char* gxtentry)

```
example:

UI::BEGIN_TEXT_COMMAND_SET_BLIP_NAME('STRING');
UI::_ADD_TEXT_COMPONENT_STRING('Name');
UI::END_TEXT_COMMAND_SET_BLIP_NAME(blip);
```

> END_TEXT_COMMAND_SET_BLIP_NAME - 0xBC38B49BCB83BC9B 0xE8E59820

void END_TEXT_COMMAND_SET_BLIP_NAME(Blip blip)



> 0x23D69E0465570028 0x0E103475

void 0x23D69E0465570028(char* p0)

```
nothin doin. 

void message()
	{
		_BEGIN_TEXT_COMMAND_OBJECTIVE('AHT_RTIT');
		_END_TEXT_COMMAND_OBJECTIVE(0);
	}
```

> 0xCFDBDF5AE59BA0F4 0x2944A6C5

void 0xCFDBDF5AE59BA0F4(BOOL p0)



> 0xE124FA80A759019C 0x550665AE

void 0xE124FA80A759019C(char* p0)

```
nothin doin.

void message(char *text)
	{
		_BEGIN_TEXT_COMMAND_CONTEXT('STRING');
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		_END_TEXT_COMMAND_CONTEXT();
	}
```

> 0xFCC75460ABA29378 0x67785AF2

void 0xFCC75460ABA29378()



> 0x8F9EE5687F8EECCD 0xBF855650

void 0x8F9EE5687F8EECCD(char* p0)

```
	void message(char *text)
	{
		_BEGIN_TEXT_COMMAND_TIMER('STRING');
		ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text);
		_END_TEXT_COMMAND_TIMER(0);
	}
```

> 0xA86911979638106F 0x6E7FDA1C

void 0xA86911979638106F(BOOL p0)



> ADD_TEXT_COMPONENT_INTEGER - 0x03B504CF259931BC 0xFE272A57

void ADD_TEXT_COMPONENT_INTEGER(int value)



> ADD_TEXT_COMPONENT_FLOAT - 0xE7DCB5B874BCD96E 0x24D78013

void ADD_TEXT_COMPONENT_FLOAT(float value, int decimalPlaces)



> _ADD_TEXT_COMPONENT_ITEM_STRING - 0xC63CD5D2920ACBE7 0xDCE05406

void _ADD_TEXT_COMPONENT_ITEM_STRING(char* labelName)



> _ADD_TEXT_COMPONENT_SUBSTRING_LOCALIZED - 0x17299B63C7683A2B 0x150E03B6

void _ADD_TEXT_COMPONENT_SUBSTRING_LOCALIZED(Hash gxtEntryHash)

```
Takes a Hash of an input (example : INPUT_FRONTEND_RIGHT) and displays it's name it when you display your notification above the map.

^^ I don't know how somebody figured it prints the name of the input, when this native is clearly used for displaying Street Names in the scripts. Can you give an example if it actually does print out the INPUTS?


MulleDK19: It does neither. It adds the localized text of the specified GXT entry name. Eg. if the argument is GET_HASH_KEY('ES_HELP'), adds 'Continue'. I've renamed it to _ADD_TEXT_COMPONENT_SUBSTRING_LOCALIZED to reflect this.

Zorg93: correct name found, just uses a text labels hash key
```

> ADD_TEXT_COMPONENT_SUBSTRING_BLIP_NAME - 0x80EAD8E2E1D5D52E 0x5DE98F0A

void ADD_TEXT_COMPONENT_SUBSTRING_BLIP_NAME(Blip blip)



> ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME - 0x6C188BE134E074AA 0x27A244D8

void ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(char* text)

```
� Description :

 Processes a string and removes the player name(max len 99)
 You can use this function to create notifications/subtitles
--------------------------------------------------------------------
� Usage(Colors) :

 ~r~ = red
 ~y~ = yellow
 ~g~ = green
 ~b~ = light blue
 ~w~ = white
 ~p~ = purple
 ~n~ = new line
--------------------------------------------------------------------
� Example (C++):

void ShowNotification(char *text)  
{ 
        UI::_SET_NOTIFICATION_TEXT_ENTRY('STRING'); 
        UI::ADD_TEXT_COMPONENT_SUBSTRING_PLAYER_NAME(text); 
        UI::_DRAW_NOTIFICATION(FALSE, FALSE); // if first param = 1, the message flashes 1 or 2 times
}

� Colors example : 

string red = '~r~Red test';
string white_and_yellow = '~w~White and ~y~yellow';
string text_with_double_line = 'First line.~n~Second line';

This native (along with 0x5F68520888E69014 and 0x94CF4AC034C9C986) do not actually filter anything. They simply add the provided text (as of 944)
```

> ADD_TEXT_COMPONENT_SUBSTRING_TIME - 0x1115F16B8AB9E8BF 0x135B3CD0

void ADD_TEXT_COMPONENT_SUBSTRING_TIME(int timestamp, int flags)

```
Adds a timer (e.g. '00:00:00:000'). The appearance of the timer depends on the flags, which needs more research.
```

> _ADD_TEXT_COMPONENT_SUBSTRING_CASH - 0x0E4C749FF9DE9CC4 0x12929BDF

void _ADD_TEXT_COMPONENT_SUBSTRING_CASH(int cashAmount, BOOL p1)



> 0x761B77454205A61D 0x65E1D404

void 0x761B77454205A61D(char* p0, int p1)

```
p1 was always -1.
used for phone applications; scaleform
```

> ADD_TEXT_COMPONENT_SUBSTRING_WEBSITE - 0x94CF4AC034C9C986 0xC736999E

void ADD_TEXT_COMPONENT_SUBSTRING_WEBSITE(char* website)

```
This native (along with 0x5F68520888E69014 and 0x6C188BE134E074AA) do not actually filter anything. They simply add the provided text (as of 944)
```

> 0x5F68520888E69014 0x0829A799

void 0x5F68520888E69014(char* p0)

```
This native (along with 0x6C188BE134E074AA and 0x94CF4AC034C9C986) do not actually filter anything. They simply add the provided text (as of 944)

did you even check the disassembly?
```

> 0x39BBF623FC803EAC 0x6F1A1901

void 0x39BBF623FC803EAC(int p0)

```
sets font color for the next notification
```

> _GET_TEXT_SUBSTRING - 0x169BD9382084C8C0 0x34A396EE

char* _GET_TEXT_SUBSTRING(char* text, int position, int length)

```
Returns a substring of a specified length starting at a specified position.

Example:
// Get 'STRING' text from 'MY_STRING'
subStr = UI::_GET_TEXT_SUBSTRING('MY_STRING', 3, 6);
```

> _GET_TEXT_SUBSTRING_SAFE - 0xB2798643312205C5 0x0183A66C

char* _GET_TEXT_SUBSTRING_SAFE(char* text, int position, int length, int maxLength)

```
Returns a substring of a specified length starting at a specified position. The result is guaranteed not to exceed the specified max length.

NOTE: The 'maxLength' parameter might actually be the size of the buffer that is returned. More research is needed. -CL69

Example:
// Condensed example of how Rockstar uses this function
strLen = UI::GET_LENGTH_OF_LITERAL_STRING(GAMEPLAY::GET_ONSCREEN_KEYBOARD_RESULT());
subStr = UI::_GET_TEXT_SUBSTRING_SAFE(GAMEPLAY::GET_ONSCREEN_KEYBOARD_RESULT(), 0, strLen, 63);

--

'fm_race_creator.ysc', line 85115:
// parameters modified for clarity
BOOL sub_8e5aa(char *text, int length) {
    for (i = 0; i &lt;= (length - 2); i += 1) {
        if (!GAMEPLAY::ARE_STRINGS_EQUAL(UI::_GET_TEXT_SUBSTRING_SAFE(text, i, i + 1, 1), ' ')) {
            return FALSE;
        }
    }
    return TRUE;
}
```

> _GET_TEXT_SUBSTRING_SLICE - 0xCE94AEBA5D82908A 0xFA6373BB

char* _GET_TEXT_SUBSTRING_SLICE(char* text, int startPosition, int endPosition)

```
Returns a substring that is between two specified positions. The length of the string will be calculated using (endPosition - startPosition).

Example:
// Get 'STRING' text from 'MY_STRING'
subStr = UI::_GET_TEXT_SUBSTRING_SLICE('MY_STRING', 3, 9);
// Overflows are possibly replaced with underscores (needs verification)
subStr = UI::_GET_TEXT_SUBSTRING_SLICE('MY_STRING', 3, 10); // 'STRING_'?
```

> _GET_LABEL_TEXT - 0x7B5280EBA9840C72 0x95C4B5AD

char* _GET_LABEL_TEXT(char* labelName)

```
Gets a string literal from a label name.
```

> CLEAR_PRINTS - 0xCC33FA791322B9D9 0x216CB1C5

void CLEAR_PRINTS()



> CLEAR_BRIEF - 0x9D292F73ADBD9313 0x9F75A929

void CLEAR_BRIEF()



> CLEAR_ALL_HELP_MESSAGES - 0x6178F68A87A4D3A0 0x9E5D9198

void CLEAR_ALL_HELP_MESSAGES()



> CLEAR_THIS_PRINT - 0xCF708001E1E536DD 0x06878327

void CLEAR_THIS_PRINT(char* p0)

```
p0: found arguments in the b617d scripts: pastebin.com/X5akCN7z
```

> CLEAR_SMALL_PRINTS - 0x2CEA2839313C09AC 0xA869A238

void CLEAR_SMALL_PRINTS()



> DOES_TEXT_BLOCK_EXIST - 0x1C7302E725259789 0x96F74838

BOOL DOES_TEXT_BLOCK_EXIST(char* gxt)



> REQUEST_ADDITIONAL_TEXT - 0x71A78003C8E71424 0x9FA9175B

void REQUEST_ADDITIONAL_TEXT(char* gxt, int slot)

```
Request a gxt into the passed slot.
```

> _REQUEST_ADDITIONAL_TEXT_2 - 0x6009F9F1AE90D8A6 0xF4D27EBE

void _REQUEST_ADDITIONAL_TEXT_2(char* gxt, int slot)



> HAS_ADDITIONAL_TEXT_LOADED - 0x02245FE4BED318B8 0xB0E56045

BOOL HAS_ADDITIONAL_TEXT_LOADED(int slot)



> CLEAR_ADDITIONAL_TEXT - 0x2A179DF17CCF04CD 0x518141E0

void CLEAR_ADDITIONAL_TEXT(int p0, BOOL p1)



> IS_STREAMING_ADDITIONAL_TEXT - 0x8B6817B71B85EBF0 0xF079E4EB

BOOL IS_STREAMING_ADDITIONAL_TEXT(int p0)



> HAS_THIS_ADDITIONAL_TEXT_LOADED - 0xADBF060E2B30C5BC 0x80A52040

BOOL HAS_THIS_ADDITIONAL_TEXT_LOADED(char* gxt, int slot)

```
Checks if the specified gxt has loaded into the passed slot.
```

> IS_MESSAGE_BEING_DISPLAYED - 0x7984C03AA5CC2F41 0x6A77FE8D

BOOL IS_MESSAGE_BEING_DISPLAYED()



> DOES_TEXT_LABEL_EXIST - 0xAC09CA973C564252 0x6ECAE560

BOOL DOES_TEXT_LABEL_EXIST(char* gxt)

```
Checks if the passed gxt name exists in the game files.
```

> GET_LENGTH_OF_STRING_WITH_THIS_TEXT_LABEL - 0x801BD273D3A23F74 0xA4CA7BE5

int GET_LENGTH_OF_STRING_WITH_THIS_TEXT_LABEL(char* gxt)

```
Returns the string length of the string from the gxt string .
```

> GET_LENGTH_OF_LITERAL_STRING - 0xF030907CCBB8A9FD 0x99379D55

int GET_LENGTH_OF_LITERAL_STRING(char* string)

```
Returns the length of the string passed (much like strlen).
```

> 0x43E4111189E54F0E 0x7DBC0764

int 0x43E4111189E54F0E(char* p0)

```
gets the length of a null terminated string, without checking unicode encodings
```

> GET_STREET_NAME_FROM_HASH_KEY - 0xD0EF8A959B8A4CB9 0x1E8E310C

char* GET_STREET_NAME_FROM_HASH_KEY(Hash hash)

```
This functions converts the hash of a street name into a readable string.

For how to get the hashes, see PATHFIND::GET_STREET_NAME_AT_COORD.
```

> IS_HUD_PREFERENCE_SWITCHED_ON - 0x1930DFA731813EC4 0xC3BC1B4F

BOOL IS_HUD_PREFERENCE_SWITCHED_ON()



> IS_RADAR_PREFERENCE_SWITCHED_ON - 0x9EB6522EA68F22FE 0x14AEAA28

BOOL IS_RADAR_PREFERENCE_SWITCHED_ON()



> IS_SUBTITLE_PREFERENCE_SWITCHED_ON - 0xAD6DACA4BA53E0A4 0x63BA19F5

BOOL IS_SUBTITLE_PREFERENCE_SWITCHED_ON()



> DISPLAY_HUD - 0xA6294919E56FF02A 0xD10E4E31

void DISPLAY_HUD(BOOL toggle)

```
If Hud should be displayed
```

> 0x7669F9E39DC17063 0xC380AC85

void 0x7669F9E39DC17063()



> 0x402F9ED62087E898 0xC47AB1B0

void 0x402F9ED62087E898()



> DISPLAY_RADAR - 0xA0EBB943C300E693 0x52816BD4

Any DISPLAY_RADAR(BOOL Toggle)

```
If Minimap / Radar should be displayed.
```

> IS_HUD_HIDDEN - 0xA86478C6958735C5 0x40BADA1D

BOOL IS_HUD_HIDDEN()



> IS_RADAR_HIDDEN - 0x157F93B036700462 0x1AB3B954

BOOL IS_RADAR_HIDDEN()



> _IS_RADAR_ENABLED - 0xAF754F20EB5CD51A 

BOOL _IS_RADAR_ENABLED()



> SET_BLIP_ROUTE - 0x4F7D8A9BFB0B43E9 0x3E160C90

void SET_BLIP_ROUTE(Blip blip, BOOL enabled)

```
Enable / disable showing route for the Blip-object.
```

> SET_BLIP_ROUTE_COLOUR - 0x837155CD2F63DA09 0xDDE7C65C

void SET_BLIP_ROUTE_COLOUR(Blip blip, int colour)



> ADD_NEXT_MESSAGE_TO_PREVIOUS_BRIEFS - 0x60296AF4BA14ABC5 0xB58B25BD

void ADD_NEXT_MESSAGE_TO_PREVIOUS_BRIEFS(BOOL p0)

```
hash collision?
```

> 0x57D760D55F54E071 0x9854485F

void 0x57D760D55F54E071(BOOL p0)



> RESPONDING_AS_TEMP - 0xBD12C5EEE184C337 0xDCA3F423

void RESPONDING_AS_TEMP(float p0)

```
Please change back to _0xBD12C5EEE184C33 (hash collision)
actual native starts with SET_RADAR_ZOOM_...
```

> SET_RADAR_ZOOM - 0x096EF57A0C999BBA 0x2A50D1A6

void SET_RADAR_ZOOM(int zoomLevel)

```
zoomLevel ranges from 0 to 200 
```

> 0xF98E4B3E56AFC7B1 0x25EC28C0

void 0xF98E4B3E56AFC7B1(Any p0, float p1)



> _SET_RADAR_ZOOM_LEVEL_THIS_FRAME - 0xCB7CC0D58405AD41 0x09CF1CE5

void _SET_RADAR_ZOOM_LEVEL_THIS_FRAME(float zoomLevel)



> 0xD2049635DEB9C375 0xE8D3A910

void 0xD2049635DEB9C375()



> GET_HUD_COLOUR - 0x7C9C91AB74A0360F 0x63F66A0B

void GET_HUD_COLOUR(int hudIndex, int* r, int* g, int* b, int* a)

```
HUD colors and their values: pastebin.com/d9aHPbXN
```

> 0xD68A5FF8A3A89874 0x0E41E45C

void 0xD68A5FF8A3A89874(int r, int g, int b, int a)



> 0x16A304E6CB2BFAB9 0x6BE3ACA8

void 0x16A304E6CB2BFAB9(int r, int g, int b, int a)



> 0x1CCC708F0F850613 0x3B216749

void 0x1CCC708F0F850613(Any p0, Any p1)

```
HUD colors and their values: pastebin.com/d9aHPbXN
--------------------------------------------------
makes hudColorIndex2 color into hudColorIndex color
```

> _SET_HUD_COLOUR - 0xF314CF4F0211894E 0xF6E7E92B

void _SET_HUD_COLOUR(int hudIndex, int r, int g, int b, int a)

```
HUD colors and their values: pastebin.com/d9aHPbXN
```

> FLASH_ABILITY_BAR - 0x02CFBA0C9E9275CE 0x3648960D

void FLASH_ABILITY_BAR(Any p0)

```
If set to true ability bar will flash
```

> SET_ABILITY_BAR_VALUE - 0x9969599CCFF5D85E 0x24E53FD8

void SET_ABILITY_BAR_VALUE(float p0, float p1)



> FLASH_WANTED_DISPLAY - 0xA18AFB39081B6A1F 0x629F866B

Any FLASH_WANTED_DISPLAY(BOOL p0)



> 0xBA8D65C1C65702E5 

void 0xBA8D65C1C65702E5(BOOL p0)



> _GET_TEXT_SCALE_HEIGHT - 0xDB88A37483346780 0x3330175B

float _GET_TEXT_SCALE_HEIGHT(float size, int font)



> SET_TEXT_SCALE - 0x07C837F9A01C34C9 0xB6E15B23

void SET_TEXT_SCALE(float p0, float size)

```
p0 is unknown, I quick disassembly will tell us what it does 

size - range from 0 to 3 or 4 I believe.
```

> SET_TEXT_COLOUR - 0xBE6B23FFA53FB442 0xE54DD2C8

void SET_TEXT_COLOUR(int red, int green, int blue, int alpha)

```
colors you input not same as you think?
A: for some reason its R B G A
```

> SET_TEXT_CENTRE - 0xC02F4DBFB51D988B 0xE26D39A1

void SET_TEXT_CENTRE(BOOL align)



> SET_TEXT_RIGHT_JUSTIFY - 0x6B3C4650BC8BEE47 0x45B60520

void SET_TEXT_RIGHT_JUSTIFY(BOOL toggle)



> SET_TEXT_JUSTIFICATION - 0x4E096588B13FFECA 0x68CDFA60

void SET_TEXT_JUSTIFICATION(int justifyType)

```
Types -
0: Center-Justify
1: Left-Justify
2: Right-Justify

Right-Justify requires SET_TEXT_WRAP, otherwise it will draw to the far right of the screen
```

> SET_TEXT_WRAP - 0x63145D9C883A1A70 0x6F60AB54

void SET_TEXT_WRAP(float start, float end)

```
It sets the text in a specified box and wraps the text if it exceeds the boundries. Both values are for X axis. Useful when positioning text set to center or aligned to the right.

start - left boundry on screen position (0.0 - 1.0)
end - right boundry on screen position (0.0 - 1.0)
```

> SET_TEXT_LEADING - 0xA50ABC31E3CDFAFF 0x98CE21D4

void SET_TEXT_LEADING(BOOL p0)

```
from script am_mp_yacht.c int?
ui::set_text_leading(2);
```

> SET_TEXT_PROPORTIONAL - 0x038C1F517D7FDCF8 0xF49D8A08

void SET_TEXT_PROPORTIONAL(BOOL p0)



> SET_TEXT_FONT - 0x66E0276CC5F6B9DA 0x80BC530D

void SET_TEXT_FONT(int fontType)

```
fonts that mess up your text where made for number values/misc stuff
```

> SET_TEXT_DROP_SHADOW - 0x1CA3E9EAC9D93E5E 0xE2A11511

void SET_TEXT_DROP_SHADOW()



> SET_TEXT_DROPSHADOW - 0x465C84BC39F1C351 0xE6587517

void SET_TEXT_DROPSHADOW(int distance, int r, int g, int b, int a)

```
distance - shadow distance in pixels, both horizontal and vertical
r, g, b, a - color
```

> SET_TEXT_OUTLINE - 0x2513DFB0FB8400FE 0xC753412F

void SET_TEXT_OUTLINE()



> SET_TEXT_EDGE - 0x441603240D202FA6 0x3F1A5DAB

void SET_TEXT_EDGE(int p0, int r, int g, int b, int a)



> SET_TEXT_RENDER_ID - 0x5F15302936E07111 0xC5C3B7F3

void SET_TEXT_RENDER_ID(int renderId)



> GET_DEFAULT_SCRIPT_RENDERTARGET_RENDER_ID - 0x52F0982D7FD156B6 0x8188935F

int GET_DEFAULT_SCRIPT_RENDERTARGET_RENDER_ID()

```
MulleDK19: This function is hard-coded to always return 1.
```

> REGISTER_NAMED_RENDERTARGET - 0x57D9C12635E25CE3 0xFAE5D6F0

BOOL REGISTER_NAMED_RENDERTARGET(char* p0, BOOL p1)



> IS_NAMED_RENDERTARGET_REGISTERED - 0x78DCDC15C9F116B4 0x284057F5

BOOL IS_NAMED_RENDERTARGET_REGISTERED(char* p0)



> RELEASE_NAMED_RENDERTARGET - 0xE9F6FFE837354DD4 0xD3F6C892

BOOL RELEASE_NAMED_RENDERTARGET(Any* p0)



> LINK_NAMED_RENDERTARGET - 0xF6C09E276AEB3F2D 0x6844C4B9

void LINK_NAMED_RENDERTARGET(Hash hash)



> GET_NAMED_RENDERTARGET_RENDER_ID - 0x1A6478B61C6BDC3B 0xF9D7A401

Any GET_NAMED_RENDERTARGET_RENDER_ID(char* p0)



> IS_NAMED_RENDERTARGET_LINKED - 0x113750538FA31298 0x8B52601F

BOOL IS_NAMED_RENDERTARGET_LINKED(Hash hash)



> CLEAR_HELP - 0x8DFCED7A656F8802 0xE6D85741

void CLEAR_HELP(BOOL toggle)



> IS_HELP_MESSAGE_ON_SCREEN - 0xDAD37F45428801AE 0x4B3C9CA9

BOOL IS_HELP_MESSAGE_ON_SCREEN()



> 0x214CD562A939246A 0x812CBE0E

BOOL 0x214CD562A939246A()

```
example

if (UI::IS_HELP_MESSAGE_BEING_DISPLAYED()&amp;&amp;(!UI::_214CD562A939246A())) {
        return 0;
}
```

> IS_HELP_MESSAGE_BEING_DISPLAYED - 0x4D79439A6B55AC67 0xA65F262A

BOOL IS_HELP_MESSAGE_BEING_DISPLAYED()



> IS_HELP_MESSAGE_FADING_OUT - 0x327EDEEEAC55C369 0x3E50AE92

BOOL IS_HELP_MESSAGE_FADING_OUT()



> 0x4A9923385BDB9DAD 0x87871CE0

BOOL 0x4A9923385BDB9DAD()

```
example:

if (!((v_7)==UI::_4A9923385BDB9DAD())) {
        UI::SET_BLIP_SPRITE((v_6), (v_7));
    }


MulleDK19: This function is hard-coded to always return 1.
```

> _GET_BLIP_INFO_ID_ITERATOR - 0x186E5D252FA50E7D 0xB9827942

int _GET_BLIP_INFO_ID_ITERATOR()



> GET_NUMBER_OF_ACTIVE_BLIPS - 0x9A3FF3DE163034E8 0x144020FA

int GET_NUMBER_OF_ACTIVE_BLIPS()



> GET_NEXT_BLIP_INFO_ID - 0x14F96AA50D6FBEA7 0x9356E92F

Blip GET_NEXT_BLIP_INFO_ID(Blip blip)



> GET_FIRST_BLIP_INFO_ID - 0x1BEDE233E6CD2A1F 0x64C0273D

Blip GET_FIRST_BLIP_INFO_ID(Blip blip)



> GET_BLIP_INFO_ID_COORD - 0xFA7C7F0AADF25D09 0xB7374A66

Vector3 GET_BLIP_INFO_ID_COORD(int p0)



> GET_BLIP_INFO_ID_DISPLAY - 0x1E314167F701DC3B 0xD0FC19F4

int GET_BLIP_INFO_ID_DISPLAY(Blip blip)



> GET_BLIP_INFO_ID_TYPE - 0xBE9B0959FFD0779B 0x501D7B4E

int GET_BLIP_INFO_ID_TYPE(Blip blip)

```
Returns a value based on what the blip is attached to
1 - Vehicle
2 - Ped
3 - Object
4 - Coord
5 - unk
6 - Pickup
7 - Radius
```

> GET_BLIP_INFO_ID_ENTITY_INDEX - 0x4BA4E2553AFEDC2C 0xA068C40B

Entity GET_BLIP_INFO_ID_ENTITY_INDEX(Blip blip)

```
 
```

> GET_BLIP_INFO_ID_PICKUP_INDEX - 0x9B6786E4C03DD382 0x86913D37

Pickup GET_BLIP_INFO_ID_PICKUP_INDEX(Blip blip)

```
MulleDK19: This function is hard-coded to always return 0.
```

> GET_BLIP_FROM_ENTITY - 0xBC8DBDCA2436F7E8 0x005A2A47

Blip GET_BLIP_FROM_ENTITY(Entity entity)

```
Returns the Blip handle of given Entity.
```

> ADD_BLIP_FOR_RADIUS - 0x46818D79B1F7499A 0x4626756C

Blip ADD_BLIP_FOR_RADIUS(float posX, float posY, float posZ, float radius)



> ADD_BLIP_FOR_ENTITY - 0x5CDE92C702A8FCE7 0x30822554

Blip ADD_BLIP_FOR_ENTITY(Entity entity)

```
Returns red ( default ) blip attached to entity.

Example:
Blip blip; //Put this outside your case or option
blip = UI::ADD_BLIP_FOR_ENTITY(YourPedOrBodyguardName);
UI::SET_BLIP_AS_FRIENDLY(blip, true);
```

> ADD_BLIP_FOR_PICKUP - 0xBE339365C863BD36 0x16693C3A

Blip ADD_BLIP_FOR_PICKUP(Pickup pickup)



> ADD_BLIP_FOR_COORD - 0x5A039BB0BCA604B6 0xC6F43D0E

Blip ADD_BLIP_FOR_COORD(float x, float y, float z)

```
Creates an orange ( default ) Blip-object. Returns a Blip-object which can then be modified.
```

> 0x72DD432F3CDFC0EE 0xBF25E7B2

void 0x72DD432F3CDFC0EE(float posX, float posY, float posZ, float radius, int p4)



> 0x60734CC207C9833C 0xE7E1E32B

void 0x60734CC207C9833C(BOOL p0)



> SET_BLIP_COORDS - 0xAE2AF67E9D9AF65D 0x680A34D4

void SET_BLIP_COORDS(Blip blip, float posX, float posY, float posZ)



> GET_BLIP_COORDS - 0x586AFE3FF72D996E 0xEF6FF47B

Vector3 GET_BLIP_COORDS(Blip blip)



> SET_BLIP_SPRITE - 0xDF735600A4696DAF 0x8DBBB0B9

void SET_BLIP_SPRITE(Blip blip, int spriteId)

```
Takes a blip object and adds a sprite to it on the map.

You may have your own list, but since dev-c didn't show it I was bored and started looking through scripts and functions to get a presumable almost positive list of a majority of blip IDs
h t t p://pastebin.com/Bpj9Sfft

Blips Images + IDs:
gtaxscripting.blogspot.com/2016/05/gta-v-blips-id-and-image.html
```

> GET_BLIP_SPRITE - 0x1FC877464A04FC4F 0x72FF2E73

int GET_BLIP_SPRITE(Blip blip)

```
Blips Images + IDs:
gtaxscripting.blogspot.com/2016/05/gta-v-blips-id-and-image.html
```

> SET_BLIP_NAME_FROM_TEXT_FILE - 0xEAA0FFE120D92784 0xAC8A5461

void SET_BLIP_NAME_FROM_TEXT_FILE(Blip blip, char* gxtEntry)



> SET_BLIP_NAME_TO_PLAYER_NAME - 0x127DE7B20C60A6A3 0x03A0B8F9

void SET_BLIP_NAME_TO_PLAYER_NAME(Blip blip, Player player)



> SET_BLIP_ALPHA - 0x45FF974EEE1C8734 0xA791FCCD

void SET_BLIP_ALPHA(Blip blip, int alpha)

```
Sets alpha-channel for blip color.

Example:

Blip blip = UI::ADD_BLIP_FOR_ENTITY(entity);
UI::SET_BLIP_COLOUR(blip , 3);
UI::SET_BLIP_ALPHA(blip , 64);

```

> GET_BLIP_ALPHA - 0x970F608F0EE6C885 0x297AF6C8

int GET_BLIP_ALPHA(Blip blip)



> SET_BLIP_FADE - 0x2AEE8F8390D2298C 0xA5999031

void SET_BLIP_FADE(Blip blip, int opacity, int duration)



> SET_BLIP_ROTATION - 0xF87683CDF73C3F6E 0x6B8F44FE

void SET_BLIP_ROTATION(Blip blip, int rotation)

```
After some testing, looks like you need to use UI:CEIL() on the rotation (vehicle/ped heading) before using it there.
```

> SET_BLIP_FLASH_TIMER - 0xD3CD6FD297AE87CC 0x8D5DF611

void SET_BLIP_FLASH_TIMER(Blip blip, int duration)

```
Adds up after viewing multiple R* scripts. I believe that the duration is in miliseconds.

- Shawn (/u/shawn_of_the_reddit) (GTAF: thunder_)
```

> SET_BLIP_FLASH_INTERVAL - 0xAA51DB313C010A7E 0xEAF67377

void SET_BLIP_FLASH_INTERVAL(Blip blip, Any p1)



> SET_BLIP_COLOUR - 0x03D7FB09E75D6B7E 0xBB3C5A41

void SET_BLIP_COLOUR(Blip blip, int color)

```
Color:

0: white
1: red
2: green
3: blue
17: orange
19: purple
20: grey
21: brown
23: pink
25: dark green
27: dark purple
29: dark blue
Default (Function not used): yellow

Those are not the only ones. i.e: 17 is Trevor's orange.
```

> SET_BLIP_SECONDARY_COLOUR - 0x14892474891E09EB 0xC6384D32

void SET_BLIP_SECONDARY_COLOUR(Blip blip, float r, float g, float b)



> GET_BLIP_COLOUR - 0xDF729E8D20CF7327 0xDD6A1E54

int GET_BLIP_COLOUR(Blip blip)



> GET_BLIP_HUD_COLOUR - 0x729B5F1EFBC0AAEE 0xE88B4BC2

int GET_BLIP_HUD_COLOUR(Blip blip)



> IS_BLIP_SHORT_RANGE - 0xDA5F8727EB75B926 0x1226765A

BOOL IS_BLIP_SHORT_RANGE(Blip blip)



> IS_BLIP_ON_MINIMAP - 0xE41CA53051197A27 0x258CBA3A

BOOL IS_BLIP_ON_MINIMAP(Blip blip)



> 0xDD2238F57B977751 0x3E47F357

BOOL 0xDD2238F57B977751(Any p0)



> 0x54318C915D27E4CE 0x43996428

void 0x54318C915D27E4CE(Any p0, BOOL p1)



> SET_BLIP_HIGH_DETAIL - 0xE2590BC29220CEBB 0xD5842BFF

void SET_BLIP_HIGH_DETAIL(Blip blip, BOOL toggle)



> SET_BLIP_AS_MISSION_CREATOR_BLIP - 0x24AC0137444F9FD5 0x802FB686

void SET_BLIP_AS_MISSION_CREATOR_BLIP(Blip blip, BOOL toggle)



> IS_MISSION_CREATOR_BLIP - 0x26F49BF3381D933D 0x24ACC4E9

BOOL IS_MISSION_CREATOR_BLIP(Blip blip)



> DISABLE_BLIP_NAME_FOR_VAR - 0x5C90988E7C8E1AF4 0xFFD7476C

Blip DISABLE_BLIP_NAME_FOR_VAR()

```
Hash collision!!! 

Returns a blip handle.
```

> 0x4167EFE0527D706E 0xC5EB849A

BOOL 0x4167EFE0527D706E()



> 0xF1A6C18B35BCADE6 0xA2CAAB4F

void 0xF1A6C18B35BCADE6(BOOL p0)



> SET_BLIP_FLASHES - 0xB14552383D39CE3E 0xC0047F15

void SET_BLIP_FLASHES(Blip blip, BOOL toggle)



> SET_BLIP_FLASHES_ALTERNATE - 0x2E8D9498C56DD0D1 0x1A81202B

void SET_BLIP_FLASHES_ALTERNATE(Blip blip, BOOL toggle)



> IS_BLIP_FLASHING - 0xA5E41FD83AD6CEF0 0x52E111D7

BOOL IS_BLIP_FLASHING(Blip blip)



> SET_BLIP_AS_SHORT_RANGE - 0xBE8BE4FE60E27B72 0x5C67725E

void SET_BLIP_AS_SHORT_RANGE(Blip blip, BOOL toggle)



> SET_BLIP_SCALE - 0xD38744167B2FA257 0x1E6EC434

void SET_BLIP_SCALE(Blip blip, float scale)



> SET_BLIP_PRIORITY - 0xAE9FC9EF6A9FAC79 0xCE87DA6F

void SET_BLIP_PRIORITY(Blip blip, int priority)



> SET_BLIP_DISPLAY - 0x9029B2F3DA924928 0x2B521F91

void SET_BLIP_DISPLAY(Blip blip, int p1)

```
displayId = 8 : shows on radar

displayId:
3 = Shows on Main map but not Radar (not selectable on map)

displayId = 2 (Shows on Main map + Radar + selectable)
```

> SET_BLIP_CATEGORY - 0x234CDD44D996FD9A 0xEF72F533

void SET_BLIP_CATEGORY(Blip blip, int index)

```
int index:

1 = No Text on blip or Distance
2 = Text on blip
3 = No text, just distance
4+ No Text on blip or distance
```

> REMOVE_BLIP - 0x86A652570E5F25DD 0xD8C3C1CD

void REMOVE_BLIP(Blip* blip)

```
In the C++ SDK, this seems not to work-- the blip isn't removed immediately. I use it for saving cars.

E.g.:

Ped pped = PLAYER::PLAYER_PED_ID();
Vehicle v = PED::GET_VEHICLE_PED_IS_USING(pped);
Blip b = UI::ADD_BLIP_FOR_ENTITY(v);

works fine.
But later attempting to delete it with:

Blip b = UI::GET_BLIP_FROM_ENTITY(v);
if (UI::DOES_BLIP_EXIST(b)) UI::REMOVE_BLIP(&amp;b);

doesn't work. And yes, doesn't work without the DOES_BLIP_EXIST check either. Also, if you attach multiple blips to the same thing (say, a vehicle), and that thing disappears, the blips randomly attach to other things (in my case, a vehicle).

Thus for me, UI::REMOVE_BLIP(&amp;b) only works if there's one blip, (in my case) the vehicle is marked as no longer needed, you drive away from it and it eventually despawns, AND there is only one blip attached to it. I never intentionally attach multiple blips but if the user saves the car, this adds a blip. Then if they delete it, it is supposed to remove the blip, but it doesn't. Then they can immediately save it again, causing another blip to re-appear.
-------------

Passing the address of the variable instead of the value works for me.
e.g.
int blip = UI::ADD_BLIP_FOR_ENTITY(ped);
UI::REMOVE_BLIP(&amp;blip);


Remove blip will currently crash your game, just artificially remove the blip by setting the sprite to a id that is 'invisible'.

--
It crashes my game.
```

> SET_BLIP_AS_FRIENDLY - 0x6F6F290102C02AB4 0xF290CFD8

void SET_BLIP_AS_FRIENDLY(Blip blip, BOOL toggle)

```
false for enemy
true for friendly
```

> PULSE_BLIP - 0x742D6FD43115AF73 0x44253855

void PULSE_BLIP(Blip blip)



> SHOW_NUMBER_ON_BLIP - 0xA3C0B359DCB848B6 0x7BFC66C6

void SHOW_NUMBER_ON_BLIP(Blip blip, int number)



> HIDE_NUMBER_ON_BLIP - 0x532CFF637EF80148 0x0B6D610D

void HIDE_NUMBER_ON_BLIP(Blip blip)



> 0x75A16C3DA34F1245 0x1D99F676

void 0x75A16C3DA34F1245(Any p0, BOOL p1)



> 0x74513EA3E505181E 0x3DCF0092

void 0x74513EA3E505181E(Blip blip, BOOL toggle)

```
Adds a green checkmark on top of a blip.
```

> _SET_BLIP_SHOW_HEADING_INDICATOR - 0x5FBCA48327B914DF 0xD1C3D71B

void _SET_BLIP_SHOW_HEADING_INDICATOR(Blip blip, BOOL toggle)

```
Adds the GTA: Online player heading indicator to a blip.
```

> 0xB81656BC81FE24D1 0x8DE82C15

void 0xB81656BC81FE24D1(Blip blip, BOOL toggle)

```
Highlights a blip by a cyan color circle.
 
Color can be changed with SET_BLIP_SECONDARY_COLOUR


```

> 0x23C3EB807312F01A 0x4C8F02B4

void 0x23C3EB807312F01A(Blip blip, BOOL toggle)

```
Highlights a blip by a half cyan circle.
```

> 0xDCFB5D4DB8BF367E 0xABBE1E45

void 0xDCFB5D4DB8BF367E(Any p0, BOOL p1)



> 0xC4278F70131BAA6D 0x6AA6A1CC

void 0xC4278F70131BAA6D(Any p0, BOOL p1)



> 0x2B6D467DAB714E8D 0xC575F0BC

void 0x2B6D467DAB714E8D(Blip blip, BOOL toggle)

```
Makes a blip go small when off the minimap.
```

> 0x25615540D894B814 0x40E25DB8

void 0x25615540D894B814(Any p0, BOOL p1)



> DOES_BLIP_EXIST - 0xA6DB27D19ECBB7DA 0xAE92DD96

BOOL DOES_BLIP_EXIST(Blip blip)



> SET_WAYPOINT_OFF - 0xA7E4E2D361C2627F 0xB3496E1B

void SET_WAYPOINT_OFF()

```
This native removes the current waypoint from the map.

Example:
C#:
Function.Call(Hash.SET_WAYPOINT_OFF);

C++:
UI::SET_WAYPOINT_OFF();
```

> 0xD8E694757BCEA8E9 0x62BABF2C

void 0xD8E694757BCEA8E9()



> REFRESH_WAYPOINT - 0x81FA173F170560D1 0xB395D753

void REFRESH_WAYPOINT()



> IS_WAYPOINT_ACTIVE - 0x1DD1F58F493F1DA5 0x5E4DF47B

BOOL IS_WAYPOINT_ACTIVE()



> SET_NEW_WAYPOINT - 0xFE43368D2AA4F2FC 0x8444E1F0

void SET_NEW_WAYPOINT(float x, float y)



> SET_BLIP_BRIGHT - 0xB203913733F27884 0x72BEE6DF

void SET_BLIP_BRIGHT(Blip blip, BOOL toggle)



> SET_BLIP_SHOW_CONE - 0x13127EC3665E8EE1 0xFF545AD8

void SET_BLIP_SHOW_CONE(Blip blip, BOOL toggle)



> 0xC594B315EDF2D4AF 0x41B0D022

void 0xC594B315EDF2D4AF(Ped ped)

```
Interesting fact: A hash collision for this is RESET_JETPACK_MODEL_SETTINGS
```

> SET_MINIMAP_COMPONENT - 0x75A9A10948D1DEA6 0x419DCDC4

Any SET_MINIMAP_COMPONENT(int p0, BOOL p1, int p2)

```
Please change to void.

p2 appears to be always -1.
```

> 0x60E892BA4F5BDCA4 

void 0x60E892BA4F5BDCA4()

```
Something with Social Club or online.
```

> GET_MAIN_PLAYER_BLIP_ID - 0xDCD4EC3F419D02FA 0xAB93F020

Blip GET_MAIN_PLAYER_BLIP_ID()



> 0x41350B4FC28E3941 

void 0x41350B4FC28E3941(BOOL p0)



> HIDE_LOADING_ON_FADE_THIS_FRAME - 0x4B0311D3CDC4648F 0x35087963

void HIDE_LOADING_ON_FADE_THIS_FRAME()



> SET_RADAR_AS_INTERIOR_THIS_FRAME - 0x59E727A1C9D3E31A 0x6F2626E1

void SET_RADAR_AS_INTERIOR_THIS_FRAME(Hash interior, float x, float y, int z, int p4)



> SET_RADAR_AS_EXTERIOR_THIS_FRAME - 0xE81B7D2A3DAB2D81 0x39ABB10E

void SET_RADAR_AS_EXTERIOR_THIS_FRAME()



> _SET_PLAYER_BLIP_POSITION_THIS_FRAME - 0x77E2DD177910E1CF 0x54E75C7D

void _SET_PLAYER_BLIP_POSITION_THIS_FRAME(float x, float y)

```
Sets the position of the arrow icon representing the player on both the minimap and world map.

Too bad this wouldn't work over the network (obviously not). Could spoof where we would be.
```

> 0x9049FE339D5F6F6F 0x199DED14

Any 0x9049FE339D5F6F6F()



> _DISABLE_RADAR_THIS_FRAME - 0x5FBAE526203990C9 0x1A4318F7

void _DISABLE_RADAR_THIS_FRAME()

```
confirmed working 
-sob
```

> 0x20FE7FDFEEAD38C0 0xCE36E3FE

void 0x20FE7FDFEEAD38C0()



> _CENTER_PLAYER_ON_RADAR_THIS_FRAME - 0x6D14BFDC33B34F55 0x334EFD46

void _CENTER_PLAYER_ON_RADAR_THIS_FRAME()

```
When calling this, the current frame will have the players 'arrow icon' be focused on the dead center of the radar. - mlgthatsme
```

> SET_WIDESCREEN_FORMAT - 0xC3B07BA00A83B0F1 0xF016E08F

void SET_WIDESCREEN_FORMAT(Any p0)



> DISPLAY_AREA_NAME - 0x276B6CE369C33678 0x489FDD41

void DISPLAY_AREA_NAME(BOOL toggle)



> DISPLAY_CASH - 0x96DEC8D5430208B7 0x0049DF83

void DISPLAY_CASH(BOOL toggle)

```
'DISPLAY_CASH(false);' makes the cash amount render on the screen when appropriate
'DISPLAY_CASH(true);' disables cash amount rendering
```

> 0x170F541E1CADD1DE 

void 0x170F541E1CADD1DE(BOOL p0)

```
Related to displaying cash on the HUD
Always called before UI::_SET_SINGLEPLAYER_HUD_CASH in decompiled scripts
```

> _SET_PLAYER_CASH_CHANGE - 0x0772DF77852C2E30 

void _SET_PLAYER_CASH_CHANGE(int cash, int bank)

```
Displays cash change notifications on HUD.
```

> DISPLAY_AMMO_THIS_FRAME - 0xA5E78BA2B1331C55 0x60693CEE

void DISPLAY_AMMO_THIS_FRAME(BOOL display)



> DISPLAY_SNIPER_SCOPE_THIS_FRAME - 0x73115226F4814E62 0xBC6C73CB

void DISPLAY_SNIPER_SCOPE_THIS_FRAME()

```
Displays the crosshair for this frame.
```

> HIDE_HUD_AND_RADAR_THIS_FRAME - 0x719FF505F097FD20 0xB75D4AD2

void HIDE_HUD_AND_RADAR_THIS_FRAME()

```
I think this works, but seems to prohibit switching to other weapons (or accessing the weapon wheel)
-sob
```

> 0xE67C6DFD386EA5E7 0x5476B9FD

void 0xE67C6DFD386EA5E7(BOOL p0)



> 0xC2D15BEF167E27BC 0xF4F3C796

void 0xC2D15BEF167E27BC()



> 0x95CF81BD06EE1887 0x7BFFE82F

void 0x95CF81BD06EE1887()



> SET_MULTIPLAYER_BANK_CASH - 0xDD21B55DF695CD0A 0x2C842D03

void SET_MULTIPLAYER_BANK_CASH()



> REMOVE_MULTIPLAYER_BANK_CASH - 0xC7C6789AA1CFEDD0 0x728B4EF4

void REMOVE_MULTIPLAYER_BANK_CASH()



> SET_MULTIPLAYER_HUD_CASH - 0xFD1D220394BCB824 0xA8DB435E

void SET_MULTIPLAYER_HUD_CASH(int p0, int p1)



> REMOVE_MULTIPLAYER_HUD_CASH - 0x968F270E39141ECA 0x07BF4A7D

void REMOVE_MULTIPLAYER_HUD_CASH()

```
Removes multiplayer cash hud per frame - Cameron
```

> HIDE_HELP_TEXT_THIS_FRAME - 0xD46923FC481CA285 0xF3807BED

void HIDE_HELP_TEXT_THIS_FRAME()



> DISPLAY_HELP_TEXT_THIS_FRAME - 0x960C9FF8F616E41C 0x18E3360A

void DISPLAY_HELP_TEXT_THIS_FRAME(char* message, BOOL p1)

```
The messages are localized strings.
Examples:
'No_bus_money'
'Enter_bus'
'Tour_help'
'LETTERS_HELP2'
'Dummy'

**The bool appears to always be false (if it even is a bool, as it's represented by a zero)**
--------
p1 doesn't seem to make a difference, regardless of the state it's in. 
```

> _SHOW_WEAPON_WHEEL - 0xEB354E5376BC81A7 0x1EFFB02A

void _SHOW_WEAPON_WHEEL(BOOL forcedShow)

```
Forces the weapon wheel to appear on screen.
```

> 0x0AFC4AF510774B47 0xB26FED2B

void 0x0AFC4AF510774B47()

```
jedijosh920: By calling this each frame, it stops the player from receiving a weapon via the weapon wheel.
```

> 0xA48931185F0536FE 0x22E9F555

Hash 0xA48931185F0536FE()



> 0x72C1056D678BB7D8 0x83B608A0

void 0x72C1056D678BB7D8(Any p0)

```
Appears to be a HIDE_* native.
```

> 0xA13E93403F26C812 

Any 0xA13E93403F26C812(Any p0)



> 0x14C9FDCC41F81F63 0xE70D1F43

void 0x14C9FDCC41F81F63(BOOL p0)



> SET_GPS_FLAGS - 0x5B440763A4C8D15B 0x60539BAB

void SET_GPS_FLAGS(int p0, float p1)

```
MulleDK19: Only the script that originally called SET_GPS_FLAGS can set them again. Another script cannot set the flags, until the first script that called it has called CLEAR_GPS_FLAGS.

Doesn't seem like the flags are actually read by the game at all.
```

> CLEAR_GPS_FLAGS - 0x21986729D6A3A830 0x056AFCE6

void CLEAR_GPS_FLAGS()

```
MulleDK19: Clears the GPS flags. Only the script that originally called SET_GPS_FLAGS can clear them.

Doesn't seem like the flags are actually read by the game at all.
```

> 0x1EAC5F91BCBC5073 0xFB9BABF5

void 0x1EAC5F91BCBC5073(BOOL p0)



> CLEAR_GPS_RACE_TRACK - 0x7AA5B4CE533C858B 0x40C59829

void CLEAR_GPS_RACE_TRACK()



> 0xDB34E8D56FC13B08 0x7F93799B

void 0xDB34E8D56FC13B08(Any p0, BOOL p1, BOOL p2)



> 0x311438A071DD9B1A 0xEEBDFE55

void 0x311438A071DD9B1A(Any p0, Any p1, Any p2)



> 0x900086F371220B6F 0xDA0AF00E

void 0x900086F371220B6F(BOOL p0, Any p1, Any p2)

```
SET_GPS_???
```

> 0xE6DE0561D9232A64 0xCF2E3E24

void 0xE6DE0561D9232A64()



> 0x3D3D15AF7BCAAF83 0xC3DCBEDB

void 0x3D3D15AF7BCAAF83(Any p0, BOOL p1, BOOL p2)



> 0xA905192A6781C41B 0xFE485135

void 0xA905192A6781C41B(float x, float y, float z)



> 0x3DDA37128DD1ACA8 0xE87CBE4C

void 0x3DDA37128DD1ACA8(BOOL p0)



> 0x67EEDEA1B9BAFD94 0x0D9969E4

void 0x67EEDEA1B9BAFD94()



> CLEAR_GPS_PLAYER_WAYPOINT - 0xFF4FB7C8CDFA3DA7 0x0B9C7FC2

void CLEAR_GPS_PLAYER_WAYPOINT()



> SET_GPS_FLASHES - 0x320D0E0D936A0E9B 0xE991F733

void SET_GPS_FLASHES(BOOL toggle)



> 0x7B21E0BB01E8224A 

void 0x7B21E0BB01E8224A(Any p0)



> FLASH_MINIMAP_DISPLAY - 0xF2DD778C22B15BDA 0xB8359952

void FLASH_MINIMAP_DISPLAY()

```
adds a short flash to the Radar/Minimap
Usage: UI.FLASH_MINIMAP_DISPLAY
```

> 0x6B1DE27EE78E6A19 0x79A6CAF6

void 0x6B1DE27EE78E6A19(Any p0)



> TOGGLE_STEALTH_RADAR - 0x6AFDFB93754950C7 0xC68D47C4

void TOGGLE_STEALTH_RADAR(BOOL toggle)



> KEY_HUD_COLOUR - 0x1A5CD7752DD28CD3 0xD5BFCADB

void KEY_HUD_COLOUR(BOOL p0, Any p1)

```
hash collision
```

> SET_MISSION_NAME - 0x5F28ECF5FC84772F 0x68DCAE10

void SET_MISSION_NAME(BOOL p0, char* name)



> 0xE45087D85F468BC2 0x8D9A1734

void 0xE45087D85F468BC2(BOOL p0, Any* p1)



> 0x817B86108EB94E51 0xD2161E77

void 0x817B86108EB94E51(BOOL p0, Any* p1, Any* p2, Any* p3, Any* p4, Any* p5, Any* p6, Any* p7, Any* p8)

```
UI::_817B86108EB94E51(1, &amp;g_189F36._f10CD1[0/*16*/], &amp;g_189F36._f10CD1[1/*16*/], &amp;g_189F36._f10CD1[2/*16*/], &amp;g_189F36._f10CD1[3/*16*/], &amp;g_189F36._f10CD1[4/*16*/], &amp;g_189F36._f10CD1[5/*16*/], &amp;g_189F36._f10CD1[6/*16*/], &amp;g_189F36._f10CD1[7/*16*/]);
```

> SET_MINIMAP_BLOCK_WAYPOINT - 0x58FADDED207897DC 0xA41C3B62

void SET_MINIMAP_BLOCK_WAYPOINT(BOOL toggle)



> _SET_MINIMAP_VISIBLE - 0x9133955F1A2DA957 0x02F5F1D1

void _SET_MINIMAP_VISIBLE(BOOL toggle)

```
Toggles the minimap-map and the map(in the mainmenu) visibility, no map will be drawn anymore
```

> _SET_MINIMAP_REVEALED - 0xF8DEE0A5600CBB93 0xD8D77733

void _SET_MINIMAP_REVEALED(BOOL toggle)

```
MulleDK19: If true, the entire map will be revealed.
```

> 0xE0130B41D3CF4574 0xA4098ACC

float 0xE0130B41D3CF4574()



> _IS_MINIMAP_AREA_REVEALED - 0x6E31B91145873922 0x65B705F6

BOOL _IS_MINIMAP_AREA_REVEALED(float x, float y, float radius)



> 0x62E849B7EB28E770 

void 0x62E849B7EB28E770(BOOL p0)



> 0x0923DBF87DFF735E 0xE010F081

void 0x0923DBF87DFF735E(float x, float y, float z)



> 0x71BDB63DBAF8DA59 0x5133A750

void 0x71BDB63DBAF8DA59(Any p0)



> 0x35EDD5B2E3FF01C0 0x20FD3E87

void 0x35EDD5B2E3FF01C0()



> LOCK_MINIMAP_ANGLE - 0x299FAEBB108AE05B 0xDEC733E4

void LOCK_MINIMAP_ANGLE(int angle)

```
Locks the minimap to the specified angle in integer degrees.

angle: The angle in whole degrees. If less than 0 or greater than 360, unlocks the angle.
```

> UNLOCK_MINIMAP_ANGLE - 0x8183455E16C42E3A 0x742043F9

void UNLOCK_MINIMAP_ANGLE()



> LOCK_MINIMAP_POSITION - 0x1279E861A329E73F 0xB9632A91

void LOCK_MINIMAP_POSITION(float x, float y)

```
Locks the minimap to the specified world position.
```

> UNLOCK_MINIMAP_POSITION - 0x3E93E06DB8EF1F30 0x5E8E6F54

void UNLOCK_MINIMAP_POSITION()



> _SET_MINIMAP_ATTITUDE_INDICATOR_LEVEL - 0xD201F3FF917A506D 0x0308EDF6

void _SET_MINIMAP_ATTITUDE_INDICATOR_LEVEL(float altitude, BOOL p1)

```
Argument must be 0.0f or above 38.0f, or it will be ignored.
```

> 0x3F5CC444DCAAA8F2 0x7FB6FB2A

void 0x3F5CC444DCAAA8F2(Any p0, Any p1, BOOL p2)



> 0x975D66A0BC17064C 0xF07D8CEF

void 0x975D66A0BC17064C(Any p0)



> 0x06A320535F5F0248 0x827F14DE

void 0x06A320535F5F0248(Any p0)



> _SET_RADAR_BIGMAP_ENABLED - 0x231C8F89D0539D8F 0x08EB83D2

void _SET_RADAR_BIGMAP_ENABLED(BOOL toggleBigMap, BOOL showFullMap)

```
Toggles the big minimap state like in GTA:Online.
```

> IS_HUD_COMPONENT_ACTIVE - 0xBC4C9EA5391ECC0D 0x6214631F

BOOL IS_HUD_COMPONENT_ACTIVE(int id)

```
Full list of components below

HUD = 0;
HUD_WANTED_STARS = 1;
HUD_WEAPON_ICON = 2;
HUD_CASH = 3;
HUD_MP_CASH = 4;
HUD_MP_MESSAGE = 5;
HUD_VEHICLE_NAME = 6;
HUD_AREA_NAME = 7;
HUD_VEHICLE_CLASS = 8;
HUD_STREET_NAME = 9;
HUD_HELP_TEXT = 10;
HUD_FLOATING_HELP_TEXT_1 = 11;
HUD_FLOATING_HELP_TEXT_2 = 12;
HUD_CASH_CHANGE = 13;
HUD_RETICLE = 14;
HUD_SUBTITLE_TEXT = 15;
HUD_RADIO_STATIONS = 16;
HUD_SAVING_GAME = 17;
HUD_GAME_STREAM = 18;
HUD_WEAPON_WHEEL = 19;
HUD_WEAPON_WHEEL_STATS = 20;
MAX_HUD_COMPONENTS = 21;
MAX_HUD_WEAPONS = 22;
MAX_SCRIPTED_HUD_COMPONENTS = 141;
```

> IS_SCRIPTED_HUD_COMPONENT_ACTIVE - 0xDD100EB17A94FF65 0x2B86F382

BOOL IS_SCRIPTED_HUD_COMPONENT_ACTIVE(int id)



> HIDE_SCRIPTED_HUD_COMPONENT_THIS_FRAME - 0xE374C498D8BADC14 0x31ABA127

void HIDE_SCRIPTED_HUD_COMPONENT_THIS_FRAME(int id)



> 0x09C0403ED9A751C2 0xE8C8E535

BOOL 0x09C0403ED9A751C2(Any p0)



> HIDE_HUD_COMPONENT_THIS_FRAME - 0x6806C51AD12B83B8 0xDB2D0762

void HIDE_HUD_COMPONENT_THIS_FRAME(int id)



> SHOW_HUD_COMPONENT_THIS_FRAME - 0x0B4DF1FA60C0E664 0x95E1546E

void SHOW_HUD_COMPONENT_THIS_FRAME(int id)



> 0xA4DEDE28B1814289 0x52746FE1

void 0xA4DEDE28B1814289()



> RESET_RETICULE_VALUES - 0x12782CE0A636E9F0 0xBE27AA3F

void RESET_RETICULE_VALUES()



> RESET_HUD_COMPONENT_VALUES - 0x450930E616475D0D 0xD15B46DA

void RESET_HUD_COMPONENT_VALUES(int id)



> SET_HUD_COMPONENT_POSITION - 0xAABB1F56E2A17CED 0x2F3A0D15

void SET_HUD_COMPONENT_POSITION(int id, float p1, float p2)



> GET_HUD_COMPONENT_POSITION - 0x223CA69A8C4417FD 0x080DCED6

int GET_HUD_COMPONENT_POSITION(Any p0)



> 0xB57D8DD645CFA2CF 0x5BBCC934

void 0xB57D8DD645CFA2CF()



> 0xF9904D11F1ACBEC3 0xFE9A39F8

Any 0xF9904D11F1ACBEC3(float x, float y, float z, Any* p3, Any* p4)

```
World to relative screen coords

this world to screen will keep the text on screen. it will keep it in the screen pos
```

> 0x523A590C1A3CC0D3 0x10DE5150

void 0x523A590C1A3CC0D3()

```
Shows a hud element for reporting jobs
```

> 0xEE4C0E6DBC6F2C6F 0x67649EE0

void 0xEE4C0E6DBC6F2C6F()

```
Hides the hud element displayed by _0x523A590C1A3CC0D3
```

> 0x9135584D09A3437E 0x9D2C94FA

Any 0x9135584D09A3437E()



> 0x2432784ACA090DA4 0x45472FD5

BOOL 0x2432784ACA090DA4(Any p0)



> 0x7679CC1BCEBE3D4C 0x198F32D7

void 0x7679CC1BCEBE3D4C(Any p0, float p1, float p2)



> 0x784BA7E0ECEB4178 0x93045157

void 0x784BA7E0ECEB4178(Any p0, float x, float y, float z)



> 0xB094BC1DB4018240 0x18B012B7

void 0xB094BC1DB4018240(Any p0, Any p1, float p2, float p3)



> 0x788E7FD431BD67F1 0x97852A82

void 0x788E7FD431BD67F1(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)



> CLEAR_FLOATING_HELP - 0x50085246ABD3FEFA 0xB181F88F

void CLEAR_FLOATING_HELP(Any p0, BOOL p1)



> 0x6DD05E9D83EFA4C9 0xC969F2D0

void 0x6DD05E9D83EFA4C9(int headDisplayId, char* username, BOOL pointedClanTag, BOOL isRockstarClan, char* clanTag, Any p5, Any p6, Any p7, Any p8)



> 0x6E0EB3EB47C8D7AA 0xEFD2564A

BOOL 0x6E0EB3EB47C8D7AA()



> _CREATE_HEAD_DISPLAY - 0xBFEFE3321A3F5015 0xF5CD2AA4

int _CREATE_HEAD_DISPLAY(Ped ped, char* username, BOOL pointedClanTag, BOOL isRockstarClan, char* clanTag, Any p5)

```
p0 was the return of NET_TO_PED in fm_mission_controler.
p4 was always ''.
returns headDisplayId
```

> 0x31698AA80E0223F8 0x3D081FE4

void 0x31698AA80E0223F8(int headDisplayId)



> _HAS_HEAD_DISPLAY_LOADED - 0x4E929E7A5796FD26 0x60118951

BOOL _HAS_HEAD_DISPLAY_LOADED(int headDisplayId)



> ADD_TREVOR_RANDOM_MODIFIER - 0x595B5178E412E199 0x63959059

BOOL ADD_TREVOR_RANDOM_MODIFIER(int headDisplayId)

```
Hash collision!
_HAS_HEAD_DISPLAY_LOADED_2
```

> _SET_HEAD_DISPLAY_FLAG - 0x63BB75ABEDC1F6A0 0xD41DF479

void _SET_HEAD_DISPLAY_FLAG(int headDisplayId, int sprite, BOOL toggle)

```
enum HeadDisplayFlag
{
  TextWithOutline = 0,
  NoneEmpty,
  HealthBar,
  AudioSpeaker,
  FlagOrPaused,
  Flag,
  PassiveMode,
  WantedStar,
  SteeringWheel,
  Headset,
  HighlightPlayer,
  TextNoOutline,
  ArrowDown,
  BreifCase,
  LittleUser,
  RankNumber,
  VoiceIndicator
};
```

> 0xEE76FF7E6A0166B0 0x767DED29

void 0xEE76FF7E6A0166B0(int headDisplayId, BOOL p1)



> 0xA67F9C46D612B6F1 0xB01A5434

void 0xA67F9C46D612B6F1(int headDisplayId, BOOL p1)

```
Displays a bunch of icons above the players name, and level, and their name twice
```

> 0x613ED644950626AE 0x7E3AA40A

void 0x613ED644950626AE(int headDisplayId, Any p1, int flag)

```
Ranges from 0 to 200. 0 is grey health bar, ~50 yellow, 200 purple.
```

> 0x3158C77A7E888AB4 0x5777EC77

void 0x3158C77A7E888AB4(int headDisplayId, Any p1)

```
Ranges from 0 to 200. 0 is grey health bar, ~50 yellow, 200 purple.
Should be enabled as flag (2). Has 0 opacity by default.
```

> 0xD48FE545CD46F857 0xF4418611

void 0xD48FE545CD46F857(int headDisplayId, Any p1, Any p2)

```
Sets flag's sprite transparency. 0-255.
```

> _SET_HEAD_DISPLAY_WANTED - 0xCF228E2AA03099C3 0x0EBB003F

void _SET_HEAD_DISPLAY_WANTED(int headDisplayId, int wantedlvl)

```
displays wanted star above head
```

> _SET_HEAD_DISPLAY_STRING - 0xDEA2B8283BAA3944 0x627A559B

void _SET_HEAD_DISPLAY_STRING(int headDisplayId, char* string)



> 0xEB709A36958ABE0D 0xF11414C4

BOOL 0xEB709A36958ABE0D(int headDisplayId)



> 0x7B7723747CCB55B6 0x939218AB

void 0x7B7723747CCB55B6(int headDisplayId, char* string)

```
Set's the string displayed when flag 3 (AudioSpeaker) active.
```

> 0x01A358D9128B7A86 0xAB5B7C18

Any 0x01A358D9128B7A86()

```
native only found once in appinternet.c4
```

> GET_CURRENT_WEBSITE_ID - 0x97D47996FC48CBAD 0x42A55B14

int GET_CURRENT_WEBSITE_ID()



> 0xE3B05614DCE1D014 0xD217EE7E

Any 0xE3B05614DCE1D014(Any p0)



> 0xB99C4E4D9499DF29 

void 0xB99C4E4D9499DF29(BOOL p0)



> 0xAF42195A42C63BBA 

Any 0xAF42195A42C63BBA()



> SET_WARNING_MESSAGE - 0x7B1776B3B53F8D74 0xBE699BDE

void SET_WARNING_MESSAGE(char* entryLine1, int instructionalKey, char* entryLine2, BOOL p3, Any p4, Any* p5, Any* p6, BOOL background)

```
You can only use text entries. No custom text.

Example: SET_WARNING_MESSAGE('t20', 3, 'adder', false, -1, 0, 0, true);
```

> _SET_WARNING_MESSAGE_2 - 0xDC38CC1E35B6A5D7 0x2DB9EAB5

void _SET_WARNING_MESSAGE_2(char* entryHeader, char* entryLine1, int instructionalKey, char* entryLine2, BOOL p4, Any p5, Any* p6, Any* p7, BOOL background)

```
You can only use text entries. No custom text.
```

> _SET_WARNING_MESSAGE_3 - 0x701919482C74B5AB 0x749929D3

void _SET_WARNING_MESSAGE_3(char* entryHeader, char* entryLine1, Any instructionalKey, char* entryLine2, BOOL p4, Any p5, Any p6, Any* p7, Any* p8, BOOL p9)

```
You can only use text entries. No custom text.
```

> 0x0C5A80A9E096D529 

BOOL 0x0C5A80A9E096D529(Any p0, Any* p1, Any p2, Any p3, Any p4, Any p5)



> 0xDAF87174BE7454FF 

BOOL 0xDAF87174BE7454FF(Any p0)



> 0x6EF54AB721DC6242 

void 0x6EF54AB721DC6242()



> IS_WARNING_MESSAGE_ACTIVE - 0xE18B138FABC53103 0x94C834AD

BOOL IS_WARNING_MESSAGE_ACTIVE()



> 0x7792424AA0EAC32E 0x2F9A309C

void 0x7792424AA0EAC32E()



> 0x5354C5BA2EA868A4 0xE4FD20D8

void 0x5354C5BA2EA868A4(BOOL p0)

```
If toggle is true, the map is shown in full screen
If toggle is false, the map is shown in normal mode
```

> 0x1EAE6DD17B7A5EFA 0x13E7A5A9

void 0x1EAE6DD17B7A5EFA(Any p0)



> 0x551DF99658DB6EE8 0x786CA0A2

Any 0x551DF99658DB6EE8(float p0, float p1, float p2)



> 0x2708FC083123F9FF 0xCBEC9369

void 0x2708FC083123F9FF()



> 0x1121BFA1A1A522A8 0x3F4AFB13

Any 0x1121BFA1A1A522A8()



> 0x82CEDC33687E1F50 0x2F28F0A6

void 0x82CEDC33687E1F50(BOOL p0)



> 0x211C4EF450086857 0x801D0D86

void 0x211C4EF450086857()



> 0xBF4F34A85CA2970C 0x317775DF

void 0xBF4F34A85CA2970C()



> ACTIVATE_FRONTEND_MENU - 0xEF01D36B9C9D0C7B 0x01D83872

void ACTIVATE_FRONTEND_MENU(Hash menuhash, BOOL Toggle_Pause, int p2)

```
Does stuff like this:
gyazo.com/7fcb78ea3520e3dbc5b2c0c0f3712617

Example:
int GetHash = GET_HASH_KEY('fe_menu_version_corona_lobby');
ACTIVATE_FRONTEND_MENU(GetHash, 0, -1);

BOOL p1 is a toggle to define the game in pause.
int p2 is unknown but -1 always works, not sure why though.
```

> RESTART_FRONTEND_MENU - 0x10706DC6AD2D49C0 0xB07DAF98

void RESTART_FRONTEND_MENU(Hash menuHash, int p1)

```
Before using this native click the native above and look at the decription.

Example:
int GetHash = Function.Call&lt;int&gt;(Hash.GET_HASH_KEY, 'fe_menu_version_corona_lobby');
Function.Call(Hash.ACTIVATE_FRONTEND_MENU, GetHash, 0, -1);
Function.Call(Hash.RESTART_FRONTEND_MENU(GetHash, -1);

This native refreshes the frontend menu.

p1 = Hash of Menu
p2 = Unknown but always works with -1.
```

> 0x2309595AD6145265 0x33D6868F

Hash 0x2309595AD6145265()

```
if (UI::_2309595AD6145265() == ${fe_menu_version_empty_no_background})

Seems to get the current frontend menu
```

> SET_PAUSE_MENU_ACTIVE - 0xDF47FC56C71569CF 0x1DCD878E

void SET_PAUSE_MENU_ACTIVE(BOOL toggle)



> DISABLE_FRONTEND_THIS_FRAME - 0x6D3465A73092F0E6 0xD86A029E

void DISABLE_FRONTEND_THIS_FRAME()



> 0xBA751764F0821256 0x7F349900

void 0xBA751764F0821256()



> 0xCC3FDDED67BCFC63 0x630CD8EE

void 0xCC3FDDED67BCFC63()



> SET_FRONTEND_ACTIVE - 0x745711A75AB09277 0x81E1AD32

void SET_FRONTEND_ACTIVE(BOOL active)



> IS_PAUSE_MENU_ACTIVE - 0xB0034A223497FFCB 0xD3600591

BOOL IS_PAUSE_MENU_ACTIVE()



> 0x2F057596F2BD0061 0xC85C4487

Any 0x2F057596F2BD0061()



> GET_PAUSE_MENU_STATE - 0x272ACD84970869C5 0x92F50134

int GET_PAUSE_MENU_STATE()

```
Returns:

0
5
10
15
20
25
30
35

```

> 0x5BFF36D6ED83E0AE 

Vector3 0x5BFF36D6ED83E0AE()



> IS_PAUSE_MENU_RESTARTING - 0x1C491717107431C7 0x3C4CF4D9

BOOL IS_PAUSE_MENU_RESTARTING()



> 0x2162C446DFDF38FD 0x2DFD35C7

void 0x2162C446DFDF38FD(Any p0)

```
Not present in retail version of the game, actual definiton seems to be
_LOG_DEBUG_INFO(char* category, char* debugText);
```

> 0x77F16B447824DA6C 0x0A89336C

void 0x77F16B447824DA6C(Any p0)



> 0xCDCA26E80FAECB8F 0xC84BE309

void 0xCDCA26E80FAECB8F()



> 0xDD564BDD0472C936 0x9FE8FD5E

void 0xDD564BDD0472C936(Hash hash)

```
Seems to add/set the current menu context (to show/hide buttons?)

Pausemenu.xml:
&lt;Contexts&gt;*ALL*, DISPLAY_CORONA_BUTTONS, *NONE*, BET_LOCKED, BET_AVAILABLE, SCROLL_OPTION&lt;/Contexts&gt;
Code:
if (...) {
    sub_bbd34(a_0, 0, 'FM_BET_HELP');
    UI::_DD564BDD0472C936(${bet_available}); // This native
    UI::OBJECT_DECAL_TOGGLE(${bet_locked});
} else { 
    sub_bbd34(a_0, 0, '');
    UI::OBJECT_DECAL_TOGGLE(${bet_available});
    UI::_DD564BDD0472C936(${bet_locked}); // This native
}

OBJECT_DECAL_TOGGLE seems to remove a context, It also has a hash collision

// Old
Scripts do not make this native's purpose clear. However, this native most likely has something to do with decals since in nearly every instance, 'OBJECT_DECAL_TOGGLE' is called prior.
```

> OBJECT_DECAL_TOGGLE - 0x444D8CF241EC25C5 0x0029046E

void OBJECT_DECAL_TOGGLE(Hash hash)

```
Please change back to _0x444D8CF241EC25C5 (hash collision)
```

> 0x84698AB38D0C6636 0xC51BC42F

BOOL 0x84698AB38D0C6636(Hash hash)



> 0x2A25ADC48F87841F 0x016D7AF9

Any 0x2A25ADC48F87841F()



> 0xDE03620F8703A9DF 

Any 0xDE03620F8703A9DF()



> 0x359AF31A4B52F5ED 

Any 0x359AF31A4B52F5ED()



> 0x13C4B962653A5280 

Any 0x13C4B962653A5280()



> 0xC8E1071177A23BE5 

BOOL 0xC8E1071177A23BE5(Any* p0, Any* p1, Any* p2)



> ENABLE_DEATHBLOOD_SEETHROUGH - 0x4895BDEA16E7C080 0x15B24768

void ENABLE_DEATHBLOOD_SEETHROUGH(BOOL p0)

```
Please change back to _0x4895BDEA16E7C080 (hash collision)
```

> 0xC78E239AC5B2DDB9 0x6C67131A

void 0xC78E239AC5B2DDB9(BOOL p0, Any p1, Any p2)



> 0xF06EBB91A81E09E3 0x11D09737

void 0xF06EBB91A81E09E3(BOOL p0)



> 0x3BAB9A4E4F2FF5C7 0xD3BF3ABD

Any 0x3BAB9A4E4F2FF5C7()



> 0xEC9264727EEC0F28 0xC06B763D

void 0xEC9264727EEC0F28()



> 0x14621BB1DF14E2B2 0xB9392CE7

void 0x14621BB1DF14E2B2()



> 0x66E7CB63C97B7D20 0x92DAFA78

Any 0x66E7CB63C97B7D20()



> 0x593FEAE1F73392D4 0x22CA9F2A

Any 0x593FEAE1F73392D4()



> 0x4E3CD0EF8A489541 0xDA7951A2

Any 0x4E3CD0EF8A489541()



> 0xF284AC67940C6812 0x7D95AFFF

Any 0xF284AC67940C6812()



> 0x2E22FEFA0100275E 0x96863460

Any 0x2E22FEFA0100275E()



> 0x0CF54F20DE43879C 

void 0x0CF54F20DE43879C(Any p0)



> 0x36C1451A88A09630 0x8543AAC8

void 0x36C1451A88A09630(Any* p0, Any* p1)



> 0x7E17BE53E1AAABAF 0x6025AA2F

void 0x7E17BE53E1AAABAF(Any* p0, Any* p1, Any* p2)



> 0xA238192F33110615 0x46794EB2

BOOL 0xA238192F33110615(int* p0, int* p1, int* p2)



> SET_USERIDS_UIHIDDEN - 0xEF4CED81CEBEDC6D 0x4370999E

BOOL SET_USERIDS_UIHIDDEN(Any p0, Any* p1)

```
Hash collision! Please change back to _0xEF4CED81CEBEDC6D
```

> 0xCA6B2F7CE32AB653 

BOOL 0xCA6B2F7CE32AB653(Any p0, Any* p1, Any p2)



> 0x90A6526CF0381030 0xD6CC4766

BOOL 0x90A6526CF0381030(Any p0, Any* p1, Any p2, Any p3)



> 0x24A49BEAF468DC90 

BOOL 0x24A49BEAF468DC90(Any p0, Any* p1, Any p2, Any p3, Any p4)



> 0x5FBD7095FE7AE57F 0x51972B04

BOOL 0x5FBD7095FE7AE57F(Any p0, float* p1)



> 0x8F08017F9D7C47BD 

BOOL 0x8F08017F9D7C47BD(Any p0, Any* p1, Any p2)



> 0x052991E59076E4E4 0xD43BB56D

BOOL 0x052991E59076E4E4(Hash p0, Any* p1)

```
p0 was always 0xAE2602A3.
```

> CLEAR_PED_IN_PAUSE_MENU - 0x5E62BE5DC58E9E06 0x28058ACF

void CLEAR_PED_IN_PAUSE_MENU()



> GIVE_PED_TO_PAUSE_MENU - 0xAC0BFBDC3BE00E14 0x2AD2C9CE

void GIVE_PED_TO_PAUSE_MENU(Ped ped, int p1)

```
p1 is either 1 or 2 in the PC scripts.
```

> 0x3CA6050692BC61B0 0x127310EB

void 0x3CA6050692BC61B0(BOOL p0)



> 0xECF128344E9FF9F1 0x8F45D327

void 0xECF128344E9FF9F1(BOOL p0)



> _SHOW_SOCIAL_CLUB_LEGAL_SCREEN - 0x805D7CBB36FD6C4C 0x19FCBBB2

void _SHOW_SOCIAL_CLUB_LEGAL_SCREEN()

```
probs one frame
```

> 0xF13FE2A80C05C561 0x850690FF

Any 0xF13FE2A80C05C561()



> 0x6F72CD94F7B5B68C 0x9D4934F4

Any 0x6F72CD94F7B5B68C()



> 0x75D3691713C3B05A 0x57218529

void 0x75D3691713C3B05A()



> 0xD2B32BE3FC1626C6 0x5F86AA39

void 0xD2B32BE3FC1626C6()



> 0x9E778248D6685FE0 0x7AD67C95

void 0x9E778248D6685FE0(char* p0)

```
UI::0x7AD67C95('Gallery');
UI::0x7AD67C95('Missions');
UI::0x7AD67C95('General');
UI::0x7AD67C95('Playlists');
```

> 0xC406BE343FC4B9AF 0xD4DA14EF

Any 0xC406BE343FC4B9AF()



> 0x1185A8087587322C 

void 0x1185A8087587322C(BOOL p0)

```
SET_TEXT_??? - Used in golf and golf_mp
```

> 0x8817605C2BA76200 

void 0x8817605C2BA76200()



> _IS_TEXT_CHAT_ACTIVE - 0xB118AF58B5F332A1 

BOOL _IS_TEXT_CHAT_ACTIVE()

```
Returns whether or not the text chat (MULTIPLAYER_CHAT Scaleform component) is active.

-- NTAuthority (http://fivem.net)
```

> _ABORT_TEXT_CHAT - 0x1AC8F4AD40E22127 

void _ABORT_TEXT_CHAT()

```
Aborts the current message in the text chat.
```

> _SET_TEXT_CHAT_UNK - 0x1DB21A44B09E8BA3 

void _SET_TEXT_CHAT_UNK(BOOL p0)

```
Sets an unknown boolean value in the text chat.
```

> 0xCEF214315D276FD1 0xFF06772A

void 0xCEF214315D276FD1(BOOL p0)



> 0xD30C50DF888D58B5 0x96C4C4DD

void 0xD30C50DF888D58B5(Ped ped, BOOL p1)



> DOES_PED_HAVE_AI_BLIP - 0x15B8ECF844EE67ED 0x3BE1257F

BOOL DOES_PED_HAVE_AI_BLIP(Ped ped)



> 0xE52B8E7F85D39A08 0xD8E31B1A

void 0xE52B8E7F85D39A08(Ped ped, Any p1)



> HIDE_SPECIAL_ABILITY_LOCKON_OPERATION - 0x3EED80DFF7325CAA 0x872C2CFB

void HIDE_SPECIAL_ABILITY_LOCKON_OPERATION(Any p0, BOOL p1)

```
Hash collision
```

> 0x0C4BBF625CA98C4E 0xFFDF46F0

void 0x0C4BBF625CA98C4E(Ped ped, BOOL p1)



> 0x97C65887D4B37FA9 0xF9DC2AF7

void 0x97C65887D4B37FA9(Ped ped, float p1)



> 0x7CD934010E115C2C 0x06349065

Any 0x7CD934010E115C2C(Any p0)



> 0x56176892826A4FE8 0xCA52CF43

Blip 0x56176892826A4FE8(Ped ped)



> 0xA277800A9EAE340E 

Any 0xA277800A9EAE340E()



> 0x2632482FD6B9AB87 

void 0x2632482FD6B9AB87()



> 0x808519373FD336A3 

void 0x808519373FD336A3(BOOL p0)

```
If toggle is true, hides special ability bar / character name in the pause menu
If toggle is false, shows special ability bar / character name in the pause menu
```

> 0x04655F9D075D0AE5 

void 0x04655F9D075D0AE5(BOOL p0)



