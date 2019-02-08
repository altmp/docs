# Graphics

> SET_DEBUG_LINES_AND_SPHERES_DRAWING_ACTIVE - 0x175B6BFC15CDD0C5 0x1418CA37

void SET_DEBUG_LINES_AND_SPHERES_DRAWING_ACTIVE(BOOL enabled)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_LINE - 0x7FDFADE676AA3CB0 0xABF783AB

void DRAW_DEBUG_LINE(float x1, float y1, float z1, float x2, float y2, float z2, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_LINE_WITH_TWO_COLOURS - 0xD8B9A8AC5608FF94 0xE8BFF632

void DRAW_DEBUG_LINE_WITH_TWO_COLOURS(float x1, float y1, float z1, float x2, float y2, float z2, int r1, int g1, int b1, int r2, int g2, int b2, int alpha1, int alpha2)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_SPHERE - 0xAAD68E1AB39DA632 0x304D0EEF

void DRAW_DEBUG_SPHERE(float x, float y, float z, float radius, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_BOX - 0x083A2CA4F2E573BD 0x8524A848

void DRAW_DEBUG_BOX(float x1, float y1, float z1, float x2, float y2, float z2, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_CROSS - 0x73B1189623049839 0xB6DF3709

void DRAW_DEBUG_CROSS(float x, float y, float z, float size, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_TEXT - 0x3903E216620488E8 0x269B006F

void DRAW_DEBUG_TEXT(char* text, float x, float y, float z, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_DEBUG_TEXT_2D - 0xA3BB2E9555C05A8F 0x528B973B

void DRAW_DEBUG_TEXT_2D(char* text, float x, float y, float z, int r, int g, int b, int alpha)

```
NOTE: Debugging functions are not present in the retail version of the game.
```

> DRAW_LINE - 0x6B7256074AE34680 0xB3426BCC

void DRAW_LINE(float x1, float y1, float z1, float x2, float y2, float z2, int r, int g, int b, int alpha)

```
Draws a depth-tested line from one point to another.
----------------
x1, y1, z1 : Coordinates for the first point
x2, y2, z2 : Coordinates for the second point
r, g, b, alpha : Color with RGBA-Values
I recommend using a predefined function to call this.
[VB.NET]
Public Sub DrawLine(from As Vector3, [to] As Vector3, col As Color)
    [Function].Call(Hash.DRAW_LINE, from.X, from.Y, from.Z, [to].X, [to].Y, [to].Z, col.R, col.G, col.B, col.A)
End Sub

[C#]
public void DrawLine(Vector3 from, Vector3 to, Color col)
{
    Function.Call(Hash.DRAW_LINE, from.X, from.Y, from.Z, to.X, to.Y, to.Z, col.R, col.G, col.B, col.A);
}
```

> DRAW_POLY - 0xAC26716048436851 0xABD19253

void DRAW_POLY(float x1, float y1, float z1, float x2, float y2, float z2, float x3, float y3, float z3, int r, int g, int b, int alpha)

```
x/y/z - Location of a vertex (in world coords), presumably.
----------------
x1, y1, z1     : Coordinates for the first point
x2, y2, z2     : Coordinates for the second point
x3, y3, z3     : Coordinates for the third point
r, g, b, alpha : Color with RGBA-Values

Keep in mind that only one side of the drawn triangle is visible: It's the side, in which the vector-product of the vectors heads to: (b-a)x(c-a) Or (b-a)x(c-b).
But be aware: The function seems to work somehow differently. I have trouble having them drawn in rotated orientation. Try it yourself and if you somehow succeed, please edit this and post your solution.
I recommend using a predefined function to call this.
[VB.NET]
Public Sub DrawPoly(a As Vector3, b As Vector3, c As Vector3, col As Color)
    [Function].Call(Hash.DRAW_POLY, a.X, a.Y, a.Z, b.X, b.Y, b.Z, c.X, c.Y, c.Z, col.R, col.G, col.B, col.A)
End Sub

[C#]
public void DrawPoly(Vector3 a, Vector3 b, Vector3 c, Color col)
{
    Function.Call(Hash.DRAW_POLY, a.X, a.Y, a.Z, b.X, b.Y, b.Z, c.X, c.Y, c.Z, col.R, col.G, col.B, col.A);
}
BTW: Intersecting triangles are not supported: They overlap in the order they were called.
```

> DRAW_BOX - 0xD3A9971CADAC7252 0xCD4D9DD5

void DRAW_BOX(float x1, float y1, float z1, float x2, float y2, float z2, int r, int g, int b, int alpha)

```
x,y,z = start pos
x2,y2,z2 = end pos

Draw's a 3D Box between the two x,y,z coords.
--------------
Keep in mind that the edges of the box do only align to the worlds base-vectors. Therefore something like rotation cannot be applied. That means this function is pretty much useless, unless you want a static unicolor box somewhere.
I recommend using a predefined function to call this.
[VB.NET]
Public Sub DrawBox(a As Vector3, b As Vector3, col As Color)
    [Function].Call(Hash.DRAW_BOX,a.X, a.Y, a.Z,b.X, b.Y, b.Z,col.R, col.G, col.B, col.A)
End Sub

[C#]
public void DrawBox(Vector3 a, Vector3 b, Color col)
{
    Function.Call(Hash.DRAW_BOX,a.X, a.Y, a.Z,b.X, b.Y, b.Z,col.R, col.G, col.B, col.A);
}
```

> 0x23BA6B0C2AD7B0D3 0xC44C2F44

void 0x23BA6B0C2AD7B0D3(BOOL p0)



> 0x1DD2139A9A20DCE8 0xBA9AD458

Any 0x1DD2139A9A20DCE8()



> 0x90A78ECAA4E78453 0xADBBA287

Any 0x90A78ECAA4E78453()



> 0x0A46AF8A78DC5E0A 0x9E553002

void 0x0A46AF8A78DC5E0A()



> 0x4862437A486F91B0 0x56C1E488

BOOL 0x4862437A486F91B0(Any* p0, Any p1, Any p2, Any p3)



> 0x1670F8D05056F257 0x226B08EA

int 0x1670F8D05056F257(Any* p0)



> 0x7FA5D82B8F58EC06 0x1F3CADB0

Any 0x7FA5D82B8F58EC06()



> 0x5B0316762AFD4A64 0xA9DC8558

Any 0x5B0316762AFD4A64()



> 0x346EF3ECAAAB149E 0x88EAF398

void 0x346EF3ECAAAB149E()



> 0xA67C35C56EB1BD9D 0x47B0C137

Any 0xA67C35C56EB1BD9D()



> 0x0D6CA79EEEBD8CA3 0x65376C9B

Any 0x0D6CA79EEEBD8CA3()



> 0xD801CC02177FA3F1 0x9CBA682A

void 0xD801CC02177FA3F1()

```
4 matches across 2 scripts.

appcamera:
called after UI::HIDE_HUD_AND_RADAR_THIS_FRAME() and before GRAPHICS::0x108F36CC();

cellphone_controller:
called after GRAPHICS::0xE9F2B68F(0, 0) and before GRAPHICS::0x108F36CC();

- Kryptus
```

> 0x1BBC135A4D25EDDE 

void 0x1BBC135A4D25EDDE(BOOL p0)



> 0x3DEC726C25A11BAC 0x3B15D33C

Any 0x3DEC726C25A11BAC(int p0)

```
1 match in 1 script. cellphone_controller.
p0 was -1. - Kryptus
```

> 0x0C0C4E81E1AC60A0 0xEC5D0317

Any 0x0C0C4E81E1AC60A0()



> 0x759650634F07B6B4 0x25D569EB

BOOL 0x759650634F07B6B4(Any p0)



> 0xCB82A0BF0E3E3265 0xCFCDC518

Any 0xCB82A0BF0E3E3265(Any p0)



> 0x6A12D88881435DCA 0x108F36CC

void 0x6A12D88881435DCA()



> 0x1072F115DAB0717E 0xE9F2B68F

void 0x1072F115DAB0717E(BOOL p0, BOOL p1)



> GET_MAXIMUM_NUMBER_OF_PHOTOS - 0x34D23450F028B0BF 0x727AA63F

int GET_MAXIMUM_NUMBER_OF_PHOTOS()

```
This function is hard-coded to always return 0.
```

> 0xDC54A7AF8B3A14EF 0x239272BD

Any 0xDC54A7AF8B3A14EF()



> 0x473151EBC762C6DA 0x21DBF0C9

Any 0x473151EBC762C6DA()

```
Returns an unknown value (dword_142317A08 in b944).
Used in appcamera.ysc and maintransition.ysc
```

> 0x2A893980E96B659A 0x199FABF0

Any 0x2A893980E96B659A(Any p0)

```
2 matches across 2 scripts. Only showed in appcamera &amp; appmedia. Both were 0. - Kryptus
```

> 0xF5BED327CEA362B1 0x596B900D

Any 0xF5BED327CEA362B1(Any p0)

```
3 matches across 3 scripts. First 2 were 0, 3rd was 1. Possibly a bool.
appcamera, appmedia, and cellphone_controller. - Kryptus
```

> 0x4AF92ACD3141D96C 0xC9EF81ED

void 0x4AF92ACD3141D96C()



> 0xE791DF1F73ED2C8B 0x9D84554C

Any 0xE791DF1F73ED2C8B(Any p0)

```
MulleDK19: This function is hard-coded to always return 0.
```

> 0xEC72C258667BE5EA 0x9C106AD9

Any 0xEC72C258667BE5EA(Any p0)

```
MulleDK19: This function is hard-coded to always return 0.
```

> 0x40AFB081F8ADD4EE 0x762E5C5F

Any 0x40AFB081F8ADD4EE(Any p0)

```
It returns two lol

li r3, 2
blr

thats all it does.

mov dword ptr [rax], 2
```

> _DRAW_LIGHT_WITH_RANGE_AND_SHADOW - 0xF49E9A9716A04595 

void _DRAW_LIGHT_WITH_RANGE_AND_SHADOW(float x, float y, float z, int r, int g, int b, float range, float intensity, float shadow)



> DRAW_LIGHT_WITH_RANGE - 0xF2A1B2771A01DBD4 0x6A396E9A

void DRAW_LIGHT_WITH_RANGE(float posX, float posY, float posZ, int colorR, int colorG, int colorB, float range, float intensity)



> DRAW_SPOT_LIGHT - 0xD0F64B265C8C8B33 0xBDBC410C

void DRAW_SPOT_LIGHT(float posX, float posY, float posZ, float dirX, float dirY, float dirZ, int colorR, int colorG, int colorB, float distance, float brightness, float roundness, float radius, float falloff)

```
Parameters:
* pos - coordinate where the spotlight is located
* dir - the direction vector the spotlight should aim at from its current position
* r,g,b - color of the spotlight
* distance - the maximum distance the light can reach
* brightness - the brightness of the light
* roundness - 'smoothness' of the circle edge
* radius - the radius size of the spotlight
* falloff - the falloff size of the light's edge (example: www.i.imgur.com/DemAWeO.jpg)

Example in C# (spotlight aims at the closest vehicle):
Vector3 myPos = Game.Player.Character.Position;
Vehicle nearest = World.GetClosestVehicle(myPos , 1000f);
Vector3 destinationCoords = nearest.Position;
Vector3 dirVector = destinationCoords - myPos;
dirVector.Normalize();
Function.Call(Hash.DRAW_SPOT_LIGHT, pos.X, pos.Y, pos.Z, dirVector.X, dirVector.Y, dirVector.Z, 255, 255, 255, 100.0f, 1f, 0.0f, 13.0f, 1f);
```

> _DRAW_SPOT_LIGHT_WITH_SHADOW - 0x5BCA583A583194DB 0x32BF9598

void _DRAW_SPOT_LIGHT_WITH_SHADOW(float posX, float posY, float posZ, float dirX, float dirY, float dirZ, int colorR, int colorG, int colorB, float distance, float brightness, float roundness, float radius, float falloff, float shadow)



> 0xC9B18B4619F48F7B 0x93628786

void 0xC9B18B4619F48F7B(float p0)



> 0xDEADC0DEDEADC0DE 

void 0xDEADC0DEDEADC0DE(Object object)

```
Only found twice in decompiled scripts. Something to do with an entity/object?

On a side note, it's very interesting how the hash for this native is 'DEADC0DE' - this is usually used as padding for initializing a buffer of some sort. I wonder if this native is actually 'dead'?

'carmod_shop.ysc', line 9520:
if (ENTITY::DOES_ENTITY_EXIST(l_324._f6)) {
    GRAPHICS::_0xDEADC0DEDEADC0DE(l_324._f6);
}

'fm_mission_controller.ysc', line 189641:
if (GAMEPLAY::IS_BIT_SET(g_1870E1._f7B64[a_0/*104*/]._f25, 28)) {
    GRAPHICS::_0xDEADC0DEDEADC0DE(NETWORK::NET_TO_OBJ(l_4064._f26A._f87[a_0/*1*/]));
    if (!GAMEPLAY::IS_BIT_SET(g_1870E1._f7B64[a_0/*104*/]._f25, 31)) {
        if (!ENTITY::IS_ENTITY_DEAD(v_7)) {
            AUDIO::PLAY_SOUND_FROM_ENTITY(-1, 'EMP_Vehicle_Hum', v_7, 'DLC_HEIST_BIOLAB_DELIVER_EMP_SOUNDS', 0, 0);
            GAMEPLAY::SET_BIT(&amp;g_1870E1._f7B64[a_0/*104*/]._f25, 31);
        }
    }
}

Console Hash: 0xC12AC47A

----------

It's most likely named UPDATE_* (like UPDATE_ENTITY_SHIT_OR_SOMETHING).
```

> DRAW_MARKER - 0x28477EC23D892089 0x48D84A02

void DRAW_MARKER(int type, float posX, float posY, float posZ, float dirX, float dirY, float dirZ, float rotX, float rotY, float rotZ, float scaleX, float scaleY, float scaleZ, int colorR, int colorG, int colorB, int alpha, BOOL bobUpAndDown, BOOL faceCamera, int p19, BOOL rotate, char* textureDict, char* textureName, BOOL drawOnEnts)

```
enum MarkerTypes
{
	MarkerTypeUpsideDownCone = 0,
	MarkerTypeVerticalCylinder = 1,
	MarkerTypeThickChevronUp = 2,
	MarkerTypeThinChevronUp = 3,
	MarkerTypeCheckeredFlagRect = 4,
	MarkerTypeCheckeredFlagCircle = 5,
	MarkerTypeVerticleCircle = 6,
	MarkerTypePlaneModel = 7,
	MarkerTypeLostMCDark = 8,
	MarkerTypeLostMCLight = 9,
	MarkerTypeNumber0 = 10,
	MarkerTypeNumber1 = 11,
	MarkerTypeNumber2 = 12,
	MarkerTypeNumber3 = 13,
	MarkerTypeNumber4 = 14,
	MarkerTypeNumber5 = 15,
	MarkerTypeNumber6 = 16,
	MarkerTypeNumber7 = 17,
	MarkerTypeNumber8 = 18,
	MarkerTypeNumber9 = 19,
	MarkerTypeChevronUpx1 = 20,
	MarkerTypeChevronUpx2 = 21,
	MarkerTypeChevronUpx3 = 22,
	MarkerTypeHorizontalCircleFat = 23,
	MarkerTypeReplayIcon = 24,
	MarkerTypeHorizontalCircleSkinny = 25,
	MarkerTypeHorizontalCircleSkinny_Arrow = 26,
	MarkerTypeHorizontalSplitArrowCircle = 27,
	MarkerTypeDebugSphere = 28,
	MarkerTypeDallorSign = 29,
	MarkerTypeHorizontalBars = 30,
	MarkerTypeWolfHead = 31
};

dirX/Y/Z represent a heading on each axis in which the marker should face, alternatively you can rotate each axis independently with rotX/Y/Z (and set dirX/Y/Z all to 0).

faceCamera - Rotates only the y-axis (the heading) towards the camera

p19 - no effect, default value in script is 2

rotate - Rotates only on the y-axis (the heading)

textureDict - Name of texture dictionary to load texture from (e.g. 'GolfPutting')

textureName - Name of texture inside dictionary to load (e.g. 'PuttingMarker')

drawOnEnts - Draws the marker onto any entities that intersect it

basically what he said, except textureDict and textureName are totally not char*, or if so, then they are always set to 0/NULL/nullptr in every script I checked, eg:

bj.c: graphics::draw_marker(6, vParam0, 0f, 0f, 1f, 0f, 0f, 0f, 4f, 4f, 4f, 240, 200, 80, iVar1, 0, 0, 2, 0, 0, 0, false);

his is what I used to draw an amber downward pointing chevron 'V', has to be redrawn every frame.  The 180 is for 180 degrees rotation around the Y axis, the 50 is alpha, assuming max is 100, but it will accept 255.

GRAPHICS::DRAW_MARKER(2, v.x, v.y, v.z + 2, 0, 0, 0, 0, 180, 0, 2, 2, 2, 255, 128, 0, 50, 0, 1, 1, 0, 0, 0, 0);


```

> CREATE_CHECKPOINT - 0x0134F0835AB6BFCB 0xF541B690

int CREATE_CHECKPOINT(int type, float posX1, float posY1, float posZ1, float posX2, float posY2, float posZ2, float radius, int colorR, int colorG, int colorB, int alpha, int reserved)

```
Creates a checkpoint. Returns the handle of the checkpoint.

Parameters:
* type - The type of checkpoint to create. See below for a list of checkpoint types.
* pos1 - The position of the checkpoint.
* pos2 - The position of the next checkpoint to point to.
* radius - The radius of the checkpoint.
* color - The color of the checkpoint.
* reserved - Special parameter, see below for details. Usually set to 0 in the scripts.

Checkpoint types:
0-4---------Cylinder: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker
5-9---------Cylinder: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker
10-14-------Ring: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker
15-19-------1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker      
20-24-------Cylinder: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker 
25-29-------Cylinder: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker    
30-34-------Cylinder: 1 arrow, 2 arrow, 3 arrows, CycleArrow, Checker 
35-38-------Ring: Airplane Up, Left, Right, UpsideDown
39----------?
40----------Ring: just a ring
41----------?
42-44-------Cylinder w/ number (uses 'reserved' parameter)
45-47-------Cylinder no arrow or number

If using type 42-44, reserved sets number / number and shape to display

0-99------------Just numbers (0-99)
100-109-----------------Arrow (0-9)
110-119------------Two arrows (0-9)
120-129----------Three arrows (0-9)
130-139----------------Circle (0-9)
140-149------------CycleArrow (0-9)
150-159----------------Circle (0-9)
160-169----Circle  w/ pointer (0-9)
170-179-------Perforated ring (0-9)
180-189----------------Sphere (0-9)
```

> 0x4B5B4DA5D79F1943 0x80151CCF

void 0x4B5B4DA5D79F1943(int checkpoint, float p0)

```
p0 - Scale? Looks to be a normalized value (0.0 - 1.0)

offroad_races.c4, line ~67407:
a_3._f7 = GRAPHICS::CREATE_CHECKPOINT(v_D, v_A, a_4, a_7, v_E, v_F, v_10, sub_62b2(v_A, 220, 255), 0);
UI::GET_HUD_COLOUR(134, &amp;v_E, &amp;v_F, &amp;v_10, &amp;v_11);
GRAPHICS::_SET_CHECKPOINT_ICON_RGBA(a_3._f7, v_E, v_F, v_10, sub_62b2(v_A, 70, 210));
GRAPHICS::_4B5B4DA5D79F1943(a_3._f7, 0.95);
GRAPHICS::SET_CHECKPOINT_CYLINDER_HEIGHT(a_3._f7, 4.0, 4.0, 100.0);

```

> SET_CHECKPOINT_CYLINDER_HEIGHT - 0x2707AAE9D9297D89 0xFF0F9B22

void SET_CHECKPOINT_CYLINDER_HEIGHT(int checkpoint, float nearHeight, float farHeight, float radius)

```
Sets the cylinder height of the checkpoint.

Parameters:
* nearHeight - The height of the checkpoint when inside of the radius.
* farHeight - The height of the checkpoint when outside of the radius.
* radius - The radius of the checkpoint.

- Aaron
```

> SET_CHECKPOINT_RGBA - 0x7167371E8AD747F7 0xEF9C8CB3

void SET_CHECKPOINT_RGBA(int checkpoint, int r, int g, int b, int alpha)

```
Sets the checkpoint color.
```

> _SET_CHECKPOINT_ICON_RGBA - 0xB9EA40907C680580 0xA5456DBB

void _SET_CHECKPOINT_ICON_RGBA(int checkpoint, int r, int g, int b, int alpha)

```
Sets the checkpoint icon color.
```

> 0xF51D36185993515D 0x20EABD0F

void 0xF51D36185993515D(int checkpoint, float posX, float posY, float posZ, float unkX, float unkY, float unkZ)

```
This does not move an existing checkpoint... so wtf.
```

> 0x615D3925E87A3B26 0x1E3A3126

void 0x615D3925E87A3B26(int checkpoint)

```
Unknown. Called after creating a checkpoint (type: 51) in the creators.
```

> DELETE_CHECKPOINT - 0xF5ED37F54CD4D52E 0xB66CF3CA

void DELETE_CHECKPOINT(int checkpoint)



> 0x22A249A53034450A 0x932FDB81

void 0x22A249A53034450A(BOOL p0)



> 0xDC459CFA0CCE245B 0x7E946E87

void 0xDC459CFA0CCE245B(BOOL p0)



> REQUEST_STREAMED_TEXTURE_DICT - 0xDFA2EF8E04127DD5 0x4C9B035F

void REQUEST_STREAMED_TEXTURE_DICT(char* textureDict, BOOL p1)

```
last param isnt a toggle
```

> HAS_STREAMED_TEXTURE_DICT_LOADED - 0x0145F696AAAAD2E4 0x3F436EEF

BOOL HAS_STREAMED_TEXTURE_DICT_LOADED(char* textureDict)



> SET_STREAMED_TEXTURE_DICT_AS_NO_LONGER_NEEDED - 0xBE2CACCF5A8AA805 0xF07DDA38

void SET_STREAMED_TEXTURE_DICT_AS_NO_LONGER_NEEDED(char* textureDict)



> DRAW_RECT - 0x3A618A217E5154F0 0xDD2BFC77

void DRAW_RECT(float x, float y, float width, float height, int r, int g, int b, int a)

```
Draws a rectangle on the screen.

-x: The relative X point of the center of the rectangle. (0.0-1.0, 0.0 is the left edge of the screen, 1.0 is the right edge of the screen)

-y: The relative Y point of the center of the rectangle. (0.0-1.0, 0.0 is the top edge of the screen, 1.0 is the bottom edge of the screen)

-width: The relative width of the rectangle. (0.0-1.0, 1.0 means the whole screen width)

-height: The relative height of the rectangle. (0.0-1.0, 1.0 means the whole screen height)

-R: Red part of the color. (0-255)

-G: Green part of the color. (0-255)

-B: Blue part of the color. (0-255)

-A: Alpha part of the color. (0-255, 0 means totally transparent, 255 means totall opaque)

The total number of rectangles to be drawn in one frame is apparently limited to 399.

```

> 0xC6372ECD45D73BCD 0xF8FBCC25

void 0xC6372ECD45D73BCD(BOOL p0)



> _SET_2D_LAYER - 0x61BB1D9B3A95D802 0xADF81D24

void _SET_2D_LAYER(int layer)

```
Called before drawing stuff.

Examples:
GRAPHICS::_61BB1D9B3A95D802(7);
GRAPHICS::DRAW_RECT(0.5, 0.5, 3.0, 3.0, v_4, v_5, v_6, a_0._f172, 0);

GRAPHICS::_61BB1D9B3A95D802(1);
GRAPHICS::DRAW_RECT(0.5, 0.5, 1.5, 1.5, 0, 0, 0, 255, 0);

Appears to be the layer it's drawn on 

```

> _SET_SCREEN_DRAW_POSITION - 0xB8A850F20A067EB6 0x228A2598

void _SET_SCREEN_DRAW_POSITION(int x, int y)

```
Seems to move all the drawn text on the screen to given coordinates.
It also removed all the drawn sprites of my screen so not to sure what the exact function is.

```

> 0xE3A3DB414A373DAB 0x3FE33BD6

void 0xE3A3DB414A373DAB()



> 0xF5A2C681787E579D 0x76C641E4

void 0xF5A2C681787E579D(float p0, float p1, float p2, float p3)



> 0x6DD8F5AA635EB4B2 

void 0x6DD8F5AA635EB4B2(float p0, float p1, Any* p2, Any* p3)



> GET_SAFE_ZONE_SIZE - 0xBAF107B6BB2C97F0 0x3F0D1A6F

float GET_SAFE_ZONE_SIZE()

```
Gets the scale of safe zone. if the safe zone size scale is max, it will return 1.0.
```

> DRAW_SPRITE - 0xE7FFAE5EBF23D890 0x1FEC16B0

void DRAW_SPRITE(char* textureDict, char* textureName, float screenX, float screenY, float scaleX, float scaleY, float heading, int colorR, int colorG, int colorB, int alpha)

```
Draws a 2D sprite on the screen.

Parameters:
textureDict - Name of texture dictionary to load texture from (e.g. 'CommonMenu', 'MPWeaponsCommon', etc.)

textureName - Name of texture to load from texture dictionary (e.g. 'last_team_standing_icon', 'tennis_icon', etc.)

screenX/Y - Screen offset (0.5 = center)
scaleX/Y - Texture scaling. Negative values can be used to flip the texture on that axis. (0.5 = half)

heading - Texture rotation in degrees (default = 0.0) positive is clockwise, measured in degrees

red,green,blue - Sprite color (default = 255/255/255)

alpha - if set to '2' it will grab all entitys in the game on call

alpha - why would it do that and where would it output the entites. And shouldn't it the alpha color for this param?
```

> ADD_ENTITY_ICON - 0x9CD43EEE12BF4DD0 0xF3027D21

Any ADD_ENTITY_ICON(Entity entity, char* icon)

```
Example:
GRAPHICS::ADD_ENTITY_ICON(a_0, 'MP_Arrow');

I tried this and nothing happened...
```

> SET_ENTITY_ICON_VISIBILITY - 0xE0E8BEECCA96BA31 0xD1D2FD52

void SET_ENTITY_ICON_VISIBILITY(Entity entity, BOOL toggle)



> SET_ENTITY_ICON_COLOR - 0x1D5F595CCAE2E238 0x6EE1E946

void SET_ENTITY_ICON_COLOR(Entity entity, int r, int g, int b, int alpha)



> SET_DRAW_ORIGIN - 0xAA0008F3BBB8F416 0xE10198D5

void SET_DRAW_ORIGIN(float x, float y, float z, Any p3)

```
Sets the on-screen drawing origin for draw-functions (which is normally x=0,y=0 in the upper left corner of the screen) to a world coordinate.
From now on, the screen coordinate which displays the given world coordinate on the screen is seen as x=0,y=0.

Example in C#:
Vector3 boneCoord = somePed.GetBoneCoord(Bone.SKEL_Head);
Function.Call(Hash.SET_DRAW_ORIGIN, boneCoord.X, boneCoord.Y, boneCoord.Z, 0);
Function.Call(Hash.DRAW_SPRITE, 'helicopterhud', 'hud_corner', -0.01, -0.015, 0.013, 0.013, 0.0, 255, 0, 0, 200);
Function.Call(Hash.DRAW_SPRITE, 'helicopterhud', 'hud_corner', 0.01, -0.015, 0.013, 0.013, 90.0, 255, 0, 0, 200);
Function.Call(Hash.DRAW_SPRITE, 'helicopterhud', 'hud_corner', -0.01, 0.015, 0.013, 0.013, 270.0, 255, 0, 0, 200);
Function.Call(Hash.DRAW_SPRITE, 'helicopterhud', 'hud_corner', 0.01, 0.015, 0.013, 0.013, 180.0, 255, 0, 0, 200);
Function.Call(Hash.CLEAR_DRAW_ORIGIN);

Result: www11.pic-upload.de/19.06.15/bkqohvil2uao.jpg
If the pedestrian starts walking around now, the sprites are always around her head, no matter where the head is displayed on the screen.

This function also effects the drawing of texts and other UI-elements.
The effect can be reset by calling GRAPHICS::CLEAR_DRAW_ORIGIN().
```

> CLEAR_DRAW_ORIGIN - 0xFF0B610F6BE0D7AF 0xDD76B263

void CLEAR_DRAW_ORIGIN()

```
Resets the screen's draw-origin which was changed by the function GRAPHICS::SET_DRAW_ORIGIN(...) back to x=0,y=0.

See GRAPHICS::SET_DRAW_ORIGIN(...) for further information.
```

> ATTACH_TV_AUDIO_TO_ENTITY - 0x845BAD77CC770633 0x784944DB

void ATTACH_TV_AUDIO_TO_ENTITY(Entity entity)

```
Might be more appropriate in AUDIO?
```

> SET_TV_AUDIO_FRONTEND - 0x113D2C5DC57E1774 0x2E0DFA35

void SET_TV_AUDIO_FRONTEND(BOOL toggle)

```
Might be more appropriate in AUDIO?

Rockstar made it like this.

Probably changes tvs from being a 3d audio to being 'global' audio
```

> LOAD_MOVIE_MESH_SET - 0xB66064452270E8F1 0x9627905C

int LOAD_MOVIE_MESH_SET(char* movieMeshSetName)



> RELEASE_MOVIE_MESH_SET - 0xEB119AA014E89183 0x4FA5501D

void RELEASE_MOVIE_MESH_SET(int movieMeshSet)



> 0x9B6E70C5CEEF4EEB 0x9D5D9B38

Any 0x9B6E70C5CEEF4EEB(Any p0)



> GET_SCREEN_RESOLUTION - 0x888D57E407E63624 0x29F3572F

void GET_SCREEN_RESOLUTION(int* x, int* y)

```
int screenresx,screenresy;
GET_SCREEN_RESOLUTION(&amp;screenresx,&amp;screenresy);
```

> _GET_SCREEN_ACTIVE_RESOLUTION - 0x873C9F3104101DD3 

void _GET_SCREEN_ACTIVE_RESOLUTION(int* x, int* y)

```
Returns current screen resolution.
```

> _GET_SCREEN_ASPECT_RATIO - 0xF1307EF624A80D87 

float _GET_SCREEN_ASPECT_RATIO(BOOL b)



> 0xB2EBE8CBC58B90E9 

Any 0xB2EBE8CBC58B90E9()



> GET_IS_WIDESCREEN - 0x30CF4BDA4FCB1905 0xEC717AEF

BOOL GET_IS_WIDESCREEN()

```
Setting Aspect Ratio Manually in game will return:

false - for Narrow format Aspect Ratios (3:2, 4:3, 5:4, etc. )
true - for Wide format Aspect Ratios (5:3, 16:9, 16:10, etc. )

Setting Aspect Ratio to 'Auto' in game will return 'false' or 'true' based on the actual set Resolution Ratio.
```

> GET_IS_HIDEF - 0x84ED31191CC5D2C9 0x1C340359

BOOL GET_IS_HIDEF()

```
false = Any resolution &lt; 1280x720
true = Any resolution &gt;= 1280x720
```

> 0xEFABC7722293DA7C 

void 0xEFABC7722293DA7C()



> SET_NIGHTVISION - 0x18F621F7A5B1F85D 0xD1E5565F

void SET_NIGHTVISION(BOOL toggle)

```
Enables Night Vision.

Example:
C#: Function.Call(Hash.SET_NIGHTVISION, true);
C++: GRAPHICS::SET_NIGHTVISION(true);

BOOL toggle:
true = turns night vision on for your player.
false = turns night vision off for your player.
```

> 0x35FB78DC42B7BD21 

Any 0x35FB78DC42B7BD21()



> _IS_NIGHTVISION_INACTIVE - 0x2202A3F42C8E5F79 0x62619061

BOOL _IS_NIGHTVISION_INACTIVE()

```
Gets whether or not NIGHTVISION is INactive.

Note:  When nightvision is actually active, this native will return FALSE!
```

> 0xEF398BEEE4EF45F9 

void 0xEF398BEEE4EF45F9(BOOL p0)



> SET_NOISEOVERIDE - 0xE787BF1C5CF823C9 0xD576F5DD

void SET_NOISEOVERIDE(BOOL toggle)



> SET_NOISINESSOVERIDE - 0xCB6A7C3BB17A0C67 0x046B62D9

void SET_NOISINESSOVERIDE(float value)



> _WORLD3D_TO_SCREEN2D - 0x34E82F05DF2974F5 0x1F950E4B

BOOL _WORLD3D_TO_SCREEN2D(float worldX, float worldY, float worldZ, float* screenX, float* screenY)

```
Convert a world coordinate into its relative screen coordinate.  (WorldToScreen)

Returns a boolean; whether or not the operation was successful. It will return false if the coordinates given are not visible to the rendering camera.


For .NET users...

VB:
Public Shared Function World3DToScreen2d(pos as vector3) As Vector2

        Dim x2dp, y2dp As New Native.OutputArgument

        Native.Function.Call(Of Boolean)(Native.Hash.GET_SCREEN_COORD_FROM_WORLD_COORD , pos.x, pos.y, pos.z, x2dp, y2dp)
        Return New Vector2(x2dp.GetResult(Of Single), y2dp.GetResult(Of Single))
      
    End Function

C#:
Vector2 World3DToScreen2d(Vector3 pos)
    {
        var x2dp = new OutputArgument();
        var y2dp = new OutputArgument();

        Function.Call&lt;bool&gt;(Hash.GET_SCREEN_COORD_FROM_WORLD_COORD , pos.X, pos.Y, pos.Z, x2dp, y2dp);
        return new Vector2(x2dp.GetResult&lt;float&gt;(), y2dp.GetResult&lt;float&gt;());
    }
//USE VERY SMALL VALUES FOR THE SCALE OF RECTS/TEXT because it is dramatically larger on screen than in 3D, e.g '0.05' small.

Used to be called _WORLD3D_TO_SCREEN2D

I thought we lost you from the scene forever. It does seem however that calling SET_DRAW_ORIGIN then your natives, then ending it. Seems to work better for certain things such as keeping boxes around people for a predator missile e.g.
```

> GET_TEXTURE_RESOLUTION - 0x35736EE65BD00C11 0x096DAA4D

Vector3 GET_TEXTURE_RESOLUTION(char* textureDict, char* textureName)

```
Returns the texture resolution of the passed texture dict+name.

Note: Most texture resolutions are doubled compared to the console version of the game.
```

> 0xE2892E7E55D7073A 0x455F1084

void 0xE2892E7E55D7073A(float p0)



> SET_FLASH - 0x0AB84296FED9CFC6 0x7E55A1EE

void SET_FLASH(float p0, float p1, float fadeIn, float duration, float fadeOut)

```
Purpose of p0 and p1 unknown.
```

> 0x3669F1B198DCAA4F 0x0DCC0B8B

void 0x3669F1B198DCAA4F()



> _SET_BLACKOUT - 0x1268615ACE24D504 0xAA2A0EAF

void _SET_BLACKOUT(BOOL enable)

```
Disables all emissive textures and lights like city lights, car lights, cop car lights. Particles still emit light

Used in Humane Labs Heist for EMP.
```

> 0xC35A6D07C93802B2 

void 0xC35A6D07C93802B2()



> CREATE_TRACKED_POINT - 0xE2C9439ED45DEA60 0x3129C31A

Object CREATE_TRACKED_POINT()

```
Creates a tracked point, useful for checking the visibility of a 3D point on screen.
```

> SET_TRACKED_POINT_INFO - 0x164ECBB3CF750CB0 0x28689AA4

Any SET_TRACKED_POINT_INFO(Object point, float x, float y, float z, float radius)



> IS_TRACKED_POINT_VISIBLE - 0xC45CCDAAC9221CA8 0x0BFC4F64

BOOL IS_TRACKED_POINT_VISIBLE(Object point)



> DESTROY_TRACKED_POINT - 0xB25DC90BAD56CA42 0x14AC675F

void DESTROY_TRACKED_POINT(Object point)



> 0xBE197EAA669238F4 

Any 0xBE197EAA669238F4(Any p0, Any p1, Any p2, Any p3)

```
This function is hard-coded to always return 0.
```

> 0x61F95E5BB3E0A8C6 

void 0x61F95E5BB3E0A8C6(Any p0)



> 0xAE51BC858F32BA66 

void 0xAE51BC858F32BA66(Any p0, float p1, float p2, float p3, float p4)



> 0x649C97D52332341A 

void 0x649C97D52332341A(Any p0)



> 0x2C42340F916C5930 

Any 0x2C42340F916C5930(Any p0)



> 0x14FC5833464340A8 

void 0x14FC5833464340A8()



> 0x0218BA067D249DEA 

void 0x0218BA067D249DEA()



> 0x1612C45F9E3E0D44 

void 0x1612C45F9E3E0D44()



> 0x5DEBD9C4DC995692 

void 0x5DEBD9C4DC995692()



> 0x6D955F6A9E0295B1 

void 0x6D955F6A9E0295B1(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)



> 0x302C91AB2D477F7E 

void 0x302C91AB2D477F7E()



> 0x03FC694AE06C5A20 0x48F16186

void 0x03FC694AE06C5A20()



> 0xD2936CAB8B58FCBD 

void 0xD2936CAB8B58FCBD(Any p0, BOOL p1, float p2, float p3, float p4, float p5, BOOL p6, float p7)



> 0x5F0F3F56635809EF 0x13D4ABC0

void 0x5F0F3F56635809EF(float p0)



> 0x5E9DAF5A20F15908 0xD2157428

void 0x5E9DAF5A20F15908(float p0)



> 0x36F6626459D91457 0xC07C64C9

void 0x36F6626459D91457(float p0)



> _SET_FAR_SHADOWS_SUPPRESSED - 0x80ECBC0C856D3B0B 0xFE903D0F

void _SET_FAR_SHADOWS_SUPPRESSED(BOOL toggle)

```
When this is set to ON, shadows only draw as you get nearer.

When OFF, they draw from a further distance.
```

> 0x25FC3E33A31AD0C9 

void 0x25FC3E33A31AD0C9(BOOL p0)



> 0xB11D94BC55F41932 0xDE10BA1F

void 0xB11D94BC55F41932(char* p0)

```
Has something to do with player switch.

Only possible values:
- 'CSM_ST_BOX3x3'
- 'CSM_ST_BOX4x4'
```

> 0x27CB772218215325 

void 0x27CB772218215325()



> 0x6DDBF9DFFC4AC080 0x9F470BE3

void 0x6DDBF9DFFC4AC080(BOOL p0)



> 0xD39D13C9FEBF0511 0x4A124267

void 0xD39D13C9FEBF0511(BOOL p0)



> 0x02AC28F3A01FA04A 0xB19B2764

Any 0x02AC28F3A01FA04A(float p0)



> 0x0AE73D8DF3A762B2 0x342FA2B4

void 0x0AE73D8DF3A762B2(BOOL p0)



> 0xA51C4B86B71652AE 0x5D3BFFC9

void 0xA51C4B86B71652AE(BOOL p0)



> 0x312342E1A4874F3F 0xD9653728

void 0x312342E1A4874F3F(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, BOOL p8)

```
p8 seems to always be false. - Kryptus
```

> 0x2485D34E50A22E84 0x72BA8A14

void 0x2485D34E50A22E84(float p0, float p1, float p2)



> 0x12995F2E53FFA601 0x804F444C

void 0x12995F2E53FFA601(int p0, int p1, int p2, int p3, int p4, int p5, int p6, int p7, int p8, int p9, int p10, int p11)

```
Only used in the golf and golf_mp script
```

> 0xDBAA5EC848BA2D46 0xBB1A1294

void 0xDBAA5EC848BA2D46(Any p0, Any p1)



> 0xC0416B061F2B7E5E 0x1A1A72EF

void 0xC0416B061F2B7E5E(BOOL p0)



> 0xB1BB03742917A5D6 0x3BB12B75

void 0xB1BB03742917A5D6(int type, float xPos, float yPos, float zPos, float p4, int r, int g, int b, int alpha)

```
12 matches across 4 scripts. All 4 scripts were job creators.

type ranged from 0 - 2.
p4 was always 0.2f. Likely scale.
assuming p5 - p8 is RGBA, the graphic is always yellow (255, 255, 0, 255).

Tested but noticed nothing.
```

> 0x9CFDD90B2B844BF7 0x4EA70FB4

void 0x9CFDD90B2B844BF7(float p0, float p1, float p2, float p3, float p4)

```
Only appeared in Golf &amp; Golf_mp. Parameters were all ptrs. - Kryptus
```

> 0x06F761EA47C1D3ED 0x0D830DC7

void 0x06F761EA47C1D3ED(BOOL p0)



> 0xA4819F5E23E2FFAD 0xA08B46AD

Any 0xA4819F5E23E2FFAD()



> 0xA4664972A9B8F8BA 0xECD470F0

int 0xA4664972A9B8F8BA(Any p0)



> SET_SEETHROUGH - 0x7E08924259E08CE0 0x74D4995C

void SET_SEETHROUGH(BOOL toggle)

```
Toggles Heatvision on/off.
```

> _IS_SEETHROUGH_ACTIVE - 0x44B80ABAB9D80BD3 0x1FE547F2

BOOL _IS_SEETHROUGH_ACTIVE()

```
Returns whether or not SEETHROUGH is active.
```

> 0xD7D0B00177485411 0x654F0287

void 0xD7D0B00177485411(Any p0, float p1)



> 0xB3C641F3630BF6DA 0xF6B837F0

void 0xB3C641F3630BF6DA(float p0)



> 0xE59343E9E96529E7 0xD906A3A9

Any 0xE59343E9E96529E7()



> 0xE63D7C6EECECB66B 0xD34A6CBA

void 0xE63D7C6EECECB66B(BOOL p0)



> 0xE3E2C1B4C59DBC77 0xD8CC7221

void 0xE3E2C1B4C59DBC77(Any p0)



> _TRANSITION_TO_BLURRED - 0xA328A24AAA6B7FDC 0x5604B890

BOOL _TRANSITION_TO_BLURRED(float transitionTime)

```
time in ms to transition to fully blurred screen
```

> _TRANSITION_FROM_BLURRED - 0xEFACC8AEF94430D5 0x46617502

BOOL _TRANSITION_FROM_BLURRED(float transitionTime)

```
time in ms to transition from fully blurred to normal
```

> 0xDE81239437E8C5A8 0xDB7AECDA

void 0xDE81239437E8C5A8()



> IS_PARTICLE_FX_DELAYED_BLINK - 0x5CCABFFCA31DDE33 0xEA432A94

float IS_PARTICLE_FX_DELAYED_BLINK()



> 0x7B226C785A52A0A9 0x926B8734

Any 0x7B226C785A52A0A9()



> _SET_FROZEN_RENDERING_DISABLED - 0xDFC252D8A3E15AB7 0x30ADE541

void _SET_FROZEN_RENDERING_DISABLED(BOOL enabled)



> 0xEB3DAC2C86001E5E 

Any 0xEB3DAC2C86001E5E()



> 0xE1C8709406F2C41C 0x0113EAE4

void 0xE1C8709406F2C41C()



> 0x851CD923176EBA7C 0xDCBA251B

void 0x851CD923176EBA7C()



> 0xBA3D65906822BED5 0x513D444B

void 0xBA3D65906822BED5(BOOL p0, BOOL p1, float p2, float p3, float p4, float p5)

```
Every p2 - p5 occurrence was 0f. - Kryptus
```

> 0x7AC24EAB6D74118D 0xB2410EAB

BOOL 0x7AC24EAB6D74118D(BOOL p0)



> 0xBCEDB009461DA156 0x5AB94128

Any 0xBCEDB009461DA156()



> 0x27FEB5254759CDE3 0xD63FCB3E

BOOL 0x27FEB5254759CDE3(char* textureDict, BOOL p1)



> START_PARTICLE_FX_NON_LOOPED_AT_COORD - 0x25129531F77B9ED3 0xDD79D679

BOOL START_PARTICLE_FX_NON_LOOPED_AT_COORD(char* effectName, float xPos, float yPos, float zPos, float xRot, float yRot, float zRot, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
GRAPHICS::START_PARTICLE_FX_NON_LOOPED_AT_COORD('scr_paleto_roof_impact', -140.8576f, 6420.789f, 41.1391f, 0f, 0f, 267.3957f, 0x3F800000, 0, 0, 0);

Axis - Invert Axis Flags

list: pastebin.com/N9unUFWY


-------------------------------------------------------------------

Alright, So, I will try to explain a bit here, since, myself was confused with the default explanation, and this is because, I am really a 'noob' when it comes to programming.

but somehow after a lot of research, try and fail method I got it to work. So I will try to explain as much I could.

C#

Function.Call&lt;int&gt;(Hash.START_PARTICLE_FX_NON_LOOPED_AT_COORD, = you are calling this function.

char *effectname = This is an in-game effect name, for e.g. 'scr_fbi4_trucks_crash' is used to give the effects when truck crashes etc

float x, y, z pos = this one is Simple, you just have to declare, where do you want this effect to take place at, so declare the ordinates

float xrot, yrot, zrot = Again simple? just mention the value in case if you want the effect to rotate.

float scale = is declare the scale of the effect, this may vary as per the effects for e.g 1.0f

bool xaxis, yaxis, zaxis = To bool the axis values.

So here is final example - 

Function.Call&lt;int&gt;(Hash.START_PARTICLE_FX_NON_LOOPED_AT_COORD, 'scr_fbi4_trucks_crash', GTA.Game.Player.Character.Position.X, GTA.Game.Player.Character.Position.Y, GTA.Game.Player.Character.Position.Z + 4f, 0, 0, 0, 5.5f, 0, 0, 0);

Hope this helps.
```

> _START_PARTICLE_FX_NON_LOOPED_AT_COORD_2 - 0xF56B8137DF10135D 0x633F8C48

BOOL _START_PARTICLE_FX_NON_LOOPED_AT_COORD_2(char* effectName, float xPos, float yPos, float zPos, float xRot, float yRot, float zRot, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
network fx
```

> START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE - 0x0E7E72961BA18619 0x53DAEF4E

BOOL START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE(char* effectName, Ped ped, float offsetX, float offsetY, float offsetZ, float rotX, float rotY, float rotZ, int boneIndex, float scale, BOOL axisX, BOOL axisY, BOOL axisZ)

```
GRAPHICS::START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE('scr_sh_bong_smoke', PLAYER::PLAYER_PED_ID(), -0.025f, 0.13f, 0f, 0f, 0f, 0f, 31086, 0x3F800000, 0, 0, 0);

Axis - Invert Axis Flags

list: pastebin.com/N9unUFWY
```

> _START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE_2 - 0xA41B6A43642AC2CF 0x161780C1

BOOL _START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE_2(char* effectName, Ped ped, float offsetX, float offsetY, float offsetZ, float rotX, float rotY, float rotZ, int boneIndex, float scale, BOOL axisX, BOOL axisY, BOOL axisZ)

```
network fx
```

> START_PARTICLE_FX_NON_LOOPED_ON_ENTITY - 0x0D53A3B8DA0809D2 0x9604DAD4

BOOL START_PARTICLE_FX_NON_LOOPED_ON_ENTITY(char* effectName, Entity entity, float offsetX, float offsetY, float offsetZ, float rotX, float rotY, float rotZ, float scale, BOOL axisX, BOOL axisY, BOOL axisZ)

```
Starts a particle effect on an entity for example your player.
List: pastebin.com/N9unUFWY

Example:
C#:
Function.Call(Hash.REQUEST_NAMED_PTFX_ASSET, 'scr_rcbarry2');                     Function.Call(Hash._SET_PTFX_ASSET_NEXT_CALL, 'scr_rcbarry2');                             Function.Call(Hash.START_PARTICLE_FX_NON_LOOPED_ON_ENTITY, 'scr_clown_appears', Game.Player.Character, 0.0, 0.0, -0.5, 0.0, 0.0, 0.0, 1.0, false, false, false);

Internally this calls the same function as GRAPHICS::START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE
however it uses -1 for the specified bone index, so it should be possible to start a non looped fx on an entity bone using that native

-can confirm START_PARTICLE_FX_NON_LOOPED_ON_PED_BONE does NOT work on vehicle bones.
```

> _START_PARTICLE_FX_NON_LOOPED_ON_ENTITY_2 - 0xC95EB1DB6E92113D 

BOOL _START_PARTICLE_FX_NON_LOOPED_ON_ENTITY_2(char* effectName, Entity entity, float offsetX, float offsetY, float offsetZ, float rotX, float rotY, float rotZ, float scale, BOOL axisX, BOOL axisY, BOOL axisZ)

```
Console hash: 0x469A2B4A

network fx
```

> SET_PARTICLE_FX_NON_LOOPED_COLOUR - 0x26143A59EF48B262 0x7B689E20

void SET_PARTICLE_FX_NON_LOOPED_COLOUR(float r, float g, float b)

```
only works on some fx's
```

> SET_PARTICLE_FX_NON_LOOPED_ALPHA - 0x77168D722C58B2FC 0x497EAFF2

void SET_PARTICLE_FX_NON_LOOPED_ALPHA(float alpha)

```
Usage example for C#:

        Function.Call(Hash.SET_PARTICLE_FX_NON_LOOPED_ALPHA, new InputArgument[] { 0.1f });

Note: the argument alpha ranges from 0.0f-1.0f !
```

> 0x8CDE909A0370BB3A 

void 0x8CDE909A0370BB3A(BOOL p0)

```
console hash: 0x19EC0001
```

> START_PARTICLE_FX_LOOPED_AT_COORD - 0xE184F4F0DC5910E7 0xD348E3E6

int START_PARTICLE_FX_LOOPED_AT_COORD(char* effectName, float x, float y, float z, float xRot, float yRot, float zRot, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis, BOOL p11)

```
GRAPHICS::START_PARTICLE_FX_LOOPED_AT_COORD('scr_fbi_falling_debris', 93.7743f, -749.4572f, 70.86904f, 0f, 0f, 0f, 0x3F800000, 0, 0, 0, 0)


```

> START_PARTICLE_FX_LOOPED_ON_PED_BONE - 0xF28DA9F38CD1787C 0xF8FC196F

int START_PARTICLE_FX_LOOPED_ON_PED_BONE(char* effectName, Ped ped, float xOffset, float yOffset, float zOffset, float xRot, float yRot, float zRot, int boneIndex, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)



> START_PARTICLE_FX_LOOPED_ON_ENTITY - 0x1AE42C1660FD6517 0x0D06FF62

int START_PARTICLE_FX_LOOPED_ON_ENTITY(char* effectName, Entity entity, float xOffset, float yOffset, float zOffset, float xRot, float yRot, float zRot, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
list: pastebin.com/N9unUFWY
```

> _START_PARTICLE_FX_LOOPED_ON_ENTITY_BONE - 0xC6EB449E33977F0B 

int _START_PARTICLE_FX_LOOPED_ON_ENTITY_BONE(char* effectName, Entity entity, float xOffset, float yOffset, float zOffset, float xRot, float yRot, float zRot, int boneIndex, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
Console Hash: 0x23BF0F9B
```

> _START_PARTICLE_FX_LOOPED_ON_ENTITY_2 - 0x6F60E89A7B64EE1D 0x110752B2

int _START_PARTICLE_FX_LOOPED_ON_ENTITY_2(char* effectName, Entity entity, float xOffset, float yOffset, float zOffset, float xRot, float yRot, float zRot, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
network fx
```

> _START_PARTICLE_FX_LOOPED_ON_ENTITY_BONE_2 - 0xDDE23F30CC5A0F03 

int _START_PARTICLE_FX_LOOPED_ON_ENTITY_BONE_2(char* effectName, Entity entity, float xOffset, float yOffset, float zOffset, float xRot, float yRot, float zRot, int boneIndex, float scale, BOOL xAxis, BOOL yAxis, BOOL zAxis)

```
Console Hash: 0xF478EFCF

network fx
```

> STOP_PARTICLE_FX_LOOPED - 0x8F75998877616996 0xD245455B

void STOP_PARTICLE_FX_LOOPED(int ptfxHandle, BOOL p1)

```
p1 is always 0 in the native scripts
```

> REMOVE_PARTICLE_FX - 0xC401503DFE8D53CF 0x6BA48C7E

void REMOVE_PARTICLE_FX(int ptfxHandle, BOOL p1)



> REMOVE_PARTICLE_FX_FROM_ENTITY - 0xB8FEAEEBCC127425 0xCEDE52E9

void REMOVE_PARTICLE_FX_FROM_ENTITY(Entity entity)



> REMOVE_PARTICLE_FX_IN_RANGE - 0xDD19FA1C6D657305 0x7EB8F275

void REMOVE_PARTICLE_FX_IN_RANGE(float X, float Y, float Z, float radius)



> DOES_PARTICLE_FX_LOOPED_EXIST - 0x74AFEF0D2E1E409B 0xCBF91D2A

BOOL DOES_PARTICLE_FX_LOOPED_EXIST(int ptfxHandle)



> SET_PARTICLE_FX_LOOPED_OFFSETS - 0xF7DDEBEC43483C43 0x641F7790

void SET_PARTICLE_FX_LOOPED_OFFSETS(int ptfxHandle, float x, float y, float z, float rotX, float rotY, float rotZ)



> SET_PARTICLE_FX_LOOPED_EVOLUTION - 0x5F0C4B5B1C393BE2 0x1CBC1373

void SET_PARTICLE_FX_LOOPED_EVOLUTION(int ptfxHandle, char* propertyName, float amount, BOOL Id)



> SET_PARTICLE_FX_LOOPED_COLOUR - 0x7F8F65877F88783B 0x5219D530

void SET_PARTICLE_FX_LOOPED_COLOUR(int ptfxHandle, float r, float g, float b, BOOL p4)

```
only works on some fx's

p4 = 0
```

> SET_PARTICLE_FX_LOOPED_ALPHA - 0x726845132380142E 0x5ED49BE1

void SET_PARTICLE_FX_LOOPED_ALPHA(int ptfxHandle, float alpha)



> SET_PARTICLE_FX_LOOPED_SCALE - 0xB44250AAA456492D 0x099B8B49

void SET_PARTICLE_FX_LOOPED_SCALE(int ptfxHandle, float scale)



> _SET_PARTICLE_FX_LOOPED_RANGE - 0xDCB194B85EF7B541 0x233DE879

void _SET_PARTICLE_FX_LOOPED_RANGE(int ptfxHandle, float range)



> SET_PARTICLE_FX_CAM_INSIDE_VEHICLE - 0xEEC4047028426510 0x19EC0001

void SET_PARTICLE_FX_CAM_INSIDE_VEHICLE(BOOL p0)



> SET_PARTICLE_FX_CAM_INSIDE_NONPLAYER_VEHICLE - 0xACEE6F360FC1F6B6 0x6B125A02

void SET_PARTICLE_FX_CAM_INSIDE_NONPLAYER_VEHICLE(Any p0, BOOL p1)



> SET_PARTICLE_FX_SHOOTOUT_BOAT - 0x96EF97DAEB89BEF5 0xD938DEE0

void SET_PARTICLE_FX_SHOOTOUT_BOAT(Any p0)



> SET_PARTICLE_FX_BLOOD_SCALE - 0x5F6DF3D92271E8A1 0x18136DE0

void SET_PARTICLE_FX_BLOOD_SCALE(BOOL p0)

```
hash collision
```

> ENABLE_CLOWN_BLOOD_VFX - 0xD821490579791273 0xC61C75E9

void ENABLE_CLOWN_BLOOD_VFX(BOOL toggle)

```
Creates cartoon effect when Michel smokes the weed
```

> ENABLE_ALIEN_BLOOD_VFX - 0x9DCE1F0F78260875 0xCE8B8748

void ENABLE_ALIEN_BLOOD_VFX(BOOL toggle)



> 0x27E32866E9A5C416 

void 0x27E32866E9A5C416(float p0)



> 0xBB90E12CAC1DAB25 

void 0xBB90E12CAC1DAB25(float p0)



> 0xCA4AE345A153D573 

void 0xCA4AE345A153D573(BOOL p0)



> 0x54E22EA2C1956A8D 

void 0x54E22EA2C1956A8D(float p0)



> 0x949F397A288B28B3 

void 0x949F397A288B28B3(float p0)



> 0x9B079E5221D984D3 

void 0x9B079E5221D984D3(BOOL p0)



> _SET_PTFX_ASSET_NEXT_CALL - 0x6C38AF3693A69A91 0x9C720B61

void _SET_PTFX_ASSET_NEXT_CALL(char* name)

```
 From the b678d decompiled scripts:

 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('FM_Mission_Controler');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_apartment_mp');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_indep_fireworks');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_mp_cig_plane');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_mp_creator');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_ornate_heist');
 GRAPHICS::_SET_PTFX_ASSET_NEXT_CALL('scr_prison_break_heist_station');
```

> _SET_PTFX_ASSET_OLD_TO_NEW - 0xEA1E2D93F6F75ED9 

void _SET_PTFX_ASSET_OLD_TO_NEW(char* oldAsset, char* newAsset)

```
console hash: 0xC92719A7
```

> 0x89C8553DD3274AAE 

void 0x89C8553DD3274AAE(char* name)

```
console hash: 0x9E8D8B72
Resets the effect of _SET_PARTICLE_FX_ASSET_OLD_TO_NEW
```

> 0xA46B73FAA3460AE1 

void 0xA46B73FAA3460AE1(BOOL p0)



> 0xF78B803082D4386F 

void 0xF78B803082D4386F(float p0)



> WASH_DECALS_IN_RANGE - 0x9C30613D50A6ADEF 0xDEECBC57

void WASH_DECALS_IN_RANGE(Any p0, Any p1, Any p2, Any p3, Any p4)



> WASH_DECALS_FROM_VEHICLE - 0x5B712761429DBC14 0x2929F11A

void WASH_DECALS_FROM_VEHICLE(Vehicle vehicle, float p1)



> FADE_DECALS_IN_RANGE - 0xD77EDADB0420E6E0 0xF81E884A

void FADE_DECALS_IN_RANGE(Any p0, Any p1, Any p2, Any p3, Any p4)

```
Fades nearby decals within the range specified
```

> REMOVE_DECALS_IN_RANGE - 0x5D6B2D4830A67C62 0x06A619A0

void REMOVE_DECALS_IN_RANGE(float x, float y, float z, float range)

```
Removes all decals in range from a position, it includes the bullet holes, blood pools, petrol...
```

> REMOVE_DECALS_FROM_OBJECT - 0xCCF71CBDDF5B6CB9 0x8B67DCA7

void REMOVE_DECALS_FROM_OBJECT(Object obj)



> REMOVE_DECALS_FROM_OBJECT_FACING - 0xA6F6F70FDC6D144C 0xF4999A55

void REMOVE_DECALS_FROM_OBJECT_FACING(Object obj, float x, float y, float z)



> REMOVE_DECALS_FROM_VEHICLE - 0xE91F1B65F2B48D57 0x831D06CA

void REMOVE_DECALS_FROM_VEHICLE(Vehicle vehicle)



> ADD_DECAL - 0xB302244A1839BDAD 0xEAD0C412

int ADD_DECAL(Any p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, float p12, float p13, float p14, float p15, float p16, BOOL p17, BOOL p18, BOOL p19)

```
thanks to JulioNIB for figuring out the parameters.

decal types:

public enum DecalTypes
{
    splatters_blood = 1010,
    splatters_blood_dir = 1015,
    splatters_blood_mist = 1017,
    splatters_mud = 1020,
    splatters_paint = 1030,
    splatters_water = 1040,
    splatters_water_hydrant = 1050,
    splatters_blood2 = 1110,
    weapImpact_metal = 4010,
    weapImpact_concrete = 4020,
    weapImpact_mattress = 4030,
    weapImpact_mud = 4032,
    weapImpact_wood = 4050,
    weapImpact_sand = 4053,
    weapImpact_cardboard = 4040,
    weapImpact_melee_glass = 4100,
    weapImpact_glass_blood = 4102,
    weapImpact_glass_blood2 = 4104,
    weapImpact_shotgun_paper = 4200,
    weapImpact_shotgun_mattress,
    weapImpact_shotgun_metal,
    weapImpact_shotgun_wood,
    weapImpact_shotgun_dirt,
    weapImpact_shotgun_tvscreen,
    weapImpact_shotgun_tvscreen2,
    weapImpact_shotgun_tvscreen3,
    weapImpact_melee_concrete = 4310,
    weapImpact_melee_wood = 4312,
    weapImpact_melee_metal = 4314,
    burn1 = 4421,
    burn2,
    burn3,
    burn4,
    burn5,
    bang_concrete_bang = 5000,
    bang_concrete_bang2,
    bang_bullet_bang,
    bang_bullet_bang2 = 5004,
    bang_glass = 5031,
    bang_glass2,
    solidPool_water = 9000,
    solidPool_blood,
    solidPool_oil,
    solidPool_petrol,
    solidPool_mud,
    porousPool_water,
    porousPool_blood,
    porousPool_oil,
    porousPool_petrol,
    porousPool_mud,
    porousPool_water_ped_drip,
    liquidTrail_water = 9050
}
```

> ADD_PETROL_DECAL - 0x4F5212C7AD880DF8 0x1259DF42

Any ADD_PETROL_DECAL(float x, float y, float z, float groundLvl, float width, float transparency)



> 0x99AC7F0D8B9C893D 0xE3938B0B

void 0x99AC7F0D8B9C893D(float p0)



> 0x967278682CB6967A 0xBAEC6ADD

void 0x967278682CB6967A(Any p0, Any p1, Any p2, Any p3)



> 0x0A123435A26C36CD 0xCCCA6855

void 0x0A123435A26C36CD()



> REMOVE_DECAL - 0xED3F346429CCD659 0xA4363188

void REMOVE_DECAL(int decal)



> IS_DECAL_ALIVE - 0xC694D74949CAFD0C 0xCDD4A61A

BOOL IS_DECAL_ALIVE(int decal)



> GET_DECAL_WASH_LEVEL - 0x323F647679A09103 0x054448EF

float GET_DECAL_WASH_LEVEL(int decal)



> 0xD9454B5752C857DC 0xEAB6417C

void 0xD9454B5752C857DC()



> 0x27CFB1B1E078CB2D 0xC2703B88

void 0x27CFB1B1E078CB2D()



> 0x4B5CFC83122DF602 0xA706E84D

void 0x4B5CFC83122DF602()



> 0x2F09F7976C512404 0x242C6A04

BOOL 0x2F09F7976C512404(float xCoord, float yCoord, float zCoord, float p3)

```
only documented. to be continued...
```

> 0x8A35C742130C6080 0x335695CF

void 0x8A35C742130C6080(Any p0, Any* p1, Any* p2)



> 0xB7ED70C49521A61D 0x7B786555

void 0xB7ED70C49521A61D(Any p0)



> MOVE_VEHICLE_DECALS - 0x84C8D7C2D30D3280 0xCE9E6CF2

void MOVE_VEHICLE_DECALS(Any p0, Any p1)



> _ADD_CLAN_DECAL_TO_VEHICLE - 0x428BDCB9DA58DA53 0x12077738

BOOL _ADD_CLAN_DECAL_TO_VEHICLE(Vehicle vehicle, Ped ped, int boneIndex, float x1, float x2, float x3, float y1, float y2, float y3, float z1, float z2, float z3, float scale, Any p13, int alpha)

```
Now has 15 parameters, previous declaration:
BOOL _0x428BDCB9DA58DA53(Any p0, Any p1, Any p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, float p12, Any p13)

boneIndex is always chassis_dummy in the scripts. The x/y/z params are location relative to the chassis bone. They are usually rotations and measurements. Haven't reversed which are what yet.

Scale is how big the decal will be.

p13 is always 0.

For alpha, 200 seems to match what the game is doing, I think. I don't have access to the new scripts to see what this parameter is, but based on guessing this seems (kind of) accurate.
```

> 0xD2300034310557E4 0x667046A8

void 0xD2300034310557E4(Vehicle vehicle, Any p1)



> 0xFE26117A5841B2FF 0x4F4D76E8

int 0xFE26117A5841B2FF(Vehicle vehicle, Any p1)



> _DOES_VEHICLE_HAVE_DECAL - 0x060D935D3981A275 0x6D58F73B

BOOL _DOES_VEHICLE_HAVE_DECAL(Vehicle vehicle, Any p1)

```
This function is called before ADD_CLAN_DECAL_TO_VEHICLE to see if it needs to run. IDK if it's for clan decal or not, but the 2nd parameter might be decal index? It's always passed 0. Not sure what this function really does. But it does return 0 if the clan tag is not on, and 1 if it is.
```

> 0x0E4299C549F0D1F1 0x9BABCBA4

void 0x0E4299C549F0D1F1(BOOL p0)



> 0x02369D5C8A51FDCF 0xFDF6D8DA

void 0x02369D5C8A51FDCF(BOOL p0)



> 0x46D1A61A21F566FC 0x2056A015

void 0x46D1A61A21F566FC(float p0)



> 0x2A2A52824DB96700 0x0F486429

void 0x2A2A52824DB96700(Any* p0)



> 0x1600FD8CF72EBC12 0xD87CC710

void 0x1600FD8CF72EBC12(float p0)



> 0xEFB55E7C25D3B3BE 0xE29EE145

void 0xEFB55E7C25D3B3BE()



> 0xA44FF770DFBC5DAE 

void 0xA44FF770DFBC5DAE()



> DISABLE_VEHICLE_DISTANTLIGHTS - 0xC9F98AC1884E73A2 0x7CFAE36F

void DISABLE_VEHICLE_DISTANTLIGHTS(BOOL toggle)



> 0x03300B57FCAC6DDB 0x60F72371

void 0x03300B57FCAC6DDB(BOOL p0)



> 0x98EDF76A7271E4F2 

void 0x98EDF76A7271E4F2()



> _SET_FORCE_PED_FOOTSTEPS_TRACKS - 0xAEEDAD1420C65CC0 

void _SET_FORCE_PED_FOOTSTEPS_TRACKS(BOOL toggle)

```
Forces footstep tracks on all surfaces.
```

> _SET_FORCE_VEHICLE_TRAILS - 0x4CC7F0FEA5283FE0 

void _SET_FORCE_VEHICLE_TRAILS(BOOL toggle)

```
Forces vehicle trails on all surfaces.
```

> 0xD7021272EB0A451E 

void 0xD7021272EB0A451E(char* p0)

```
Only one match in the scripts:

GRAPHICS::_D7021272EB0A451E('int_carrier_hanger');
```

> SET_TIMECYCLE_MODIFIER - 0x2C933ABF17A1DF41 0xA81F3638

void SET_TIMECYCLE_MODIFIER(char* modifierName)

```
Loads the specified timecycle modifier. Modifiers are defined separately in another file (e.g. 'timecycle_mods_1.xml')

Parameters:
modifierName - The modifier to load (e.g. 'V_FIB_IT3', 'scanline_cam', etc.)
```

> SET_TIMECYCLE_MODIFIER_STRENGTH - 0x82E7FFCD5B2326B3 0x458F4F45

void SET_TIMECYCLE_MODIFIER_STRENGTH(float strength)



> SET_TRANSITION_TIMECYCLE_MODIFIER - 0x3BCF567485E1971C 0xBB2BA72A

void SET_TRANSITION_TIMECYCLE_MODIFIER(char* modifierName, float transition)



> 0x1CBA05AE7BD7EE05 0x56345F6B

void 0x1CBA05AE7BD7EE05(float p0)



> CLEAR_TIMECYCLE_MODIFIER - 0x0F07E7745A236711 0x8D8DF8EE

void CLEAR_TIMECYCLE_MODIFIER()



> GET_TIMECYCLE_MODIFIER_INDEX - 0xFDF3D97C674AFB66 0x594FEEC4

int GET_TIMECYCLE_MODIFIER_INDEX()

```
Only use for this in the PC scripts is:

if (GRAPHICS::GET_TIMECYCLE_MODIFIER_INDEX() != -1)
```

> 0x459FD2C8D0AB78BC 0x03C44E4B

Any 0x459FD2C8D0AB78BC()



> PUSH_TIMECYCLE_MODIFIER - 0x58F735290861E6B4 0x7E082045

void PUSH_TIMECYCLE_MODIFIER()



> POP_TIMECYCLE_MODIFIER - 0x3C8938D7D872211E 0x79D7D235

void POP_TIMECYCLE_MODIFIER()



> 0xBBF327DED94E4DEB 0x85BA15A4

void 0xBBF327DED94E4DEB(char* p0)



> 0xBDEB86F4D5809204 0x9559BB38

void 0xBDEB86F4D5809204(float p0)



> 0xBF59707B3E5ED531 0x554BA16E

void 0xBF59707B3E5ED531(Any* p0)



> 0x1A8E2C8B9CF4549C 0xE8F538B5

void 0x1A8E2C8B9CF4549C(Any* p0, Any* p1)



> 0x15E33297C3E8DC60 0x805BAB08

void 0x15E33297C3E8DC60(Any p0)



> 0x5096FD9CCB49056D 0x908A335E

void 0x5096FD9CCB49056D(Any* p0)



> 0x92CCC17A7A2285DA 0x6776720A

void 0x92CCC17A7A2285DA()



> 0xBB0527EC6341496D 

Any 0xBB0527EC6341496D()



> 0x2C328AF17210F009 

void 0x2C328AF17210F009(float p0)



> 0x2BF72AD5B41AA739 

void 0x2BF72AD5B41AA739()



> REQUEST_SCALEFORM_MOVIE - 0x11FE353CF9733E6F 0xC67E3DCB

int REQUEST_SCALEFORM_MOVIE(char* scaleformName)

```
Gets a new native after almost every update.

Update 1.0.393.2
0x67D02A194A2FC2BD

Update 1.0.463.1
0xC97D787CE7726A2F

Update 1.0.505.2
0x36ECDA4DD9A3F08D

Update 1.0.573.1
0xE3C796DC28BC3254

Update 1.0.678.1
0x2F14983962462691

```

> REQUEST_SCALEFORM_MOVIE_INSTANCE - 0xC514489CFB8AF806 0x7CC8057D

int REQUEST_SCALEFORM_MOVIE_INSTANCE(char* scaleformName)

```
Also used by 0x67D02A194A2FC2BD
```

> _REQUEST_SCALEFORM_MOVIE3 - 0xBD06C611BB9048C2 

int _REQUEST_SCALEFORM_MOVIE3(char* scaleformName)

```
Similar to REQUEST_SCALEFORM_MOVIE, but seems to be some kind of 'interactive' scaleform movie?

These seem to be the only scaleforms ever requested by this native:
'breaking_news'
'desktop_pc'
'ECG_MONITOR'
'Hacking_PC'
'TEETH_PULLING'

Note: Unless this hash is out-of-order, this native is next-gen only.

```

> HAS_SCALEFORM_MOVIE_LOADED - 0x85F01B8D5B90570E 0xDDFB6448

BOOL HAS_SCALEFORM_MOVIE_LOADED(int scaleformHandle)



> _HAS_NAMED_SCALEFORM_MOVIE_LOADED - 0x0C1C5D756FB5F337 

BOOL _HAS_NAMED_SCALEFORM_MOVIE_LOADED(char* scaleformName)

```
Pretty sure it's the real name (not 100% sure so I added the _ prefix); can someone else confirm it?

Only values used in the scripts are:

'heist_mp'
'heistmap_mp'
'instructional_buttons'
'heist_pre'
```

> HAS_SCALEFORM_CONTAINER_MOVIE_LOADED_INTO_PARENT - 0x8217150E1217EBFD 0x1DFE8D8A

BOOL HAS_SCALEFORM_CONTAINER_MOVIE_LOADED_INTO_PARENT(int scaleformHandle)



> SET_SCALEFORM_MOVIE_AS_NO_LONGER_NEEDED - 0x1D132D614DD86811 0x5FED3BA1

void SET_SCALEFORM_MOVIE_AS_NO_LONGER_NEEDED(int* scaleformHandle)



> SET_SCALEFORM_MOVIE_TO_USE_SYSTEM_TIME - 0x6D8EB211944DCE08 0x18C9DE8D

void SET_SCALEFORM_MOVIE_TO_USE_SYSTEM_TIME(int scaleform, BOOL toggle)



> DRAW_SCALEFORM_MOVIE - 0x54972ADAF0294A93 0x48DA6A58

void DRAW_SCALEFORM_MOVIE(int scaleformHandle, float x, float y, float width, float height, int red, int green, int blue, int alpha, int p9)



> DRAW_SCALEFORM_MOVIE_FULLSCREEN - 0x0DF606929C105BE1 0x7B48E696

void DRAW_SCALEFORM_MOVIE_FULLSCREEN(int scaleform, int red, int green, int blue, int alpha, BOOL unk)

```
unk is not used so no need
```

> DRAW_SCALEFORM_MOVIE_FULLSCREEN_MASKED - 0xCF537FDE4FBD4CE5 0x9C59FC06

void DRAW_SCALEFORM_MOVIE_FULLSCREEN_MASKED(int scaleform1, int scaleform2, int red, int green, int blue, int alpha)



> DRAW_SCALEFORM_MOVIE_3D - 0x87D51D72255D4E78 0xC4F63A89

void DRAW_SCALEFORM_MOVIE_3D(int scaleform, float posX, float posY, float posZ, float rotX, float rotY, float rotZ, float p7, float p8, float p9, float scaleX, float scaleY, float scaleZ, Any p13)



> _DRAW_SCALEFORM_MOVIE_3D_NON_ADDITIVE - 0x1CE592FDC749D6F5 0x899933C8

void _DRAW_SCALEFORM_MOVIE_3D_NON_ADDITIVE(int scaleform, float posX, float posY, float posZ, float rotX, float rotY, float rotZ, float p7, float p8, float p9, float scaleX, float scaleY, float scaleZ, Any p13)

```
Originally called '_DRAW_SCALEFORM_MOVIE_3D'. Since the actual 'DRAW_SCALEFORM_MOVIE_3D' native was found, what the heck does this one do differently?
```

> CALL_SCALEFORM_MOVIE_METHOD - 0xFBD96D87AC96D533 0x7AB77B57

void CALL_SCALEFORM_MOVIE_METHOD(int scaleform, char* method)

```
Calls the Scaleform function.
```

> _CALL_SCALEFORM_MOVIE_FUNCTION_FLOAT_PARAMS - 0xD0837058AE2E4BEE 0x557EDA1D

void _CALL_SCALEFORM_MOVIE_FUNCTION_FLOAT_PARAMS(int scaleform, char* functionName, float param1, float param2, float param3, float param4, float param5)

```
Calls the Scaleform function and passes the parameters as floats.

The number of parameters passed to the function varies, so the end of the parameter list is represented by -1.0.
```

> _CALL_SCALEFORM_MOVIE_FUNCTION_STRING_PARAMS - 0x51BC1ED3CC44E8F7 0x91A7FCEB

void _CALL_SCALEFORM_MOVIE_FUNCTION_STRING_PARAMS(int scaleform, char* functionName, char* param1, char* param2, char* param3, char* param4, char* param5)

```
Calls the Scaleform function and passes the parameters as strings.

The number of parameters passed to the function varies, so the end of the parameter list is represented by 0 (NULL).
```

> _CALL_SCALEFORM_MOVIE_FUNCTION_MIXED_PARAMS - 0xEF662D8D57E290B1 0x6EAF56DE

void _CALL_SCALEFORM_MOVIE_FUNCTION_MIXED_PARAMS(int scaleform, char* functionName, float floatParam1, float floatParam2, float floatParam3, float floatParam4, float floatParam5, char* stringParam1, char* stringParam2, char* stringParam3, char* stringParam4, char* stringParam5)

```
Calls the Scaleform function and passes both float and string parameters (in their respective order).

The number of parameters passed to the function varies, so the end of the float parameters is represented by -1.0, and the end of the string parameters is represented by 0 (NULL).

NOTE: The order of parameters in the function prototype is important! All float parameters must come first, followed by the string parameters.

Examples:
// function MY_FUNCTION(floatParam1, floatParam2, stringParam)
GRAPHICS::_CALL_SCALEFORM_MOVIE_FUNCTION_MIXED_PARAMS(scaleform, 'MY_FUNCTION', 10.0, 20.0, -1.0, -1.0, -1.0, 'String param', 0, 0, 0, 0);

// function MY_FUNCTION_2(floatParam, stringParam1, stringParam2)
GRAPHICS::_CALL_SCALEFORM_MOVIE_FUNCTION_MIXED_PARAMS(scaleform, 'MY_FUNCTION_2', 10.0, -1.0, -1.0, -1.0, -1.0, 'String param #1', 'String param #2', 0, 0, 0);
```

> _PUSH_SCALEFORM_MOVIE_FUNCTION_FROM_HUD_COMPONENT - 0x98C494FD5BDFBFD5 0x5D66CE1E

BOOL _PUSH_SCALEFORM_MOVIE_FUNCTION_FROM_HUD_COMPONENT(int hudComponent, char* functionName)

```
Pushes a function from the Hud component Scaleform onto the stack. Same behavior as GRAPHICS::_PUSH_SCALEFORM_MOVIE_FUNCTION, just a hud component id instead of a Scaleform.

Known components:
19 - MP_RANK_BAR
20 - HUD_DIRECTOR_MODE

This native requires more research - all information can be found inside of 'hud.gfx'. Using a decompiler, the different components are located under 'scripts/__Packages/com/rockstargames/gtav/hud/hudComponents' and 'scripts/__Packages/com/rockstargames/gtav/Multiplayer'.
```

> _PUSH_SCALEFORM_MOVIE_FUNCTION - 0xF6E48914C7A8694E 0x215ABBE8

BOOL _PUSH_SCALEFORM_MOVIE_FUNCTION(int scaleform, char* functionName)

```
Push a function from the Scaleform onto the stack

```

> _PUSH_SCALEFORM_MOVIE_FUNCTION_N - 0xAB58C27C2E6123C6 0xF6015178

BOOL _PUSH_SCALEFORM_MOVIE_FUNCTION_N(char* functionName)

```
Possibly calls 'global' Scaleform functions - needs more research!
```

> 0xB9449845F73F5E9C 0x5E219B67

BOOL 0xB9449845F73F5E9C(char* functionName)



> _POP_SCALEFORM_MOVIE_FUNCTION_VOID - 0xC6796A8FFA375E53 0x02DBF2D7

void _POP_SCALEFORM_MOVIE_FUNCTION_VOID()

```
Pops and calls the Scaleform function on the stack
```

> _POP_SCALEFORM_MOVIE_FUNCTION - 0xC50AA39A577AF886 0x2F38B526

Any _POP_SCALEFORM_MOVIE_FUNCTION()

```
Pops and calls the Scaleform movie on the stack. Returns data from the function (not sure if this is a string).
```

> 0x768FF8961BA904D6 0x5CD7C3C0

BOOL 0x768FF8961BA904D6(Any funcData)

```
Seems to take data that is returned from '_POP_SCALEFORM_MOVIE_FUNCTION' and checks to see if it's not null/empty.

'agency_heist3b.ysc', line 71836:
if (CONTROLS::IS_CONTROL_JUST_PRESSED(2, 201) || CONTROLS::IS_CONTROL_JUST_PRESSED(2, 237)) {
    GRAPHICS::_PUSH_SCALEFORM_MOVIE_FUNCTION(l_46, 'SET_INPUT_EVENT_SELECT');
    l_45 = GRAPHICS::_POP_SCALEFORM_MOVIE_FUNCTION();
}
if (GRAPHICS::_0x768FF8961BA904D6(l_45)) {
    v_13 = GRAPHICS::_0x2DE7EFA66B906036(l_45);
    if (v_13 == 6) {
        sub_73269(a_0);
    }
}

```

> 0x2DE7EFA66B906036 0x2CFB0E6D

int 0x2DE7EFA66B906036(Any funcData)

```
Needs a bit more research, but it seems to return an int.

'agency_heist3b.ysc', line 71836:
if (CONTROLS::IS_CONTROL_JUST_PRESSED(2, 201) || CONTROLS::IS_CONTROL_JUST_PRESSED(2, 237)) {
    GRAPHICS::_PUSH_SCALEFORM_MOVIE_FUNCTION(l_46, 'SET_INPUT_EVENT_SELECT');
    l_45 = GRAPHICS::_POP_SCALEFORM_MOVIE_FUNCTION();
}
if (GRAPHICS::_0x768FF8961BA904D6(l_45)) {
    v_13 = GRAPHICS::_0x2DE7EFA66B906036(l_45);
    if (v_13 == 6) {
        sub_73269(a_0);
    }
}
```

> SITTING_TV - 0xE1E258829A885245 0x516862EB

char* SITTING_TV(int scaleform)

```
Unsurprisingly, this native is incorrectly named. Instead, this returns the name of the scaleform movie.

HASH COLLISION. PLEASE REMOVE NATIVE NAME.
```

> _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_INT - 0xC3D0841A0CC546A6 0x716777CB

void _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_INT(int value)

```
Pushes an integer for the Scaleform function onto the stack.
```

> _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_FLOAT - 0xD69736AAE04DB51A 0x9A01FFDA

void _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_FLOAT(float value)

```
Pushes a float for the Scaleform function onto the stack.
```

> _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_BOOL - 0xC58424BA936EB458 0x0D4AE8CB

void _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_BOOL(BOOL value)

```
Pushes a boolean for the Scaleform function onto the stack.
```

> _BEGIN_TEXT_COMPONENT - 0x80338406F3475E55 0x3AC9CB55

void _BEGIN_TEXT_COMPONENT(char* componentType)

```
Called prior to adding a text component to the UI. After doing so, GRAPHICS::_END_TEXT_COMPONENT is called.

Examples:
GRAPHICS::_BEGIN_TEXT_COMMAND_SCALEFORM('NUMBER');
UI::ADD_TEXT_COMPONENT_INTEGER(GAMEPLAY::ABSI(a_1));
GRAPHICS::_END_TEXT_COMPONENT();

GRAPHICS::_BEGIN_TEXT_COMPONENT('STRING');
UI::_ADD_TEXT_COMPONENT_STRING(a_2);
GRAPHICS::_END_TEXT_COMPONENT();

GRAPHICS::_BEGIN_TEXT_COMPONENT('STRTNM2');
UI::_0x17299B63C7683A2B(v_3);
UI::_0x17299B63C7683A2B(v_4);
GRAPHICS::_END_TEXT_COMPONENT();

GRAPHICS::_BEGIN_TEXT_COMPONENT('STRTNM1');
UI::_0x17299B63C7683A2B(v_3);
GRAPHICS::_END_TEXT_COMPONENT();



This is _BEGIN_TEXT_COMPONENT
```

> _END_TEXT_COMPONENT - 0x362E2D3FE93A9959 0x386CE0B8

void _END_TEXT_COMPONENT()



> 0xAE4E8157D9ECF087 0x2E80DB52

void 0xAE4E8157D9ECF087()



> _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_STRING - 0xBA7148484BD90365 0x4DAAD55B

void _PUSH_SCALEFORM_MOVIE_FUNCTION_PARAMETER_STRING(char* value)



> 0xE83A3E3557A56640 0xCCBF0334

void 0xE83A3E3557A56640(char* p0)



> 0x5E657EF1099EDD65 0x91A081A1

BOOL 0x5E657EF1099EDD65(Any p0)



> 0xEC52C631A1831C03 0x83A9811D

void 0xEC52C631A1831C03(Any p0)



> _REQUEST_HUD_SCALEFORM - 0x9304881D6F6537EA 0x7AF85862

void _REQUEST_HUD_SCALEFORM(int hudComponent)

```
http://gtaforums.com/topic/717612-v-scriptnative-documentation-and-research/?p=1068285912
```

> _HAS_HUD_SCALEFORM_LOADED - 0xDF6E5987D2B4D140 0x79B43255

BOOL _HAS_HUD_SCALEFORM_LOADED(int hudComponent)

```
Check to see if hud component Scaleform has loaded?
```

> 0xF44A5456AC3F4F97 0x03D87600

void 0xF44A5456AC3F4F97(Any p0)

```
Another function related to 'HUD scaleforms'
```

> 0xD1C7CB175E012964 0xE9183D3A

BOOL 0xD1C7CB175E012964(int scaleformHandle)



> SET_TV_CHANNEL - 0xBAABBB23EB6E484E 0x41A8A627

void SET_TV_CHANNEL(int channel)



> GET_TV_CHANNEL - 0xFC1E275A90D39995 0x6B96145A

int GET_TV_CHANNEL()



> SET_TV_VOLUME - 0x2982BF73F66E9DDC 0xF3504F4D

void SET_TV_VOLUME(float volume)



> GET_TV_VOLUME - 0x2170813D3DD8661B 0x39555CF0

float GET_TV_VOLUME()



> DRAW_TV_CHANNEL - 0xFDDC2B4ED3C69DF0 0x8129EF89

void DRAW_TV_CHANNEL(float xPos, float yPos, float xScale, float yScale, float rotation, int r, int g, int b, int alpha)

```
All calls to this native are preceded by calls to GRAPHICS::_0x61BB1D9B3A95D802 and GRAPHICS::_0xC6372ECD45D73BCD, respectively.

'act_cinema.ysc', line 1483:
UI::SET_HUD_COMPONENT_POSITION(15, 0.0, -0.0375);
UI::SET_TEXT_RENDER_ID(l_AE);
GRAPHICS::_0x61BB1D9B3A95D802(4);
GRAPHICS::_0xC6372ECD45D73BCD(1);
if (GRAPHICS::_0x0AD973CA1E077B60(${movie_arthouse})) {
    GRAPHICS::DRAW_TV_CHANNEL(0.5, 0.5, 0.7375, 1.0, 0.0, 255, 255, 255, 255);
} else { 
    GRAPHICS::DRAW_TV_CHANNEL(0.5, 0.5, 1.0, 1.0, 0.0, 255, 255, 255, 255);
}

'am_mp_property_int.ysc', line 102545:
if (ENTITY::DOES_ENTITY_EXIST(a_2._f3)) {
    if (UI::IS_NAMED_RENDERTARGET_LINKED(ENTITY::GET_ENTITY_MODEL(a_2._f3))) {
        UI::SET_TEXT_RENDER_ID(a_2._f1);
        GRAPHICS::_0x61BB1D9B3A95D802(4);
        GRAPHICS::_0xC6372ECD45D73BCD(1);
        GRAPHICS::DRAW_TV_CHANNEL(0.5, 0.5, 1.0, 1.0, 0.0, 255, 255, 255, 255);
        if (GRAPHICS::GET_TV_CHANNEL() == -1) {
            sub_a8fa5(a_2, 1);
        } else { 
            sub_a8fa5(a_2, 1);
            GRAPHICS::ATTACH_TV_AUDIO_TO_ENTITY(a_2._f3);
        }
        UI::SET_TEXT_RENDER_ID(UI::GET_DEFAULT_SCRIPT_RENDERTARGET_RENDER_ID());
    }
}

```

> 0xF7B38B8305F1FE8B 0xB262DE67

void 0xF7B38B8305F1FE8B(int p0, char* p1, BOOL p2)

```
SET_TV_???
```

> 0x2201C576FACAEBE8 0x78C4DCBE

void 0x2201C576FACAEBE8(Any p0, Any* p1, Any p2)

```
SET_TV_???
```

> 0xBEB3D46BB7F043C0 0xCBE7068F

void 0xBEB3D46BB7F043C0(Any p0)



> _LOAD_TV_CHANNEL - 0x0AD973CA1E077B60 0x4D1EB0FB

BOOL _LOAD_TV_CHANNEL(Hash tvChannel)



> 0x74C180030FDE4B69 0x796DE696

void 0x74C180030FDE4B69(BOOL p0)



> 0xD1C55B110E4DF534 0xD99EC000

void 0xD1C55B110E4DF534(Any p0)

```
SET_TV_???
```

> ENABLE_MOVIE_SUBTITLES - 0x873FA65C778AD970 0xC2DEBA3D

void ENABLE_MOVIE_SUBTITLES(BOOL toggle)



> 0xD3A10FC7FD8D98CD 0xE40A0F1A

BOOL 0xD3A10FC7FD8D98CD()



> 0xF1CEA8A4198D8E9A 0x2E7D9B98

BOOL 0xF1CEA8A4198D8E9A(char* p0)



> 0x98C4FE6EC34154CA 0x9A0E3BFE

BOOL 0x98C4FE6EC34154CA(char* p0, Ped ped, int p2, float posX, float posY, float posZ)

```
It's called after 0xD3A10FC7FD8D98CD and 0xF1CEA8A4198D8E9A

p0 was always 'CELEBRATION_WINNER'
```

> 0x7A42B2E236E71415 0x431AA036

void 0x7A42B2E236E71415()



> 0x108BE26959A9D9BB 0x24A7A7F6

void 0x108BE26959A9D9BB(BOOL p0)



> 0xA356990E161C9E65 0xA1CB6C94

void 0xA356990E161C9E65(BOOL p0)



> 0x1C4FC5752BCD8E48 0x3B637AA7

void 0x1C4FC5752BCD8E48(float p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, float p8, float p9, float p10, float p11, float p12)



> 0x5CE62918F8D703C7 0xDF552973

void 0x5CE62918F8D703C7(int p0, int p1, int p2, int p3, int p4, int p5, int p6, int p7, int p8, int p9, int p10, int p11)

```
Only called in golf and golf_mp
parameters used are 
GRAPHICS::_0x5CE62918F8D703C7(255, 0, 0, 64, 255, 255, 255, 5, 255, 255, 0, 64);

```

> _START_SCREEN_EFFECT - 0x2206BF9A37B7F724 0x1D980479

void _START_SCREEN_EFFECT(char* effectName, int duration, BOOL looped)

```
playLength - is how long to play the effect for in milliseconds. If 0, it plays the default length
if loop is true, the effect wont stop until you call _STOP_SCREEN_EFFECT on it. (only loopable effects)

Example and list of screen FX: www.pastebin.com/dafBAjs0

```

> _STOP_SCREEN_EFFECT - 0x068E835A1D0DC0E3 0x06BB5CDA

void _STOP_SCREEN_EFFECT(char* effectName)



> _GET_SCREEN_EFFECT_IS_ACTIVE - 0x36AD3E690DA5ACEB 0x089D5921

int _GET_SCREEN_EFFECT_IS_ACTIVE(char* effectName)



> _STOP_ALL_SCREEN_EFFECTS - 0xB4EDDC19532BFB85 0x4E6D875B

void _STOP_ALL_SCREEN_EFFECTS()



> 0xD2209BE128B5418C 

void 0xD2209BE128B5418C(char* graphicsName)

```
'SwitchHUDFranklinOut',
'SwitchHUDMichaelOut',
'SwitchHUDOut',
'SwitchHUDTrevorOut',
'SwitchOpenFranklinOut',
'SwitchOpenMichaelIn',
'SwitchOpenNeutral'
```

