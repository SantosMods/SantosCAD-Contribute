---
title: esx_clotheshop
description: esx_clotheshop provides clothing stores and character clothing customization for ESX Legacy.
published: true
date: 2026-09-11T20:37:12.150Z
tags: appearance, clothing, esx, script
editor: markdown
dateCreated: 2026-09-08T00:53:36.938Z
---

# esx_clotheshop [![](https://badges.5metrics.dev/esx_clotheshop/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_clotheshop)

`esx_clotheshop` provides clothing stores and character clothing customization for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information      |
| ------------- | ---------------- |
| **Name**      | `esx_clotheshop` |
| **Creator**   | ESX Framework    |
| **Type**      | Script           |
| **Category**  | Clothing         |
| **Game**      | FiveM            |
| **Framework** | ESX Legacy       |
| **Version**   | `1.0`            |
| **Source**    | ESX Framework    |
| {.dense}      |                  |

---

## Resource Details {.tabset}

### Overview

`esx_clotheshop` adds clothing stores where players can change their character appearance.

The resource supports:

* Configurable clothing prices
* Optional per-piece charging
* Multiple clothing store locations
* Configurable markers
* Configurable `skinchanger` components

### Requirements

The resource requires:

* `es_extended`
* `esx_skin`

It also uses:

* `esx_lib`
* `oxmysql`

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Install `esx_skin`
* [ ] Complete the ESX database setup
* [ ] Download `esx_clotheshop`
* [ ] Place `esx_clotheshop` in your resources folder
* [ ] Review `config.lua`
* [ ] Configure clothing stores
* [ ] Add `esx_clotheshop` to `server.cfg`
* [ ] Restart your server
* [ ] Test clothing purchases and saved appearance

### Resource Order

```cfg
ensure es_extended
ensure esx_skin
ensure esx_clotheshop
```

---

## Configuration {.tabset}

### Clothing Price

Configure the clothing price with:

```lua
Config.Price = 250
```

### Per-Piece Charging

Control whether each changed clothing component is charged separately:

```lua
Config.ChargePerPiece = false
```

### Shop Locations

Store locations are configured through:

```lua
Config.Shops
```

### Clothing Components

Configure available `skinchanger` components through:

```lua
Config.SkinProps
```

Documented components include:

```text
tshirt
torso
decals
arms
pants
shoes
bags
chain
helmet
glasses
watches
```

---

## Compatibility

| Component       | Support               |
| --------------- | --------------------- |
| **FiveM**       | Yes                   |
| **ESX Legacy**  | Yes                   |
| **es_extended** | Required              |
| **esx_skin**    | Required              |
| **skinchanger** | Used through esx_skin |
| **oxmysql**     | Used                  |
| {.dense}        |                       |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_clotheshop)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_clotheshop)
* [Official ESX Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
