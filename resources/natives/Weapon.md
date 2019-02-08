# Weapon

> ENABLE_LASER_SIGHT_RENDERING - 0xC8B46D7727D864AA 0xE3438955

void ENABLE_LASER_SIGHT_RENDERING(BOOL toggle)

```
Enables laser sight on any weapon.

It doesn't work. Neither on tick nor OnKeyDown
```

> GET_WEAPON_COMPONENT_TYPE_MODEL - 0x0DB57B41EC1DB083 0x324FA47A

Hash GET_WEAPON_COMPONENT_TYPE_MODEL(Hash componentHash)



> GET_WEAPONTYPE_MODEL - 0xF46CDC33180FDA94 0x44E1C269

Hash GET_WEAPONTYPE_MODEL(Hash weaponHash)

```
Returns the model of any weapon.

Can also take an ammo hash?
sub_6663a(&amp;l_115B, WEAPON::GET_WEAPONTYPE_MODEL(${ammo_rpg}));
```

> GET_WEAPONTYPE_SLOT - 0x4215460B9B8B7FA0 0x2E3759AF

Hash GET_WEAPONTYPE_SLOT(Hash weaponHash)



> GET_WEAPONTYPE_GROUP - 0xC3287EE3050FB74C 0x5F2DE833

Hash GET_WEAPONTYPE_GROUP(Hash weaponHash)



> SET_CURRENT_PED_WEAPON - 0xADF692B254977C0C 0xB8278882

void SET_CURRENT_PED_WEAPON(Ped ped, Hash weaponHash, BOOL equipNow)



> GET_CURRENT_PED_WEAPON - 0x3A87E44BB9A01D54 0xB0237302

BOOL GET_CURRENT_PED_WEAPON(Ped ped, Hash* weaponHash, BOOL p2)

```
The return value seems to indicate if the weapon is ready to use.
No idea what p2 does, it seems to be 1 most of the time.

-------------------------------------------------------------------------

^ Wrong
Returns true if the hash of the weapon object weapon equals the weapon hash. Also, p2 is not implemented.

```

> GET_CURRENT_PED_WEAPON_ENTITY_INDEX - 0x3B390A939AF0B5FC 0x5D73CD20

Entity GET_CURRENT_PED_WEAPON_ENTITY_INDEX(Ped ped)



> GET_BEST_PED_WEAPON - 0x8483E98E8B888AE2 0xB998D444

Hash GET_BEST_PED_WEAPON(Ped ped, BOOL p1)

```
p1 is always 0 in the scripts.
```

> SET_CURRENT_PED_VEHICLE_WEAPON - 0x75C55983C2C39DAA 0x8E6F2AF1

BOOL SET_CURRENT_PED_VEHICLE_WEAPON(Ped ped, Hash weaponHash)



> GET_CURRENT_PED_VEHICLE_WEAPON - 0x1017582BCD3832DC 0xF26C5D65

BOOL GET_CURRENT_PED_VEHICLE_WEAPON(Ped ped, Hash* weaponHash)

```
Example in VB

    Public Shared Function GetVehicleCurrentWeapon(Ped As Ped) As Integer
        Dim arg As New OutputArgument()
        Native.Function.Call(Hash.GET_CURRENT_PED_VEHICLE_WEAPON, Ped, arg)
        Return arg.GetResult(Of Integer)()
    End Function

Usage:
If GetVehicleCurrentWeapon(Game.Player.Character) = -821520672 Then ...Do something
Note: -821520672 = VEHICLE_WEAPON_PLANE_ROCKET

By I'm Not MentaL
```

> IS_PED_ARMED - 0x475768A975D5AD17 0x0BFC892C

BOOL IS_PED_ARMED(Ped ped, int p1)

