---
title: ox_inventory
description: An inventory system for FiveM.
published: true
date: 2026-09-07T19:08:17.740Z
tags: free, inventory, overextended, script
editor: markdown
dateCreated: 2026-09-07T03:54:06.881Z
---

# ox_inventory [![](https://badges.5metrics.dev/ox_inventory/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_inventory)

A slot-based FiveM inventory system with item metadata, shops, stashes, crafting, weapons, and vehicle storage.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information      |
| ------------ | ---------------- |
| **Name**     | `ox_inventory`   |
| **Creator**  | Overextended     |
| **Type**     | Script           |
| **Category** | Inventory        |
| **Game**     | FiveM            |
| **Price**    | Free             |
| **License**  | GPL-3.0 or later |
| **Source**   | GitHub           |
| **Status**   | Active           |
| {.dense}     |                  |

---

## Resource Details {.tabset}

### Overview

`ox_inventory` is a slot-based inventory system for FiveM.

Features include:

* Per-slot item metadata
* Weapons as inventory items
* Weapon attachments and ammunition
* Item durability
* Shops
* Stashes
* Crafting
* Vehicle gloveboxes and trunks
* Containers
* Server-side validation
* Inventory logging
* Synchronised inventory access

### Requirements

Required dependencies:

* `oxmysql`
* `ox_lib`

Optional dependency:

* `ox_target`

### Framework Support

Official framework support includes:

| Framework   | Support   |
| ----------- | --------- |
| **ox_core** | Supported |
| **ESX**     | Supported |
| **Qbox**    | Supported |
| **ND Core** | Supported |
| {.dense}    |           |

> Frameworks with their own inventory, item, or weapon systems may have compatibility issues when replacing their built-in inventory.
> {.is-warning}

---

## Installation

### Installation Checklist

* [ ] Install `oxmysql`
* [ ] Install `ox_lib`
* [ ] Install your supported framework
* [ ] Download the latest `ox_inventory` release
* [ ] Place `ox_inventory` in your resources folder
* [ ] Configure the inventory convars
* [ ] Check your resource start order
* [ ] Start the server
* [ ] Check the server console for errors

### Resource Order

Use a logical resource order so dependencies start before `ox_inventory`.

```cfg
start oxmysql
start ox_lib
start framework
start ox_target
start ox_inventory
```

Replace `framework` with your framework resource, such as `ox_core`, `es_extended`, or `qbx_core`.

`ox_target` is optional.

---

## Configuration

`ox_inventory` uses FiveM convars for configuration.

Set your framework with `inventory:framework`.

```cfg
setr inventory:framework "esx"
```

Supported framework values documented by Overextended are:

```text
ox
esx
qbx
nd
```

Basic inventory settings include:

```cfg
setr inventory:slots 50
setr inventory:weight 30000
setr inventory:dropslots 50
setr inventory:dropweight 30000
```

Enable integrated target support when required:

```cfg
setr inventory:target true
```

> Check the official documentation before copying a complete configuration. Available convars and defaults can change between releases.
> {.is-info}

---

## Compatibility

| Component     | Compatibility |
| ------------- | ------------- |
| **FiveM**     | Yes           |
| **ox_core**   | Supported     |
| **ESX**       | Supported     |
| **Qbox**      | Supported     |
| **ND Core**   | Supported     |
| **ox_lib**    | Required      |
| **oxmysql**   | Required      |
| **ox_target** | Optional      |
| {.dense}      |               |

### Framework Incompatibilities

Frameworks with built-in inventory, item, or weapon systems are expected to have compatibility issues.

Money represented as an inventory item can also conflict with framework banking or account systems.

Unsupported frameworks require a custom bridge and database references.

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_inventory)
* [GitHub Repository](https://github.com/overextended/ox_inventory)
* [Latest Release](https://github.com/overextended/ox_inventory/releases/latest)
* [Overextended](https://overextended.dev/)

---

## Before You Install

> Replacing a framework's built-in inventory can cause compatibility errors. Review your framework and resource compatibility before migrating.
> {.is-warning}

Back up your server and database before replacing an existing inventory system.

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
