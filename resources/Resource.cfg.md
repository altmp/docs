# Resource.cfg

This file describes the content and functionality of an resource. This file is located inside the resource root folder.

```
resources/
└── my-example-resource/
    └── resource.cfg
```



## Fields

### General Information

| Field Name | Available Values      | Description                                                  |
| ---------- | --------------------- | ------------------------------------------------------------ |
| type       | `js`, `csharp`, `dlc` | Sets the resource type for the given resource<br />- `js` (Needs **node-module.dll** in Modules Directory)<br />- `csharp` (Needs **csharp-module.dll** in Modules Directory)<br />- `dlc` (No extra Module needed) |
| main       | `<File.Name>`         | Sets the main Script file of the resource<br />(if type is `dlc` then you specific here your __stream.cfg) |
| name       | `Resource Title`      | Sets the name of the resource                                |

### Client-Side

| Field Name   | Available Values                   | Description                                      |
| ------------ | ---------------------------------- | ------------------------------------------------ |
| client-main  | `<FileName.mjs>`                   | Sets the main Client-Script file of the resource |
| client-files | `["FileName.mjs", fileB.mjs, ...]` | Here all client-side files are specified         |



## Example

```json
"type": "js",
"main": "index.mjs",
"client-main": "client.mjs",
"client-files": [
	"client.mjs"
]
```

