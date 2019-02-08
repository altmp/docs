# Decisionevent

> SET_DECISION_MAKER - 0xB604A2942ADED0EE 0x19CEAC9E

void SET_DECISION_MAKER(Ped ped, Hash name)



> CLEAR_DECISION_MAKER_EVENT_RESPONSE - 0x4FC9381A7AEE8968 0x07ABD94D

void CLEAR_DECISION_MAKER_EVENT_RESPONSE(Hash name, int type)



> BLOCK_DECISION_MAKER_EVENT - 0xE42FCDFD0E4196F7 0x57506EA6

void BLOCK_DECISION_MAKER_EVENT(Hash name, int type)



> UNBLOCK_DECISION_MAKER_EVENT - 0xD7CD9CF34F2C99E8 0x62A3161D

void UNBLOCK_DECISION_MAKER_EVENT(Hash name, int type)



> ADD_SHOCKING_EVENT_AT_POSITION - 0xD9F8455409B525E9 0x0B30F779

ScrHandle ADD_SHOCKING_EVENT_AT_POSITION(int type, float x, float y, float z, float duration)

```
duration is float here

Event types- camx.me/gtav/tasks/shockingevents.txt
```

> ADD_SHOCKING_EVENT_FOR_ENTITY - 0x7FD8F3BE76F89422 0xA81B5B71

ScrHandle ADD_SHOCKING_EVENT_FOR_ENTITY(int type, Entity entity, float duration)

```
duration is float here

Event types - camx.me/gtav/tasks/shockingevents.txt
```

> IS_SHOCKING_EVENT_IN_SPHERE - 0x1374ABB7C15BAB92 0x2F98823E

BOOL IS_SHOCKING_EVENT_IN_SPHERE(int type, float x, float y, float z, float radius)

```
Some events that i found, not sure about them, but seems to have logic based on my tests:

        '82 - dead body
        '86 - explosion
        '87 - fire
        '88 - shooting, fire extinguisher in use
        '89 - shooting
        '93 - ped using horn
        '95 - ped receiving melee attack
        '102 - living ped receiving shot
        '104 - player thrown grenade, tear gas, smoke grenade, jerry can dropping gasoline
        '105 - melee attack against veh
        '106 - player running
        '108 - vehicle theft
        '112 - melee attack
        '113 - veh rollover ped
        '114 - dead ped receiving shot
        '116 - aiming at ped
        '121 - armed

*JulioNIB

Here is full dump of shocking event types from the exe camx.me/gtav/tasks/shockingevents.txt 
(Looks like julios guesses are pretty accurate)
```

> REMOVE_SHOCKING_EVENT - 0x2CDA538C44C6CCE5 0xF82D5A87

BOOL REMOVE_SHOCKING_EVENT(ScrHandle event)



> REMOVE_ALL_SHOCKING_EVENTS - 0xEAABE8FDFA21274C 0x64DF6282

void REMOVE_ALL_SHOCKING_EVENTS(BOOL p0)



> REMOVE_SHOCKING_EVENT_SPAWN_BLOCKING_AREAS - 0x340F1415B68AEADE 0xA0CE89C8

void REMOVE_SHOCKING_EVENT_SPAWN_BLOCKING_AREAS()



> SUPPRESS_SHOCKING_EVENTS_NEXT_FRAME - 0x2F9A292AD0A3BD89 0x4CC674B5

void SUPPRESS_SHOCKING_EVENTS_NEXT_FRAME()



> SUPPRESS_SHOCKING_EVENT_TYPE_NEXT_FRAME - 0x3FD2EC8BF1F1CF30 0xA0FDCB82

void SUPPRESS_SHOCKING_EVENT_TYPE_NEXT_FRAME(int type)



> SUPPRESS_AGITATION_EVENTS_NEXT_FRAME - 0x5F3B7749C112D552 0x80340396

void SUPPRESS_AGITATION_EVENTS_NEXT_FRAME()



