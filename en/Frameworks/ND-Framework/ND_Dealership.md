---
title: ND_Dealership
description: ND_Dealership provides vehicle dealerships for ND Framework.
published: true
date: 2026-09-08T00:21:27.798Z
tags: nd, script, vehicles, dealership
editor: markdown
dateCreated: 2026-09-07T18:43:02.682Z
---

# ND_Dealership [![](https://badges.5metrics.dev/ND_Dealership/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ND_Dealership)

ND_Dealership provides vehicle dealerships for ND Framework.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information     |
| ------------- | --------------- |
| **Name**      | `ND_Dealership` |
| **Creator**   | Andyyy          |
| **Type**      | Script          |
| **Category**  | Vehicles        |
| **Game**      | FiveM           |
| **Framework** | ND Framework    |
| **Version**   | `2.0.1`         |
| **License**   | GPL-3.0         |
| **Source**    | GitHub          |
| {.dense}      |                 |

---

## Resource Details {.tabset}

### Overview

ND_Dealership is a vehicle dealership resource for ND Framework.

Officially documented features include:

* Showcase rooms
* Vehicle catalog menu
* Vehicle previews
* Test drives
* `ox_target` interactions

### Requirements

The manifest declares these dependencies:

* `ND_Core`
* `ox_lib`
* `ox_target`

---

## Installation

### Installation Checklist

* [ ] Install `ND_Core`
* [ ] Install `ox_lib`
* [ ] Install `ox_target`
* [ ] Download `ND_Dealership` from the official GitHub repository
* [ ] Place `ND_Dealership` in your resources folder
* [ ] Configure dealerships
* [ ] Configure available vehicles
* [ ] Add `ND_Dealership` to `server.cfg`
* [ ] Restart your server
* [ ] Test dealership interactions

### Resource Order

```cfg
ensure ox_lib
ensure ox_target
ensure ND_Core
ensure ND_Dealership
```

---

## Configuration {.tabset}

### Dealerships

Dealership definitions are stored in:

```text
data/dealerships.lua
```

### Vehicles

Vehicle definitions are stored in:

```text
data/vehicles.lua
```

The manifest also includes client files for showroom, test-drive, menu, and ped functionality.

---

## Features

### Showcase Rooms

ND_Dealership supports showroom displays for dealership vehicles.

### Vehicle Catalog

Players can browse vehicles through the dealership catalog menu.

### Preview and Test Drive

The resource supports vehicle previewing and test drives before purchase.

### Target Interactions

Dealership interactions use `ox_target`.

---

## Compatibility

| Component     | Support  |
| ------------- | -------- |
| **FiveM**     | Yes      |
| **ND Core**   | Required |
| **ox_lib**    | Required |
| **ox_target** | Required |
| {.dense}      |          |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Dealership)

---

## Credits

Created by **Andyyy** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
