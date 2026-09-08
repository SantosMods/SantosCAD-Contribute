---
title: esx_vehicleshop
description: esx_vehicleshop provides vehicle purchasing and dealership systems for ESX Legacy.
published: true
date: 2026-09-08T00:54:22.509Z
tags: dealership, esx, script, vehicles
editor: markdown
dateCreated: 2026-09-08T00:54:22.509Z
---

# esx_vehicleshop [![](https://badges.5metrics.dev/esx_vehicleshop/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_vehicleshop)

`esx_vehicleshop` provides vehicle purchasing and dealership systems for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information       |
| ------------- | ----------------- |
| **Name**      | `esx_vehicleshop` |
| **Creator**   | ESX Framework     |
| **Type**      | Script            |
| **Category**  | Vehicles          |
| **Game**      | FiveM             |
| **Framework** | ESX Legacy        |
| **Source**    | ESX Framework     |
| {.dense}      |                   |

---

## Resource Details {.tabset}

### Overview

`esx_vehicleshop` allows players to purchase vehicles.

The resource can operate as a standard vehicle shop or use an optional player-managed car dealership.

Features include:

* Vehicle purchasing
* Configurable vehicle shop zones
* Generated license plates
* Optional car dealer job
* Optional vehicle license requirement
* Configurable blips and markers

### Requirements

The resource uses:

* `es_extended`
* `esx_lib`
* `oxmysql`

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Configure `oxmysql`
* [ ] Download `esx_vehicleshop`
* [ ] Place `esx_vehicleshop` in your resources folder
* [ ] Complete the required database setup
* [ ] Review `config.lua`
* [ ] Configure vehicle shop behavior
* [ ] Add `esx_vehicleshop` to `server.cfg`
* [ ] Restart your server
* [ ] Test vehicle purchasing and ownership

### Resource Order

```cfg
ensure es_extended
ensure esx_vehicleshop
```

---

## Configuration {.tabset}

### Player Management

Enable the car dealer job with:

```lua
Config.EnablePlayerManagement = true
```

Disable player management with:

```lua
Config.EnablePlayerManagement = false
```

### Vehicle License

Control whether players need a license to purchase vehicles with:

```lua
Config.LicenseEnable = true
```

### License Plates

Configure plate letters with:

```lua
Config.PlateLetters = 3
```

Configure plate numbers with:

```lua
Config.PlateNumbers = 3
```

Control spaces in generated plates with:

```lua
Config.PlateUseSpace = true
```

### Shop Zones

Vehicle shop zones are configured through:

```lua
Config.Zones
```

Zones can define their position, size, and marker settings.

---

## Developer Usage

The resource provides the plate generation export:

```text
GeneratePlate
```

Use the official source when integrating this export into another resource.

---

## Compatibility

| Component                     | Support  |
| ----------------------------- | -------- |
| **FiveM**                     | Yes      |
| **ESX Legacy**                | Yes      |
| **es_extended**               | Required |
| **oxmysql**                   | Used     |
| **Player-managed dealership** | Optional |
| {.dense}                      |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_vehicleshop)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_vehicleshop)
* [Official ESX Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
