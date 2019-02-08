# Pathfind

> SET_ROADS_IN_AREA - 0xBF1A602B5BA52FEE 0xEBC7B918

void SET_ROADS_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, BOOL unknown1, BOOL unknown2)

```
/* Corrected conflicting parameter names */
```

> SET_ROADS_IN_ANGLED_AREA - 0x1A5AA1208AF5DB59 0xBD088F4B

void SET_ROADS_IN_ANGLED_AREA(float x1, float y1, float z1, float x2, float y2, float z2, float angle, BOOL unknown1, BOOL unknown2, BOOL unknown3)

```
/* Corrected conflicting parameter names */
```

> SET_PED_PATHS_IN_AREA - 0x34F060F4BF92E018 0x2148EA84

void SET_PED_PATHS_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2, BOOL unknown)



> GET_SAFE_COORD_FOR_PED - 0xB61C8E878A4199CA 0xB370270A

BOOL GET_SAFE_COORD_FOR_PED(float x, float y, float z, BOOL onGround, Vector3* outPosition, int flags)

```
When onGround == true outPosition is a position located on the nearest pavement.

When a safe coord could not be found the result of a function is false and outPosition == Vector3.Zero.

In the scripts these flags are used: 0, 14, 12, 16, 20, 21, 28. 0 is most commonly used, then 16. 

16 works for me, 0 crashed the script.
```

> GET_CLOSEST_VEHICLE_NODE - 0x240A18690AE96513 0x6F5F1E6C

BOOL GET_CLOSEST_VEHICLE_NODE(float x, float y, float z, Vector3* outPosition, int nodeType, float p5, float p6)

```
FYI: When falling through the map (or however you got under it) you will respawn when your player ped's height is &lt;= -200.0 meters (I think you all know this) and when in a vehicle you will actually respawn at the closest vehicle node.

----------

Vector3 nodePos;
GET_CLOSEST_VEHICLE_NODE(x,y,z,&amp;nodePos,...)

p4 is either 0, 1 or 8. 1 means any path/road. 0 means node in the middle of the closest main (asphalt) road.
p5, p6 are always the same:
0x40400000 (3.0), 0
p5 can also be 100.0 and p6 can be 2.5:
PATHFIND::GET_CLOSEST_VEHICLE_NODE(a_0, &amp;v_5, v_9, 100.0, 2.5)

Known node types: simple path/asphalt road, only asphalt road, water, under the map at always the same coords. 

The node types follows a pattern. For example, every fourth node is of the type water i.e. 3, 7, 11, 15, 19, 23, 27, 31, 35, 39... 239. Could not see any difference between nodes within certain types. 
Starting at 2, every fourth node is under the map, always same coords.
Same with only asphalt road (0, 4, 8, etc) and simple path/asphalt road (1, 5, 9, etc). 

gtaforums.com/topic/843561-pathfind-node-types
```

> GET_CLOSEST_MAJOR_VEHICLE_NODE - 0x2EABE3B06F58C1BE 0x04B5F15B

BOOL GET_CLOSEST_MAJOR_VEHICLE_NODE(float x, float y, float z, Vector3* outPosition, float unknown1, int unknown2)

```
Get the closest vehicle node to a given position, unknown1 = 3.0, unknown2 = 0
```

> GET_CLOSEST_VEHICLE_NODE_WITH_HEADING - 0xFF071FB798B803B0 0x8BD5759B

BOOL GET_CLOSEST_VEHICLE_NODE_WITH_HEADING(float x, float y, float z, Vector3* outPosition, float* outHeading, int nodeType, float p6, int p7)

