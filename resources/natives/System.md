# System

> WAIT - 0x4EDE34FBADD967A6 0x7715C03B

void WAIT(int ms)

```
Pauses execution of the current script, please note this behavior is only seen when called from one of the game script files(ysc). In order to wait an asi script use 
    static void WAIT(DWORD time);
found in main.h 

--------------------------------------------------------------------
It does not actually seem to wait the amount of milliseconds stated like the normal WAIT() command does, but it does seem to make task sequences work more smoothly

System native hashes do not change on gameupdate
```

> START_NEW_SCRIPT - 0xE81651AD79516E48 0x3F166D0E

int START_NEW_SCRIPT(char* scriptName, int stackSize)

```
Examples:
 g_384A = SYSTEM::START_NEW_SCRIPT('cellphone_flashhand', 1424);
 l_10D = SYSTEM::START_NEW_SCRIPT('taxiService', 1828);
 SYSTEM::START_NEW_SCRIPT('AM_MP_YACHT', 5000);
 SYSTEM::START_NEW_SCRIPT('emergencycall', 512);
 SYSTEM::START_NEW_SCRIPT('emergencycall', 512); 
 SYSTEM::START_NEW_SCRIPT('FM_maintain_cloud_header_data', 1424);
 SYSTEM::START_NEW_SCRIPT('FM_Mission_Controller', 31000);
 SYSTEM::START_NEW_SCRIPT('tennis_family', 3650);
 SYSTEM::START_NEW_SCRIPT('Celebrations', 3650);

Decompiled examples of usage when starting a script:
 
    SCRIPT::REQUEST_SCRIPT(a_0);
    if (SCRIPT::HAS_SCRIPT_LOADED(a_0)) {
        SYSTEM::START_NEW_SCRIPT(a_0, v_3);
        SCRIPT::SET_SCRIPT_AS_NO_LONGER_NEEDED(a_0);
        return 1;
    }
 
or:

    v_2 = 'MrsPhilips2';
    SCRIPT::REQUEST_SCRIPT(v_2);
    while (!SCRIPT::HAS_SCRIPT_LOADED(v_2)) {
    SCRIPT::REQUEST_SCRIPT(v_2);
    SYSTEM::WAIT(0);
    }
    sub_8792(36);
    SYSTEM::START_NEW_SCRIPT(v_2, 17000);
    SCRIPT::SET_SCRIPT_AS_NO_LONGER_NEEDED(v_2);

All native script names: pastebin.com/K9adDsu4 and pastebin.com/yLNWicUi
```

> START_NEW_SCRIPT_WITH_ARGS - 0xB8BA7F44DF1575E1 0x4A2100E4

int START_NEW_SCRIPT_WITH_ARGS(char* scriptName, Any* args, int argCount, int stackSize)

```
return : script thread id, 0 if failed
Pass pointer to struct of args in p1, size of struct goes into p2
```

> _START_NEW_STREAMED_SCRIPT - 0xEB1C67C3A5333A92 0x8D15BE5D

int _START_NEW_STREAMED_SCRIPT(Hash scriptHash, int stackSize)



> _START_NEW_STREAMED_SCRIPT_WITH_ARGS - 0xC4BB298BD441BE78 0xE38A3AD4

int _START_NEW_STREAMED_SCRIPT_WITH_ARGS(Hash scriptHash, Any* args, int argCount, int stackSize)



> TIMERA - 0x83666F9FB8FEBD4B 0x45C8C188

int TIMERA()

```
Counts up. Every 1000 is 1 real-time second. Use SETTIMERA(int value) to set the timer (e.g.: SETTIMERA(0)).
```

> TIMERB - 0xC9D9444186B5A374 0x330A9C0C

int TIMERB()



> SETTIMERA - 0xC1B1E9A034A63A62 0x35785333

void SETTIMERA(int value)



> SETTIMERB - 0x5AE11BC36633DE4E 0x27C1B7C6

void SETTIMERB(int value)



> TIMESTEP - 0x0000000050597EE2 0x50597EE2

float TIMESTEP()

```
Gets the current frame time.
```

> SIN - 0x0BADBFA3B172435F 0xBF987F58

float SIN(float value)



> COS - 0xD0FFB162F40A139C 0x00238FE9

float COS(float value)



> SQRT - 0x71D93B57D07F9804 0x145C7701

float SQRT(float value)



> POW - 0xE3621CC40F31FE2E 0x85D134F8

float POW(float base, float exponent)



> VMAG - 0x652D2EEEF1D3E62C 0x1FCF1ECD

float VMAG(float p0, float p1, float p2)

```
Calculates the magnitude of a vector.
```

> VMAG2 - 0xA8CEACB4F35AE058 0xE796E629

float VMAG2(float p0, float p1, float p2)

```
Calculates the magnitude of a vector but does not perform Sqrt operations. (Its way faster)
```

> VDIST - 0x2A488C176D52CCA5 0x3C08ECB7

float VDIST(float x1, float y1, float z1, float x2, float y2, float z2)

```
Calculates distance between vectors.
```

> VDIST2 - 0xB7A628320EFF8E47 0xC85DEF1F

float VDIST2(float x1, float y1, float z1, float x2, float y2, float z2)

```
Calculates distance between vectors but does not perform Sqrt operations. (Its way faster)
```

> SHIFT_LEFT - 0xEDD95A39E5544DE8 0x314CC6CD

int SHIFT_LEFT(int value, int bitShift)



> SHIFT_RIGHT - 0x97EF1E5BCE9DC075 0x352633CA

int SHIFT_RIGHT(int value, int bitShift)



> FLOOR - 0xF34EE736CF047844 0x32E9BE04

int FLOOR(float value)



> CEIL - 0x11E019C8F43ACC8A 0xD536A1DF

int CEIL(float value)

```
I'm guessing this rounds a float value up to the next whole number, and FLOOR rounds it down
```

> ROUND - 0xF2DB717A73826179 0x323B0E24

int ROUND(float value)



> TO_FLOAT - 0xBBDA792448DB5A89 0x67116627

float TO_FLOAT(int value)



