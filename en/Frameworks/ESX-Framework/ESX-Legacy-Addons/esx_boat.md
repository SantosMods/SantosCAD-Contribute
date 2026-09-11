---
title: esx_boat
description: ESX resource that adds boat shops and boat garages and integrates with esx_vehicleshop.
published: true
date: 2026-09-11T20:31:41.578Z
tags: esx, script, boats, vehicle-shop
editor: markdown
dateCreated: 2026-09-11T20:31:41.578Z
---

# esx_boat [![](https://badges.5metrics.dev/esx_boat/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_boat)

ESX boat shop and garage resource with `esx_vehicleshop` integration.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_boat`          |
| **Creator / Maintainer** | ESX Framework       |
| **Original Copyright**   | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Vehicles            |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_boat.sql`      |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_boat` adds boat shops and boat garages around San Andreas.

The official resource includes one boat shop by default.

### Requirements

* `es_extended`
* `esx_vehicleshop`
* `oxmysql`

The manifest declares `es_extended` and `esx_vehicleshop` as dependencies and loads `@oxmysql/lib/MySQL.lua`.

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
* [ ] Install `esx_vehicleshop`
* [ ] Install and start `oxmysql`
* [ ] Download `esx_boat` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_boat.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

```cfg
ensure oxmysql
ensure es_extended
ensure esx_vehicleshop
ensure esx_boat
```

> Import `esx_boat.sql` before using the boat shop.
> {.is-success}

---

## Configuration {.tabset}

### Boat License

`Config.LicenseEnable` controls whether players need a boating license before purchasing boats.

The documented default is:

```lua
Config.LicenseEnable = true
```

`Config.LicensePrice` controls the boating license price.

The documented default is:

```lua
Config.LicensePrice = 5000
```

### Markers

The official documentation includes:

* `Config.MarkerType`
* `Config.DrawDistance`
* `Config.Marker`
* `Config.StoreMarker`

Marker tables contain positional and display values used by the boat shop and storage locations.

---

## Exports

### getGarages

The official documentation exposes a `getGarages` export for retrieving boat garage information.

Use the current ESX documentation when integrating this export so its current return structure is preserved.

---

## Compatibility

| Component           | Compatibility                    |
| ------------------- | -------------------------------- |
| **FiveM**           | Yes                              |
| **ESX Legacy**      | Yes                              |
| **esx_vehicleshop** | Required                         |
| **oxmysql**         | Used by server scripts           |
| **Lua 5.4**         | Enabled by the resource manifest |
| {.dense}            |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_boat)
* Official source repository: ESX Framework `ESX-Legacy-Addons`

---

## Before You Install

* [ ] Confirm `es_extended` is running
* [ ] Confirm `esx_vehicleshop` is installed
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `esx_boat.sql`
* [ ] Review boating license settings
* [ ] Test boat purchasing and garage storage

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