```
p5, p6 and p7 seems to be about the same as p4, p5 and p6 for GET_CLOSEST_VEHICLE_NODE. p6 and/or p7 has something to do with finding a node on the same path/road and same direction(at least for this native, something to do with the heading maybe). Edit this when you find out more.

p5 is either 1 or 12. 1 means any path/road. 12, 8, 0 means node in the middle of the closest main (asphalt) road.
p6 is always 3.0
p7 is always 0.

Known node types: simple path/asphalt road, only asphalt road, water, under the map at always the same coords. 

The node types follows a pattern. For example, every fourth node is of the type water i.e. 3, 7, 11, 15, 19, 23, 27, 31, 35, 39... 239. Could not see any difference between nodes within certain types. 
Starting at 2, every fourth node is under the map, always same coords.
Same with only asphalt road (0, 4, 8, etc) and simple path/asphalt road (1, 5, 9, etc).

gtaforums.com/topic/843561-pathfind-node-types

Example of usage, moving vehicle to closest path/road:
Vector3 coords = ENTITY::GET_ENTITY_COORDS(playerVeh, true);
Vector3 closestVehicleNodeCoords; 
float roadHeading; 
PATHFIND::GET_CLOSEST_VEHICLE_NODE_WITH_HEADING(coords.x, coords.y, coords.z, &amp;closestVehicleNodeCoords, &amp;roadHeading, 1, 3, 0); 
ENTITY::SET_ENTITY_HEADING(playerVeh, roadHeading);
ENTITY::SET_ENTITY_COORDS(playerVeh, closestVehicleNodeCoords.x, closestVehicleNodeCoords.y, closestVehicleNodeCoords.z, 1, 0, 0, 1);
VEHICLE::SET_VEHICLE_ON_GROUND_PROPERLY(playerVeh);

------------------------------------------------------------------
C# Example (ins1de) : pastebin.com/fxtMWAHD
```

> GET_NTH_CLOSEST_VEHICLE_NODE - 0xE50E52416CCF948B 0xF125BFCC

BOOL GET_NTH_CLOSEST_VEHICLE_NODE(float x, float y, float z, int nthClosest, Vector3* outPosition, Any unknown1, Any unknown2, Any unknown3)



> GET_NTH_CLOSEST_VEHICLE_NODE_ID - 0x22D7275A79FE8215 0x3F358BEA

int GET_NTH_CLOSEST_VEHICLE_NODE_ID(float x, float y, float z, int nth, int nodetype, float p5, float p6)

```
Returns the id.
```

> GET_NTH_CLOSEST_VEHICLE_NODE_WITH_HEADING - 0x80CA6A8B6C094CC4 0x7349C856

BOOL GET_NTH_CLOSEST_VEHICLE_NODE_WITH_HEADING(float x, float y, float z, int nthClosest, Vector3* outPosition, float* heading, Any* unknown1, int unknown2, float unknown3, float unknown4)

```
Get the nth closest vehicle node and its heading. (unknown2 = 9, unknown3 = 3.0, unknown4 = 2.5)
```

> GET_NTH_CLOSEST_VEHICLE_NODE_ID_WITH_HEADING - 0x6448050E9C2A7207 0xC1AEB88D

Any GET_NTH_CLOSEST_VEHICLE_NODE_ID_WITH_HEADING(float x, float y, float z, int nthClosest, Vector3* outPosition, float outHeading, Any p6, float p7, float p8)



> GET_NTH_CLOSEST_VEHICLE_NODE_FAVOUR_DIRECTION - 0x45905BE8654AE067 0x928A4DEC

BOOL GET_NTH_CLOSEST_VEHICLE_NODE_FAVOUR_DIRECTION(float x, float y, float z, float desiredX, float desiredY, float desiredZ, int nthClosest, Vector3* outPosition, float* outHeading, int nodetype, Any p10, Any p11)

```
See gtaforums.com/topic/843561-pathfind-node-types for node type info. 0 = paved road only, 1 = any road, 3 = water

p10 always equal 0x40400000
p11 always equal 0
```

> GET_VEHICLE_NODE_PROPERTIES - 0x0568566ACBB5DEDC 0xCC90110B

BOOL GET_VEHICLE_NODE_PROPERTIES(float x, float y, float z, int* density, int* flags)

```
MulleDK19: Gets the density and flags of the closest node to the specified position.
Density is a value between 0 and 15, indicating how busy the road is.
Flags is a bit field.
```

> IS_VEHICLE_NODE_ID_VALID - 0x1EAF30FCFBF5AF74 0x57DFB1EF

BOOL IS_VEHICLE_NODE_ID_VALID(int vehicleNodeId)

```
Returns true if the id is non zero.
```

> GET_VEHICLE_NODE_POSITION - 0x703123E5E7D429C2 0xE38E252D

void GET_VEHICLE_NODE_POSITION(int nodeId, Vector3* outPosition)

