---
title: esx_basicneeds
description: ESX hunger and thirst resource that uses esx_status and supports configurable food and drink items.
published: true
date: 2026-09-11T20:30:19.698Z
tags: esx, script, status, needs
editor: markdown
dateCreated: 2026-09-11T20:30:19.698Z
---

# esx_basicneeds [![](https://badges.5metrics.dev/esx_basicneeds/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_basicneeds)

ESX hunger and thirst resource with configurable food and drink items.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information          |
| ------------------------ | -------------------- |
| **Name**                 | `esx_basicneeds`     |
| **Creator / Maintainer** | ESX Framework        |
| **Original Copyright**   | Jérémie N'gadi       |
| **Type**                 | Script               |
| **Category**             | Player Needs         |
| **Game**                 | FiveM                |
| **Framework**            | ESX                  |
| **License**              | GNU GPL v3 or later  |
| **Price**                | Free                 |
| **Database File**        | `esx_basicneeds.sql` |
| **Configuration File**   | `config.lua`         |
| {.dense}                 |                      |

---

## Resource Details {.tabset}

### Overview

`esx_basicneeds` implements hunger and thirst statuses for ESX.

Food and drink items can increase those statuses when used.

### Requirements

* `es_extended`
* `esx_status`

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
* [ ] Install `esx_status`
* [ ] Download `esx_basicneeds` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_basicneeds.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

```cfg
ensure es_extended
ensure esx_status
ensure esx_basicneeds
```

> Import `esx_basicneeds.sql` before using the resource.
> {.is-success}

---

## Configuration {.tabset}

### Items

`Config.Items` registers usable food and drink items.

The documented structure includes:

```lua
Config.Items = {
    ['item'] = {
        type = 'food',
        prop = "prop_name",
        status = 200000,
        remove = true,
        anim = {
            dict = 'anim_dict',
            name = 'anim_name',
            settings = {8.0, -8, -1, 49, 0, 0, 0, 0}
        },
        pos = vector3(0.15, 0.03, 0.0),
        rot = vector3(15.0, 175.0, 5.0)
    },
}
```

Documented item fields include:

* `type`
* `prop`
* `status`
* `remove`
* `anim`
* `pos`
* `rot`

`type` accepts food or drink behavior.

### Deprecated Setting

`Config.Visible` is documented as deprecated.

---

## Events {.tabset}

### resetStatus

Resets hunger and thirst status on the client.

```lua
TriggerEvent('esx_basicneeds:resetStatus')
```

### healPlayer

The documented heal event can be triggered client-side or server-side.

```lua
TriggerEvent('esx_basicneeds:healPlayer')
```

Server-side example:

```lua
TriggerClientEvent('esx_basicneeds:healPlayer', source)
```

### onUse

`esx_basicneeds:onUse` runs when a configured item is used.

```lua
RegisterNetEvent('esx_basicneeds:onUse', function(itemType, propName, anim, pos, rot)
    -- Custom handling
end)
```

---

## Compatibility

| Component      | Compatibility                    |
| -------------- | -------------------------------- |
| **FiveM**      | Yes                              |
| **ESX Legacy** | Yes                              |
| **esx_status** | Required                         |
| **Lua 5.4**    | Enabled by the resource manifest |
| {.dense}       |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_basicneeds)
* Official source repository: ESX Framework `ESX-Legacy-Addons`

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `esx_status` is installed
* [ ] Back up your database
* [ ] Import `esx_basicneeds.sql`
* [ ] Review `Config.Items`
* [ ] Confirm the resource starts without console errors

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
