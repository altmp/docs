# Water

> GET_WATER_HEIGHT - 0xF6829842C06AE524 0xD864E17C

BOOL GET_WATER_HEIGHT(float x, float y, float z, float* height)

```
This function set height to the value of z-axis of the water surface.

This function works with sea and lake. However it does not work with shallow rivers (e.g. raton canyon will return -100000.0f)

note: seems to return true when you are in water
```

> GET_WATER_HEIGHT_NO_WAVES - 0x8EE6B53CE13A9794 0x262017F8

BOOL GET_WATER_HEIGHT_NO_WAVES(float x, float y, float z, float* height)



> TEST_PROBE_AGAINST_WATER - 0xFFA5D878809819DB 0xAA4AE00C

BOOL TEST_PROBE_AGAINST_WATER(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)



> TEST_PROBE_AGAINST_ALL_WATER - 0x8974647ED222EA5F 0x4A962D55

BOOL TEST_PROBE_AGAINST_ALL_WATER(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7)



> TEST_VERTICAL_PROBE_AGAINST_ALL_WATER - 0x2B3451FA1E3142E2 0x4C71D143

BOOL TEST_VERTICAL_PROBE_AGAINST_ALL_WATER(float x, float y, float z, Any p3, Any* p4)



> MODIFY_WATER - 0xC443FD757C3BA637 0xC49E005A

void MODIFY_WATER(float x, float y, float radius, float height)

```
Sets the water height for a given position and radius.

```

> 0xFDBF4CDBC07E1706 

int 0xFDBF4CDBC07E1706(float x, float y, float z, float radius, float unk)

```
console hash: 0x45268B6F

Most likely ADD_CURRENT_*
```

> 0xB1252E3E59A82AAF 

void 0xB1252E3E59A82AAF(int p0)

```
p0 is the handle returned from _0xFDBF4CDBC07E1706

console hash: 0x7DBCEF6F

Most likely REMOVE_CURRENT_*
```

> _SET_WAVES_INTENSITY - 0xB96B00E976BE977F 

void _SET_WAVES_INTENSITY(float intensity)

```
Sets a value that determines how aggressive the ocean waves will be. Values of 2.0 or more make for very aggressive waves like you see during a thunderstorm.

Works only ~200 meters around the player.

Most likely SET_CURRENT_*
```

> _GET_WAVES_INTENSITY - 0x2B2A2CC86778B619 

float _GET_WAVES_INTENSITY()

```
Gets the aggressiveness factor of the ocean waves.

console hash: 0xBD0A67FB

Most likely GET_CURRENT_*
```

> _RESET_WAVES_INTENSITY - 0x5E5E99285AE812DB 

void _RESET_WAVES_INTENSITY()

```
Sets the waves intensity back to original (1.0 in most cases).

console hash: 0x4AD23212

Most likely RESET_CURRENT_*
```

