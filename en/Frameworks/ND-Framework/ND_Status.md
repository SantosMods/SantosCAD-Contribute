---
title: ND_Status
description: ND_Status provides configurable player status systems for ND Core.
published: true
date: 2026-09-07T18:40:26.119Z
tags: nd, script, status, hud
editor: markdown
dateCreated: 2026-09-07T18:40:26.119Z
---

# ND_Status

ND_Status provides configurable player status systems for ND Core.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information   |
| ------------- | ------------- |
| **Name**      | `ND_Status`   |
| **Creator**   | Andyyy7666    |
| **Type**      | Script        |
| **Category**  | Player Status |
| **Game**      | FiveM         |
| **Framework** | ND Core       |
| **Version**   | `1.0.0`       |
| **Source**    | GitHub        |
| {.dense}      |               |

---

## Resource Details {.tabset}

### Overview

ND_Status provides player status tracking for ND Core.

The resource supports configurable statuses and allows you to add or remove status entries from its configuration. The default configuration includes health, armor, hunger, thirst, and alcohol status handling.

### Requirements

ND_Status declares these dependencies:

* `ND_Core`
* `ox_lib`

The resource loads:

```text
@ND_Core/init.lua
@ox_lib/init.lua
```

---

## Installation

### Installation Checklist

* [ ] Install `ND_Core`
* [ ] Install `ox_lib`
* [ ] Download `ND_Status` from the official GitHub repository
* [ ] Place `ND_Status` in your resources folder
* [ ] Review `config.lua`
* [ ] Add `ND_Status` to `server.cfg`
* [ ] Restart your server
* [ ] Check player statuses in game

### Resource Order

```cfg
ensure ox_lib
ensure ND_Core
ensure ND_Status
```

---

## Configuration

Use:

```text
config.lua
```

The status configuration supports options including:

* Status type
* Enabled state
* Maximum value
* Decrease rate
* Default value
* Status action
* UI styling
* Icons

Default status entries include health, armor, hunger, thirst, and alcohol.

---

## Developer Usage

The resource exports:

```text
setStatus
changeStatus
setMaxStatus
getStatus
```

---

## Compatibility

| Component   | Support  |
| ----------- | -------- |
| **FiveM**   | Yes      |
| **ND Core** | Required |
| **ox_lib**  | Required |
| {.dense}    |          |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Status)

---

## Credits

Created by **Andyyy7666** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
