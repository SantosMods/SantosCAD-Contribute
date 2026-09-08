---
title: esx_textui
description: esx_textui provides the persistent text UI used by ESX Legacy resources.
published: true
date: 2026-09-08T00:29:43.731Z
tags: esx, script, ui, text-ui
editor: markdown
dateCreated: 2026-09-08T00:29:43.731Z
---

# esx_textui

`esx_textui` provides the persistent text UI used by ESX Legacy resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information   |
| ------------- | ------------- |
| **Name**      | `esx_textui`  |
| **Creator**   | ESX-Framework |
| **Type**      | Script        |
| **Category**  | UI            |
| **Game**      | FiveM         |
| **Framework** | ESX Legacy    |
| **Version**   | `1.14.1`      |
| **Source**    | ESX Framework |
| {.dense}      |               |

---

## Resource Details {.tabset}

### Overview

`esx_textui` provides a client-side text UI for ESX resources.

Use it to display persistent interaction prompts such as:

```text
Press [E] to use
```

The official documentation provides three UI types:

* `success`
* `error`
* `info`

### Requirements

The current manifest imports:

```text
@es_extended/imports.lua
```

The resource also uses an NUI interface.

### Client Side

The official documentation states that `esx_textui` is only available on the client side.

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Keep `esx_textui` with your ESX core resources
* [ ] Start `es_extended` before `esx_textui`
* [ ] Add `esx_textui` to your server startup
* [ ] Restart your server
* [ ] Test an interaction prompt

### Resource Order

```cfg
ensure es_extended
ensure esx_textui
```

---

## Developer Usage {.tabset}

### Show Text UI

Use the ESX function:

```lua
ESX.TextUI("Press [E] to use", "error")
```

You can also use the resource export:

```lua
exports["esx_textui"]:TextUI("Press [E] to use", "error")
```

### Hide Text UI

Hide the current text UI with:

```lua
ESX.HideUI()
```

Or use the export:

```lua
exports["esx_textui"]:HideUI()
```

> `HideUI` closes any TextUI that is currently open.
> {.is-info}

---

## UI Types

The official documentation lists:

```text
success
error
info
```

Use the type argument to control the displayed style.

---

## Compatibility

| Component       | Support |
| --------------- | ------- |
| **FiveM**       | Yes     |
| **ESX Legacy**  | Yes     |
| **es_extended** | Used    |
| **Client-side** | Yes     |
| **NUI**         | Yes     |
| {.dense}        |         |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_textui)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_textui)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX-Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.