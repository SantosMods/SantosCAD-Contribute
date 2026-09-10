---
title: esx_addoninventory
description: ESX addon that provides shared and player-specific item inventories for other resources.
published: true
date: 2026-09-10T03:28:25.715Z
tags: esx, inventory, script, shared-inventory
editor: markdown
dateCreated: 2026-09-10T03:28:25.715Z
---

# esx_addoninventory [![](https://badges.5metrics.dev/esx_addoninventory/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_addoninventory)

`esx_addoninventory` provides shared and player-specific item storage for ESX resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                           | Information          |
| ------------------------------- | -------------------- |
| **Name**                        | `esx_addoninventory` |
| **Creator**                     | ESX Framework        |
| **Type**                        | Script               |
| **Category**                    | Inventory            |
| **Game**                        | FiveM                |
| **Framework**                   | ESX                  |
| **Price**                       | Free                 |
| **License**                     | GNU GPL v3 or later  |
| **Version in current manifest** | `1.0`                |
| **Legacy version**              | `1.15.0`             |
| {.dense}                        |                      |

---

## Resource Details {.tabset}

### Overview

`esx_addoninventory` allows other ESX resources to store items outside a player's standard inventory.

The official documentation defines two inventory types:

* **Shared inventories** are available without belonging to one specific player.
* **Non-shared inventories** are created separately for individual players when they load.

`esx_society` is one ESX resource that uses addon inventories.

### Requirements

* `es_extended`
* `oxmysql`

The current `fxmanifest.lua` loads:

```lua
'@es_extended/imports.lua',
'@oxmysql/lib/MySQL.lua'
```

### Framework Support

| Framework | Support |
| --------- | ------- |
| **ESX**   | Yes     |
| {.dense}  |         |

---

## Installation

### Installation Checklist

* [ ] Install and configure ESX
* [ ] Install `oxmysql`
* [ ] Obtain `esx_addoninventory` from the official ESX repository
* [ ] Place `esx_addoninventory` in your server resources
* [ ] Import `esx_addoninventory.sql`
* [ ] Configure required addon inventories in the database
* [ ] Start `esx_addoninventory`
* [ ] Restart the server after adding new inventory definitions
* [ ] Check the server console for errors

### Resource Order

```cfg
ensure es_extended
ensure oxmysql
ensure esx_addoninventory
```

> An addon inventory must be configured in the database before another resource uses it.
> {.is-warning}

---

## Database Configuration

Addon inventories use the `addon_inventory` table.

| Field    | Type    | Purpose                                   |
| -------- | ------- | ----------------------------------------- |
| `name`   | string  | Inventory name                            |
| `label`  | string  | Inventory label                           |
| `shared` | boolean | `1` for shared or `0` for player-specific |
| {.dense} |         |                                           |

After adding an inventory definition, restart the server. The official repository also notes that you can restart the resource and have clients reconnect.

---

## Usage {.tabset}

### Shared Inventory

```lua
TriggerEvent('esx_addoninventory:getSharedInventory', 'society_police', function(inventory)
    inventory.addItem('bread', 1)
end)
```

### Player Inventory

```lua
TriggerEvent('esx_addoninventory:getInventory', 'property', 'steam:0123456789', function(inventory)
    inventory.removeItem('water', 1)
end)
```

### Server Exports

The current manifest exposes:

```text
GetSharedInventory
AddSharedInventory
```

---

## Compatibility

| Component            | Information                     |
| -------------------- | ------------------------------- |
| **FiveM**            | Yes                             |
| **ESX**              | Required                        |
| **Database library** | `oxmysql`                       |
| **Lua 5.4**          | Enabled in the current manifest |
| {.dense}             |                                 |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_addoninventory)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_addoninventory Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_addoninventory)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Confirm `es_extended` is running.
* Confirm `oxmysql` is installed and connected.
* Import `esx_addoninventory.sql`.
* Create required inventory definitions before dependent resources access them.

---

## Credits

Created and maintained through the **ESX Framework** project and its contributors. The resource copyright notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
