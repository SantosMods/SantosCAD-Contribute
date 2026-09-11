---
title: esx_billing
description: ESX billing resource that lets jobs send player invoices and provides a menu for viewing and paying bills.
published: true
date: 2026-09-11T20:31:04.793Z
tags: esx, jobs, script, billing
editor: markdown
dateCreated: 2026-09-11T20:31:04.793Z
---

# esx_billing [![](https://badges.5metrics.dev/esx_billing/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_billing)

ESX billing resource for sending, viewing, and paying player invoices.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_billing`       |
| **Creator / Maintainer** | ESX Framework       |
| **Original Copyright**   | Jérémie N'gadi      |
| **Type**                 | Script              |
| **Category**             | Billing             |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_billing.sql`   |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_billing` allows jobs to send bills to other players.

The official documentation gives police fines as one example.

Players can open a billing menu to view and pay invoices.

### Requirements

The current resource manifest uses:

* `es_extended`
* `oxmysql`

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
* [ ] Install and start `oxmysql`
* [ ] Download `esx_billing` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_billing.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

```cfg
ensure oxmysql
ensure es_extended
ensure esx_billing
```

> Import `esx_billing.sql` before using the billing system.
> {.is-success}

---

## Usage {.tabset}

### Billing Menu

The default documented keybind is:

```text
F7
```

The current client resource registers the `showbills` command and maps it to `F7`.

### Sending a Bill

The official documentation uses `esx_billing:sendBill` to create a bill.

```lua
local amount = 100
local closestPlayer, closestDistance = ESX.Game.GetClosestPlayer()

if closestPlayer == -1 or closestDistance > 3.0 then
    ESX.ShowNotification('There\'s no players nearby!')
else
    TriggerServerEvent(
        'esx_billing:sendBill',
        GetPlayerServerId(closestPlayer),
        'society_taxi',
        'Taxi',
        amount
    )
end
```

The event parameters in the example identify the target player, society account, bill label, and amount.

---

## Compatibility

| Component      | Compatibility                    |
| -------------- | -------------------------------- |
| **FiveM**      | Yes                              |
| **ESX Legacy** | Yes                              |
| **oxmysql**    | Used by server scripts           |
| **Lua 5.4**    | Enabled by the resource manifest |
| {.dense}       |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_billing)
* Official source repository: ESX Framework `ESX-Legacy-Addons`

---

## Before You Install

* [ ] Confirm `es_extended` is running
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `esx_billing.sql`
* [ ] Confirm jobs that send bills use the expected society accounts
* [ ] Test invoice creation and payment

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
