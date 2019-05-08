
# Resource Config #

## Fields

| Key | Type | Description |
| - | - | - |
| type | string ("js" or "csharp") | (Serverside) Language of the resource |
| deps | string array | Resource dependencies (deps will be started before this resource) |
| main | string | Serverside entry point of the resource, e.g. 'server.mjs' or 'server.dll' |
| client-main | string | Clientside entry point of the resource, e.g. 'client.js'  |
| client-files | string array | Clientside files (you have to add your client-main file here too!) |


## Examples

**Example resource.cfg**

```
type: js,

main: index.mjs,
client-main: client.mjs,
deps: [
  chat
]

client-files: [
  client.mjs
  client/html/*
]
```
