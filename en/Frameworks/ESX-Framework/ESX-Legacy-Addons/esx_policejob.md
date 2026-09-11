---
title: esx_policejob
description: ESX police job with armories, vehicle garages, searching, handcuffing, and configurable police management features.
published: true
date: 2026-09-11T20:34:37.907Z
tags: esx, law-enforcement, police, script
editor: markdown
dateCreated: 2026-09-10T03:31:16.521Z
---

# esx_policejob [![](https://badges.5metrics.dev/esx_policejob/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_policejob)

`esx_policejob` provides an ESX police job with police armories, vehicle garages, searching, handcuffing, and related police interactions.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field              | Information         |
| ------------------ | ------------------- |
| **Name**           | `esx_policejob`     |
| **Creator**        | ESX Framework       |
| **Type**           | Script              |
| **Category**       | Police Job          |
| **Game**           | FiveM               |
| **Framework**      | ESX                 |
| **Price**          | Free                |
| **License**        | GNU GPL v3 or later |
| **Version**        | `1.0.2`             |
| **Legacy Version** | `1.14.1`            |
| {.dense}           |                     |

---

## Resource Details {.tabset}

### Overview

`esx_policejob` adds police gameplay to ESX.

The official repository documents features including:

* Police armories
* Vehicle garages
* Searching players
* Handcuffing players
* Player management
* Armory management
* License integration
* Service integration

### Base Requirements

The current manifest lists:

* `es_extended`
* `esx_billing`
* `esx_vehicleshop`

The server scripts also load `oxmysql`.

### Optional Feature Requirements

Additional ESX resources are used for specific features.

| Feature                                        | Resources                                            |
| ---------------------------------------------- | ---------------------------------------------------- |
| **Player management / buyable armory weapons** | `esx_addoninventory`, `esx_datastore`, `esx_society` |
| **Identity support**                           | `esx_identity`                                       |
| **License support**                            | `esx_license`                                        |
| **Service support**                            | `esx_service`                                        |
| **Status support**                             | `esx_status`                                         |
| {.dense}                                       |                                                      |

### Framework Support

| Framework | Support |
| --------- | ------- |
| **ESX**   | Yes     |
| {.dense}  |         |

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Install `esx_billing`
* [ ] Install `esx_vehicleshop`
* [ ] Confirm `oxmysql` is available
* [ ] Install optional ESX resources for the features you enable
* [ ] Obtain `esx_policejob` from the official ESX repository
* [ ] Place `esx_policejob` in your resources folder
* [ ] Import `esx_policejob.sql`
* [ ] Review `config.lua`
* [ ] Start `esx_policejob`
* [ ] Check the server console for errors

### Resource Order

Load required resources before `esx_policejob`.

```cfg
ensure es_extended
ensure esx_billing
ensure esx_vehicleshop
ensure esx_policejob
```

Start optional dependencies before `esx_policejob` when their corresponding features are enabled.

---

## Configuration {.tabset}

### Player Management

Enable player management with:

```lua
Config.EnablePlayerManagement = true
```

### Armory Management

Enable armory management with:

```lua
Config.EnableArmoryManagement = true
```

### License Management

Enable license management with:

```lua
Config.EnableLicenses = true
```

This feature uses `esx_license`.

### Service Management

The official repository instructs you to set `Config.MaxInService` above `-1` to enable service management.

```lua
Config.MaxInService = 10
```

Adjust the value for your server requirements.

---

## Database

Import:

```text
esx_policejob.sql
```

> Back up your database before importing or modifying SQL data.
> {.is-warning}

---

## Compatibility

| Component           | Information            |
| ------------------- | ---------------------- |
| **FiveM**           | Yes                    |
| **ESX**             | Required               |
| **esx_billing**     | Required               |
| **esx_vehicleshop** | Required               |
| **oxmysql**         | Used by server scripts |
| **Lua 5.4**         | Enabled                |
| {.dense}            |                        |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_policejob)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_policejob Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_policejob)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Install the base dependencies.
* Import `esx_policejob.sql`.
* Install optional dependencies only for features you plan to use.
* Review player, armory, license, and service management settings.
* Test police interactions and permissions before deployment.

---

## Credits

Created through the **ESX Framework** project and its contributors. The resource license notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
