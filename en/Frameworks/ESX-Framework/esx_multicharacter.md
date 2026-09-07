---
title: esx_multicharacter
description: esx_multicharacter allows ESX Legacy players to create and use multiple characters.
published: true
date: 2026-09-07T23:43:52.645Z
tags: characters, esx, multicharacter, script
editor: markdown
dateCreated: 2026-09-07T23:40:50.580Z
---

# esx_multicharacter [![](https://badges.5metrics.dev/esx_multicharacter/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_multicharacter)

`esx_multicharacter` allows ESX Legacy players to create and use multiple characters.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information                  |
| ------------- | ---------------------------- |
| **Name**      | `esx_multicharacter`         |
| **Creator**   | ESX-Framework, Linden & KASH |
| **Type**      | Script                       |
| **Category**  | Characters                   |
| **Game**      | FiveM                        |
| **Framework** | ESX Legacy                   |
| **Version**   | `1.15.0`                     |
| **License**   | GPL-3.0-or-later             |
| {.dense}      |                              |

---

## Resource Details {.tabset}

### Overview

`esx_multicharacter` provides the official multi-character system for ESX Legacy.

Players can create and select multiple characters from the same account.

The system supports:

* Multiple character slots
* Character creation
* Character selection
* Character deletion
* Per-player slot management
* Character appearance loading
* Relogging
* Configurable character selection spawn

### Requirements

The current manifest declares:

* `es_extended`
* `esx_context`
* `esx_identity`
* `esx_skin`

The resource also uses `oxmysql` for server-side database access and imports `esx_lib`.

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Install `esx_context`
* [ ] Install `esx_identity`
* [ ] Install `esx_skin`
* [ ] Keep `esx_multicharacter` with your ESX core resources
* [ ] Review `config.lua`
* [ ] Start the required ESX resources first
* [ ] Restart your server
* [ ] Test character creation and selection

---

## Configuration {.tabset}

### Character Slots

Configure the default number of character slots with:

```lua
Config.Slots = 3
```

This value applies to players unless you assign individual slot counts.

### Character Deletion

Allow players to delete characters with:

```lua
Config.CanDelete = true
```

### Character Prefix

Character identifiers use the configured prefix:

```lua
Config.Prefix = "char"
```

Characters are stored using identifiers based on the character slot and player identifier.

### Relogging

Relogging is controlled with:

```lua
Config.Relog = true
```

The client registers the `relog` command when this option is enabled.

> The configuration warns that relogging can require other resources to correctly reset their data.
> {.is-warning}

---

## Commands

The project documents commands for managing individual character access and slot counts:

```text
setslots
remslots
enablechar
disablechar
```

The client can also provide:

```text
relog
```

when relogging is enabled.

---

## Compatibility

| Component        | Support  |
| ---------------- | -------- |
| **FiveM**        | Yes      |
| **ESX Legacy**   | Yes      |
| **es_extended**  | Required |
| **esx_context**  | Required |
| **esx_identity** | Required |
| **esx_skin**     | Required |
| {.dense}         |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_multicharacter)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_multicharacter)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX-Framework, Linden, KASH**, and project contributors.

The project is based on the earlier Kashacters resource and states that much of the code was rewritten with permission from KASH.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
