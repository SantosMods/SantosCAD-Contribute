---
title: esx_ambulancejob
description: ESX EMS job resource with death handling, reviving, vehicle garages, and on-duty ambulance features.
published: true
date: 2026-09-11T20:35:17.354Z
tags: ems, esx, revive, script
editor: markdown
dateCreated: 2026-09-10T03:29:14.811Z
---

# esx_ambulancejob [![](https://badges.5metrics.dev/esx_ambulancejob/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_ambulancejob)

`esx_ambulancejob` provides EMS gameplay for ESX, including reviving players, death handling, ambulance garages, and EMS job interactions.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                           | Information         |
| ------------------------------- | ------------------- |
| **Name**                        | `esx_ambulancejob`  |
| **Creator**                     | ESX Framework       |
| **Type**                        | Script              |
| **Category**                    | EMS Job             |
| **Game**                        | FiveM               |
| **Framework**                   | ESX                 |
| **Price**                       | Free                |
| **License**                     | GNU GPL v3 or later |
| **Version in current manifest** | `1.0.2`             |
| **Legacy version**              | `1.15.0`            |
| {.dense}                        |                     |

---

## Resource Details {.tabset}

### Overview

`esx_ambulancejob` provides an ambulance and EMS job for ESX.

Officially documented features include:

* Death screen
* Early respawn timer
* Bleedout timer
* Player revival
* Vehicle garages
* EMS job interactions

> The ESX documentation states that the resource's death handling will be removed in the future and replaced by a new system in `es_extended`.
> {.is-warning}

### Requirements

The current manifest lists these dependencies:

* `es_extended`
* `esx_skin`
* `esx_vehicleshop`

The resource also loads:

* `esx_lib`
* `oxmysql`

`esx_society` is optional and is used for player and society management.

### Framework Support

| Framework | Support |
| --------- | ------- |
| **ESX**   | Yes     |
| {.dense}  |         |

---

## Installation

### Installation Checklist

* [ ] Install and configure ESX
* [ ] Install `esx_skin`
* [ ] Install `esx_vehicleshop`
* [ ] Confirm `esx_lib` and `oxmysql` are available
* [ ] Install `esx_society` if you need society management
* [ ] Obtain `esx_ambulancejob` from the official ESX repository
* [ ] Place `esx_ambulancejob` in your server resources
* [ ] Import `esx_ambulancejob.sql`
* [ ] Review `config.lua`
* [ ] Start `esx_ambulancejob`
* [ ] Check the server console for errors

### Resource Order

Load required ESX resources before `esx_ambulancejob`.

```cfg
ensure es_extended
ensure esx_skin
ensure esx_vehicleshop
ensure esx_ambulancejob
```

Add other required resources such as `oxmysql` and `esx_lib` according to your ESX installation.

---

## Configuration {.tabset}

### General

The official documentation exposes settings including:

| Setting                            | Default      | Purpose                               |
| ---------------------------------- | ------------ | ------------------------------------- |
| `Config.DrawDistance`              | `10.0`       | Marker draw distance                  |
| `Config.ReviveReward`              | `700`        | Reward for reviving a player          |
| `Config.LoadIpl`                   | `true`       | Loads the hospital interior           |
| `Config.EnablePlayerManagement`    | `true`       | Enables player and society management |
| `Config.EarlyRespawnTimer`         | `60000 * 1`  | Delay before early respawn            |
| `Config.BleedoutTimer`             | `60000 * 10` | Bleedout timer                        |
| `Config.RemoveWeaponsAfterRPDeath` | `true`       | Removes weapons after RP death        |
| `Config.RemoveCashAfterRPDeath`    | `true`       | Removes cash after RP death           |
| `Config.RemoveItemsAfterRPDeath`   | `true`       | Removes items after RP death          |
| `Config.EarlyRespawnFine`          | `false`      | Enables an early respawn fine         |
| `Config.EarlyRespawnFineAmount`    | `500`        | Early respawn fine amount             |
| {.dense}                           |              |                                       |

### Pharmacy Items

Configure available pharmacy items through `Config.PharmacyItems`.

```lua
Config.PharmacyItems = {
    {title = 'Item Label', item = 'name'},
}
```

### Hospitals

`Config.Hospitals` controls hospital locations and associated features such as:

* Blips
* Ambulance actions
* Pharmacies
* Vehicle spawners
* Helicopter spawners
* Fast travel

### Authorized Vehicles

`Config.AuthorizedVehicles` controls EMS vehicles by vehicle type and job grade.

```lua
Config.AuthorizedVehicles = {
    vehicleType = {
        grade_name = {
            {model = 'model', price = 5000},
        },
    },
}
```

### Medal Auto-Clips

The current official repository includes Medal.tv automatic death clipping.

It is enabled by default and can be disabled in `config.lua`:

```lua
Config.Medal.enabled = false
```

Each player needs the Medal desktop application running with its Events API enabled for this feature to work.

---

## Database

Import:

```text
esx_ambulancejob.sql
```

The SQL file defines database data required by the ambulance job.

> Back up your database before importing or modifying SQL files.
> {.is-warning}

---

## Compatibility

| Component           | Information                     |
| ------------------- | ------------------------------- |
| **FiveM**           | Yes                             |
| **ESX**             | Required                        |
| **esx_skin**        | Required                        |
| **esx_vehicleshop** | Required                        |
| **esx_society**     | Optional                        |
| **oxmysql**         | Loaded by the resource          |
| **esx_lib**         | Loaded by the resource          |
| **Lua 5.4**         | Enabled in the current manifest |
| {.dense}            |                                 |

---

## Known Changes

> The official ESX documentation warns that `esx_ambulancejob` death handling is planned for removal and replacement by a new system inside `es_extended`.
> {.is-warning}

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_ambulancejob)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_ambulancejob Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_ambulancejob)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Check that all required ESX resources are installed.
* Import `esx_ambulancejob.sql`.
* Review death and respawn settings before going live.
* Review inventory, cash, and weapon removal settings.
* Configure hospital locations and EMS vehicles for your server.
* Decide whether you want the Medal.tv integration enabled.

---

## Credits

Created and maintained through the **ESX Framework** project and its contributors. The resource copyright notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