```
p1 is anywhere from 4 to 7 in the scripts. Might be a weapon wheel group?

^It's kinda like that. 
7 returns true if you are equipped with any weapon except your fists.
6 returns true if you are equipped with any weapon except melee weapons.
5 returns true if you are equipped with any weapon except the Explosives weapon group.
4 returns true if you are equipped with any weapon except Explosives weapon group AND melee weapons.
3 returns true if you are equipped with either Explosives or Melee weapons (the exact opposite of 4).
2 returns true only if you are equipped with any weapon from the Explosives weapon group.
1 returns true only if you are equipped with any Melee weapon.
0 never returns true.

Note: When I say 'Explosives weapon group', it does not include the Jerry can and Fire Extinguisher.
```

> IS_WEAPON_VALID - 0x937C71165CF334B3 0x38CA2954

BOOL IS_WEAPON_VALID(Hash weaponHash)



> HAS_PED_GOT_WEAPON - 0x8DECB02F88F428BC 0x43D2FA82

BOOL HAS_PED_GOT_WEAPON(Ped ped, Hash weaponHash, BOOL p2)

```
p2 should be FALSE, otherwise it seems to always return FALSE

bool could be that if that weapon is current weapon in hand
```

> IS_PED_WEAPON_READY_TO_SHOOT - 0xB80CA294F2F26749 0x02A32CB0

BOOL IS_PED_WEAPON_READY_TO_SHOOT(Ped ped)



> GET_PED_WEAPONTYPE_IN_SLOT - 0xEFFED78E9011134D 0x9BC64E16

Hash GET_PED_WEAPONTYPE_IN_SLOT(Ped ped, Hash weaponSlot)



> GET_AMMO_IN_PED_WEAPON - 0x015A522136D7F951 0x0C755733

int GET_AMMO_IN_PED_WEAPON(Ped ped, Hash weaponhash)

```
WEAPON::GET_AMMO_IN_PED_WEAPON(PLAYER::PLAYER_PED_ID(), a_0)

From decompiled scripts
Returns total ammo in weapon

GTALua Example :
natives.WEAPON.GET_AMMO_IN_PED_WEAPON(plyPed, WeaponHash)
```

> ADD_AMMO_TO_PED - 0x78F0424C34306220 0x7F0580C7

void ADD_AMMO_TO_PED(Ped ped, Hash weaponHash, int ammo)



> SET_PED_AMMO - 0x14E56BC5B5DB6A19 0xBF90DF1A

void SET_PED_AMMO(Ped ped, Hash weaponHash, int ammo)



> SET_PED_INFINITE_AMMO - 0x3EDCB0505123623B 0x9CB8D278

void SET_PED_INFINITE_AMMO(Ped ped, BOOL toggle, Hash weaponHash)



> SET_PED_INFINITE_AMMO_CLIP - 0x183DADC6AA953186 0x5A5E3B67

void SET_PED_INFINITE_AMMO_CLIP(Ped ped, BOOL toggle)



> GIVE_WEAPON_TO_PED - 0xBF0FD6E56C964FCB 0xC4D88A85

void GIVE_WEAPON_TO_PED(Ped ped, Hash weaponHash, int ammoCount, BOOL isHidden, BOOL equipNow)

