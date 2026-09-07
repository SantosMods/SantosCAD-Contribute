---
title: es_extended
description: es_extended is the main core resource for ESX Framework.
published: true
date: 2026-09-07T23:38:18.285Z
tags: core, esx, framework, roleplay
editor: markdown
dateCreated: 2026-09-07T21:37:08.904Z
---

# es_extended [![](https://badges.5metrics.dev/es_extended/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/es_extended)

`es_extended` is the main core resource for ESX Framework.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information            |
| ------------- | ---------------------- |
| **Name**      | `es_extended`          |
| **Creator**   | ESX Framework          |
| **Type**      | Framework              |
| **Category**  | Core                   |
| **Game**      | FiveM                  |
| **Framework** | ESX Legacy             |
| **Version**   | `1.14.1`               |
| **License**   | GPL-3.0                |
| **Source**    | Official ESX Framework |
| {.dense}      |                        |

---

## Resource Details {.tabset}

### Overview

`es_extended` is the main script for ESX Framework.

It provides core functionality used by ESX resources, including:

* Commands
* Callbacks
* Player data
* Money and accounts
* Jobs
* Inventory handling
* Paychecks
* OneSync functionality
* Shared functions and modules
* Server and client events

The framework exposes functions that other resources can use to extend ESX functionality.

### Requirements

The current resource manifest declares:

* `oxmysql`
* Required FiveM native versions

The official ESX server configuration also starts `esx_lib` before `es_extended`.

### Framework Role

`es_extended` is the core of ESX Legacy.

Other ESX core resources and addons depend on the functionality it provides.

---

## Installation

> ESX recommends installing the complete ESX Legacy recipe instead of manually editing core files.
> {.is-info}

### Installation Checklist

* [ ] Install the official ESX Legacy resources
* [ ] Configure `oxmysql`
* [ ] Configure your database connection
* [ ] Import the ESX database files
* [ ] Configure `server.cfg`
* [ ] Start `esx_lib`
* [ ] Start `es_extended`
* [ ] Start the remaining ESX core resources
* [ ] Restart your server
* [ ] Check the server console for errors

### Resource Order

The official ESX configuration starts `oxmysql` before the ESX Legacy resources.

```cfg
ensure oxmysql
ensure esx_lib
ensure es_extended
ensure [core]
```

> Keep your ESX resources in the startup order provided by the official ESX recipe.
> {.is-warning}

---

## Configuration {.tabset}

### Main Configuration

The primary configuration is located in:

```text
shared/config/main.lua
```

Current options include settings for:

* Locale
* Locale fallback
* Inventory handling
* Paychecks
* Society payouts
* Maximum inventory weight
* Death status saving
* Debug mode
* Default job duty
* Off-duty paycheck multiplier
* Multicharacter detection
* Identity
* Item giving distance
* Player identifiers

### Inventory

The current configuration automatically detects `ox_inventory`.

When `ox_inventory` is running, ESX sets its custom inventory mode accordingly.

### Locale

You can configure the ESX locale through the server convar:

```cfg
setr esx:locale "en"
```

If no ESX locale is configured, the framework can use the locale selected through txAdmin.

### Identifier

The default identifier setting uses:

```text
license
```

You can change it through the `esx:identifier` convar where supported.

---

## Developer Usage

### Importing ESX

The resource provides `imports.lua` for accessing the ESX object.

The current import initializes ESX through:

```lua
ESX = exports["es_extended"]:getSharedObject()
```

### Core API

The official documentation provides sections for:

* Client functions
* Server functions
* `xPlayer`
* Callbacks
* Events
* `PlayerData`
* Commands
* OneSync
* Shared modules

Use the official documentation when developing resources against ESX.

---

## Compatibility

| Component      | Support                                             |
| -------------- | --------------------------------------------------- |
| **FiveM**      | Yes                                                 |
| **ESX Legacy** | Core resource                                       |
| **oxmysql**    | Required                                            |
| **esx_lib**    | Used by current ESX Legacy setup                    |
| **OneSync**    | Required by current ESX Legacy server configuration |
| {.dense}       |                                                     |

---

## Before You Install

> The ESX documentation states that editing core files is unsupported and may break the framework. Extend ESX through its provided functions, exports, events, and supported configuration instead.
> {.is-warning}

Use the official ESX Legacy installation recipe when setting up a new server.

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/es_extended)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)
* [Official es_extended Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/es_extended)
* [Official ESX Framework Website](https://www.esx-framework.org/)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

The project traces its original development to **Jérémie N'gadi (Gizz)**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
