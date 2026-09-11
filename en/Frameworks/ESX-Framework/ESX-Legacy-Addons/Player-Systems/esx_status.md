---
title: esx_status
description: ESX status system for registering and managing player statuses such as the hunger and thirst values used by esx_basicneeds.
published: true
date: 2026-09-11T20:47:30.207Z
tags: esx, script, status, player-needs
editor: markdown
dateCreated: 2026-09-11T20:47:30.207Z
---

# esx_status [![](https://badges.5metrics.dev/esx_status/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_status)

ESX system for registering and managing player statuses such as hunger and thirst.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_status`        |
| **Creator / Maintainer** | ESX Framework       |
| **Type**                 | Script              |
| **Category**             | Player Status       |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_status.sql`    |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_status` provides the status system used to add and manage player status values.

`esx_basicneeds` uses it to manage hunger and thirst.

Resources can register additional statuses and update their values through the documented events.

### Requirements

* `es_extended`
* `oxmysql`

The current resource manifest declares `es_extended` as a dependency and loads `@oxmysql/lib/MySQL.lua`.

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
* [ ] Download `esx_status` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_status.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

```cfg
ensure oxmysql
ensure es_extended
ensure esx_status
```

> Import `esx_status.sql` before using resources that depend on the status system.
> {.is-success}

---

## Configuration

| Setting                 | Documented Default | Purpose                           |
| ----------------------- | -----------------: | --------------------------------- |
| `Config.StatusMax`      |          `1000000` | Maximum status value              |
| `Config.TickTime`       |             `1000` | Milliseconds between status ticks |
| `Config.UpdateInterval` |            `10000` | Milliseconds between status saves |
| `Config.Display`        |            `false` | Controls status display           |
| {.dense}                |                    |                                   |

---

## Client API {.tabset}

### registerStatus

Registers a status.

```lua
TriggerEvent("esx_status:registerStatus", 'hunger', 1000000, {r = 255, g = 255, b = 255}, function(status)
    status.remove(1000)
end)
```

The documented parameters include:

* `name`
* `default`
* `color`
* `visible` (deprecated)
* `tickCallback`

### unregisterStatus

Unregisters a status.

```lua
TriggerEvent("esx_status:unregisterStatus", 'hunger')
```

### set

Sets a status value.

```lua
TriggerEvent("esx_status:set", 'hunger', 1000000)
```

### add

Adds to a status value.

```lua
TriggerEvent("esx_status:add", 'hunger', 1000)
```

### remove

Removes from a status value.

```lua
TriggerEvent("esx_status:remove", 'hunger', 1000)
```

### getStatus

Retrieves a status.

```lua
TriggerEvent("esx_status:getStatus", 'hunger', function(status)
    print(status.val)
end)
```

### getAllStatus

Retrieves all registered statuses.

```lua
TriggerEvent("esx_status:getAllStatus", function(stats)
    for i = 1, #stats, 1 do
        print(stats[i].name, stats[i].val)
    end
end)
```

---

## Server API

The server-side `esx_status:getStatus` event retrieves a player's status.

```lua
TriggerEvent("esx_status:getStatus", source, 'hunger', function(status)
    print(status.val)
end)
```

> The documented `esx_status:update` event is triggered automatically and should not be called manually.
> {.is-warning}

---

## Compatibility

| Component          | Compatibility                           |
| ------------------ | --------------------------------------- |
| **FiveM**          | Yes                                     |
| **ESX Legacy**     | Yes                                     |
| **esx_basicneeds** | Uses `esx_status` for hunger and thirst |
| **oxmysql**        | Used by server scripts                  |
| **Lua 5.4**        | Enabled by the resource manifest        |
| {.dense}           |                                         |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_status)
* [Official ESX Legacy Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [Official esx_status Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_status)

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `esx_status.sql`
* [ ] Review tick and update intervals
* [ ] Check resources that depend on `esx_status`
* [ ] Test status registration and updates

---

## Credits

Created and maintained through the **ESX Framework** project and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
