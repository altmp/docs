# Dlc1

> 0x278F76C3B0A8F109 0x71D0CF3E

int 0x278F76C3B0A8F109(int character)

```
_GET_NUM_DECORATIONS
only documented to be continued...
```

> 0xFF56381874F82086 0x2E9D628C

BOOL 0xFF56381874F82086(int p0, int p1, int* outComponent)



> INIT_SHOP_PED_COMPONENT - 0x1E8C308FD312C036 0xB818C7FC

void INIT_SHOP_PED_COMPONENT(int* outComponent)



> INIT_SHOP_PED_PROP - 0xEB0A2B758F7B850F 0xF5659E50

void INIT_SHOP_PED_PROP(int* outProp)



> 0x50F457823CE6EB5F 0xC937FF3D

int 0x50F457823CE6EB5F(int p0, int p1, int p2, int p3)



> _GET_NUM_PROPS_FROM_OUTFIT - 0x9BDF59818B1E38C1 0x594E862C

int _GET_NUM_PROPS_FROM_OUTFIT(int character, int p1, int p2, BOOL p3, int p4, int componentId)

```
character is 0 for Michael, 1 for Franklin, 2 for Trevor, 3 for freemode male, and 4 for freemode female.

componentId is between 0 and 11 and corresponds to the usual component slots.

p1 could be the outfit number; unsure.

p2 is usually -1; unknown function.

p3 appears to be a boolean flag; unknown function.

p4 is usually -1; unknown function.
```

> GET_SHOP_PED_QUERY_COMPONENT - 0x249E310B2D920699 0xC0718904

void GET_SHOP_PED_QUERY_COMPONENT(int componentId, int* outComponent)



> GET_SHOP_PED_COMPONENT - 0x74C0E2A57EC66760 0xB39677C5

void GET_SHOP_PED_COMPONENT(Any p0, Any* p1)



> GET_SHOP_PED_QUERY_PROP - 0xDE44A00999B2837D 0x1D3C1466

void GET_SHOP_PED_QUERY_PROP(Any p0, Any* p1)



> 0x5D5CAFF661DDF6FC 

void 0x5D5CAFF661DDF6FC(Any p0, Any* p1)



> GET_HASH_NAME_FOR_COMPONENT - 0x0368B3A838070348 0xC8A4BF12

Hash GET_HASH_NAME_FOR_COMPONENT(Entity entity, int componentId, int drawableVariant, int textureVariant)



> GET_HASH_NAME_FOR_PROP - 0x5D6160275CAEC8DD 0x7D876DC0

Hash GET_HASH_NAME_FOR_PROP(Entity entity, int componentId, int propIndex, int propTextureIndex)



> 0xC17AD0E5752BECDA 0x159751B4

int 0xC17AD0E5752BECDA(Hash componentHash)



> GET_VARIANT_COMPONENT - 0x6E11F282F11863B6 0xE4FF7103

void GET_VARIANT_COMPONENT(Hash componentHash, int componentId, Any* p2, Any* p3, Any* p4)



> _GET_NUM_FORCED_COMPONENTS - 0xC6B9DB42C04DD8C3 0xCE70F183

int _GET_NUM_FORCED_COMPONENTS(Hash componentHash)

```
Returns number of possible values of the componentId argument of GET_FORCED_COMPONENT.
```

> 0x017568A8182D98A6 

Any 0x017568A8182D98A6(Any p0)



> GET_FORCED_COMPONENT - 0x6C93ED8C2F74859B 0x382C70BE

void GET_FORCED_COMPONENT(Hash componentHash, int componentId, Any* p2, Any* p3, Any* p4)



> 0xE1CA84EBF72E691D 

void 0xE1CA84EBF72E691D(Any p0, Any p1, Any* p2, Any* p3, Any* p4)



> 0x341DE7ED1D2A1BFD 0x8E2C7FD5

BOOL 0x341DE7ED1D2A1BFD(Hash componentHash, Hash drawableSlotHash, BOOL p2)

```
6,000+ calls from scripts, all with either 0 or 1 for p2, that's a boolean in my book
```

> 0xF3FBE2D50A6A8C28 0x1ECD23E7

int 0xF3FBE2D50A6A8C28(int character, BOOL p1)

```
characters

0: Michael
1: Franklin
2: Trevor
3: MPMale
4: MPFemale
```

> GET_SHOP_PED_QUERY_OUTFIT - 0x6D793F03A631FE56 0x2F8013A1

void GET_SHOP_PED_QUERY_OUTFIT(Any p0, Any* outfit)

