# Networkcash

> NETWORK_INITIALIZE_CASH - 0x3DA5ECD1A56CBA6D 0x66DA9935

void NETWORK_INITIALIZE_CASH(int p0, int p1)



> NETWORK_DELETE_CHARACTER - 0x05A50AF38947EB8D 0xA9F7E9C3

void NETWORK_DELETE_CHARACTER(int characterIndex, BOOL p1, BOOL p2)

```
Note the 2nd parameters are always 1, 0. I have a feeling it deals with your money, wallet, bank. So when you delete the character it of course wipes the wallet cash at that time. So if that was the case, it would be eg, NETWORK_DELETE_CHARACTER(characterIndex, deleteWalletCash, deleteBankCash);
```

> 0xA921DED15FDF28F5 0x19F0C471

void 0xA921DED15FDF28F5(Any p0)



> NETWORK_GIVE_PLAYER_JOBSHARE_CASH - 0xFB18DF9CB95E0105 0xC6047FDB

void NETWORK_GIVE_PLAYER_JOBSHARE_CASH(int amount, Player* player)



> NETWORK_RECEIVE_PLAYER_JOBSHARE_CASH - 0x56A3B51944C50598 0x4ED71C1A

void NETWORK_RECEIVE_PLAYER_JOBSHARE_CASH(int amount, Player* player)



> 0x1C2473301B1C66BA 0xA27B9FE8

Any 0x1C2473301B1C66BA()

```
NETWORK_CAN_R??? or NETWORK_CAN_S???
```

> NETWORK_REFUND_CASH - 0xF9C812CD7C46E817 0x07C92F21

void NETWORK_REFUND_CASH(int index, char* context, char* reason, BOOL unk)

```
index
-------
See function sub_1005 in am_boat_taxi.ysc

context
----------
'BACKUP_VAGOS'
'BACKUP_LOST'
'BACKUP_FAMILIES'
'HIRE_MUGGER'
'HIRE_MERCENARY'
'BUY_CARDROPOFF'
'HELI_PICKUP'
'BOAT_PICKUP'
'CLEAR_WANTED'
'HEAD_2_HEAD'
'CHALLENGE'
'SHARE_LAST_JOB'
'DEFAULT'

reason
---------
'NOTREACHTARGET'
'TARGET_ESCAPE'
'DELIVERY_FAIL'
'NOT_USED'
'TEAM_QUIT'
'SERVER_ERROR'
'RECEIVE_LJ_L'
'CHALLENGE_PLAYER_LEFT'
'DEFAULT'

unk
-----
Unknown bool value


```

> 0x81404F3DC124FE5B 0x8474E6F0

BOOL 0x81404F3DC124FE5B(Any p0, BOOL p1, BOOL p2)



> NETWORK_CAN_BET - 0x3A54E33660DED67F 0xE3802533

BOOL NETWORK_CAN_BET(Any p0)



> NETWORK_EARN_FROM_PICKUP - 0xED1517D3AF17C698 0x70A0ED62

Any NETWORK_EARN_FROM_PICKUP(int amount)



> 0xA03D4ACE0A3284CE 0x33C20BC4

void 0xA03D4ACE0A3284CE(int amount)



> _NETWORK_EARN_FROM_BAG - 0xF514621E8EA463D0 0x30B3EC0A

void _NETWORK_EARN_FROM_BAG(int amount)

```
For the money bags that drop a max of $40,000. Often called 40k bags.

Most likely NETWORK_EARN_FROM_ROB***
```

> _NETWORK_EARN_FROM_CRATE_DROP - 0xB1CC1B9EC3007A2A 0xEAF04923

void _NETWORK_EARN_FROM_CRATE_DROP(int amount)



> NETWORK_EARN_FROM_BETTING - 0x827A5BA1A44ACA6D 0xA0F7F07C

void NETWORK_EARN_FROM_BETTING(int amount, char* p1)



> NETWORK_EARN_FROM_JOB - 0xB2CC4836834E8A98 0x0B6997FC

void NETWORK_EARN_FROM_JOB(int amount, char* p1)



> 0x61326EE6DF15B0CA 0x5E81F55C

void 0x61326EE6DF15B0CA(Any p0, Any* p1)

```
Pretty sure this is actually a hash collision.
It should be NETWORK_EARN_FROM_A*** or NETWORK_EARN_FROM_B***
```

> 0x2B171E6B2F64D8DF 0x2BEFB6C4

void 0x2B171E6B2F64D8DF(Any p0, Any* p1, BOOL p2)



> NETWORK_EARN_FROM_BOUNTY - 0x131BB5DA15453ACF 0x127F2DAE

