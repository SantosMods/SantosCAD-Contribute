---
title: esx_weaponshop
description: esx_weaponshop provides configurable weapon shops for ESX Legacy.
published: true
date: 2026-09-11T20:38:58.083Z
tags: esx, script, shops, weapons
editor: markdown
dateCreated: 2026-09-08T00:52:30.197Z
---

# esx_weaponshop [![](https://badges.5metrics.dev/esx_weaponshop/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_weaponshop)

`esx_weaponshop` provides configurable weapon shops for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information      |
| ------------- | ---------------- |
| **Name**      | `esx_weaponshop` |
| **Creator**   | ESX Framework    |
| **Type**      | Script           |
| **Category**  | Weapons          |
| **Game**      | FiveM            |
| **Framework** | ESX Legacy       |
| **Version**   | `1.0`            |
| **Source**    | ESX Framework    |
| {.dense}      |                  |

---

## Resource Details {.tabset}

### Overview

`esx_weaponshop` allows players to purchase weapons from configured shops.

The resource supports:

* Legal weapon shops
* Illegal weapon shops
* Configurable weapon prices
* Configurable locations
* Shop blips
* Shop markers
* Optional weapon-license requirement

### Requirements

The resource requires:

* `es_extended`

It also imports ESX locale and framework files.

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Download `esx_weaponshop` from the official ESX addons repository
* [ ] Place `esx_weaponshop` in your resources folder
* [ ] Review `config.lua`
* [ ] Configure weapon shops and prices
* [ ] Configure weapon licensing if needed
* [ ] Add `esx_weaponshop` to `server.cfg`
* [ ] Restart your server
* [ ] Test configured weapon shops

### Resource Order

```cfg
ensure es_extended
ensure esx_weaponshop
```

---

## Configuration {.tabset}

### Menu

Set the menu position with:

```lua
Config.MenuPosition = 'right'
```

Documented positions are:

```text
right
left
```

### Weapon License

Enable the weapon-license requirement with:

```lua
Config.LicenseEnable = true
```

Configure the license price with:

```lua
Config.LicensePrice = 5000
```

### Shop Zones

Shop definitions are configured through:

```lua
Config.Zones
```

Shops can define:

* Legal status
* Weapons
* Prices
* Locations
* Blips

---

## Compatibility

| Component           | Support   |
| ------------------- | --------- |
| **FiveM**           | Yes       |
| **ESX Legacy**      | Yes       |
| **es_extended**     | Required  |
| **Legal shops**     | Supported |
| **Illegal shops**   | Supported |
| **Weapon licenses** | Optional  |
| {.dense}            |           |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_weaponshop)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_weaponshop)
* [Official ESX Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
