---
title: esx_shops
description: esx_shops provides configurable item shops for ESX Legacy.
published: true
date: 2026-09-08T00:51:21.685Z
tags: esx, inventory, script, shops
editor: markdown
dateCreated: 2026-09-08T00:51:21.685Z
---

# esx_shops [![](https://badges.5metrics.dev/esx_shops/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_shops)

`esx_shops` provides configurable item shops for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information   |
| ------------- | ------------- |
| **Name**      | `esx_shops`   |
| **Creator**   | ESX Framework |
| **Type**      | Script        |
| **Category**  | Shops         |
| **Game**      | FiveM         |
| **Framework** | ESX Legacy    |
| **Version**   | `2.0.0`       |
| **Source**    | ESX Framework |
| {.dense}      |               |

---

## Resource Details {.tabset}

### Overview

`esx_shops` provides configurable shops with an NUI interface.

Features include:

* Configurable shop locations
* Item categories
* Configurable items and prices
* ESX inventory support
* `ox_inventory` support
* Tax calculation
* Optional tax collection
* Job-based tax exemptions
* Configurable markers and blips
* Server-side purchase validation

### Requirements

The resource requires:

* `es_extended`

The resource also uses:

* `esx_lib`
* `oxmysql`

`esx_addonaccount` is required when tax collection is enabled.

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Download `esx_shops` from the official ESX addons repository
* [ ] Place `esx_shops` in your resources folder
* [ ] Configure inventory support
* [ ] Configure shops and items
* [ ] Add `esx_shops` to `server.cfg`
* [ ] Restart your server
* [ ] Test purchases

### Resource Order

```cfg
ensure es_extended
ensure esx_shops
```

---

## Configuration {.tabset}

### Main Configuration

Main settings are stored in:

```text
shared/config/main.lua
```

Configuration includes:

* Debug mode
* Inventory system
* Item image paths
* Tax rate
* Tax collection
* Tax-exempt jobs
* Marker settings
* Purchase cooldown
* Maximum purchase quantity
* Price validation

### Inventory

Select the inventory system with:

```lua
Config.Inventory = 'ox_inventory'
```

Documented options are:

```text
esx
ox_inventory
```

### Shops

Configure shop definitions in:

```text
shared/config/shops.lua
```

Each shop can define:

* Items
* Categories
* Locations
* Marker settings
* Blip settings

### Tax System

Set the tax rate with:

```lua
Config.TaxRate = 0.19
```

Enable tax collection with:

```lua
Config.EnableTaxCollection = true
```

Tax collection requires `esx_addonaccount`.

---

## Compatibility

| Component            | Support                     |
| -------------------- | --------------------------- |
| **FiveM**            | Yes                         |
| **ESX Legacy**       | Yes                         |
| **es_extended**      | Required                    |
| **ESX Inventory**    | Supported                   |
| **ox_inventory**     | Supported                   |
| **esx_addonaccount** | Optional for tax collection |
| {.dense}             |                             |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_shops)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_shops)
* [Official ESX Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