void NETWORK_EARN_FROM_BOUNTY(int amount, int* playerHandle, Any* p2, Any p3)



> NETWORK_EARN_FROM_IMPORT_EXPORT - 0xF92A014A634442D6 0xF11FC458

void NETWORK_EARN_FROM_IMPORT_EXPORT(Any p0, Any p1)



> NETWORK_EARN_FROM_HOLDUPS - 0x45B8154E077D9E4D 0xE6B90E9C

void NETWORK_EARN_FROM_HOLDUPS(int amount)



> NETWORK_EARN_FROM_PROPERTY - 0x849648349D77F5C5 0x9BE4F7E1

void NETWORK_EARN_FROM_PROPERTY(int amount, Hash propertyName)



> 0x515B4A22E4D3C6D7 0x866004A8

void 0x515B4A22E4D3C6D7(Any p0, Any p1)

```
DSPORT
```

> 0x4337511FA8221D36 0xCC068380

void 0x4337511FA8221D36(int amount)



> NETWORK_EARN_FROM_ROCKSTAR - 0x02CE1D6AC0FC73EA 0x5A3733CC

void NETWORK_EARN_FROM_ROCKSTAR(int amount)

```
This merely adds an entry in the Network Transaction Log; 
it does not grant cash to the player (on PC).

Max value for amount is 9999999.
```

> NETWORK_EARN_FROM_VEHICLE - 0xB539BD8A4C1EECF8 0xF803589D

void NETWORK_EARN_FROM_VEHICLE(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7)

```
Now has 8 params.
```

> 0x3F4D00167E41E0AD 0x96B8BEE8

void 0x3F4D00167E41E0AD(Any p0, Any p1, Any p2, Any p3, Any p4, Any p5, Any p6, Any p7, Any p8)

```
Now has 9 parameters.
```

> 0x6EA318C91C1A8786 

void 0x6EA318C91C1A8786(int p0, char* p1, int p2)

```
Console Hash - 0xAB6BD72F = NETWORK_EARN_FROM_DAILY_OBJECTIVE
```

> 0xFB6DB092FBAE29E6 

void 0xFB6DB092FBAE29E6(int p0, char* p1, Any* p2)

```
Console Hash - 0xA14CC95D = NETWORK_EARN_FROM_AMBIENT_JOB
Example for p1: 'AM_DISTRACT_COPS'
```

> 0x6816FB4416760775 

void 0x6816FB4416760775(Any p0, Any* p1, Any* p2)

```
Console Hash - 0xBEE23713 = NETWORK_EARN_FROM_JOB_BONUS
```

> _HAS_ITEM_BEEN_UNLOCKED - 0xAB3CAA6B422164DA 0x5AA379D9

BOOL _HAS_ITEM_BEEN_UNLOCKED(Any p0, BOOL p1, BOOL p2, BOOL p3, Any p4)



> 0x7303E27CC6532080 

BOOL 0x7303E27CC6532080(Any p0, BOOL p1, BOOL p2, BOOL p3, Any* p4, Any p5)

```
NETWORK_CAN_R??? or NETWORK_CAN_S???
```

> NETWORK_BUY_ITEM - 0xF0077C797F66A355 0xA07B6368

void NETWORK_BUY_ITEM(Ped player, Hash item, Any p2, Any p3, BOOL p4, char* item_name, Any p6, Any p7, Any p8, BOOL p9)



> NETWORK_SPENT_TAXI - 0x17C3A7D31EAE39F9 0x1F3DB3E3

void NETWORK_SPENT_TAXI(int amount, BOOL p1, BOOL p2)



> 0x5FD5ED82CBBE9989 0xBE70849B

void 0x5FD5ED82CBBE9989(Any p0, BOOL p1, BOOL p2)



> 0xAFE08B35EC0C9EAE 0x451A2644

void 0xAFE08B35EC0C9EAE(Any p0, BOOL p1, BOOL p2)



> 0x9346E14F2AF74D46 0x224A3488

void 0x9346E14F2AF74D46(Any p0, Any* p1, BOOL p2, BOOL p3)



> NETWORK_SPENT_BETTING - 0x1C436FD11FFA692F 0xF8A07513

void NETWORK_SPENT_BETTING(Any p0, Any p1, Any* p2, BOOL p3, BOOL p4)



> 0xEE99784E4467689C 0x8957038E

void 0xEE99784E4467689C(Any p0, BOOL p1, Any p2, BOOL p3)



> NETWORK_BUY_HEALTHCARE - 0xD9B067E55253E3DD 0x832150E5

void NETWORK_BUY_HEALTHCARE(int cost, BOOL p1, BOOL p2)



> NETWORK_BUY_AIRSTRIKE - 0x763B4BD305338F19 0x40470683