```
Calling this with an invalid node id, will crash the game.
Note that IS_VEHICLE_NODE_ID_VALID simply checks if nodeId is not zero. It does not actually ensure that the id is valid.
Eg. IS_VEHICLE_NODE_ID_VALID(1) will return true, but will crash when calling GET_VEHICLE_NODE_POSITION().

sfink: This native returns a pointer to a packed Vector3 struct in the RAX register, as do the following natives:
AI::WAYPOINT_RECORDING_GET_COORD
ENTITY::GET_ENTITY_MATRIX
FIRE::GET_CLOSEST_FIRE_POS
GAMEPLAY::FIND_SPAWN_POINT_IN_DIRECTION
GAMEPLAY::GET_MODEL_DIMENSIONS
GAMEPLAY::OVERRIDE_SAVE_HOUSE
GAMEPLAY::_0x82FDE6A57EE4EE44
GAMEPLAY::_0x8BDC7BFC57A81E76
GAMEPLAY::_0x8D7A43EC6A5FEA45
GAMEPLAY::_0xA4A0065E39C9F25C
GAMEPLAY::_0xDFB4138EEFED7B81
MOBILE::GET_MOBILE_PHONE_POSITION
MOBILE::GET_MOBILE_PHONE_ROTATION
NETWORK::NETWORK_GET_RESPAWN_RESULT
OBJECT::_0x163F8B586BC95F2A
PATHFIND::GET_CLOSEST_MAJOR_VEHICLE_NODE
PATHFIND::GET_CLOSEST_ROAD
PATHFIND::GET_CLOSEST_VEHICLE_NODE
PATHFIND::GET_CLOSEST_VEHICLE_NODE_WITH_HEADING
PATHFIND::GET_NTH_CLOSEST_VEHICLE_NODE
PATHFIND::GET_NTH_CLOSEST_VEHICLE_NODE_FAVOUR_DIRECTION
PATHFIND::GET_NTH_CLOSEST_VEHICLE_NODE_WITH_HEADING
PATHFIND::GET_RANDOM_VEHICLE_NODE
PATHFIND::GET_SAFE_COORD_FOR_PED
PATHFIND::GET_VEHICLE_NODE_POSITION
PATHFIND::_0x16F46FB18C8009E4
VEHICLE::_0xA4822F1CF23F4810
VEHICLE::_0xDF7E3EEB29642C38
WATER::TEST_PROBE_AGAINST_ALL_WATER
WATER::TEST_PROBE_AGAINST_WATER
WEAPON::GET_PED_LAST_WEAPON_IMPACT_COORD
WORLDPROBE::_0xFF6BE494C7987F34
WORLDPROBE::_GET_RAYCAST_RESULT

```

> _GET_SUPPORTS_GPS_ROUTE_FLAG - 0xA2AE5C478B96E3B6 0xEE4B1219

BOOL _GET_SUPPORTS_GPS_ROUTE_FLAG(int nodeID)

```
p0 = VEHICLE_NODE_ID

Returns false for nodes that aren't used for GPS routes.
Example:
Nodes in Fort Zancudo and LSIA are false
```

> _GET_IS_SLOW_ROAD_FLAG - 0x4F5070AA58F69279 0x56737A3C

BOOL _GET_IS_SLOW_ROAD_FLAG(int nodeID)

```
p0 = VEHICLE_NODE_ID

Returns true when the node is Offroad. Alleys, some dirt roads, and carparks return true.
Normal roads where plenty of Peds spawn will return false

```

> GET_CLOSEST_ROAD - 0x132F52BBA570FE92 0x567B0E11

Any GET_CLOSEST_ROAD(float x, float y, float z, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8, Any p9, Any p10)



> LOAD_ALL_PATH_NODES - 0x80E4A6EDDB0BE8D9 0xC66E28C3

BOOL LOAD_ALL_PATH_NODES(BOOL keepInMemory)

```
Loads all path nodes.

If keepInMemory is true, all path nodes will be loaded and be kept in memory; otherwise, all path nodes will be loaded, but unloaded as the game sees fit.

-MulleDK19.
```

> 0x228E5C6AD4D74BFD 0xD6A3B458

void 0x228E5C6AD4D74BFD(BOOL p0)



> 0xF7B79A50B905A30D 0x86E80A17