```
All weapon names (add to the list if something is missing), use GAMEPLAY::GET_HASH_KEY((char *)weaponNames[i]) to get get the hash:

static LPCSTR weaponNames[] = {
	'WEAPON_KNIFE', 'WEAPON_NIGHTSTICK', 'WEAPON_HAMMER', 'WEAPON_BAT', 'WEAPON_GOLFCLUB',
	'WEAPON_CROWBAR', 'WEAPON_PISTOL', 'WEAPON_COMBATPISTOL', 'WEAPON_APPISTOL', 'WEAPON_PISTOL50',
	'WEAPON_MICROSMG', 'WEAPON_SMG', 'WEAPON_ASSAULTSMG', 'WEAPON_ASSAULTRIFLE',
	'WEAPON_CARBINERIFLE', 'WEAPON_ADVANCEDRIFLE', 'WEAPON_MG', 'WEAPON_COMBATMG', 'WEAPON_PUMPSHOTGUN',
	'WEAPON_SAWNOFFSHOTGUN', 'WEAPON_ASSAULTSHOTGUN', 'WEAPON_BULLPUPSHOTGUN', 'WEAPON_STUNGUN', 'WEAPON_SNIPERRIFLE',
	'WEAPON_HEAVYSNIPER', 'WEAPON_GRENADELAUNCHER', 'WEAPON_GRENADELAUNCHER_SMOKE', 'WEAPON_RPG', 'WEAPON_MINIGUN',
	'WEAPON_GRENADE', 'WEAPON_STICKYBOMB', 'WEAPON_SMOKEGRENADE', 'WEAPON_BZGAS', 'WEAPON_MOLOTOV',
	'WEAPON_FIREEXTINGUISHER', 'WEAPON_PETROLCAN', 'WEAPON_FLARE', 'WEAPON_SNSPISTOL', 'WEAPON_SPECIALCARBINE',
	'WEAPON_HEAVYPISTOL', 'WEAPON_BULLPUPRIFLE', 'WEAPON_HOMINGLAUNCHER', 'WEAPON_PROXMINE', 'WEAPON_SNOWBALL',
	'WEAPON_VINTAGEPISTOL', 'WEAPON_DAGGER', 'WEAPON_FIREWORK', 'WEAPON_MUSKET', 'WEAPON_MARKSMANRIFLE',
	'WEAPON_HEAVYSHOTGUN', 'WEAPON_GUSENBERG', 'WEAPON_HATCHET', 'WEAPON_RAILGUN', 'WEAPON_COMBATPDW',
	'WEAPON_KNUCKLE', 'WEAPON_MARKSMANPISTOL', 'WEAPON_FLASHLIGHT', 'WEAPON_MACHETE', 'WEAPON_MACHINEPISTOL',
	'WEAPON_SWITCHBLADE', 'WEAPON_REVOLVER', 'WEAPON_COMPACTRIFLE', 'WEAPON_DBSHOTGUN', 'WEAPON_FLAREGUN',
	'WEAPON_AUTOSHOTGUN', 'WEAPON_BATTLEAXE', 'WEAPON_COMPACTLAUNCHER', 'WEAPON_MINISMG', 'WEAPON_PIPEBOMB',
	'WEAPON_POOLCUE', 'WEAPON_SWEEPER', 'WEAPON_WRENCH'
};
----------------------------------------------------------------------------------------------------------------------------------------
Translation table:
pastebin.com/a39K8Nz8
```

> GIVE_DELAYED_WEAPON_TO_PED - 0xB282DC6EBD803C75 0x5868D20D

void GIVE_DELAYED_WEAPON_TO_PED(Ped ped, Hash weaponHash, int time, BOOL equipNow)

```
Gives a weapon to PED with a delay, example:

WEAPON::GIVE_DELAYED_WEAPON_TO_PED(PED::PLAYER_PED_ID(), GAMEPLAY::GET_HASH_KEY('WEAPON_PISTOL'), 1000, false)
----------------------------------------------------------------------------------------------------------------------------------------
Translation table:
pastebin.com/a39K8Nz8


```

> REMOVE_ALL_PED_WEAPONS - 0xF25DF915FA38C5F3 0xA44CE817

void REMOVE_ALL_PED_WEAPONS(Ped ped, BOOL toggle)

```
setting the last params to false it does that same so I would suggest its not a toggle
```

> REMOVE_WEAPON_FROM_PED - 0x4899CB088EDF59B8 0x9C37F220

void REMOVE_WEAPON_FROM_PED(Ped ped, Hash weaponHash)

```
This native removes a specified weapon from your selected ped.
Weapon Hashes: pastebin.com/0wwDZgkF

Example:
C#:
Function.Call(Hash.REMOVE_WEAPON_FROM_PED, Game.Player.Character, 0x99B507EA);

C++:
WEAPON::REMOVE_WEAPON_FROM_PED(PLAYER::PLAYER_PED_ID(), 0x99B507EA);

The code above removes the knife from the player.
```

