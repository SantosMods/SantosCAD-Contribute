---
title: esx_mechanicjob
description: ESX mechanic job for repairing and modifying vehicles, with billing, boss actions, and mechanic job interactions.
published: true
date: 2026-09-11T20:35:00.672Z
tags: esx, mechanic, script, vehicle-repair
editor: markdown
dateCreated: 2026-09-10T03:30:38.334Z
---

# esx_mechanicjob [![](https://badges.5metrics.dev/esx_mechanicjob/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_mechanicjob)

`esx_mechanicjob` provides an ESX mechanic job for repairing and modifying vehicles.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

> The ESX documentation states that the ESX team is aware of major issues with this resource and is working on a complete rewrite.
> {.is-warning}

---

## Resource Information

| Field              | Information         |
| ------------------ | ------------------- |
| **Name**           | `esx_mechanicjob`   |
| **Creator**        | ESX Framework       |
| **Type**           | Script              |
| **Category**       | Mechanic Job        |
| **Game**           | FiveM               |
| **Framework**      | ESX                 |
| **Price**          | Free                |
| **License**        | GNU GPL v3 or later |
| **Version**        | `1.0`               |
| **Legacy Version** | `1.13.4`            |
| {.dense}           |                     |

---

## Resource Details {.tabset}

### Overview

`esx_mechanicjob` allows players to work as mechanics.

The current resource includes mechanic interactions for vehicle repair and modification. Its client code also contains mechanic actions for repair kits, body repair, towing-related NPC work, and mechanic vehicle handling.

### Requirements

The current `fxmanifest.lua` lists:

* `es_extended`
* `esx_society`
* `esx_billing`

### Framework Support

| Framework | Support |
| --------- | ------- |
| **ESX**   | Yes     |
| {.dense}  |         |

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Install `esx_society`
* [ ] Install `esx_billing`
* [ ] Obtain `esx_mechanicjob` from the official ESX repository
* [ ] Place `esx_mechanicjob` in your resources folder
* [ ] Import `esx_mechanicjob.sql`
* [ ] Review `config.lua`
* [ ] Start `esx_mechanicjob`
* [ ] Check the server console for errors

### Resource Order

Load its dependencies before `esx_mechanicjob`.

```cfg
ensure es_extended
ensure esx_society
ensure esx_billing
ensure esx_mechanicjob
```

---

## Configuration

### Player Management

The official repository instructs you to enable player management through:

```lua
Config.EnablePlayerManagement = true
```

Player management covers billing and boss actions and uses `esx_society` and `esx_billing`.

---

## Commands

The current client resource registers mechanic commands including:

```text
mechanicMenu
mechanicjob
```

`mechanicMenu` opens the mechanic menu for players with the `mechanic` job.

`mechanicjob` toggles the NPC mechanic job when its requirements are met.

---

## Database

Import the included file:

```text
esx_mechanicjob.sql
```

The official repository also contains:

```text
update_mechanic_uniforms.sql
```

> Back up your database before importing or changing SQL data.
> {.is-warning}

---

## Compatibility

| Component       | Information                  |
| --------------- | ---------------------------- |
| **FiveM**       | Yes                          |
| **ESX**         | Required                     |
| **esx_society** | Required by current manifest |
| **esx_billing** | Required by current manifest |
| **Lua 5.4**     | Enabled                      |
| {.dense}        |                              |

---

## Known Issues

> The official ESX documentation explicitly warns that `esx_mechanicjob` has major issues and that the ESX team is working on a complete rewrite.
> {.is-warning}

Review the current ESX documentation before deploying this resource on a production server.

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_mechanicjob)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_mechanicjob Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_mechanicjob)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Review the official major-issues warning.
* Install the required ESX dependencies.
* Import `esx_mechanicjob.sql`.
* Review `config.lua`.
* Test mechanic actions before using the resource on a live server.

---

## Credits

Created through the **ESX Framework** project and its contributors. The resource license notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
