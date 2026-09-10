---
title: esx_addonaccount
description: ESX addon that stores shared and player-specific account data such as society funds.
published: true
date: 2026-09-10T03:27:39.810Z
tags: esx, script, accounts, shared-accounts
editor: markdown
dateCreated: 2026-09-10T03:27:39.810Z
---

# esx_addonaccount [![](https://badges.5metrics.dev/esx_addonaccount/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_addonaccount)

`esx_addonaccount` provides shared and player-specific account storage for ESX resources, including society funds.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                           | Information         |
| ------------------------------- | ------------------- |
| **Name**                        | `esx_addonaccount`  |
| **Creator**                     | ESX Framework       |
| **Type**                        | Script              |
| **Category**                    | Account storage     |
| **Game**                        | FiveM               |
| **Framework**                   | ESX                 |
| **Price**                       | Free                |
| **License**                     | GNU GPL v3 or later |
| **Version in current manifest** | `1.1`               |
| **Legacy version**              | `1.15.0`            |
| {.dense}                        |                     |

---

## Resource Details {.tabset}

### Overview

`esx_addonaccount` allows other ESX resources to store account data.

The official ESX documentation identifies two account types:

* **Shared accounts** are not assigned to one player. Society accounts are a common example.
* **Non-shared accounts** are created for individual players when they load.

The resource is used by ESX resources including `esx_society` and `esx_billing`.

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
* [ ] Obtain `esx_addonaccount` from the official ESX repository
* [ ] Place `esx_addonaccount` in your server resources
* [ ] Configure required accounts in the database
* [ ] Start `esx_addonaccount`
* [ ] Restart the server after adding new addon accounts
* [ ] Check the server console for errors

### Resource Order

Start `es_extended` and `oxmysql` before `esx_addonaccount`.

```cfg
ensure es_extended
ensure oxmysql
ensure esx_addonaccount
```

> An addon account must exist in the database before a resource can use it. Restart the server after adding a new account.
> {.is-warning}

---

## Database Configuration

Addon accounts use the `addon_account` table.

| Field    | Type    | Purpose                                   |
| -------- | ------- | ----------------------------------------- |
| `name`   | string  | Account name                              |
| `label`  | string  | Account label                             |
| `shared` | boolean | `1` for shared or `0` for player-specific |
| {.dense} |         |                                           |

---

## Usage {.tabset}

### Shared Account Event

```lua
TriggerEvent('esx_addonaccount:getSharedAccount', 'society_realestateagent', function(account)
    account.addMoney(500)
end)
```

### Player Account Event

```lua
TriggerEvent('esx_addonaccount:getAccount', 'property_black_money', 'steam:0123456789', function(account)
    account.removeMoney(500)
end)
```

### Exports

The current resource exposes account functions through exports.

```lua
local account = exports['esx_addonaccount']:GetAccount('property_black_money', 'steam:0123456789')
account.addMoney(500)
```

```lua
local account = exports['esx_addonaccount']:GetSharedAccount('society_realestateagent')
account.addMoney(500)
```

Available server exports in the current manifest include:

```text
GetSharedAccount
AddSharedAccount
GetAccount
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

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_addonaccount)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_addonaccount Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_addonaccount)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Confirm `es_extended` is running.
* Confirm `oxmysql` is installed and connected to your database.
* Add required addon accounts before scripts try to access them.
* Restart the server after adding database account definitions.

---

## Credits

Created and maintained through the **ESX Framework** project and its contributors. The resource copyright notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
