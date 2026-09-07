---
title: ox_target
description: A standalone FiveM targeting resource for interacting with entities, zones, vehicles, players, and the game world.
published: true
date: 2026-09-07T19:09:21.525Z
tags: free, overextended, script, target
editor: markdown
dateCreated: 2026-09-07T05:03:23.005Z
---

# ox_target [![](https://badges.5metrics.dev/ox_target/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_target)

A standalone FiveM targeting resource for interacting with entities, zones, vehicles, players, and the game world.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information  |
| ------------- | ------------ |
| **Name**      | `ox_target`  |
| **Creator**   | Overextended |
| **Type**      | Script       |
| **Category**  | Targeting    |
| **Game**      | FiveM        |
| **Price**     | Free         |
| **License**   | MIT          |
| **Framework** | Standalone   |
| **Source**    | GitHub       |
| {.dense}      |              |

---

## Resource Details {.tabset}

### Overview

`ox_target` is a standalone "third-eye" targeting resource.

It provides interactions with the world, entities, and zones.

Features include:

* Entity targeting
* World interactions
* Zone targeting
* Nested target option menus
* Built-in targeting options
* Group checks for supported frameworks
* Item checks
* Partial qtarget compatibility
* Configurable target hotkey
* Debugging and testing options

### Requirements

Required dependency:

* `ox_lib`

### Framework Support

A framework is not required to run `ox_target`.

Official integrations provide additional functionality for:

| Framework             | Support                  |
| --------------------- | ------------------------ |
| **Standalone**        | Supported                |
| **ox_core**           | Additional functionality |
| **ESX / es_extended** | Additional functionality |
| **Qbox / qbx_core**   | Additional functionality |
| {.dense}              |                          |

The official documentation also identifies additional functionality for `ox_inventory`.

---

## Installation

### Installation Checklist

* [ ] Install `ox_lib`
* [ ] Download the latest `ox_target` release
* [ ] Place `ox_target` in your resources folder
* [ ] Configure the convars
* [ ] Start `ox_lib` before `ox_target`
* [ ] Start the resource
* [ ] Test targeting in-game
* [ ] Check the console for errors

### Clone From Source

```bash
git clone https://github.com/overextended/ox_target.git
```

---

## Configuration

`ox_target` uses FiveM convars.

### Hotkey Behaviour

Toggle targeting instead of holding the hotkey:

```cfg
setr ox_target:toggleHotkey 0
```

Set the default targeting key:

```cfg
setr ox_target:defaultHotkey LMENU
```

### Zone Sprite

Draw a sprite at the centre of a zone:

```cfg
setr ox_target:drawSprite 1
```

### Default Options

Enable built-in targeting options such as vehicle door interactions:

```cfg
setr ox_target:defaults 1
```

### Debugging

Enable debugging, testing options, entity outlines, and the raycast indicator:

```cfg
setr ox_target:debug 0
```

### Left Click

Configure left-click option selection:

```cfg
setr ox_target:leftClick 1
```

> Keep production debugging disabled unless you are diagnosing or testing targeting behaviour.
> {.is-info}

---

## Compatibility

| Component        | Compatibility            |
| ---------------- | ------------------------ |
| **FiveM**        | Supported                |
| **Standalone**   | Supported                |
| **ox_lib**       | Required                 |
| **ox_core**      | Additional functionality |
| **es_extended**  | Additional functionality |
| **qbx_core**     | Additional functionality |
| **ox_inventory** | Additional functionality |
| **qtarget**      | Partial compatibility    |
| {.dense}         |                          |

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_target)
* [GitHub Repository](https://github.com/overextended/ox_target)
* [Latest Release](https://github.com/overextended/ox_target/releases/latest)
* [Overextended](https://overextended.dev/)

---

## Before You Install

`ox_target` does not require a roleplay framework.

Install `ox_lib` before starting the resource.

Framework integrations provide additional functionality but are not required for standalone use.

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