> HIDE_PED_WEAPON_FOR_SCRIPTED_CUTSCENE - 0x6F6981D2253C208F 0x00CFD6E9

void HIDE_PED_WEAPON_FOR_SCRIPTED_CUTSCENE(Ped ped, BOOL toggle)

```
Hides the players weapon during a cutscene.
```

> SET_PED_CURRENT_WEAPON_VISIBLE - 0x0725A4CCFDED9A70 0x00BECD77

void SET_PED_CURRENT_WEAPON_VISIBLE(Ped ped, BOOL visible, BOOL deselectWeapon, BOOL p3, BOOL p4)

```
Has 5 parameters since latest patches.
```

> SET_PED_DROPS_WEAPONS_WHEN_DEAD - 0x476AE72C1D19D1A8 0x8A444056

void SET_PED_DROPS_WEAPONS_WHEN_DEAD(Ped ped, BOOL toggle)



> HAS_PED_BEEN_DAMAGED_BY_WEAPON - 0x2D343D2219CD027A 0xCDFBBCC6

BOOL HAS_PED_BEEN_DAMAGED_BY_WEAPON(Ped ped, Hash weaponHash, int weaponType)

```
It determines what weapons caused damage:

If you want to define only a specific weapon, second parameter=weapon hash code, third parameter=0
If you want to define any melee weapon, second parameter=0, third parameter=1.
If you want to identify any weapon (firearms, melee, rockets, etc.), second parameter=0, third parameter=2.
```

> CLEAR_PED_LAST_WEAPON_DAMAGE - 0x0E98F88A24C5F4B8 0x52C68832

void CLEAR_PED_LAST_WEAPON_DAMAGE(Ped ped)



> HAS_ENTITY_BEEN_DAMAGED_BY_WEAPON - 0x131D401334815E94 0x6DAABB39

BOOL HAS_ENTITY_BEEN_DAMAGED_BY_WEAPON(Entity entity, Hash weaponHash, int weaponType)

```
It determines what weapons caused damage:

If youu want to define only a specific weapon, second parameter=weapon hash code, third parameter=0
If you want to define any melee weapon, second parameter=0, third parameter=1.
If you want to identify any weapon (firearms, melee, rockets, etc.), second parameter=0, third parameter=2.
```

> CLEAR_ENTITY_LAST_WEAPON_DAMAGE - 0xAC678E40BE7C74D2 0xCEC2732B

void CLEAR_ENTITY_LAST_WEAPON_DAMAGE(Entity entity)



> SET_PED_DROPS_WEAPON - 0x6B7513D9966FBEC0 0x3D3329FA

void SET_PED_DROPS_WEAPON(Ped ped)



> SET_PED_DROPS_INVENTORY_WEAPON - 0x208A1888007FC0E6 0x81FFB874

void SET_PED_DROPS_INVENTORY_WEAPON(Ped ped, Hash weaponHash, float xOffset, float yOffset, float zOffset, Any p5)



> GET_MAX_AMMO_IN_CLIP - 0xA38DCFFCEA8962FA 0x6961E2A4

int GET_MAX_AMMO_IN_CLIP(Ped ped, Hash weaponHash, BOOL p2)

```
p2 is mostly 1 in the scripts.
```

> GET_AMMO_IN_CLIP - 0x2E1202248937775C 0x73C100C3

BOOL GET_AMMO_IN_CLIP(Ped ped, Hash weaponHash, int* ammo)



> SET_AMMO_IN_CLIP - 0xDCD2A934D65CB497 0xA54B0B10

BOOL SET_AMMO_IN_CLIP(Ped ped, Hash weaponHash, int ammo)



> GET_MAX_AMMO - 0xDC16122C7A20C933 0x0B294796

