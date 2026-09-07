---
title: ND_GunAnims
description: ND_GunAnims is a configurable weapon animation system for FiveM.
published: true
date: 2026-09-07T06:21:39.964Z
tags: nd, script, weapons, animations
editor: markdown
dateCreated: 2026-09-07T06:21:13.764Z
---

# ND_GunAnims

ND_GunAnims is a configurable weapon animation system for FiveM.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information   |
| ------------ | ------------- |
| **Name**     | `ND_GunAnims` |
| **Creator**  | ND-Framework  |
| **Type**     | Script        |
| **Category** | Weapons       |
| **Game**     | FiveM         |
| **License**  | GPL-3.0       |
| **Source**   | GitHub        |
| {.dense}     |               |

---

## Resource Details {.tabset}

### Overview

ND_GunAnims controls weapon aiming, holstering, and unholstering animations.

Animation selection can use:

* Weapon groups
* Individual weapons
* Clothing components
* Default aim animations

### Configuration Files

Aim animations:

```text
ND_GunAnims/data/aim.lua
```

Clothing holsters:

```text
ND_GunAnims/data/holster.lua
```

Holster animations:

```text
ND_GunAnims/data/animations.lua
```

---

## Installation

### Installation Checklist

* [ ] Download `ND_GunAnims`
* [ ] Place `ND_GunAnims` in your resources folder
* [ ] Review the animation configuration
* [ ] Add `ND_GunAnims` to `server.cfg`
* [ ] Restart your server
* [ ] Test weapon animations

```cfg
ensure ND_GunAnims
```

---

## Configuration {.tabset}

### Aim Animations

Open:

```text
ND_GunAnims/data/aim.lua
```

Set `command` to define the command players use to select an aim animation.

For example:

```lua
command = "aim"
```

Disable the command with:

```lua
command = false
```

Set a default animation with the `default` option.

### Clothing Holsters

Open:

```text
ND_GunAnims/data/holster.lua
```

Use the `male` and `female` configuration to select clothing components used by the holster system.

### Weapon Animations

Open:

```text
ND_GunAnims/data/animations.lua
```

The configuration supports animation selection by weapon group, individual weapon, and clothing component.

---

## Developer Usage

Set the player's aim animation:

```lua
exports["ND_GunAnims"]:setAimAnim("gang")
```

Get the current aim animation:

```lua
exports["ND_GunAnims"]:getAimAnim()
```

The documented values include:

```text
default
gang
hillbilly
```

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_GunAnims)

---

## Credits

Created by **ND-Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
