---
title: esx_drugs
description: ESX marijuana resource for harvesting, processing, and selling configured drug items.
published: true
date: 2026-09-11T20:44:59.428Z
tags: esx, script, drugs, item-farming
editor: markdown
dateCreated: 2026-09-11T20:44:59.428Z
---

# esx_drugs [![](https://badges.5metrics.dev/esx_drugs/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_drugs)

ESX marijuana resource for harvesting, processing, and selling configured drug items.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_drugs`         |
| **Creator / Maintainer** | ESX Framework       |
| **Original Copyright**   | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Drugs               |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_drugs.sql`     |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_drugs` provides marijuana harvesting, processing, and selling functionality for ESX.

The current resource uses `oxmysql` for database access.

### Requirements

* `es_extended`
* `oxmysql`

`esx_license` is also required when `Config.LicenseEnable` is enabled.

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
* [ ] Install and start `oxmysql`
* [ ] Install `esx_license` when using processing licenses
* [ ] Download `esx_drugs` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_drugs.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

When processing licenses are enabled:

```cfg
ensure oxmysql
ensure es_extended
ensure esx_license
ensure esx_drugs
```

> Import `esx_drugs.sql` before using the resource.
> {.is-success}

---

## Configuration {.tabset}

### Processing

`Config.Delays` controls drug processing times.

The documented default includes:

```lua
Config.Delays = {
    WeedProcessing = 1000 * 7
}
```

### Dealer Items

`Config.DrugDealerItems` defines the items the drug dealer purchases.

The documented default includes:

```lua
Config.DrugDealerItems = {
    marijuana = 91
}
```

### Processing License

The documented default enables a processing license:

```lua
Config.LicenseEnable = true
```

> Enabling `Config.LicenseEnable` requires `esx_license`.
> {.is-info}

The documented processing license price is configured through `Config.LicensePrices`.

### Payments

The documented default uses black money when selling drugs:

```lua
Config.GiveBlack = true
```

### Markers and Selling

`Config.Marker` controls marker settings including:

* `Distance`
* `Type`
* `Color`
* `Size`

`Config.SellMenu` controls the minimum and maximum quantity that can be sold through the sell menu.

---

## Compatibility

| Component       | Compatibility                                 |
| --------------- | --------------------------------------------- |
| **FiveM**       | Yes                                           |
| **ESX Legacy**  | Yes                                           |
| **oxmysql**     | Used by server scripts                        |
| **esx_license** | Required when processing licenses are enabled |
| **Lua 5.4**     | Enabled by the resource manifest              |
| {.dense}        |                                               |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_drugs)
* [Official ESX Legacy Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [Official esx_drugs Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_drugs)

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `esx_drugs.sql`
* [ ] Review processing delays
* [ ] Review dealer items and prices
* [ ] Review `Config.LicenseEnable`
* [ ] Review payment configuration

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
