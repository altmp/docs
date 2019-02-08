# Decorator

> DECOR_SET_TIME - 0x95AED7B8E39ECAA4 0xBBAEEF94

BOOL DECOR_SET_TIME(Entity entity, char* propertyName, int value)



> DECOR_SET_BOOL - 0x6B1E8E2ED1335B71 0x8E101F5C

BOOL DECOR_SET_BOOL(Entity entity, char* propertyName, BOOL value)

```
This function sets metadata of type bool to specified entity.

```

> _DECOR_SET_FLOAT - 0x211AB1DD8D0F363A 

BOOL _DECOR_SET_FLOAT(Entity entity, char* propertyName, float value)

```
console hash: 0xBC7BD5CB = DECOR_SET_FLOAT
```

> DECOR_SET_INT - 0x0CE3AA5E1CA19E10 0xDB718B21

BOOL DECOR_SET_INT(Entity entity, char* propertyName, int value)

```
Sets property to int.
```

> DECOR_GET_BOOL - 0xDACE671663F2F5DB 0xDBCE51E0

BOOL DECOR_GET_BOOL(Entity entity, char* propertyName)



> _DECOR_GET_FLOAT - 0x6524A2F114706F43 

float _DECOR_GET_FLOAT(Entity entity, char* propertyName)

```
console hash: 0x8DE5382F = DECOR_GET_FLOAT
```

> DECOR_GET_INT - 0xA06C969B02A97298 0xDDDE59B5

int DECOR_GET_INT(Entity entity, char* propertyName)



> DECOR_EXIST_ON - 0x05661B80A8C9165F 0x74EF9C40

BOOL DECOR_EXIST_ON(Entity entity, char* propertyName)

```
Checks if property with that name exists on entity.
```

> DECOR_REMOVE - 0x00EE9F297C738720 0xE0E2640B

BOOL DECOR_REMOVE(Entity entity, char* propertyName)



> DECOR_REGISTER - 0x9FD90732F56403CE 0x68BD42A9

void DECOR_REGISTER(char* propertyName, int type)

```
Found this in standard_global_init.c4 line 1898

void sub_523a() {
    DECORATOR::DECOR_REGISTER('Player_Vehicle', 3);
    DECORATOR::DECOR_REGISTER('PV_Slot', 3);
    DECORATOR::DECOR_REGISTER('Previous_Owner', 3);
    DECORATOR::DECOR_REGISTER('Sprayed_Vehicle_Decorator', 2);
    DECORATOR::DECOR_REGISTER('Sprayed_Vehicle_Timer_Dec', 5);
    DECORATOR::DECOR_REGISTER('Vehicle_Reward', 3);
    DECORATOR::DECOR_REGISTER('Vehicle_Reward_Teams', 3);
    DECORATOR::DECOR_REGISTER('Skill_Blocker', 2);
    DECORATOR::DECOR_REGISTER('TargetPlayerForTeam', 3);
    DECORATOR::DECOR_REGISTER('XP_Blocker', 2);
    DECORATOR::DECOR_REGISTER('CrowdControlSetUp', 3);
    DECORATOR::DECOR_REGISTER('Bought_Drugs', 2);
    DECORATOR::DECOR_REGISTER('HeroinInPossession', 1);
    DECORATOR::DECOR_REGISTER('CokeInPossession', 1);
    DECORATOR::DECOR_REGISTER('WeedInPossession', 1);
    DECORATOR::DECOR_REGISTER('MethInPossession', 1);
    DECORATOR::DECOR_REGISTER('bombdec', 3);
    DECORATOR::DECOR_REGISTER('bombdec1', 3);
    DECORATOR::DECOR_REGISTER('bombowner', 3);
    DECORATOR::DECOR_REGISTER('noPlateScan', 2);
    DECORATOR::DECOR_REGISTER('prisonBreakBoss', 2);
    DECORATOR::DECOR_REGISTER('cashondeadbody', 3);
    DECORATOR::DECOR_REGISTER('MissionType', 3);
    DECORATOR::DECOR_REGISTER('MatchId', 3);
    DECORATOR::DECOR_REGISTER('TeamId', 3);
    DECORATOR::DECOR_REGISTER('Not_Allow_As_Saved_Veh', 3);
    DECORATOR::DECOR_REGISTER('Veh_Modded_By_Player', 3);
    DECORATOR::DECOR_REGISTER('MPBitset', 3);
    DECORATOR::DECOR_REGISTER('MC_EntityID', 3);
    DECORATOR::DECOR_REGISTER('MC_ChasePedID', 3);
    DECORATOR::DECOR_REGISTER('MC_Team0_VehDeliveredRules', 3);
    DECORATOR::DECOR_REGISTER('MC_Team1_VehDeliveredRules', 3);
    DECORATOR::DECOR_REGISTER('MC_Team2_VehDeliveredRules', 3);
    DECORATOR::DECOR_REGISTER('MC_Team3_VehDeliveredRules', 3);
    DECORATOR::DECOR_REGISTER('AttributeDamage', 3);
    DECORATOR::DECOR_REGISTER('GangBackup', 3);
    DECORATOR::DECOR_REGISTER('CreatedByPegasus', 2);
    DECORATOR::DECOR_REGISTER('BeforeCorona_0', 2);
}

-----------------------------------------------------------------------
Defines type of property for property name.

1 - float,
2 - bool,
3 - int
5 - time

```

> DECOR_IS_REGISTERED_AS_TYPE - 0x4F14F9F870D6FBC8 0x7CF0971D

BOOL DECOR_IS_REGISTERED_AS_TYPE(char* propertyName, int type)

```
Is property of that type.

1 - float
2 - bool
3 - int
5 - time

```

> DECOR_REGISTER_LOCK - 0xA9D14EEA259F9248 0x7F3F1C02

void DECOR_REGISTER_LOCK()

```
Called after all decorator type initializations.
```

> 0x241FCA5B1AA14F75 

int 0x241FCA5B1AA14F75()

```
console hash: 0x0AF83036
Unknown. Needs more research. Used only once in the scripts.

maintransition.c4, line ~82432:
if (PED::_7350823473013C02(PLAYER::PLAYER_PED_ID()) &amp;&amp; (DECORATOR::_241FCA5B1AA14F75() == 0)) {
    g_2542A5 = a_1; // 'g_2542A5' used in 'building_controller.ysc' for IPL stuff?
    return 1;
}



```