BOOL GET_MAX_AMMO(Ped ped, Hash weaponHash, int* ammo)



> SET_PED_AMMO_BY_TYPE - 0x5FD1E1F011E76D7E 0x311C52BB

void SET_PED_AMMO_BY_TYPE(Ped ped, Any ammoType, int ammo)



> GET_PED_AMMO_BY_TYPE - 0x39D22031557946C1 0x54077C4D

int GET_PED_AMMO_BY_TYPE(Ped ped, Any ammoType)



> SET_PED_AMMO_TO_DROP - 0xA4EFEF9440A5B0EF 0x2386A307

void SET_PED_AMMO_TO_DROP(Any p0, Any p1)



> 0xE620FD3512A04F18 0xD6460EA2

void 0xE620FD3512A04F18(float p0)



> GET_PED_AMMO_TYPE_FROM_WEAPON - 0x7FEAD38B326B9F74 0x09337863

Hash GET_PED_AMMO_TYPE_FROM_WEAPON(Ped ped, Hash weaponHash)



> GET_PED_LAST_WEAPON_IMPACT_COORD - 0x6C4D0409BA1A2BC2 0x9B266079

BOOL GET_PED_LAST_WEAPON_IMPACT_COORD(Ped ped, Vector3* coords)

```
Pass ped. Pass address of Vector3.
The coord will be put into the Vector3.
The return will determine whether there was a coord found or not.
```

> SET_PED_GADGET - 0xD0D7B1E680ED4A1A 0x8A256D0A

void SET_PED_GADGET(Ped ped, Hash gadgetHash, BOOL p2)

```
p1/gadgetHash was always 0xFBAB5776 ('GADGET_PARACHUTE').
p2 is always true.
```

> GET_IS_PED_GADGET_EQUIPPED - 0xF731332072F5156C 0x8DDD0B5B

BOOL GET_IS_PED_GADGET_EQUIPPED(Ped ped, Hash gadgetHash)

```
gadgetHash - was always 0xFBAB5776 ('GADGET_PARACHUTE').
```

> GET_SELECTED_PED_WEAPON - 0x0A6DB4965674D243 0xD240123E

Hash GET_SELECTED_PED_WEAPON(Ped ped)

```
Returns the hash of the weapon. 

            var num7 = WEAPON::GET_SELECTED_PED_WEAPON(num4);
            sub_27D3(num7);
            switch (num7)
            {
                case 0x24B17070:

Also see WEAPON::GET_CURRENT_PED_WEAPON. Difference?

-------------------------------------------------------------------------

The difference is that GET_SELECTED_PED_WEAPON simply returns the ped's current weapon hash but GET_CURRENT_PED_WEAPON also checks the weapon object and returns true if the hash of the weapon object equals the weapon hash
```

> EXPLODE_PROJECTILES - 0xFC4BD125DE7611E4 0x35A0B955

void EXPLODE_PROJECTILES(Ped ped, Hash weaponHash, BOOL p2)



> REMOVE_ALL_PROJECTILES_OF_TYPE - 0xFC52E0F37E446528 0xA5F89919

void REMOVE_ALL_PROJECTILES_OF_TYPE(Hash weaponHash, BOOL p1)

```
p1 seems always to be 0
```

> _GET_LOCKON_RANGE_OF_CURRENT_PED_WEAPON - 0x840F03E9041E2C9C 0x3612110D

float _GET_LOCKON_RANGE_OF_CURRENT_PED_WEAPON(Ped ped)



> GET_MAX_RANGE_OF_CURRENT_PED_WEAPON - 0x814C9D19DFD69679 0xB2B2BBAA

float GET_MAX_RANGE_OF_CURRENT_PED_WEAPON(Ped ped)



> HAS_VEHICLE_GOT_PROJECTILE_ATTACHED - 0x717C8481234E3B88 0xA57E2E80

