---
title: esx_progressbar
description: esx_progressbar provides an NUI progress bar for ESX resources.
published: true
date: 2026-09-08T00:25:46.210Z
tags: esx, script, ui, progressbar
editor: markdown
dateCreated: 2026-09-07T23:42:24.824Z
---

# esx_progressbar [![](https://badges.5metrics.dev/esx_progressbar/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_progressbar)

`esx_progressbar` provides an NUI progress bar for ESX resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information       |
| ------------- | ----------------- |
| **Name**      | `esx_progressbar` |
| **Creator**   | ESX-Framework     |
| **Type**      | Script            |
| **Category**  | UI                |
| **Game**      | FiveM             |
| **Framework** | ESX Legacy        |
| **Version**   | `1.14.0`          |
| **License**   | GPL-3.0-or-later  |
| {.dense}      |                   |

---

## Resource Details {.tabset}

### Overview

`esx_progressbar` provides progress indicators for ESX resources.

The progress bar supports:

* Custom messages
* Custom duration
* Player freezing
* Animations
* Scenarios
* Completion callbacks
* Cancellation callbacks
* Manual cancellation

### Requirements

The resource imports:

```text
@es_extended/imports.lua
```

It runs as a client-side NUI resource.

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Keep `esx_progressbar` with your ESX core resources
* [ ] Start `es_extended`
* [ ] Start `esx_progressbar`
* [ ] Restart your server
* [ ] Test a progress bar from an ESX resource

### Resource Order

```cfg
ensure es_extended
ensure esx_progressbar
```

---

## Developer Usage {.tabset}

### ESX Function

Create a progress bar with:

```lua
ESX.Progressbar("Unlocking Storage", 3000, {
    FreezePlayer = true,
    onFinish = function()
        -- Code here
    end
})
```

### Export

Use the resource export directly:

```lua
exports["esx_progressbar"]:Progressbar("Unlocking Storage", 3000, {
    FreezePlayer = true,
    onFinish = function()
        -- Code here
    end
})
```

### Animation

Run an animation during the progress bar:

```lua
ESX.Progressbar("Unlocking Storage", 3000, {
    FreezePlayer = true,
    animation = {
        type = "anim",
        dict = "anim@mp_player_intmenu@key_fob@",
        lib = "fob_click"
    },
    onFinish = function()
        -- Code here
    end
})
```

### Scenario

Use a scenario instead:

```lua
ESX.Progressbar("Unlocking Storage", 3000, {
    FreezePlayer = true,
    animation = {
        type = "Scenario",
        Scenario = "PROP_HUMAN_BUM_BIN"
    },
    onFinish = function()
        -- Code here
    end
})
```

---

## Cancellation

The resource supports an `onCancel` callback.

```lua
ESX.Progressbar("Unlocking Storage", 3000, {
    FreezePlayer = true,
    onFinish = function()
        -- Code here
    end,
    onCancel = function()
        -- Code here
    end
})
```

The resource also exports:

```text
CancelProgressbar
```

The default cancellation input is registered to `BACK`.

---

## Compatibility

| Component               | Support |
| ----------------------- | ------- |
| **FiveM**               | Yes     |
| **ESX Legacy**          | Yes     |
| **es_extended imports** | Used    |
| **NUI**                 | Yes     |
| {.dense}                |         |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_progressbar)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_progressbar)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX-Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
