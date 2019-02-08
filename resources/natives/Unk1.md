# Unk1

> 0x48621C9FCA3EBD28 

void 0x48621C9FCA3EBD28(BOOL p0)



> 0x81CBAE94390F9F89 

void 0x81CBAE94390F9F89()



> 0x13B350B8AD0EEE10 

void 0x13B350B8AD0EEE10()



> 0x293220DA1B46CEBC 

void 0x293220DA1B46CEBC(float p0, float p1, BOOL p2)



> 0x208784099002BC30 

void 0x208784099002BC30(char* missionNameLabel, Any p1)

```
-This function appears to be deprecated/ unused. Tracing the call internally leads to a _nullsub -

first one seems to be a string of a mission name, second one seems to be a bool/toggle

p1 was always 0.

```

> 0xEB2D525B57F42B40 

void 0xEB2D525B57F42B40()



> 0xF854439EFBB3B583 

void 0xF854439EFBB3B583()



> 0xAF66DCEE6609B148 

void 0xAF66DCEE6609B148()



> 0x66972397E0757E7A 

void 0x66972397E0757E7A(Any p0, Any p1, Any p2)



> _START_RECORDING - 0xC3AC2FFF9612AC81 

void _START_RECORDING(int mode)

```
Starts recording a replay.
If mode is 0, turns on action replay.
If mode is 1, starts recording.
If already recording a replay, does nothing.
```

> _STOP_RECORDING_AND_SAVE_CLIP - 0x071A5197D6AFC8B3 

void _STOP_RECORDING_AND_SAVE_CLIP()

```
Stops recording and saves the recorded clip.
```

> _STOP_RECORDING_AND_DISCARD_CLIP - 0x88BB3507ED41A240 

void _STOP_RECORDING_AND_DISCARD_CLIP()

```
Stops recording and discards the recorded clip.
```

> 0x644546EC5287471B 

BOOL 0x644546EC5287471B()



> _IS_RECORDING - 0x1897CA71995A90B4 

BOOL _IS_RECORDING()

```
Checks if you're recording, returns TRUE when you start recording (F1) or turn on action replay (F2)

mov al, cs:g_bIsRecordingGameplay // byte_141DD0CD0 in b944
retn
```

> 0xDF4B952F7D381B95 

Any 0xDF4B952F7D381B95()



> 0x4282E08174868BE3 

Any 0x4282E08174868BE3()



> 0x33D47E85B476ABCD 

BOOL 0x33D47E85B476ABCD(BOOL p0)



