# Mobile

> CREATE_MOBILE_PHONE - 0xA4E8E696C532FBC7 0x5BBC5E23

void CREATE_MOBILE_PHONE(int phoneType)

```
Creates a mobile phone of the specified type.

Possible phone types:

0 - Default phone / Michael's phone
1 - Trevor's phone
2 - Franklin's phone
4 - Prologue phone

These values represent bit flags, so a value of '3' would toggle Trevor and Franklin's phones together, causing unexpected behavior and most likely crash the game.
```

> DESTROY_MOBILE_PHONE - 0x3BC861DF703E5097 0x1A65037B

void DESTROY_MOBILE_PHONE()

```
Destroys the currently active mobile phone.
```

> SET_MOBILE_PHONE_SCALE - 0xCBDD322A73D6D932 0x09BCF1BE

void SET_MOBILE_PHONE_SCALE(float scale)

```
The minimum/default is 500.0f. If you plan to make it bigger set it's position as well. Also this seems to need to be called in a loop as when you close the phone the scale is reset. If not in a loop you'd need to call it everytime before you re-open the phone.
```

> SET_MOBILE_PHONE_ROTATION - 0xBB779C0CA917E865 0x209C28CF

void SET_MOBILE_PHONE_ROTATION(float rotX, float rotY, float rotZ, Any p3)

```
Last parameter is unknown and always zero.
```

> GET_MOBILE_PHONE_ROTATION - 0x1CEFB61F193070AE 0x17A29F23

void GET_MOBILE_PHONE_ROTATION(Vector3* rotation, Any p1)



> SET_MOBILE_PHONE_POSITION - 0x693A5C6D6734085B 0x841800B3

void SET_MOBILE_PHONE_POSITION(float posX, float posY, float posZ)



> GET_MOBILE_PHONE_POSITION - 0x584FDFDA48805B86 0xB2E1E1A0

void GET_MOBILE_PHONE_POSITION(Vector3* position)



> SCRIPT_IS_MOVING_MOBILE_PHONE_OFFSCREEN - 0xF511F759238A5122 0x29828690

void SCRIPT_IS_MOVING_MOBILE_PHONE_OFFSCREEN(BOOL toggle)

```
If bool Toggle = true so the mobile is hide to screen.
If bool Toggle = false so the mobile is show to screen.
```

> CAN_PHONE_BE_SEEN_ON_SCREEN - 0xC4E2813898C97A4B 0x5F978584

BOOL CAN_PHONE_BE_SEEN_ON_SCREEN()

```
This one is weird and seems to return a TRUE state regardless of whether the phone is visible on screen or tucked away.


MulleDK19: I can confirm the above. This function is hard-coded to always return 1.
```

> _MOVE_FINGER - 0x95C9E72F3D7DEC9B 

void _MOVE_FINGER(int direction)

```
For move the finger of player, the value of int goes 1 at 5.
```

> _SET_PHONE_LEAN - 0x44E44169EF70138E 

void _SET_PHONE_LEAN(BOOL Toggle)

```
if the bool 'Toggle' is 'true' so the phone is lean.
if the bool 'Toggle' is 'false' so the phone is not lean.
```

> CELL_CAM_ACTIVATE - 0xFDE8F069C542D126 0x234C1AE9

void CELL_CAM_ACTIVATE(BOOL p0, BOOL p1)



> 0x015C49A93E3E086E 0x4479B304

void 0x015C49A93E3E086E(BOOL phoneKeyEnabled)

```
Disables the phone up-button, oddly enough. 
i.e.: When the phone is out, and this method is called with false as it's parameter, the phone will not be able to scroll up. However, when you use the down arrow key, it's functionality still, works on the phone. 

When the phone is not out, and this method is called with false as it's parameter, you will not be able to bring up the phone. Although the up arrow key still works for whatever functionality it's used for, just not for the phone.

This can be used for creating menu's when trying to disable the phone from being used. 

You do not have to call the function again with false as a parameter, as soon as the function stops being called, the phone will again be usable.
```

> 0xA2CCBE62CD4C91A4 0xC273BB4D

void 0xA2CCBE62CD4C91A4(BOOL toggle)

```
Needs more research. If the 'phone_cam12' filter is applied, this function is called with 'TRUE'; otherwise, 'FALSE'.

Example (XBOX 360):

// check current filter selection
if (GAMEPLAY::ARE_STRINGS_EQUAL(getElem(g_2471024, &amp;l_17, 4), 'phone_cam12') != 0)
{
    MOBILE::_0xC273BB4D(0); // FALSE
}
else
{
    MOBILE::_0xC273BB4D(1); // TRUE
}
```

> 0x1B0B4AEED5B9B41C 

void 0x1B0B4AEED5B9B41C(float p0)



> 0x53F4892D18EC90A4 

void 0x53F4892D18EC90A4(float p0)



> 0x3117D84EFA60F77B 

void 0x3117D84EFA60F77B(float p0)



> 0x15E69E2802C24B8D 

void 0x15E69E2802C24B8D(float p0)



> 0xAC2890471901861C 

void 0xAC2890471901861C(float p0)



> 0xD6ADE981781FCA09 

void 0xD6ADE981781FCA09(float p0)



> 0xF1E22DC13F5EEBAD 

void 0xF1E22DC13F5EEBAD(float p0)



> 0x466DA42C89865553 0x66DCD9D2

void 0x466DA42C89865553(float p0)



> CELL_CAM_IS_CHAR_VISIBLE_NO_FACE_CHECK - 0x439E9BC95B7E7FBE 0xBEA88097

BOOL CELL_CAM_IS_CHAR_VISIBLE_NO_FACE_CHECK(Entity entity)



> GET_MOBILE_PHONE_RENDER_ID - 0xB4A53E05F68B6FA1 0x88E4FECE

void GET_MOBILE_PHONE_RENDER_ID(int* renderId)



> 0xBD4D7EAF8A30F637 

BOOL 0xBD4D7EAF8A30F637(char* name)

```
Belongs in UNK3, non-hashed version of 0x247F0F73A182EA0B
```

> 0x247F0F73A182EA0B 

BOOL 0x247F0F73A182EA0B(Hash hash)

```
ex.:

v_15 = sub_10cc8(VEHICLE::GET_VEHICLE_WHEEL_TYPE(a_2));
if (!MOBILE::_247F0F73A182EA0B(v_15)) {
    return 1;
}

Belongs in UNK3, hashed version of 0xBD4D7EAF8A30F637
```

