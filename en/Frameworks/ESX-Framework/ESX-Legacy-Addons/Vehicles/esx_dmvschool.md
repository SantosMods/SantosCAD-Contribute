---
title: esx_dmvschool
description: ESX driving school resource with theory and practical tests for car, motorcycle, and truck licenses.
published: true
date: 2026-09-11T20:44:19.190Z
tags: esx, script, driving-school, licenses
editor: markdown
dateCreated: 2026-09-11T20:44:19.190Z
---

# esx_dmvschool [![](https://badges.5metrics.dev/esx_dmvschool/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_dmvschool)

ESX driving school resource with theory and practical driving tests for car, motorcycle, and truck licenses.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_dmvschool`     |
| **Creator / Maintainer** | ESX Framework       |
| **Type**                 | Script              |
| **Category**             | Driving School      |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_dmvschool.sql` |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_dmvschool` provides a DMV system for obtaining driving licenses.

Players can complete theory and practical driving tests. The official documentation covers tests for cars, motorcycles, and trucks.

### Requirements

* `es_extended`
* `esx_license`

The current resource manifest declares both resources as dependencies.

### Framework Support

| Framework      | Support        |
| -------------- | -------------- |
| **ESX**        | Yes            |
| **QBCore**     | Not documented |
| **Qbox**       | Not documented |
| **Standalone** | No             |
| {.dense}       |                |

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Install `esx_license`
* [ ] Download `esx_dmvschool` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_dmvschool.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server
* [ ] Check the console for errors

### Resource Order

```cfg
ensure es_extended
ensure esx_license
ensure esx_dmvschool
```

> Import `esx_dmvschool.sql` before using the resource.
> {.is-success}

---

## Configuration {.tabset}

### Driving Tests

The official documentation exposes these settings:

| Setting                     | Purpose                                          |
| --------------------------- | ------------------------------------------------ |
| `Config.DrawDistance`       | Marker draw distance                             |
| `Config.MaxErrors`          | Maximum errors allowed during the practical test |
| `Config.SpeedMultiplier`    | Converts speed for km/h or mph                   |
| `Config.SpeedingErrorDelay` | Delay before a speeding error is counted         |
| `Config.Prices`             | Prices for each test                             |
| `Config.VehicleModels`      | Vehicle model assigned to each test              |
| `Config.SpeedLimits`        | Speed limits by area                             |
| `Config.Zones`              | DMV marker zones                                 |
| `Config.CheckPoints`        | Practical test checkpoints                       |
| {.dense}                    |                                                  |

### Error Limit

The documented default maximum is:

```lua
Config.MaxErrors = 3
```

### Speed Units

The documented default multiplier is:

```lua
Config.SpeedMultiplier = 3.6
```

`3.6` represents km/h. The official documentation lists `2.23694` for mph.

### Checkpoints

`Config.CheckPoints` defines positions and actions for the practical driving test.

```lua
Config.CheckPoints = {
    {
        Pos = {x = 255.139, y = -1400.731, z = 29.537},
        Action = function(playerPed, vehicle, setCurrentZoneType)
            -- Do Action
        end
    },
}
```

---

## Compatibility

| Component       | Compatibility                    |
| --------------- | -------------------------------- |
| **FiveM**       | Yes                              |
| **ESX Legacy**  | Yes                              |
| **esx_license** | Required                         |
| **Lua 5.4**     | Enabled by the resource manifest |
| {.dense}        |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_dmvschool)
* [Official ESX Legacy Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [Official esx_dmvschool Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_dmvschool)

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `esx_license` is installed
* [ ] Back up your database
* [ ] Import `esx_dmvschool.sql`
* [ ] Review test prices
* [ ] Review speed limits and units
* [ ] Test each configured license type

---

## Credits

Created and maintained through the **ESX Framework** project and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