BOOL HAS_VEHICLE_GOT_PROJECTILE_ATTACHED(Ped driver, Vehicle vehicle, Hash weapon, Any p3)

```
Third Parameter = unsure, but pretty sure it is weapon hash
--&gt; get_hash_key('weapon_stickybomb')

Fourth Parameter = unsure, almost always -1
```

> GIVE_WEAPON_COMPONENT_TO_PED - 0xD966D51AA5B28BB9 0x3E1E286D

void GIVE_WEAPON_COMPONENT_TO_PED(Ped ped, Hash weaponHash, Hash componentHash)



> REMOVE_WEAPON_COMPONENT_FROM_PED - 0x1E8BE90C74FB4C09 0x412AA00D

void REMOVE_WEAPON_COMPONENT_FROM_PED(Ped ped, Hash weaponHash, Hash componentHash)



> HAS_PED_GOT_WEAPON_COMPONENT - 0xC593212475FAE340 0xDC0FC145

BOOL HAS_PED_GOT_WEAPON_COMPONENT(Ped ped, Hash weaponHash, Hash componentHash)



> IS_PED_WEAPON_COMPONENT_ACTIVE - 0x0D78DE0572D3969E 0x7565FB19

BOOL IS_PED_WEAPON_COMPONENT_ACTIVE(Ped ped, Hash weaponHash, Hash componentHash)



> _IS_PED_RELOADING - 0x8C0D57EA686FAD87 0x82EEAF0F

BOOL _IS_PED_RELOADING(Ped ped)



> MAKE_PED_RELOAD - 0x20AE33F3AC9C0033 0x515292C2

BOOL MAKE_PED_RELOAD(Ped ped)



> REQUEST_WEAPON_ASSET - 0x5443438F033E29C3 0x65D139A5

void REQUEST_WEAPON_ASSET(Hash weaponHash, int p1, int p2)

```
Nearly every instance of p1 I found was 31. Nearly every instance of p2 I found was 0.

REQUEST_WEAPON_ASSET(iLocal_1888, 31, 26);
```

> HAS_WEAPON_ASSET_LOADED - 0x36E353271F0E90EE 0x1891D5BB

BOOL HAS_WEAPON_ASSET_LOADED(Hash weaponHash)



> REMOVE_WEAPON_ASSET - 0xAA08EF13F341C8FC 0x2C0DFE3C

void REMOVE_WEAPON_ASSET(Hash weaponHash)



> CREATE_WEAPON_OBJECT - 0x9541D3CF0D398F36 0x62F5987F

Object CREATE_WEAPON_OBJECT(Hash weaponHash, int ammoCount, float x, float y, float z, BOOL showWorldModel, float heading, Any p7)

```
Now has 8 params.
```

> GIVE_WEAPON_COMPONENT_TO_WEAPON_OBJECT - 0x33E179436C0B31DB 0xF7612A37

void GIVE_WEAPON_COMPONENT_TO_WEAPON_OBJECT(Object weaponObject, Hash addonHash)

```
addonHash:
(use WEAPON::GET_WEAPON_COMPONENT_TYPE_MODEL() to get hash value)
${component_at_ar_flsh}, ${component_at_ar_supp}, ${component_at_pi_flsh}, ${component_at_scope_large}, ${component_at_ar_supp_02}
```

> REMOVE_WEAPON_COMPONENT_FROM_WEAPON_OBJECT - 0xF7D82B0D66777611 0xA6E7ED3C

void REMOVE_WEAPON_COMPONENT_FROM_WEAPON_OBJECT(Any p0, Any p1)



> HAS_WEAPON_GOT_WEAPON_COMPONENT - 0x76A18844E743BF91 0x1D368510

BOOL HAS_WEAPON_GOT_WEAPON_COMPONENT(Object weapon, Hash addonHash)



> GIVE_WEAPON_OBJECT_TO_PED - 0xB1FA61371AF7C4B7 0x639AF3EF

void GIVE_WEAPON_OBJECT_TO_PED(Object weaponObject, Ped ped)



