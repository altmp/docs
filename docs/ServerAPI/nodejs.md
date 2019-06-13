# NodeJS API

This documentation has been automatically generated based on source code from branch `{BRANCH}` at `{DATETIME}`

**DISCLAIMER**: Current Client API and documentation are heavy Work In Progress! Documentation doesn't contain all available features and it can contain some misleading information

## Modules
* [alt](docs/ServerAPI/nodejs/modules/alt/index.md)
* [events](docs/ServerAPI/nodejs/modules/events/index.md)

## Server Structure

**Folder Structure**

```
modules/
└── node-module.dll
resources/
└── myresource/
    ├── resource.cfg
    ├── server/
    |   └── server.mjs
    └── client/
        └── client.mjs
node_modules/
package.json
server.cfg
```

** resource.cfg **
```
type: js,
main: server/server.mjs,
client-main: client/client.mjs,
client-files: [
    client/*
],
deps: [ ]
```
