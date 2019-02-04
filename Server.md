# Server API

## Resource Types

### C# - Resource

**Folder Structure**

```
modules/
└── csharp-module.dll
resources/
└── my-example-csharp-resource/
    ├── Alt.Net.Example.dll
    ├── resource.cfg
    └── ... (any .dll dependency like "AltV.Net.dll" or "mysql.dll")
```

**resource.cfg**

```json
{
    "type": "csharp",
	"main": "AltV.Net.Example.dll"
}
```

<hr/>

### Client - Resource

**Folder Structure**

```
resources/
└── my-example-client-resource/
    ├── client.mjs
    └── resource.cfg
altv-server.exe
```

**resource.cfg**

```json
{
    "type": "js",
	"client-main": "client.mjs",
	"client-files": [ 
    	"client.mjs" 
    ]
}
```

<hr/>

### DLC - Resource

**Folder Structure**

```
resources/
└── stream-ap2
    ├── resource.cfg
    ├── __stream.cfg
    └── stream/
        ├── assets/
        │   ├── ...
        │   └── ...
        └── xyz.meta
altv-server.exe
```

**resource.cfg**

```json
{
    "type":"dlc",
    "main":"__stream.cfg",
    "name":"stream-ap2"
}
```

**__stream.cfg**

```json
{
  "files": [
    "stream/assets/vehiclemods/sk_atmp_c.yft",
    "stream/assets/vehiclemods/sk_atmp_m.yft",
    "stream/assets/vehiclemods/sk_exh1.yft",
    "stream/assets/vehiclemods/sk_exh2.yft",
    "stream/assets/vehiclemods/sk_exh3.yft",
    "stream/assets/vehiclemods/sk_kaput_b.yft",
    "stream/assets/vehiclemods/sk_kaput_k.yft",
    "stream/assets/vehiclemods/sk_otmp_lip.yft",
    "stream/assets/vehiclemods/sk_otmp_m.yft",
    "stream/assets/vehiclemods/sk_otmp_split.yft",
    "stream/assets/vehiclemods/sk_skirt_c.yft",
    "stream/assets/vehiclemods/sk_skirt_s.yft",
    "stream/assets/vehiclemods/sk_sp_cc.yft",
    "stream/assets/vehiclemods/sk_sp_cr.yft",
    "stream/assets/vehiclemods/sk_sp_lip.yft",
    "stream/assets/vehiclemods/sk_top_mugen.yft",
    "stream/assets/vehicles/ap2.yft",
    "stream/assets/vehicles/ap2.ytd",
    "stream/assets/vehicles/ap2_hi.yft",
    "stream/assets/vehicles/vehicles_s2000_interior.ytd"
  ],
  "meta": {
    "stream/carcols.meta": "CARCOLS_FILE",
    "stream/carvariations.meta": "VEHICLE_VARIATION_FILE",
    "stream/handling.meta": "HANDLING_FILE",
    "stream/vehicles.meta": "VEHICLE_METADATA_FILE"
  }
}
```



## Events

## Vehicle

## Player

