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

**resource.cfg** ([More Information here](Resources/Resource.cfg))

```json
{
    "type": "csharp",
	"main": "AltV.Net.Example.dll"
}
```

#### Client-Files

**Folder Structure**

```
resources/
└── my-example-client-resource/
    ├── client.mjs
    └── resource.cfg
altv-server.exe
```

**resource.cfg** ([More Information here](Resources/Resource.cfg))

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

**resource.cfg** ([More Information here](Resources/Resource.cfg))

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
    "stream/assets/vehicles/vehicles_s2000_interior.ytd",
    ...
  ],
  "meta": {
    "stream/carcols.meta": "CARCOLS_FILE",
    "stream/carvariations.meta": "VEHICLE_VARIATION_FILE",
    "stream/handling.meta": "HANDLING_FILE",
    ...
  }
}
```



## Events

## Vehicle

## Player