BOOL 0xF7B79A50B905A30D(float p0, float p1, float p2, float p3)

```
Only did a quick disassembly, but this function seems to load all path nodes in the given area. Parameters appear to be start x, start y, end x, end y.
```

> 0x07FB139B592FA687 0x2CDA5012

BOOL 0x07FB139B592FA687(float p0, float p1, float p2, float p3)



> SET_ROADS_BACK_TO_ORIGINAL - 0x1EE7063B80FFC77C 0x86AC4A85

void SET_ROADS_BACK_TO_ORIGINAL(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)

```
missing a last parameter int p6 
```

> SET_ROADS_BACK_TO_ORIGINAL_IN_ANGLED_AREA - 0x0027501B9F3B407E 0x9DB5D209

void SET_ROADS_BACK_TO_ORIGINAL_IN_ANGLED_AREA(float x1, float y1, float z1, float x2, float y2, float z2, float p6)

```
bool p7 - always 1
```

> 0x0B919E1FB47CC4E0 0x3C5085E4

void 0x0B919E1FB47CC4E0(float p0)



> 0xAA76052DDA9BFC3E 0xD0F51299

void 0xAA76052DDA9BFC3E(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)



> SET_PED_PATHS_BACK_TO_ORIGINAL - 0xE04B48F2CC926253 0x3F1ABDA4

void SET_PED_PATHS_BACK_TO_ORIGINAL(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)



> GET_RANDOM_VEHICLE_NODE - 0x93E0DB8440B73A7D 0xAD1476EA

BOOL GET_RANDOM_VEHICLE_NODE(float x, float y, float z, float radius, BOOL p4, BOOL p5, BOOL p6, Vector3* outPosition, float* heading)



> GET_STREET_NAME_AT_COORD - 0x2EB41072B4C1E4C0 0xDEBEEFCF

void GET_STREET_NAME_AT_COORD(float x, float y, float z, Hash* streetName, Hash* crossingRoad)

```
Determines the name of the street which is the closest to the given coordinates.

x,y,z - the coordinates of the street
streetName - returns a hash to the name of the street the coords are on
crossingRoad - if the coordinates are on an intersection, a hash to the name of the crossing road

Note: the names are returned as hashes, the strings can be returned using the function UI::GET_STREET_NAME_FROM_HASH_KEY.
```

> GENERATE_DIRECTIONS_TO_COORD - 0xF90125F1F79ECDF8 0xED35C094

Any GENERATE_DIRECTIONS_TO_COORD(float x, float y, float z, Any p3, int* p4, Vehicle* vehicle, float* p6)

```
I'm Not MentaL: 

Example Usage:

Public Function GenerateDirectionsToCoord(Pos As Vector3) As Tuple(Of String, Single, Single)
        Dim f4, f5, f6 As New OutputArgument()
        Native.Function.Call(Hash.GENERATE_DIRECTIONS_TO_COORD, Pos.X, Pos.Y, Pos.Z, True, f4, f5, f6)
        Dim direction As String = f4.GetResult(Of Single)()
        Return New Tuple(Of String, Single, Single)(direction.Substring(0, 1), f5.GetResult(Of Single)(), f6.GetResult(Of Single)())
    End Function

p3 I use 1

direction:
0 = You Have Arrive
1 = Recalculating Route, Please make a u-turn where safe
2 = Please Proceed the Highlighted Route
3 = Keep Left (unsure)
4 = In (distToNxJunction) Turn Left
5 = In (distToNxJunction) Turn Right
6 = Keep Right (unsure)
7 = In (distToNxJunction) Go Straight Ahead
8 = In (distToNxJunction) Join the freeway
9 = In (distToNxJunction) Exit Freeway

return value set to 0 always
```

> SET_IGNORE_NO_GPS_FLAG - 0x72751156E7678833 0xB72CF194

void SET_IGNORE_NO_GPS_FLAG(BOOL ignore)



> 0x1FC289A0C3FF470F 0x90DF7A4C

Any 0x1FC289A0C3FF470F(BOOL p0)



> SET_GPS_DISABLED_ZONE - 0xDC20483CD3DD5201 0x720B8073

void SET_GPS_DISABLED_ZONE(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5)



> 0xBBB45C3CF5C8AA85 0x4B770634

