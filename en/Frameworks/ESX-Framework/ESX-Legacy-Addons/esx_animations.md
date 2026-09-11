---
title: esx_animations
description: Lightweight ESX script that lets players select and play configured FiveM animations.
published: true
date: 2026-09-11T20:36:46.547Z
tags: animation-menu, animations, esx, script
editor: markdown
dateCreated: 2026-09-10T03:32:05.252Z
---

# esx_animations [![](https://badges.5metrics.dev/esx_animations/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_animations)

`esx_animations` is an ESX script that allows players to select and perform configured animations in FiveM.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field              | Information         |
| ------------------ | ------------------- |
| **Name**           | `esx_animations`    |
| **Creator**        | ESX Framework       |
| **Type**           | Script              |
| **Category**       | Animations          |
| **Game**           | FiveM               |
| **Framework**      | ESX                 |
| **Price**          | Free                |
| **License**        | GNU GPL v3 or later |
| **Version**        | `1.0`               |
| **Legacy Version** | `1.15.0`            |
| {.dense}           |                     |

---

## Resource Details {.tabset}

### Overview

`esx_animations` provides a menu for playing animations.

The official documentation describes it as a simple, lightweight animation resource.

Players can:

* Open the animation menu
* Select configured animation categories
* Play animations
* Play scenarios
* Use attitude animations
* Stop the current animation

### Requirements

The official documentation lists:

* `es_extended`
* `esx_context`

The current manifest also loads:

```lua
@esx_lib/imports.lua
```

### Framework Support

| Framework | Support |
| --------- | ------- |
| **ESX**   | Yes     |
| {.dense}  |         |

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Install `esx_context`
* [ ] Confirm the ESX library resources required by your current ESX installation are available
* [ ] Obtain `esx_animations` from the official ESX repository
* [ ] Place `esx_animations` in your resources folder
* [ ] Review `config.lua`
* [ ] Start `esx_animations`
* [ ] Check the client and server consoles for errors

### Resource Order

```cfg
ensure es_extended
ensure esx_context
ensure esx_animations
```

---

## Controls

The official documentation lists these default controls:

| Action             | Key  |
| ------------------ | ---- |
| **Open Menu**      | `F3` |
| **Stop Animation** | `Z`  |
| {.dense}           |      |

---

## Configuration

Animations are configured through `Config.Animations`.

```lua
Config.Animations = {
    {
        name = 'category',
        label = 'Category',
        items = {
            {
                label = 'Animation Name',
                type = 'scenario',
                data = {
                    anim = 'anim_lib',
                    lib = 'lib_name'
                }
            }
        }
    }
}
```

Supported animation types documented by ESX include:

```text
attitude
scenario
anim
```

The `lib` value is used for `anim` and `attitude` types.

---

## Exports {.tabset}

### GetConfig

Use `GetConfig` to retrieve the animation configuration table.

```lua
local animations = exports['esx_animations']:GetConfig()
```

### SetConfig

Use `SetConfig` to replace the animation configuration table.

```lua
exports['esx_animations']:SetConfig(animations)
```

---

## Compatibility

| Component       | Information                        |
| --------------- | ---------------------------------- |
| **FiveM**       | Yes                                |
| **ESX**         | Required                           |
| **esx_context** | Required by official documentation |
| **Lua 5.4**     | Enabled                            |
| {.dense}        |                                    |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_animations)
* [Official ESX-Legacy-Addons Repository](https://github.com/esx-framework/ESX-Legacy-Addons)
* [esx_animations Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_animations)
* [ESX Framework](https://www.esx-framework.org/)

---

## Before You Install

* Install the documented requirements.
* Review the default `F3` and `Z` controls for conflicts.
* Review `Config.Animations` before adding or replacing animations.
* Test custom animation dictionaries and scenarios before deployment.

---

## Credits

Created through the **ESX Framework** project and its contributors. The resource license notice credits **Jérémie N'gadi**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
