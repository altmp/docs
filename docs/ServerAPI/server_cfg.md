# Server Config #

## Fields

| Field Name   | Available Values                    | Description                                      |
| ------------ | ----------------------------------- | ------------------------------------------------ |
| name  	   |  any string 			             | displayname of the server					    |
| host 		   |  any IPv4 or IPv6 Address as string | binding address of the server					|
| port 		   |  0 to 65535						 | Port of the server (Default 7788)                |
| players 	   |  0 to xxx							 | amount of players that can join					|
| announce 	   |  true or false						 | true = server is shown in masterlist		        |
| gamemode 	   |  any string						 | gamemodename shown in the masterlist             |
| website 	   |  any string                         | url of website shown in the masterlist           |
| language     |  any string						 | language shown in the masterlist	     	        |
| description  |  any string						 | description shown in the masterlist              |
| modules      |  "node-module", "csharp-module"     | modules that are started with the server         |
| resources    |  string list						 | list of resources wich staring with the server   |



## Examples

**Example server.cfg**

```
name: "TestServer",
host: "0.0.0.0",
port: 7788,
players: 1024,
announce: true,
gamemode: "Freeroam",
website: "test",
language: "en",
description: "test",
modules: ["csharp-module"],
resources: [
     "example"
]
```