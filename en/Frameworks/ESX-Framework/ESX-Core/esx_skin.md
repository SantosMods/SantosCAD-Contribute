---
title: esx_skin
description: esx_skin provides character appearance customization and skin saving for ESX Legacy.
published: true
date: 2026-09-08T00:26:07.242Z
tags: characters, esx, script, appearance
editor: markdown
dateCreated: 2026-09-07T23:43:04.901Z
---

# esx_skin [![](https://badges.5metrics.dev/esx_skin/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_skin)

`esx_skin` provides character appearance customization and skin saving for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information      |
| ------------- | ---------------- |
| **Name**      | `esx_skin`       |
| **Creator**   | ESX Framework    |
| **Type**      | Script           |
| **Category**  | Characters       |
| **Game**      | FiveM            |
| **Framework** | ESX Legacy       |
| **Version**   | `1.15.2`         |
| **License**   | GPL-3.0-or-later |
| {.dense}      |                  |

---

## Resource Details {.tabset}

### Overview

`esx_skin` allows players to customize and save their character appearance.

The resource provides the ESX skin selector and works with `skinchanger` to apply character appearance.

Character skin data is stored against the player's identifier in the ESX `users` table.

### Requirements

The current manifest declares:

* `es_extended`
* `skinchanger`

The resource also imports:

* `esx_lib`
* `oxmysql`

### Inventory Weight

When ESX custom inventory mode is not active, `esx_skin` can adjust a player's maximum inventory weight based on the configured backpack.

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Install `skinchanger`
* [ ] Keep `esx_skin` with your ESX core resources
* [ ] Complete the ESX database setup
* [ ] Review `config.lua`
* [ ] Start the required dependencies first
* [ ] Start `esx_skin`
* [ ] Restart your server
* [ ] Test character appearance saving

### Resource Order

Start `skinchanger` before `esx_skin`.

```cfg
ensure es_extended
ensure skinchanger
ensure esx_skin
```

---

## Configuration

The resource includes:

```text
config.lua
```

Review this file before changing skin-related configuration.

The current server implementation uses configured backpack values to modify maximum player weight when ESX is not using a custom inventory.

---

## Developer Usage {.tabset}

### Save Skin

The server listens for:

```text
esx_skin:save
```

The supplied skin is stored in the `users` table for the player's identifier.

### Get Player Skin

The resource provides a callback for retrieving the player's saved skin and job skin information:

```text
esx_skin:getPlayerSkin
```

### Open Skin Menu

The resource uses:

```text
esx_skin:openSaveableMenu
```

to open a saveable character appearance menu.

`esx_multicharacter` also uses this event during new-character creation.

---

## Commands

The resource registers the admin command:

```text
skin
```

It can open the saveable skin menu for a selected player.

---

## Compatibility

| Component       | Support  |
| --------------- | -------- |
| **FiveM**       | Yes      |
| **ESX Legacy**  | Yes      |
| **es_extended** | Required |
| **skinchanger** | Required |
| **oxmysql**     | Used     |
| **esx_lib**     | Used     |
| {.dense}        |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_skin)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_skin)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX Framework** and project contributors.

The project's licensing information credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
