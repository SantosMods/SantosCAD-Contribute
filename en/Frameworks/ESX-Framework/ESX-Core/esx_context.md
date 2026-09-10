---
title: esx_context
description: esx_context provides the context menu system used by es_extended.
published: true
date: 2026-09-08T00:24:01.801Z
tags: esx, script, ui, menus
editor: markdown
dateCreated: 2026-09-07T23:31:34.639Z
---

# esx_context [![](https://badges.5metrics.dev/esx_context/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_context)

`esx_context` provides the context menu system used by `es_extended`.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information             |
| ------------- | ----------------------- |
| **Name**      | `esx_context`           |
| **Creator**   | ESX-Framework & Brayden |
| **Type**      | Script                  |
| **Category**  | UI                      |
| **Game**      | FiveM                   |
| **Framework** | ESX Legacy              |
| **Version**   | `1.14.1`                |
| **License**   | GPL-3.0-or-later        |
| {.dense}      |                         |

---

## Resource Details {.tabset}

### Overview

`esx_context` provides context menus for ESX resources.

The context system supports:

* Selectable and unselectable entries
* Disabled entries
* Font Awesome icons
* Titles and descriptions
* Text inputs
* Number inputs
* Radio inputs
* Input limits
* Menu refreshes
* Configurable menu positioning

### Requirements

The resource declares:

* `es_extended`

The manifest imports:

```text
@es_extended/imports.lua
```

### Menu Positions

Supported positions are:

* `left`
* `center`
* `right`

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Download the official ESX Legacy core resources
* [ ] Keep `esx_context` in the ESX core resource collection
* [ ] Start `es_extended` before `esx_context`
* [ ] Restart your server
* [ ] Check the server console for errors

### Resource Order

```cfg
ensure es_extended
ensure esx_context
```

---

## Developer Usage {.tabset}

### OpenContext

Use `ESX.OpenContext` to open a context menu and enable mouse focus.

```lua
ESX.OpenContext("right", elements, function(menu, element)
    print(element.title)
end, function()
    print("Context closed")
end)
```

### PreviewContext

Use `ESX.PreviewContext` to display a context menu without enabling mouse focus.

### CloseContext

Close the current context with:

```lua
ESX.CloseContext()
```

### RefreshContext

Update the current context menu with:

```lua
ESX.RefreshContext("right", elements)
```

---

## Input Types

Context entries can use these documented input types:

```text
radio
number
text
```

Number inputs can use minimum and maximum values.

---

## Compatibility

| Component       | Support  |
| --------------- | -------- |
| **FiveM**       | Yes      |
| **ESX Legacy**  | Yes      |
| **es_extended** | Required |
| **Client UI**   | Yes      |
| {.dense}        |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_context)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_context)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX-Framework & Brayden** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