```
struct Outfit_s
	{
		int mask, torso, pants, parachute, shoes, misc1, tops1, armour, crew, tops2, hat, glasses, earpiece;
		int maskTexture, torsoTexture, pantsTexture, parachuteTexture, shoesTexture, misc1Texture, tops1Texture, 
			armourTexture, crewTexture, tops2Texture, hatTexture, glassesTexture, earpieceTexture;
	};
```

> GET_SHOP_PED_OUTFIT - 0xB7952076E444979D 0xCAFE9209

void GET_SHOP_PED_OUTFIT(Any p0, Any* p1)



> 0x073CA26B079F956E 0x2798F56F

Any 0x073CA26B079F956E(Any p0)



> 0xA9F9C2E0FDE11CBB 0x6641A864

BOOL 0xA9F9C2E0FDE11CBB(Any p0, Any p1, Any* p2)



> _GET_PROP_FROM_OUTFIT - 0x19F2A026EDF0013F 0x818534AC

BOOL _GET_PROP_FROM_OUTFIT(Any outfit, int slot, Any* item)

```
outfit = a structure passing though it - see GET_SHOP_PED_QUERY_OUTFIT
slot - outfit slot
item - hold 3 ints in a struct, you can use Vector3 structure

GET_SHOP_PED_???
```

> GET_NUM_DLC_VEHICLES - 0xA7A866D21CD2329B 0x8EAF9CF6

int GET_NUM_DLC_VEHICLES()



> GET_DLC_VEHICLE_MODEL - 0xECC01B7C5763333C 0xA2201E09

Hash GET_DLC_VEHICLE_MODEL(int dlcVehicleIndex)

```
dlcVehicleIndex is 0 to GET_NUM_DLC_VEHICLS() - 1
```

> GET_DLC_VEHICLE_DATA - 0x33468EDC08E371F6 0xCF428FA4

BOOL GET_DLC_VEHICLE_DATA(int dlcVehicleIndex, Any* outData)

```
dlcVehicleIndex takes a number from 0 - GET_NUM_DLC_VEHICLES() - 1.
outData is a struct of 3 8-byte items.
The Second item in the struct *(Hash *)(outData + 1) is the vehicle hash.
```

> GET_DLC_VEHICLE_FLAGS - 0x5549EE11FA22FCF2 0xAB12738C

int GET_DLC_VEHICLE_FLAGS(int p0)



> GET_NUM_DLC_WEAPONS - 0xEE47635F352DA367 0x2B757E6C

int GET_NUM_DLC_WEAPONS()

```
Gets the total number of DLC weapons.
```

> GET_DLC_WEAPON_DATA - 0x79923CD21BECE14E 0xD88EC8EA

BOOL GET_DLC_WEAPON_DATA(int dlcWeaponIndex, Any* outData)

```

dlcWeaponIndex takes a number from 0 - GET_NUM_DLC_WEAPONS() - 1.
struct DlcWeaponData
{
int emptyCheck; //use DLC1::_IS_DLC_DATA_EMPTY on this
int padding1;
int weaponHash;
int padding2;
int unk;
int padding3;
int weaponCost;
int padding4;
int ammoCost;
int padding5;
int ammoType;
int padding6;
int defaultClipSize;
int padding7;
char nameLabel[64];
char descLabel[64];
char desc2Label[64]; // usually 'the' + name
char upperCaseNameLabel[64];
};
```

> GET_NUM_DLC_WEAPON_COMPONENTS - 0x405425358A7D61FE 0x476B23A9

int GET_NUM_DLC_WEAPON_COMPONENTS(int dlcWeaponIndex)

```
Allowed Values from 0 - DLC1::GET_NUM_DLC_WEAPONS() - 1
```

> GET_DLC_WEAPON_COMPONENT_DATA - 0x6CF598A2957C2BF8 0x4B83FCAF

BOOL GET_DLC_WEAPON_COMPONENT_DATA(Any p0, Any p1, Any* ComponentDataPtr)

```
p0 seems to be the weapon index
p1 seems to be the weapon component index
struct DlcComponentData{
int attachBone;
int padding1;
int bActiveByDefault;
int padding2;
int unk;
int padding3;
int componentHash;
int padding4;
int unk2;
int padding5;
int componentCost;
int padding6;
char nameLabel[64];
char descLabel[64];
};

```

> _IS_DLC_DATA_EMPTY - 0xD4D7B033C3AA243C 0x06396058

BOOL _IS_DLC_DATA_EMPTY(int dlcData)



> 0x0564B9FF9631B82C 0x35BCA844

BOOL 0x0564B9FF9631B82C(Any p0)

```
Use _GET_VEHICLE_MOD_DATA for modData
```

> 0xC098810437312FFF 0x59352658

Any 0xC098810437312FFF(Any p0)

```
Use _GET_VEHICLE_MOD_DATA for modData

Appears to be a GET_DLC_VEHICLE_MOD_* native.
```