void NETWORK_BUY_AIRSTRIKE(int cost, BOOL p1, BOOL p2)

```
p1 = 0 (always)
p2 = 1 (always)
```

> NETWORK_BUY_HELI_STRIKE - 0x81AA4610E3FD3A69 0x047547D4

void NETWORK_BUY_HELI_STRIKE(int cost, BOOL p1, BOOL p2)

```
p1 = 0 (always)
p2 = 1 (always)
```

> NETWORK_SPENT_AMMO_DROP - 0xB162DC95C0A3317B 0x4B643076

void NETWORK_SPENT_AMMO_DROP(Any p0, BOOL p1, BOOL p2)



> NETWORK_BUY_BOUNTY - 0x7B718E197453F2D9 0xCB89CBE0

void NETWORK_BUY_BOUNTY(int amount, Player victim, BOOL p2, BOOL p3)

```
p1 is just an assumption. p2 was false and p3 was true.
```

> NETWORK_BUY_PROPERTY - 0x650A08A280870AF6 0x7D479AAB

void NETWORK_BUY_PROPERTY(float propertyCost, Hash propertyName, BOOL p2, BOOL p3)



> NETWORK_SPENT_HELI_PICKUP - 0x7BF1D73DB2ECA492 0x27EEBCAB

void NETWORK_SPENT_HELI_PICKUP(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_BOAT_PICKUP - 0x524EE43A37232C00 0xB241CABD

void NETWORK_SPENT_BOAT_PICKUP(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_BULL_SHARK - 0xA6DD8458CE24012C 0xDE7D398C

void NETWORK_SPENT_BULL_SHARK(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_CASH_DROP - 0x289016EC778D60E0 0x87BD1D11

void NETWORK_SPENT_CASH_DROP(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_HIRE_MUGGER - 0xE404BFB981665BF0 0xE792C4A5

void NETWORK_SPENT_HIRE_MUGGER(Any p0, BOOL p1, BOOL p2)

```
Only used once in a script (am_contact_requests)
p1 = 0
p2 = 1
```

> 0x995A65F15F581359 0xE6AAA0D5

void 0x995A65F15F581359(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_HIRE_MERCENARY - 0xE7B80E2BF9D80BD6 0x99CF02C4

void NETWORK_SPENT_HIRE_MERCENARY(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_BUY_WANTEDLEVEL - 0xE1B13771A843C4F6 0xE7CB4F95

void NETWORK_SPENT_BUY_WANTEDLEVEL(Any p0, Any* p1, BOOL p2, BOOL p3)



> NETWORK_SPENT_BUY_OFFTHERADAR - 0xA628A745E2275C5D 0x20DDCF2F

void NETWORK_SPENT_BUY_OFFTHERADAR(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_BUY_REVEAL_PLAYERS - 0x6E176F1B18BC0637 0x2F7836E2

void NETWORK_SPENT_BUY_REVEAL_PLAYERS(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_CARWASH - 0xEC03C719DB2F4306 0x8283E028

void NETWORK_SPENT_CARWASH(Any p0, Any p1, Any p2, BOOL p3, BOOL p4)



> NETWORK_SPENT_CINEMA - 0x6B38ECB05A63A685 0x1100CAF5

void NETWORK_SPENT_CINEMA(Any p0, Any p1, BOOL p2, BOOL p3)



> NETWORK_SPENT_TELESCOPE - 0x7FE61782AD94CC09 0xAE7FF044

void NETWORK_SPENT_TELESCOPE(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_HOLDUPS - 0xD9B86B9872039763 0x1B3803B1

void NETWORK_SPENT_HOLDUPS(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_BUY_PASSIVE_MODE - 0x6D3A430D1A809179 0x7E97C92C

void NETWORK_SPENT_BUY_PASSIVE_MODE(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_PROSTITUTES - 0xB21B89501CFAC79E 0x78436D07

void NETWORK_SPENT_PROSTITUTES(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_ARREST_BAIL - 0x812F5488B1B2A299 0x5AEE2FC1

void NETWORK_SPENT_ARREST_BAIL(Any p0, BOOL p1, BOOL p2)



> NETWORK_SPENT_PAY_VEHICLE_INSURANCE_PREMIUM - 0x9FF28D88C766E3E8 0x4E665BB2

void NETWORK_SPENT_PAY_VEHICLE_INSURANCE_PREMIUM(Any p0, Hash VehicleModel, Any* p2, BOOL p3, BOOL p4)

```
According to how I understood this in the freemode script alone,
The first parameter is determined by a function named, func_5749 within the freemode script which has a list of all the vehicles and a set price to return which some vehicles deals with globals as well. So the first parameter is basically the set in stone insurance cost it's gonna charge you for that specific vehicle model.

The second parameter whoever put it was right, they call GET_ENTITY_MODEL with the vehicle as the paremeter.

The third parameter is the network handle as they call their little struct&lt;13&gt; func or atleast how the script decompiled it to look which in lamens terms just returns the network handle of the previous owner based on DECOR_GET_INT(vehicle, 'Previous_Owner').

The fourth parameter is a bool that returns true/false depending on if your bank balance is greater then 0.

The fifth and last parameter is a bool that returns true/false depending on if you have the money for the car based on the cost returned by func_5749. In the freemode script eg,
bool hasTheMoney = NETWORKCASH::_GET_BANK_BALANCE() &lt; carCost.
```

> NETWORK_SPENT_CALL_PLAYER - 0xACDE7185B374177C 0x1A89B5FC

void NETWORK_SPENT_CALL_PLAYER(Any p0, Any* p1, BOOL p2, BOOL p3)



> NETWORK_SPENT_BOUNTY - 0x29B260B84947DFCC 0x3401FC96

void NETWORK_SPENT_BOUNTY(Any p0, BOOL p1, BOOL p2)



> 0x6A445B64ED7ABEB5 0x54198922

void 0x6A445B64ED7ABEB5(Any p0, BOOL p1, BOOL p2)



> PROCESS_CASH_GIFT - 0x20194D48EAEC9A41 0xC5D8B1E9

Any PROCESS_CASH_GIFT(Any p0, Any p1, Any p2)

```
This isn't a hash collision. It is used to give the player cash via the CASH_GIFT stats.
```

> 0x7C99101F7FCE2EE5 0x3D96A21C

void 0x7C99101F7FCE2EE5(Any p0, Any p1, BOOL p2, BOOL p3)



> 0xD5BB406F4E04019F 0x2E51C61C

void 0xD5BB406F4E04019F(Any p0, BOOL p1, BOOL p2)



> 0x8204DA7934DF3155 0xD57A5125

void 0x8204DA7934DF3155(Any p0, BOOL p1, BOOL p2)



> 0x9D26502BB97BFE62 

void 0x9D26502BB97BFE62(Any p0, BOOL p1, BOOL p2)

```
Console Hash 0xF4287778 = NETWORK_SPENT_REQUEST_HEIST
```

> 0x8A7B3952DD64D2B5 0xD9622D64

void 0x8A7B3952DD64D2B5(Any p0, Any p1, BOOL p2, BOOL p3)

```
The first parameter is the amount spent which is store in a global when this native is called. The global returns 10. Which is the price for both rides.

The last 3 parameters are, 
2,0,1 in the am_ferriswheel.c
1,0,1 in the am_rollercoaster.c

```

> 0x7C4FCCD2E4DEB394 

Any 0x7C4FCCD2E4DEB394()

```
Used for cash gifts
Console Hash - 0x468CC978
```

> _GET_BANK_BALANCE - 0x76EF28DA05EA395A 0x16184FB5

int _GET_BANK_BALANCE()

```
From what I can see in ida, I believe it retrieves the players online bank balance.
```

> _WALLET_BALANCE - 0xA40F9C2623F6A8B5 0x4F5B781C

int _WALLET_BALANCE(int player)

```
From what I understand, it retrieves STAT_WALLET_BALANCE for the specified character (-1 means use MPPLY_LAST_MP_CHAR)
```

> 0x5CBAD97E059E1B94 0xADF8F882

Any 0x5CBAD97E059E1B94()



> 0xA6FA3979BED01B81 

Any 0xA6FA3979BED01B81()

```
Console Hash: Probably 0xAA7EA3BD
```

> 0xDC18531D7019A535 

BOOL 0xDC18531D7019A535(Any p0, Any p1)

```
probably 0x3461981 on console
```

> NETWORK_CAN_RECEIVE_PLAYER_CASH - 0x5D17BE59D2123284 0x41F5F10E

BOOL NETWORK_CAN_RECEIVE_PLAYER_CASH(Any p0, Any p1, Any p2, Any p3)



> 0xF70EFA14FE091429 0x8B755993

Any 0xF70EFA14FE091429(Any p0)



> 0xE260E0BB9CD995AC 0x8F266745

BOOL 0xE260E0BB9CD995AC(Any p0)



> 0xE154B48B68EF72BC 0x531E4892

Any 0xE154B48B68EF72BC(Any p0)

```
This function is hard-coded to always return 1.
```

> 0x6FCF8DDEA146C45B 0xB96C7ABE

Any 0x6FCF8DDEA146C45B(Any p0)

```
This function is hard-coded to always return 1.
```

