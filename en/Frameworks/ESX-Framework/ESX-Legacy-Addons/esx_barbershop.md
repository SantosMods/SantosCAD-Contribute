---
title: esx_barbershop
description: ESX barbershop resource that uses esx_skin to let players pay to change hair and beard styles.
published: true
date: 2026-09-11T20:29:43.116Z
tags: esx, script, character-customization, barbershop
editor: markdown
dateCreated: 2026-09-11T20:29:43.116Z
---

# esx_barbershop [![](https://badges.5metrics.dev/esx_barbershop/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_barbershop)

ESX barbershop resource that uses `esx_skin` to let players change hair and beard styles.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information             |
| ------------------------ | ----------------------- |
| **Name**                 | `esx_barbershop`        |
| **Creator / Maintainer** | ESX Framework           |
| **Original Copyright**   | Jérémie N'gadi          |
| **Type**                 | Script                  |
| **Category**             | Character Customization |
| **Game**                 | FiveM                   |
| **Framework**            | ESX                     |
| **License**              | GNU GPL v3 or later     |
| **Price**                | Free                    |
| **Configuration File**   | `config.lua`            |
| {.dense}                 |                         |

---

## Resource Details {.tabset}

### Overview

`esx_barbershop` adds barber shops where players can pay to change their hair and beard appearance.

It uses `esx_skin` for character appearance changes.

### Requirements

* `es_extended`
* `esx_skin`

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
* [ ] Install `esx_skin`
* [ ] Download `esx_barbershop` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server
* [ ] Check the console for errors

### Resource Order

```cfg
ensure es_extended
ensure esx_skin
ensure esx_barbershop
```

---

## Configuration {.tabset}

### Pricing

`Config.Price` controls the price charged for a hairstyle or beard change.

The documented default is:

```lua
Config.Price = 100
```

### Markers

The official documentation exposes:

* `Config.DrawDistance`
* `Config.MarkerSize`
* `Config.MarkerColor`
* `Config.MarkerType`

### Shop Locations

`Config.Shops` contains the configured barber shop coordinates.

Example structure:

```lua
Config.Shops = {
    vector3(-814.3, -183.8, 36.6),
    vector3(136.8, -1708.4, 28.3)
}
```

Add or change entries in this table to modify barber shop locations.

---

## Compatibility

| Component      | Compatibility                    |
| -------------- | -------------------------------- |
| **FiveM**      | Yes                              |
| **ESX Legacy** | Yes                              |
| **esx_skin**   | Required                         |
| **Lua 5.4**    | Enabled by the resource manifest |
| {.dense}       |                                  |

---

## Links

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_barbershop)
* Official source repository: ESX Framework `ESX-Legacy-Addons`

---

## Before You Install

* [ ] Confirm `es_extended` is running
* [ ] Confirm `esx_skin` is installed
* [ ] Review `Config.Price`
* [ ] Review barber shop locations in `Config.Shops`
* [ ] Confirm the resource starts without console errors

---

## Credits

Created and maintained through the **ESX Framework** project, with copyright credited to **Jérémie N'gadi** and contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
