# PPE Essentials

[![Modrinth](https://img.shields.io/badge/Modrinth-PPE%20Essentials-00AF5C?style=flat&logo=modrinth&logoColor=white)](https://modrinth.com/mod/ppe-essentials) [![CurseForge](https://img.shields.io/badge/CurseForge-PPE%20Essentials-F16436?style=flat&logo=curseforge&logoColor=white)](https://www.curseforge.com/minecraft/mc-mods/ppe-essentials) [![GitHub](https://img.shields.io/badge/GitHub-PurpleEastZQ%2Fppe--essentials-181717?style=flat&logo=github&logoColor=white)](https://github.com/PurpleEastZQ/ppe-essentials)

PPE Essentials is a lightweight mod that adds useful commands (like /tpa /repeat) and tweaks, with highly configurable options.

> **Kawa build:** This is an unofficial derivative of [PurpleEastZQ/ppe-essentials](https://github.com/PurpleEastZQ/ppe-essentials). It adds the `[blacklists]` dimension configuration described below. See [NOTICE.md](NOTICE.md) for upstream attribution and licensing.

![PPE Essentials command preview](https://raw.githubusercontent.com/PurpleEastZQ/ppe-essentials/master/artwork/ppe-essentials-help-preview.png)

## Features

- Server-side only mod (Can still be installed on your client for singleplayer use.)
- Configurable command toggles, permission levels and more.
- Configurable protection against creeper, enderman, and ravager block damage.
- Ready out of the box; Fabric only requires Fabric API.
- Polished messages with clickable buttons, titles, and sounds.
- Player-selection menus for `/tpa` and `/tpahere` when no target is provided.
- Multilingual support with automatic client language detection and a configurable `fallbackLanguage`.
- Persistent player data for homes, warps, back locations, fly, god mode, and notice triggers.

## Supported Versions

- NeoForge 1.21.1, 26.1.2
- Fabric 1.21.1, 26.1.2

## Commands

### Teleport

| Command | Description |
| --- | --- |
| `/tpa [player]` | Request to teleport to another player, or open the player menu when omitted. |
| `/tpaa` | Accept a pending TPA request. |
| `/tpad` | Deny a pending TPA request. |
| `/tpaauto` | Toggle automatic TPA acceptance. |
| `/tpahere [player]` | Request another player to teleport to you, or open the player menu when omitted. |
| `/tpaherea` | Accept a pending TPAhere request. |
| `/tpahered` | Deny a pending TPAhere request. |
| `/rtp` | Randomly teleport nearby. |
| `/spawn` | Teleport to world spawn. |
| `/back` or `/dback` | Return to your last death location. |
| `/tback` | Return to your previous teleport location. |

### Homes And Warps

| Command | Description |
| --- | --- |
| `/sethome` | Set your home. |
| `/home` | Teleport home. |
| `/delhome` | Delete your home. |
| `/setwarp <name>` | Create a server warp. |
| `/warp <name>` | Teleport to a server warp. |
| `/delwarp <name>` | Delete a server warp. |

### Utility And Admin

| Command | Description |
| --- | --- |
| `/trash` | Open a temporary trash inventory that clears on close. |
| `/suicide` | Kill yourself. |
| `/heal [player]` | Heal yourself or another player. |
| `/fly [player]` | Toggle persistent flight for yourself or another player. |
| `/god [player]` | Toggle god mode for yourself or another player. |
| `/repeat <times> [command]` | Repeat your last command or a specified command. |
| `/ppe-ess help` | Show the command list. Disabled or unavailable commands are shown in red. |
| `/ppe-ess reset all` | Clear all player data. |
| `/ppe-ess reset notice` | Clear notice trigger data. |

## Configuration

All configuration options are located in `config/ppe_essentials-common.toml`.

### Teleport Dimension Blacklist

`[blacklists]` restricts dimensions for PPE Essentials teleport commands only. It does not affect vanilla commands or teleport commands from other mods.

```toml
[blacklists]
# Dimensions players aren't permitted to run teleport commands in.
# Default: []
from = ["void:the_nothing01", "void:the_nothing02"]

# Dimensions players aren't permitted to teleport into.
# Default: []
to = ["void:the_nothing01", "void:the_nothing02"]
```

## Installation & Building

Prebuilt Kawa jars are provided in [`dist/`](dist/). Download the jar matching your Minecraft version and mod loader, then place it in the `mods` folder.

| Minecraft | NeoForge | Fabric |
| --- | --- | --- |
| 1.21.1 | `dist/ppe_essentials-neoforge-1.21.1-1.7.0.jar` | `dist/ppe_essentials-fabric-1.21.1-1.7.0.jar` |
| 26.1.2 | `dist/ppe_essentials-neoforge-26.1.2-1.7.0.jar` | `dist/ppe_essentials-fabric-26.1.2-1.7.0.jar` |

SHA-256 checksums are available in [`dist/SHA256SUMS.txt`](dist/SHA256SUMS.txt).

Fabric installations also require Fabric API.

To build all supported versions from source using JDK 25:

```powershell
.\build-all-versions.ps1
```

To build a single target:

```powershell
.\gradlew.bat buildNeoForge --no-daemon --no-configuration-cache
.\gradlew.bat buildFabric "-Ptarget_minecraft_version=26.1.2" --no-daemon --no-configuration-cache
```

Built jars are generated under `build/libs/`.
