---
title: ox_core
description: A modern FiveM framework, designed to properly support features like OneSync, statebags, and server-side entities.
published: true
date: 2026-09-07T19:09:39.764Z
tags: framework, free, overextended, roleplay
editor: markdown
dateCreated: 2026-09-07T04:57:04.536Z
---

# ox_core [![](https://badges.5metrics.dev/ox_core/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_core)

A FiveM framework for player and vehicle management designed around features including OneSync, statebags, and server-side entities.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information  |
| ------------ | ------------ |
| **Name**     | `ox_core`    |
| **Creator**  | Overextended |
| **Type**     | Framework    |
| **Category** | Framework    |
| **Game**     | FiveM        |
| **Price**    | Free         |
| **License**  | LGPL-3.0     |
| **Source**   | GitHub       |
| **Status**   | Active       |
| {.dense}     |              |

---

## Resource Details {.tabset}

### Overview

`ox_core` is a FiveM framework for player and vehicle management and persistence.

It is designed to support FiveM features including:

* OneSync
* Statebags
* Server-side entities
* Character management
* Player state
* Vehicle management and persistence
* Lua resource integration
* JavaScript and TypeScript resource integration

### Requirements

Required dependencies:

* `oxmysql`
* `ox_lib`
* MariaDB 11.4+

Optional dependencies recommended by Overextended include:

* `ox_inventory`
* `npwd`
* `illenium-appearance`

---

## Installation

### Installation Checklist

* [ ] Install `oxmysql`
* [ ] Install `ox_lib`
* [ ] Set up MariaDB 11.4 or newer
* [ ] Download the latest `ox_core` release
* [ ] Place `ox_core` in your resources folder
* [ ] Configure the required convars
* [ ] Start dependencies before `ox_core`
* [ ] Restart the server
* [ ] Check the server console for errors

Overextended also provides a txAdmin recipe for setting up `ox_core`.

### Building From Source

If you need to build the source:

```bash
git clone https://github.com/overextended/ox_core.git
cd ox_core
bun i
bun run build
```

Git, Node.js, and bun are required when building the resource from source.

---

## Using ox_core {.tabset}

### Lua

Load the `ox_core` definitions through your `fxmanifest.lua`:

```lua
shared_script '@ox_core/lib/init.lua'
```

You can also use the `require` functionality provided through `ox_lib`:

```lua
local Ox = require '@ox_core.lib.init'
```

### JavaScript

Overextended provides an npm package for JavaScript and TypeScript resources.

Install it with:

```bash
bun i @overextended/ox_core
```

The package provides TypeScript and IntelliSense support.

---

## Configuration

`ox_core` uses FiveM convars.

Documented replicated settings include:

| Convar                   | Default      | Purpose                                                               |
| ------------------------ | ------------ | --------------------------------------------------------------------- |
| `ox:debug`               | `false`      | Enables debug messages and commands                                   |
| `ox:characterSlots`      | `1`          | Sets available character slots                                        |
| `ox:plateFormat`         | `"........"` | Sets the vehicle plate format                                         |
| `ox:deathSystem`         | `true`       | Enables the built-in death and respawn system                         |
| `ox:hospitalBlips`       | `true`       | Enables hospital blips used by the default death system               |
| `ox:characterSelect`     | `true`       | Enables built-in character registration                               |
| `ox:defaultVehicleStore` | `'impound'`  | Sets the store used for previously spawned vehicles on resource start |
| {.dense}                 |              |                                                                       |

Replicated convars should use `setr`.

Example:

```cfg
setr ox:characterSlots 1
setr ox:deathSystem true
setr ox:hospitalBlips true
setr ox:characterSelect true
setr ox:defaultVehicleStore "impound"
```

> Review the official documentation before changing production configuration. Available convars and defaults can change between releases.
> {.is-info}

---

## Compatibility

| Component                             | Compatibility             |
| ------------------------------------- | ------------------------- |
| **FiveM**                             | Yes                       |
| **OneSync**                           | Designed for support      |
| **Statebags**                         | Designed for support      |
| **Server-side entities**              | Designed for support      |
| **ox_lib**                            | Required                  |
| **oxmysql**                           | Required                  |
| **MariaDB**                           | 11.4+                     |
| **ox_inventory**                      | Optional, recommended     |
| **Lua resources**                     | Supported                 |
| **JavaScript / TypeScript resources** | Supported through package |
| {.dense}                              |                           |

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_core)
* [GitHub Repository](https://github.com/overextended/ox_core)
* [Latest Release](https://github.com/overextended/ox_core/releases/latest)
* [npm Package](https://www.npmjs.com/package/@overextended/ox_core)
* [Overextended](https://overextended.dev/)

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
