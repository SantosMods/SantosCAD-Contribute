---
title: esx_menu_default
description: esx_menu_default provides the default list-style menu used by ESX Legacy resources.
published: true
date: 2026-09-08T00:24:39.655Z
tags: esx, menus, script, ui
editor: markdown
dateCreated: 2026-09-07T23:34:01.519Z
---

# esx_menu_default [![](https://badges.5metrics.dev/esx_menu_default/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_menu_default)

`esx_menu_default` provides the default list-style menu used by ESX Legacy resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information        |
| ------------- | ------------------ |
| **Name**      | `esx_menu_default` |
| **Creator**   | ESX Framework      |
| **Type**      | Script             |
| **Category**  | UI                 |
| **Game**      | FiveM              |
| **Framework** | ESX Legacy         |
| **Version**   | `1.14.1`           |
| **License**   | GPL-3.0-or-later   |
| {.dense}      |                    |

---

## Resource Details {.tabset}

### Overview

`esx_menu_default` provides a list-style menu for `es_extended`.

It is available on the client side.

The menu supports:

* Buttons
* Sliders
* Selectable elements
* Unselectable elements
* Icons
* Custom values
* Slider options
* Multiple menu alignments

### Requirements

The resource declares:

* `es_extended`

The manifest loads:

```text
@es_extended/imports.lua
```

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Download the official ESX Legacy core resources
* [ ] Keep `esx_menu_default` with your ESX core resources
* [ ] Start `es_extended` before `esx_menu_default`
* [ ] Restart your server
* [ ] Test menus used by your ESX resources

```cfg
ensure es_extended
ensure esx_menu_default
```

---

## Developer Usage

Open a default menu with:

```lua
ESX.UI.Menu.Open(
    "default",
    GetCurrentResourceName(),
    "example_menu",
    {
        title = "Example Menu",
        align = "top-left",
        elements = elements
    },
    function(data, menu)
        print(data.current.name)
    end,
    function(data, menu)
        menu.close()
    end
)
```

### Element Types

Documented element types include:

```text
button
slider
```

Slider elements can use:

* `min`
* `max`
* `value`
* `options`

### Alignment

Documented menu positions include:

* `top-left`
* `top-right`
* `bottom-left`
* `bottom-right`
* `center`

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

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_menu_default)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_menu_default)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX Framework** and project contributors.

The project credits **Jérémie N'gadi** in its licensing information.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.