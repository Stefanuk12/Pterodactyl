# Installation

- [How to install Pterodactyl](https://www.youtube.com/watch?v=E2hEork-DYc)
- [How to install Pterodactyl eggs](https://youtu.be/qcfM3_99kNs?t=95)

**Do not install on a virtual machine, it's highly recommended you get a virtual private server**

# Notice

1. Please note that this may take a lot of CPU. There are a few fixes.
   - 100% CPU Limit and allocate additional cores
   - Install the [Liquorix](https://liquorix.net/#install) kernel which can reduce usage by 30%+
2. Make sure to set your RCON password to something very secure (30 characters, symbols, etc.)

# Using Mounts

It is highly recommended that you do this. Majority of the files that a game server needs (i.e. the zone files) will not change between servers. Instead, you can setup a mount which allows certain eggs and nodes to access a shared resource.

For more information, please refer to the [official documentation](https://pterodactyl.io/guides/mounts.html).

**Make sure it is read only**
  
# [Plutonium](games/egg-plutonium.json)

## Stats

- Each server roughly takes up 3-5 GiB of disk space, if slimmed correctly
  - IW4X would take 5-7 GiB
- Each server takes up roughly 0.5-1 GiB of memory usage
- CPU usage is rougly between 40% and 100%

## IW4M

This egg does not have IW4M Admin built in, instead it has the log server. You should have one instance of IW4M Admin in another container which controls **all** other Plutonium servers.

For more information on how to setup, please refer to the [IW4M Egg](#config)

*starts 30 seconds after server run*

# [BOIII](games/egg-boiii.json)

## Stats

- Each server roughly takes up 3-4 GiB of disk space, if slimmed correctly
- Each server takes up roughly 2-4 GiB of memory usage
- CPU usage is rougly between 40% and 100%

## IW4M

Please refer to [this](#iw4m)

# [IW4M](misc/egg-iw4madmin.json)

## Stats

- Each server roughly takes up 100 MiB of disk space
- Each server takes up roughly 200-400 MiB of memory usage
- CPU usage is usaully quite low (below 5%) but can spike up to 200% on startup

## Setup

- Webfront is automatically configurated on server start, so do not change (all changes will be overridden)
- You must set the servers within `/Configuration/IW4MAdminSettings.json` yourself. 
  - The IP address, port, and RCON password can be found within the server panel
  - Make sure to set the `rcon_password` within your `server.cfg`, if the egg does not do it for you
  
## Config

For each server set **either** the:
- `ManualLogPath` to something unique. You can name it something like `logs/` followed by the port of the server then `.log`. For example: `logs/1025.log`
- **Or** set the `GameLogServerUrl` to `http://SERVER_IP:PORT` (replace SERVER_IP, and PORT of course)

**NOTE IF USING T7**: You must set `ManualLogPath` to the **full** path, regardless if you are using a `GameLogServerUrl` or not.

### Example

```json
{
  "IPAddress": "SERVER_IP",
  "Port": PORT,
  "Password": "RCON_PASSWORD",
  "Rules": [],
  "AutoMessages": [],
  "ManualLogPath": null,
  "RConParserVersion": "Plutonium T6 Parser",
  "EventParserVersion": "Plutonium T6 Parser",
  "ReservedSlotNumber": 0,
  "GameLogServerUrl": "http://SERVER_IP:PORT",
  "CustomHostname": null
},
```
**OR**
```json
{
  "IPAddress": "SERVER_IP",
  "Port": PORT,
  "Password": "RCON_PASSWORD",
  "Rules": [],
  "AutoMessages": [],
  "ManualLogPath": "logs/PORT.log",
  "RConParserVersion": "Plutonium T6 Parser",
  "EventParserVersion": "Plutonium T6 Parser",
  "ReservedSlotNumber": 0,
  "GameLogServerUrl": null,
  "CustomHostname": null
}
```