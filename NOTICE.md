# NOTICE

This repository (`ppe-essentials-kawa`) is an unofficial derivative of **PPE Essentials**.

- Upstream repository: https://github.com/PurpleEastZQ/ppe-essentials
- Upstream author: Purple_East
- Upstream license: MIT (see [LICENSE](LICENSE))
- Derivative maintainer: fulide

This derivative is not affiliated with or endorsed by the upstream author.

## Changes in this derivative

- Added the `[blacklists]` configuration section with `from` and `to` dimension lists.
- Teleport commands from PPE Essentials are blocked when the source or destination dimension is blacklisted.
- The restriction applies only to PPE Essentials teleport commands; vanilla and third-party commands are not affected.
- Added localized messages for every bundled language.
- Documented the new configuration in the README.

## Licensing of modifications

The modifications in this repository are released under the same MIT license as the upstream project.
Modification copyright (c) 2026 fulide.

## Third-party content

The repository contains source code and build configuration derived from the upstream project, plus the changes listed above. It does not contain Minecraft client/server jars, Mojang assets, or third-party mod binaries. Jars under `dist/`, when present, contain only this mod's compiled code and resources.
