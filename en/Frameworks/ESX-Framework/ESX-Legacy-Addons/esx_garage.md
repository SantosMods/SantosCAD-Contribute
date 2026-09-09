---
title: esx_garage
description: esx_garage provides vehicle garages and impounds for ESX Legacy.
published: true
date: 2026-09-09T20:21:57.343Z
tags: esx, script, vehicles, garage
editor: markdown
dateCreated: 2026-09-09T20:21:57.343Z
---

# esx_garage [![](https://badges.5metrics.dev/esx_garage/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_garage)

esx_garage provides vehicle garages and impounds for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information   |
| ------------- | ------------- |
| **Name**      | `esx_garage`  |
| **Creator**   | ESX Framework |
| **Type**      | Script        |
| **Category**  | Vehicles      |
| **Game**      | FiveM         |
| **Framework** | ESX Legacy    |
| **License**   | GPL-3.0       |
| **Source**    | GitHub        |
| {.dense}      |               |

---

## Overview

esx_garage provides an ESX vehicle garage system with a user interface.

The resource supports configurable garage and impound locations.

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `esx_garage` from the official ESX source
* [ ] Import the included database file if required by your installed version
* [ ] Review `config.lua`
* [ ] Configure garages
* [ ] Configure impounds
* [ ] Add `esx_garage` to `server.cfg`
* [ ] Restart your server
* [ ] Test vehicle storage and retrieval

### Resource

```cfg
ensure esx_garage
```

---

## Configuration {.tabset}

### General

`Config.DrawDistance` controls the distance at which garage markers are drawn.

Default:

```lua
Config.DrawDistance = 10.0
```

`Config.Markers` controls marker types, sizes, and colors.

### Garages

Configure garage locations through `Config.Garages`.

A garage can define:

* `EntryPoint`
* `SpawnPoint`
* `Sprite`
* `Scale`
* `Colour`
* `ImpoundedName`

Example structure:

```lua
Config.Garages = {
    GarageName = {
        EntryPoint = {x = 0.0, y = 0.0, z = 0.0},
        SpawnPoint = {x = 0.0, y = 0.0, z = 0.0, heading = 0.0},
        Sprite = 357,
        Scale = 0.8,
        Colour = 3,
        ImpoundedName = "impoundName"
    }
}
```

### Impounds

Configure impounds through `Config.Impounds`.

An impound can define:

* `GetOutPoint`
* `SpawnPoint`
* `Sprite`
* `Scale`
* `Colour`
* `Cost`

---

## Developer Usage

### Get Garages

`getGarages` returns the `Config.Garages` table.

```lua
local garages = exports['esx_garage']:getGarages()
```

### Get Impounds

`getImpounds` returns the `Config.Impounds` table.

```lua
local impounds = exports['esx_garage']:getImpounds()
```

---

## Compatibility

| Component            | Support |
| -------------------- | ------- |
| **FiveM**            | Yes     |
| **ESX Legacy**       | Yes     |
| **Vehicle garages**  | Yes     |
| **Vehicle impounds** | Yes     |
| {.dense}             |         |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_garage)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_garage)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