> DOES_WEAPON_TAKE_WEAPON_COMPONENT - 0x5CEE3DF569CECAB0 0xB1817BAA

BOOL DOES_WEAPON_TAKE_WEAPON_COMPONENT(Hash weaponHash, Hash componentHash)



> GET_WEAPON_OBJECT_FROM_PED - 0xCAE1DC9A0E22A16D 0xDF939A38

Object GET_WEAPON_OBJECT_FROM_PED(Ped ped, BOOL p1)

```
Drops the current weapon and returns the object

Unknown behavior when unarmed.
```

> SET_PED_WEAPON_TINT_INDEX - 0x50969B9B89ED5738 0xEB2A7B23

void SET_PED_WEAPON_TINT_INDEX(Ped ped, Hash weaponHash, int colorIndex)

```
tintIndex can be the following:

0 - Normal
1 - Green
2 - Gold
3 - Pink
4 - Army
5 - LSPD
6 - Orange
7 - Platinum
```

> GET_PED_WEAPON_TINT_INDEX - 0x2B9EEDC07BD06B9F 0x3F9C90A7

int GET_PED_WEAPON_TINT_INDEX(Ped ped, Hash weaponHash)



> SET_WEAPON_OBJECT_TINT_INDEX - 0xF827589017D4E4A9 0x44ACC1DA

void SET_WEAPON_OBJECT_TINT_INDEX(Entity weapon, int tint)



> GET_WEAPON_OBJECT_TINT_INDEX - 0xCD183314F7CD2E57 0xD91D9576

int GET_WEAPON_OBJECT_TINT_INDEX(Entity weapon)



> GET_WEAPON_TINT_COUNT - 0x5DCF6C5CAB2E9BF7 0x99E4EAAB

int GET_WEAPON_TINT_COUNT(Hash weaponHash)



> GET_WEAPON_HUD_STATS - 0xD92C739EE34C9EBA 0xA9AD3D98

BOOL GET_WEAPON_HUD_STATS(Any p0, Any* p1)

```
struct WeaponHudStatsData
{
    BYTE hudDamage; // 0x0000
    char _0x0001[0x7]; // 0x0001
    BYTE hudSpeed; // 0x0008
    char _0x0009[0x7]; // 0x0009
    BYTE hudCapacity; // 0x0010
    char _0x0011[0x7]; // 0x0011
    BYTE hudAccuracy; // 0x0018
    char _0x0019[0x7]; // 0x0019
    BYTE hudRange; // 0x0020
};

Usage:

WeaponHudStatsData data;
if (GET_WEAPON_HUD_STATS(weaponHash, (int *)&amp;data))
{
    // BYTE damagePercentage = data.hudDamage and so on
}
```

> GET_WEAPON_COMPONENT_HUD_STATS - 0xB3CAF387AE12E9F8 0xBB5498F4

BOOL GET_WEAPON_COMPONENT_HUD_STATS(Any p0, Any* p1)



> 0x3133B907D8B32053 

float 0x3133B907D8B32053(Any p0, Any p1)



> GET_WEAPON_CLIP_SIZE - 0x583BE370B1EC6EB4 0x8D515E66

int GET_WEAPON_CLIP_SIZE(Hash weaponHash)

```
// Returns the size of the default weapon component clip.

Use it like this:

char cClipSize[32];
Hash cur;
if (WEAPON::GET_CURRENT_PED_WEAPON(playerPed, &amp;cur, 1))
{
    if (WEAPON::IS_WEAPON_VALID(cur))
    {
        int iClipSize = WEAPON::GET_WEAPON_CLIP_SIZE(cur);
        sprintf_s(cClipSize, 'ClipSize: %.d', iClipSize);
        vDrawString(cClipSize, 0.5f, 0.5f);
    }
}

```

> SET_PED_CHANCE_OF_FIRING_BLANKS - 0x8378627201D5497D 0xB4F44C6E

