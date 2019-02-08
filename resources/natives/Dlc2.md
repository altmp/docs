# Dlc2

> IS_DLC_PRESENT - 0x812595A0644CE1DE 0x1F321943

BOOL IS_DLC_PRESENT(Hash DlcHash)

```
Example:
DLC2::IS_DLC_PRESENT($/mpbusiness2/);
($ = gethashkey)

bruteforce these:
0xB119F6D
0x96F02EE6
```

> 0xF2E07819EF1A5289 0x881B1FDB

BOOL 0xF2E07819EF1A5289()

```
MulleDK19: This function is hard-coded to always return 1.
```

> 0x9489659372A81585 0xC2169164

Any 0x9489659372A81585()

```
MulleDK19: This function is hard-coded to always return 0.
```

> 0xA213B11DFF526300 0xF79A97F5

Any 0xA213B11DFF526300()

```
MulleDK19: This function is hard-coded to always return 1.
```

> 0x8D30F648014A92B5 0xF69B729C

Any 0x8D30F648014A92B5()



> GET_IS_LOADING_SCREEN_ACTIVE - 0x10D0A8F259E93EC9 0x517B601B

BOOL GET_IS_LOADING_SCREEN_ACTIVE()



> _NULLIFY - 0x46E2B844905BC5F0 0x6087C10C

BOOL _NULLIFY(Any* variable, Any unused)

```
Sets the value of the specified variable to 0.
Always returns true.

bool _NULLIFY(void* variable, int unused)
{
    *variable = NULL;
    return true;
}
```

> _LOAD_SP_DLC_MAPS - 0xD7C10C4A637992C9 

void _LOAD_SP_DLC_MAPS()

```
Unloads GROUP_MAP (GTAO/MP) DLC data and loads GROUP_MAP_SP DLC. Neither are loaded by default, 0888C3502DBBEEF5 is a cognate to this function and loads MP DLC (and unloads SP DLC by extension).

The original (and wrong) definition is below:

This unload the GTA:O DLC map parts (like high end garages/apartments).
Works in singleplayer.

console hash: 0x8BF60FC3
```

> _LOAD_MP_DLC_MAPS - 0x0888C3502DBBEEF5 

void _LOAD_MP_DLC_MAPS()

```
This loads the GTA:O dlc map parts (high end garages, apartments).
Works in singleplayer.
In order to use GTA:O heist IPL's you have to call this native with the following params: _9BAE5AD2508DF078(1);

console hash: 0xC65586A9
```

