# C# #

## Navigation

* [Getting Started](docs/ServerAPI/csharp/Getting_Started.md)
* [Events & Methods](docs/ServerAPI/csharp/Server_CSharp.md)
* [Events & Methods (Async)](docs/ServerAPI/csharp/Server_CSharp_Async.md)
* [Blip](docs/ServerAPI/csharp/Blip.md)
* [Checkpoint](docs/ServerAPI/csharp/Checkpoint.md)
* [Player](docs/ServerAPI/csharp/Player.md)
* [Position](docs/ServerAPI/csharp/Position.md)
* [Rgba](docs/ServerAPI/csharp/Rgba.md)
* [Rotation](docs/ServerAPI/csharp/Rotation.md)
* [Vehicle](docs/ServerAPI/csharp/Vehicle.md)



## Server Structure

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
"type": "csharp",
"main": "AltV.Net.Example.dll"
```
