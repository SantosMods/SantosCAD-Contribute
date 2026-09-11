---
title: esx_jobs
description: ESX job system with configurable farming jobs, job vehicles, and included slaughterer, miner, fisherman, journalist, fueler, and tailor jobs.
published: true
date: 2026-09-11T20:45:48.329Z
tags: esx, item-farming, jobs, script
editor: markdown
dateCreated: 2026-09-11T20:45:48.328Z
---

# esx_jobs [![](https://badges.5metrics.dev/esx_jobs/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_jobs)

ESX job system with configurable farming jobs and job vehicles.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

> The official ESX documentation states that `esx_jobs` is currently being completely rewritten.
> {.is-warning}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_jobs`          |
| **Creator / Maintainer** | ESX Framework       |
| **Original Copyright**   | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Jobs                |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_jobs.sql`      |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_jobs` provides basic jobs where players can work for money.

The official source includes these jobs:

* Slaughterer
* Miner
* Fisherman
* Journalist
* Fueler
* Tailor

The resource also includes sample job definitions under the `jobs` folder.

### Features

The official repository documents:

* Item farming jobs
* Job vehicle rentals
* Security deposits for rented job vehicles
* Sample definitions for creating jobs
* Optional iZone integration

The resource does not provide player management.

### Requirements

The official repository lists:

* `esx_addonaccount`
* `esx_skin`

The current resource manifest also declares `es_extended` as a dependency.

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
* [ ] Install `esx_addonaccount`
* [ ] Install `esx_skin`
* [ ] Download `esx_jobs` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_jobs.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server
* [ ] Test the configured jobs

### Resource Order

```cfg
ensure es_extended
ensure esx_addonaccount
ensure esx_skin
ensure esx_jobs
```

> Import `esx_jobs.sql` before using the resource.
> {.is-success}

---

## Job Configuration

Job definitions are loaded from:

```text
jobs/*.lua
```

The official repository includes sample jobs that can be used as references when configuring additional farming jobs.

---

## Optional iZone Integration

The official source documents optional iZone support.

A job zone can specify an iZone polygon name using the `Zone` field.

```lua
CloakRoom = {
    Zone = "miner_room",
    Size = {x = 3.0, y = 3.0, z = 1.0},
    Color = {r = 50, g = 200, b = 50},
    Marker = 1,
    Blip = true,
    Name = TranslateCap("m_miner_locker"),
    Type = "cloakroom",
    Hint = TranslateCap("cloak_change"),
    GPS = {x = 884.86, y = -2176.51, z = 29.51}
}
```

iZone is optional and is used to provide custom zones instead of radius-based areas.

---

## Status

> The official ESX documentation states that a complete rewrite of this resource is in progress. Check the official documentation and repository before making significant custom modifications.
> {.is-warning}

---

## Compatibility

| Component            | Compatibility                                 |
| -------------------- | --------------------------------------------- |
| **FiveM**            | Yes                                           |
| **ESX Legacy**       | Yes                                           |
| **esx_addonaccount** | Required by official repository documentation |
| **esx_skin**         | Required by official repository documentation |
| **iZone**            | Optional                                      |
| **Lua 5.4**          | Enabled by the resource manifest              |
| {.dense}             |                                               |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_jobs)
* [Official ESX Legacy Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [Official esx_jobs Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_jobs)

---

## Before You Install

* [ ] Confirm all required ESX resources are installed
* [ ] Back up your database
* [ ] Import `esx_jobs.sql`
* [ ] Review `config.lua`
* [ ] Review the definitions under `jobs`
* [ ] Check the official rewrite status
* [ ] Test job vehicle deposits
* [ ] Test farming jobs

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
