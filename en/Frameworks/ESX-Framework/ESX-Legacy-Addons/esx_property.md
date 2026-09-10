---
title: esx_property
description: esx_property provides configurable player properties and housing for ESX Legacy.
published: true
date: 2026-09-09T20:22:34.915Z
tags: esx, script, housing, property
editor: markdown
dateCreated: 2026-09-09T20:22:32.750Z
---

# esx_property

esx_property provides configurable player properties and housing for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

> The ESX Team reports major issues with the current resource and states that a complete rewrite is in progress.
> {.is-warning}

---

## Resource Information

| Field            | Information                       |
| ---------------- | --------------------------------- |
| **Name**         | `esx_property`                    |
| **Creator**      | ESX Framework                     |
| **Type**         | Script                            |
| **Category**     | Housing / Property                |
| **Game**         | FiveM                             |
| **Framework**    | ESX Legacy                        |
| **Source**       | GitHub                            |
| **Known Issues** | Major issues reported by ESX Team |
| {.dense}         |                                   |

---

## Overview

esx_property provides a property system for ESX.

Players can buy, sell, and rent properties. The resource also provides property garages and systems for managing access and interiors.

---

## Features

* 95 premade properties
* Dynamic JSON storage
* Key management
* Property garages
* Furniture system
* Furniture stores
* Property editing
* Shell and IPL support
* Police raiding
* In-game property creation
* Routing buckets
* Wardrobes
* OX Inventory support
* CCTV cameras
* Night vision
* Property HUD
* Discord webhook support
* Admin menu
* Real estate job support
* Discord logging

---

## Creating Properties

Administrators can start property creation with:

```text
property:create
```

The creation process lets you configure:

1. Street number
2. Property price
3. Interior
4. Entrance position

The entrance uses the player's current coordinates.

> The default shells require the shell pack linked by the official ESX documentation.
> {.is-warning}

---

## Property Offsets

Enter the property and move to the position where you want the wardrobe or storage location.

Run:

```text
getoffset
```

The resource prints the offset to the F8 console.

---

## Admin Menu

Administrators can open the property administration menu with:

```text
property:admin
```

The menu supports property management actions including:

* Manage
* Teleport To Entrance
* Delete
* Edit property options
* Evict users

---

## Compatibility

| Component           | Support   |
| ------------------- | --------- |
| **FiveM**           | Yes       |
| **ESX Legacy**      | Yes       |
| **Shells / IPLs**   | Supported |
| **OX Inventory**    | Supported |
| **Routing buckets** | Supported |
| **Real estate job** | Supported |
| {.dense}            |           |

---

## Known Issues

The official ESX documentation currently warns that the ESX Team is aware of **major issues** with esx_property.

A complete rewrite is stated to be in progress.

Review the current official documentation and repository before deploying the resource to a production server.

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_property)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_property)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
