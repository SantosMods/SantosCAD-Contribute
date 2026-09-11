---
title: esx_taxijob
description: ESX taxi job resource for transporting players or completing NPC passenger missions for payment.
published: true
date: 2026-09-11T20:50:37.739Z
tags: esx, jobs, script, taxi
editor: markdown
dateCreated: 2026-09-11T20:50:37.739Z
---

# esx_taxijob [![](https://badges.5metrics.dev/esx_taxijob/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_taxijob)

ESX taxi job resource for transporting players or completing NPC passenger missions for payment.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_taxijob`       |
| **Creator / Maintainer** | ESX Framework       |
| **Copyright**            | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Job                 |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_taxijob.sql`   |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_taxijob` lets players work as taxi drivers.

The resource supports:

* Player taxi services
* NPC passenger missions
* Configurable NPC job earnings
* Authorized taxi vehicles
* Configurable drop-off locations
* Optional player management
* Optional society-owned vehicles

### Requirements

* `es_extended`

The current `fxmanifest.lua` declares `es_extended` as its dependency.

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
* [ ] Download `esx_taxijob` from the official ESX source
* [ ] Place the resource in your server resources folder
* [ ] Import `esx_taxijob.sql`
* [ ] Add `esx_taxijob` to `server.cfg`
* [ ] Restart the server
* [ ] Check the console for errors

### Resource Order

```cfg
ensure es_extended
ensure esx_taxijob
```

> Import `esx_taxijob.sql` before using the resource.
> {.is-success}

---

## Configuration

| Setting                            | Default                  | Purpose                         |
| ---------------------------------- | ------------------------ | ------------------------------- |
| `Config.DrawDistance`              | `10.0`                   | Marker draw distance            |
| `Config.NPCJobEarnings`            | `{min = 300, max = 600}` | NPC mission payment range       |
| `Config.MinimumDistance`           | `3000.0`                 | Minimum distance for each job   |
| `Config.MaxInService`              | `-1`                     | Maximum players in service      |
| `Config.EnablePlayerManagement`    | `true`                   | Enables player management       |
| `Config.EnableSocietyOwnedVehicle` | `false`                  | Enables society-owned vehicles  |
| `Config.AuthorizedVehicles`        | Taxi configuration       | Defines authorized job vehicles |
| `Config.JobLocations`              | Table                    | Defines drop-off locations      |
| {.dense}                           |                          |                                 |

The documented default authorized vehicle is:

```lua
{
    model = 'taxi',
    title = 'Taxi',
    icon = 'fas fa-car'
}
```

---

## Compatibility

| Component      | Compatibility               |
| -------------- | --------------------------- |
| **FiveM**      | Yes                         |
| **ESX Legacy** | Yes                         |
| **Lua 5.4**    | Enabled in `fxmanifest.lua` |
| {.dense}       |                             |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_taxijob)
* [Official ESX Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_taxijob)

---

## Before You Install

* [ ] Confirm `es_extended` is running
* [ ] Back up your database
* [ ] Import `esx_taxijob.sql`
* [ ] Review NPC job earnings
* [ ] Review authorized vehicles
* [ ] Review service limits
* [ ] Test player and NPC taxi jobs

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