void SET_PED_CHANCE_OF_FIRING_BLANKS(Ped ped, float xBias, float yBias)



> 0xB4C8D77C80C0421E 0xEC2E5304

Entity 0xB4C8D77C80C0421E(Ped ped, float p1)

```
This does not take a weapon hash...
```

> REQUEST_WEAPON_HIGH_DETAIL_MODEL - 0x48164DBB970AC3F0 0xE3BD00F9

void REQUEST_WEAPON_HIGH_DETAIL_MODEL(Entity weaponObject)



> IS_PED_CURRENT_WEAPON_SILENCED - 0x65F0C5AE05943EC7 0xBAF7BFBE

BOOL IS_PED_CURRENT_WEAPON_SILENCED(Ped ped)

```
This native returns a true or false value.

Ped ped = The ped whose weapon you want to check.
```

> SET_WEAPON_SMOKEGRENADE_ASSIGNED - 0x4B7620C47217126C 0x76876154

BOOL SET_WEAPON_SMOKEGRENADE_ASSIGNED(Ped ped)

```
Hash collision!!! IS_FLASH_LIGHT_ON

HASH COLLISION

Hash Collision

hASH cOLLISION

HASH COLLISION
A            O
S            I
H            S
             I
C            L
O            L
L            O
L            C
I
S            H
I            S
O            A
NOISILLOC HSAH

What do we need to fuck up around here to get someone to notice and fix this?
```

> SET_FLASH_LIGHT_FADE_DISTANCE - 0xCEA66DAD478CD39B 0xB0127EA7

Any SET_FLASH_LIGHT_FADE_DISTANCE(float distance)



> SET_WEAPON_ANIMATION_OVERRIDE - 0x1055AC3A667F09D9 0xA5DF7484

void SET_WEAPON_ANIMATION_OVERRIDE(Ped ped, Hash animStyle)

```
Changes the selected ped aiming animation style. 
Note : You must use GET_HASH_KEY!

Strings to use with GET_HASH_KEY :

	'Ballistic',
	'Default',
	'Fat',
	'Female',
	'FirstPerson',
	'FirstPersonAiming',
	'FirstPersonFranklin',
	'FirstPersonFranklinAiming',
	'FirstPersonFranklinRNG',
	'FirstPersonFranklinScope',
	'FirstPersonMPFemale',
	'FirstPersonMichael',
	'FirstPersonMichaelAiming',
	'FirstPersonMichaelRNG',
	'FirstPersonMichaelScope',
	'FirstPersonRNG',
	'FirstPersonScope',
	'FirstPersonTrevor',
	'FirstPersonTrevorAiming',
	'FirstPersonTrevorRNG',
	'FirstPersonTrevorScope',
	'Franklin',
	'Gang',
	'Gang1H',
	'GangFemale',
	'Hillbilly',
	'MP_F_Freemode',
	'Michael',
	'SuperFat',
	'Trevor'
```

> GET_WEAPON_DAMAGE_TYPE - 0x3BE0BB12D25FB305 0x013AFC13

int GET_WEAPON_DAMAGE_TYPE(Hash weaponHash)

```
0=unknown (or incorrect weaponHash)
1= no damage (flare,snowball, petrolcan)
2=melee
3=bullet
4=force ragdoll fall
5=explosive (RPG, Railgun, grenade)
6=fire(molotov)
8=fall(WEAPON_HELI_CRASH)
10=electric
11=barbed wire
12=extinguisher
13=gas
14=water cannon(WEAPON_HIT_BY_WATER_CANNON)
```

> 0xE4DCEC7FD5B739A5 0x64646F1D

void 0xE4DCEC7FD5B739A5(Ped ped)



> CAN_USE_WEAPON_ON_PARACHUTE - 0xBC7BE5ABC0879F74 0x135E7AD4

BOOL CAN_USE_WEAPON_ON_PARACHUTE(Hash weaponHash)



