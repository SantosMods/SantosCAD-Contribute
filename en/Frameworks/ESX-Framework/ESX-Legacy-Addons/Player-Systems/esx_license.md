---
title: esx_license
description: ESX license system for adding, removing, retrieving, and checking player licenses such as driving licenses.
published: true
date: 2026-09-11T20:46:46.691Z
tags: developer-tool, esx, licenses, script
editor: markdown
dateCreated: 2026-09-11T20:46:46.691Z
---

# esx_license [![](https://badges.5metrics.dev/esx_license/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_license)

ESX license system for managing player licenses such as driving licenses.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                    | Information         |
| ------------------------ | ------------------- |
| **Name**                 | `esx_license`       |
| **Creator / Maintainer** | ESX Framework       |
| **Type**                 | Script              |
| **Category**             | License System      |
| **Game**                 | FiveM               |
| **Framework**            | ESX                 |
| **License**              | GNU GPL v3 or later |
| **Price**                | Free                |
| **Database File**        | `esx_license.sql`   |
| **Configuration File**   | `config.lua`        |
| {.dense}                 |                     |

---

## Resource Details {.tabset}

### Overview

`esx_license` provides license management for ESX resources.

Other resources can add, remove, retrieve, and check licenses assigned to players.

Driving licenses are one documented use case.

### Requirements

The current resource loads:

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
* [ ] Download `esx_license` from the official ESX source
* [ ] Place the resource in your server resources
* [ ] Import `esx_license.sql`
* [ ] Add the resource to `server.cfg`
* [ ] Restart the server

### Resource Order

```cfg
ensure oxmysql
ensure es_extended
ensure esx_license
```

> Import `esx_license.sql` before using the license system.
> {.is-success}

---

## Developer API {.tabset}

### AddLicense

Adds a license to a player.

```lua
TriggerEvent('esx_license:addLicense', target, licenseType, cb)
```

Example:

```lua
TriggerEvent('esx_license:addLicense', source, 'drive_bike', function()
end)
```

### RemoveLicense

Removes a license from a player.

```lua
TriggerEvent('esx_license:removeLicense', target, licenseType, cb)
```

Example:

```lua
TriggerEvent('esx_license:removeLicense', source, 'drive_bike', function()
end)
```

### GetLicense

Retrieves a license.

```lua
TriggerEvent('esx_license:getLicense', licenseType, cb)
```

### GetLicenses

Retrieves a player's licenses.

```lua
TriggerEvent('esx_license:getLicenses', target, cb)
```

### CheckLicense

Checks whether a player has a specified license.

```lua
TriggerEvent('esx_license:checkLicense', target, licenseType, cb)
```

Example:

```lua
TriggerEvent('esx_license:checkLicense', source, 'drive_bike', function(hasLicense)
end)
```

### getLicensesList

Retrieves the license list.

```lua
TriggerEvent('esx_license:getLicensesList', cb)
```

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

* [Official ESX Documentation](https://docs.esx-framework.org/en/esx_addons/esx_license)
* [Official ESX Legacy Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [Official esx_license Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_license)

---

## Before You Install

* [ ] Confirm `es_extended` is installed
* [ ] Confirm `oxmysql` is running
* [ ] Back up your database
* [ ] Import `esx_license.sql`
* [ ] Check license types used by dependent resources
* [ ] Test adding and removing a license
* [ ] Test license checks

---

## Credits

Created and maintained through the **ESX Framework** project and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
