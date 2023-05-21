# Installation

- [How to install Pterodactyl](https://www.youtube.com/watch?v=E2hEork-DYc)
- [How to install Pterodactyl eggs](https://youtu.be/qcfM3_99kNs?t=95)

**Do not install on a virtual machine, it's highly recommended you get a virtual private server**

# Notice

Please note that this may take a lot of CPU. There are a few fixes.
- 100% CPU Limit and allocate additional cores
- Install the [Liquorix](https://liquorix.net/#install) kernel which can reduce usage by 30%+
  
# [Plutonium](games/egg-plutonium.json)

This egg is no longer supported and maintained.

# [BOIII](games/egg-boiii.json)

## Server Config

This is the configuration file the server will use. Make sure this file is within the `zone` folder.
- Name it as `server_` then the gamemode (i.e. zm, mp, cp). For example, `server_zm.cfg`

## Mod Folder

If you are using mods, this should be set to `mods` but can be any name. Put all of your workshop mods inside that folder.

## Enable IW4MAdmin

If enabled:
- Automatically installs IW4M on server installation
- Automatically runs IW4M 30 seconds after server starts

## RCON Password

**Highly recommend this is changed. Use 30+ characters with symbols and uppercase, etc**

- Used to send commands to the server remotely

## Log file

The name does not matter but generally set it to `games_` followed by the gamemode (i.e. zm, mp, cp). For example `games_zm`

## Installation Slimming

On server installation, all map files are removed. Only core files are kept which are **needed** for running the server.

# [IW4M](misc/egg-iw4madmin.json)

- Webfront is automatically configurated on server start, so do not change (all changes will be overridden)
- You must set the servers within `/Configuration/IW4MAdminSettings.json` yourself. 
  - The IP address, port, and RCON password can be found within the BOIII's server panel
  - Make sure you set each server's `ManualLogPath` to something unique. You can name it something like `logs/` followed by the port of the server then `.log`. For example: `logs/1025.log`