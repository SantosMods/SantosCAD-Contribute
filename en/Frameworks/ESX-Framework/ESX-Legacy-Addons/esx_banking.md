---
title: esx_banking
description: ESX banking and ATM resource with configurable banks, peds, transaction logging, and a web-based interface.
published: true
date: 2026-09-11T20:29:02.264Z
tags: esx, script, banking, atm
editor: markdown
dateCreated: 2026-09-11T20:29:02.264Z
---

# esx_banking [![](https://badges.5metrics.dev/esx_banking/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_banking)

ESX banking and ATM resource with configurable bank locations, peds, and transaction logging.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_banking`       |
| **Creator / Maintainer** | ESX Framework       |
| **Original Copyright**   | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Banking             |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `banking.sql`       |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_banking` provides banking and ATM functionality for ESX servers.

The official documentation exposes configuration for:

* Bank locations
* Bank blips
* Bank peds
* Supported ATM models
* Marker draw distance
* Debug mode
* Transaction logging

### Requirements

* `es_extended`
* `oxmysql`

The resource manifest loads `@oxmysql/lib/MySQL.lua` and declares `es_extended` as a dependency.

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

* [ ] Install ESX and database dependencies
* [ ] Download `esx_banking` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `banking.sql`
* [ ] Add `esx_banking` to `server.cfg`
* [ ] Restart the server
* [ ] Check the server console for errors

### Resource Order

Load the required framework and database resource before `esx_banking`.

```cfg
ensure oxmysql
ensure es_extended
ensure esx_banking
```

> Import `banking.sql` before using the resource.
> {.is-success}

---

## Configuration {.tabset}

### General

The official documentation describes these settings in `config.lua`:

| Setting             | Purpose                                 |
| ------------------- | --------------------------------------- |
| `Config.Debug`      | Enables or disables debug mode          |
| `Config.DrawMarker` | Sets marker draw distance               |
| `Config.EnablePeds` | Enables bank peds                       |
| `Config.AtmModels`  | Defines supported ATM models            |
| `Config.Banks`      | Defines bank locations and blips        |
| `Config.Peds`       | Defines bank ped locations and behavior |
| {.dense}            |                                         |

### Bank Configuration

Each entry in `Config.Banks` can define a bank position and blip settings.

Documented blip fields include:

* `Enabled`
* `Color`
* `Label`
* `Sprite`
* `Scale`

### Ped Configuration

Documented `Config.Peds` fields include:

* `Position`
* `Model`
* `Scenario`

---

## Developer API {.tabset}

### Server Export

The resource provides a server-side transaction logging export.

```lua
exports["esx_banking"]:logTransaction(source, label, logType, amount)
```

Example:

```lua
exports["esx_banking"]:logTransaction(source, "CAR PURCHASE", "WITHDRAW", 200)
```

Supported transaction types documented by ESX include:

```text
WITHDRAW
DEPOSIT
TRANSFER_RECEIVE
```

> The transaction logging API records a transaction. It does not perform the banking operation itself.
> {.is-info}

### Client Event

The official documentation also documents the transaction logging server event:

```lua
TriggerServerEvent("esx_banking:logTransaction", label, logType, amount)
```

---

## Compatibility

| Component      | Compatibility                    |
| -------------- | -------------------------------- |
| **FiveM**      | Yes                              |
| **ESX Legacy** | Yes                              |
| **Lua 5.4**    | Enabled by the resource manifest |
| **oxmysql**    | Used by server scripts           |
| {.dense}       |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_banking)
* Official source repository: ESX Framework `ESX-Legacy-Addons`

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `banking.sql`
* [ ] Review `config.lua`
* [ ] Confirm the resource starts without console errors

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
