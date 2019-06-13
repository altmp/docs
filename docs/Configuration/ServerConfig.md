
# Server Config #

## Fields

| Key | Type | Default value | Description |
| - | - | - | - |
| name | string (max. 64 chars) | New alt:V server | Display name of the server |
| host | string (IPv4 or IPv6) | 0.0.0.0 | Binding address of the server |
| port | number (0 - 65535) | 7788 | Port of the server |
| players | number (1 - 4095) | 10 | Amount of players that can join the server concurrently |
| password | string | *no-password* | Password required to connect to the server |
| announce | boolean (true/false) | false | Announce server to public masterlist? *You need a masterlist token to announce your server!* |
| token | string | *no-token* | Ask @Master-Bot#3667 in https://discord.gg/q3zUUEC for masterlist token |
| gamemode | string (max. 20 chars) | 'unknown' | Gamemode displayed in the masterlist |
| website | string (max. 64 chars) | 'example.com' | Website displayed in the masterlist |
| language | string (max. 20 chars) | 'English' | Language displayed in the masterlist |
| description | string (max. 140 chars) | 'No description provided' | Description displayed in the masterlist |
| modules | string array | [] | Modules that are started with the server ("node-module", "csharp-module") |
| resources | string array | [] | Resources that are started with the server |


## Examples

**Example server.cfg**

```
name: "TestServer",
host: "0.0.0.0",
port: 7788,
players: 1024,
#password: "verysecurepassword", # remove hashtag before password to enable
announce: true, # set to false during development
token: no-token, # only needed when announce: true
gamemode: "Freeroam",
website: "test.com",
language: "en",
description: "test",
modules: ["csharp-module"],
resources: [
  "example"
]
```