Any 0xBBB45C3CF5C8AA85()



> 0x869DAACBBE9FA006 0x286F82CC

Any 0x869DAACBBE9FA006()



> 0x16F46FB18C8009E4 0xF6422F9A

Any 0x16F46FB18C8009E4(Any p0, Any p1, Any p2, Any p3, Any p4)



> IS_POINT_ON_ROAD - 0x125BF4ABFC536B09 0xCF198055

BOOL IS_POINT_ON_ROAD(float x, float y, float z, Vehicle vehicle)

```
Gets a value indicating whether the specified position is on a road.
The vehicle parameter is not implemented (ignored).

-MulleDK19
```

> 0xD3A6A0EF48823A8C 

Any 0xD3A6A0EF48823A8C()



> 0xD0BC1C6FB18EE154 

void 0xD0BC1C6FB18EE154(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)



> 0x2801D0012266DF07 

void 0x2801D0012266DF07(Any p0)



> ADD_NAVMESH_REQUIRED_REGION - 0x387EAD7EE42F6685 0x12B086EA

void ADD_NAVMESH_REQUIRED_REGION(float p0, float p1, float p2)



> REMOVE_NAVMESH_REQUIRED_REGIONS - 0x916F0A3CDEC3445E 0x637BB680

void REMOVE_NAVMESH_REQUIRED_REGIONS()



> DISABLE_NAVMESH_IN_AREA - 0x4C8872D8CDBE1B8B 0x6E37F132

void DISABLE_NAVMESH_IN_AREA(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6)



> ARE_ALL_NAVMESH_REGIONS_LOADED - 0x8415D95B194A3AEA 0x34C4E789

BOOL ARE_ALL_NAVMESH_REGIONS_LOADED()



> IS_NAVMESH_LOADED_IN_AREA - 0xF813C7E63F9062A5 0x4C2BA99E

BOOL IS_NAVMESH_LOADED_IN_AREA(float x1, float y1, float z1, float x2, float y2, float z2)

```
Returns whether navmesh for the region is loaded. The region is a rectangular prism defined by it's top left deepest corner to it's bottom right shallowest corner.

If you can re-word this so it makes more sense, please do. I'm horrible with words sometimes...
```

> 0x01708E8DD3FF8C65 

Any 0x01708E8DD3FF8C65(float p0, float p1, float p2, float p3, float p4, float p5)



> ADD_NAVMESH_BLOCKING_OBJECT - 0xFCD5C8E06E502F5A 0x2952BA56

Any ADD_NAVMESH_BLOCKING_OBJECT(float p0, float p1, float p2, float p3, float p4, float p5, float p6, BOOL p7, Any p8)



> UPDATE_NAVMESH_BLOCKING_OBJECT - 0x109E99373F290687 0x4E9776D0

void UPDATE_NAVMESH_BLOCKING_OBJECT(Any p0, float p1, float p2, float p3, float p4, float p5, float p6, float p7, Any p8)



> REMOVE_NAVMESH_BLOCKING_OBJECT - 0x46399A7895957C0E 0x098602B0

void REMOVE_NAVMESH_BLOCKING_OBJECT(Any p0)



> 0x0EAEB0DB4B132399 0x4B67D7EE

BOOL 0x0EAEB0DB4B132399(Any p0)



> 0x29C24BFBED8AB8FB 0x3FE8C5A0

float 0x29C24BFBED8AB8FB(float p0, float p1)



> 0x8ABE8608576D9CE3 0x3ED21C90

float 0x8ABE8608576D9CE3(float p0, float p1, float p2, float p3)



> 0x336511A34F2E5185 0xA07C5B7D

float 0x336511A34F2E5185(float left, float right)

```
calculates two distances  
```

> 0x3599D741C9AC6310 0x76751DD4

float 0x3599D741C9AC6310(float p0, float p1, float p2, float p3)



> CALCULATE_TRAVEL_DISTANCE_BETWEEN_POINTS - 0xADD95C7005C4A197 0xB114489B

float CALCULATE_TRAVEL_DISTANCE_BETWEEN_POINTS(float x1, float y1, float z1, float x2, float y2, float z2)

```
Calculates the travel distance between a set of points.

Doesn't seem to correlate with distance on gps sometimes.
```

