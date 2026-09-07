---
title: esx_menu_dialog
description: esx_menu_dialog provides an input dialog used by ESX Legacy resources.
published: true
date: 2026-09-07T23:34:51.978Z
tags: esx, script, ui, input
editor: markdown
dateCreated: 2026-09-07T23:34:51.978Z
---

# esx_menu_dialog

`esx_menu_dialog` provides an input dialog used by ESX Legacy resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information       |
| ------------- | ----------------- |
| **Name**      | `esx_menu_dialog` |
| **Creator**   | ESX Framework     |
| **Type**      | Script            |
| **Category**  | UI                |
| **Game**      | FiveM             |
| **Framework** | ESX Legacy        |
| **Version**   | `1.15.2`          |
| **License**   | GPL-3.0-or-later  |
| {.dense}      |                   |

---

## Resource Details {.tabset}

### Overview

`esx_menu_dialog` provides a client-side menu for collecting input from players.

It integrates with `ESX.UI.Menu.Open` using the `dialog` menu type.

### Requirements

The resource declares:

* `es_extended`

The current manifest also imports:

```text
@esx_lib/imports.lua
@es_extended/imports.lua
@es_extended/client/modules/wrapper.lua
```

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Keep `esx_menu_dialog` with your ESX core resources
* [ ] Start its ESX dependencies first
* [ ] Start `esx_menu_dialog`
* [ ] Restart your server
* [ ] Test resources that use dialog input

```cfg
ensure es_extended
ensure esx_menu_dialog
```

---

## Developer Usage

Open a dialog with:

```lua
ESX.UI.Menu.Open(
    "dialog",
    GetCurrentResourceName(),
    "example_menu",
    {
        title = "Example Menu"
    },
    function(data, menu)
        local value = data.value
        print(value)
        menu.close()
    end,
    function(data, menu)
        menu.close()
    end
)
```

The value entered by the player is available through:

```lua
data.value
```

### Menu Type

Use:

```text
dialog
```

as the `type` when opening this menu.

---

## Compatibility

| Component       | Support  |
| --------------- | -------- |
| **FiveM**       | Yes      |
| **ESX Legacy**  | Yes      |
| **es_extended** | Required |
| **Client-side** | Yes      |
| {.dense}        |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_menu_dialog)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_menu_dialog)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX Framework** and project contributors.

The project credits **Jérémie N'gadi** in its licensing information.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.