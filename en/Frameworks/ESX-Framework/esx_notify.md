---
title: esx_notify
description: esx_notify provides the notification system used by ESX resources.
published: true
date: 2026-09-07T23:44:04.527Z
tags: esx, notifications, script, ui
editor: markdown
dateCreated: 2026-09-07T23:41:35.633Z
---

# esx_notify [![](https://badges.5metrics.dev/esx_notify/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_notify)

`esx_notify` provides the notification system used by ESX resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information      |
| ------------- | ---------------- |
| **Name**      | `esx_notify`     |
| **Creator**   | ESX-Framework    |
| **Type**      | Script           |
| **Category**  | UI               |
| **Game**      | FiveM            |
| **Framework** | ESX Legacy       |
| **Version**   | `1.14.0`         |
| **License**   | GPL-3.0-or-later |
| {.dense}      |                  |

---

## Resource Details {.tabset}

### Overview

`esx_notify` is an NUI notification system for ESX.

Notifications support:

* Notification types
* Custom duration
* Titles
* Configurable positions
* Text color codes
* Line breaks
* ESX function usage
* Exports
* Events

### Notification Types

The documented notification types include:

```text
error
success
info
warning
```

### Positions

Supported positions include:

```text
top-right
top-left
top-middle
bottom-right
bottom-left
bottom-middle
middle-left
middle-right
```

---

## Installation

### Installation Checklist

* [ ] Install `es_extended`
* [ ] Keep `esx_notify` with your ESX core resources
* [ ] Start `es_extended`
* [ ] Start `esx_notify`
* [ ] Restart your server
* [ ] Test notifications from an ESX resource

### Resource Order

```cfg
ensure es_extended
ensure esx_notify
```

---

## Developer Usage {.tabset}

### ESX Function

Display a notification with:

```lua
ESX.ShowNotification("message here", "success", 3000)
```

Add an optional title:

```lua
ESX.ShowNotification("message here", "success", 3000, "Achievement")
```

Add a position:

```lua
ESX.ShowNotification("message here", "info", 3000, "Information", "top-right")
```

### Export

Use the resource export directly:

```lua
exports["esx_notify"]:Notify("info", 3000, "message here")
```

### Event

Trigger a notification through the documented event:

```lua
TriggerEvent("ESX:Notify", "success", 4000, "Welcome!", "Greetings", "top-middle")
```

---

## Text Formatting

The notification system supports GTA text color codes.

Examples include:

```text
~r~ Red
~b~ Blue
~g~ Green
~y~ Yellow
~p~ Purple
~c~ Grey
~m~ Dark Grey
~u~ Black
~o~ Orange
```

Use:

```text
~br~
```

for a line break.

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

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_notify)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_notify)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX-Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
