---
title: esx_accessories
description: esx_accessories adds accessory shops and accessory management to ESX Legacy.
published: true
date: 2026-09-09T20:19:24.543Z
tags: clothing, esx, script, accessories
editor: markdown
dateCreated: 2026-09-09T20:19:22.980Z
---

# esx_accessories [![](https://badges.5metrics.dev/esx_accessories/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_accessories)

esx_accessories adds accessory shops and accessory management to ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information            |
| ------------- | ---------------------- |
| **Name**      | `esx_accessories`      |
| **Creator**   | ESX Framework          |
| **Type**      | Script                 |
| **Category**  | Clothing / Accessories |
| **Game**      | FiveM                  |
| **Framework** | ESX Legacy             |
| **License**   | GPL-3.0                |
| **Source**    | GitHub                 |
| {.dense}      |                        |

---

## Resource Details {.tabset}

### Overview

esx_accessories provides shops for hats, helmets, glasses, masks, and ear accessories.

Players can equip or remove purchased accessories through a menu. Purchased accessories are saved in the database.

> Accessories must be purchased through the dedicated accessory shop areas. Accessories purchased through `esx_clotheshop` are not supported.
> {.is-warning}

### Requirements

Install these resources before esx_accessories:

* `esx_skin`
* `esx_datastore`

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `esx_skin`
* [ ] Install `esx_datastore`
* [ ] Install `esx_accessories` from the official ESX Legacy Addons repository
* [ ] Import `esx_accessories.sql`
* [ ] Review `config.lua`
* [ ] Add `esx_accessories` to `server.cfg`
* [ ] Restart your server
* [ ] Test accessory shops and saved accessories

### Resource

```cfg
ensure esx_accessories
```

---

## Configuration

Configure the resource through `config.lua`.

| Option                  | Default                       | Purpose                                      |
| ----------------------- | ----------------------------- | -------------------------------------------- |
| `Config.Price`          | `100`                         | Accessory purchase price                     |
| `Config.EnableControls` | `true`                        | Enables accessory equip and removal controls |
| `Config.DrawDistance`   | `10.0`                        | Shop marker draw distance                    |
| `Config.Size`           | `{x = 1.5, y = 1.5, z = 1.0}` | Shop marker size                             |
| `Config.Color`          | `{r = 50, g = 200, b = 50}`   | Shop marker color                            |
| `Config.Type`           | `1`                           | Shop marker type                             |
| `Config.ShopsBlips`     | Table                         | Shop blip definitions                        |
| `Config.Zones`          | Table                         | Accessory shop zones                         |
| {.dense}                |                               |                                              |

Example shop blip:

```lua
Config.ShopsBlips = {
    Mask = {
        Pos = {
            vector3(-1338.1, -1278.2, 3.8),
        },
        Blip = {sprite = 362, color = 2}
    },
}
```

---

## Compatibility

| Component                    | Support  |
| ---------------------------- | -------- |
| **FiveM**                    | Yes      |
| **ESX Legacy**               | Yes      |
| **esx_skin**                 | Required |
| **esx_datastore**            | Required |
| **esx_clotheshop purchases** | No       |
| {.dense}                     |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_accessories)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_accessories)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
