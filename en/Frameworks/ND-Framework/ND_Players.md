---
title: ND_Players
description: ND_Players provides multi-character selection for ND Core.
published: true
date: 2026-09-08T00:21:36.794Z
tags: nd, script, multicharacter, characters
editor: markdown
dateCreated: 2026-09-07T18:41:21.997Z
---

# ND_Players [![](https://badges.5metrics.dev/ND_Players/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ND_Players)

ND_Players provides multi-character selection for ND Core.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information        |
| ------------- | ------------------ |
| **Name**      | `ND_Players`       |
| **Creator**   | Andy's Development |
| **Type**      | Script             |
| **Category**  | Characters         |
| **Game**      | FiveM              |
| **Framework** | ND Core            |
| **Version**   | `1.0.0`            |
| **License**   | GPL-3.0            |
| **Source**    | GitHub             |
| {.dense}      |                    |

---

## Resource Details {.tabset}

### Overview

ND_Players is a multi-character and character selection resource for ND Core.

The project describes the current resource as a rewrite of an earlier character system originally worked on by the creator and Lucas.

### Requirements

The resource loads:

* `ND_Core`
* `ox_lib`

Its manifest uses:

```text
@ox_lib/init.lua
@ND_Core/init.lua
```

---

## Installation

### Installation Checklist

* [ ] Install `ND_Core`
* [ ] Install `ox_lib`
* [ ] Download `ND_Players` from the official GitHub repository
* [ ] Place `ND_Players` in your resources folder
* [ ] Review the included character data and modules
* [ ] Add `ND_Players` to `server.cfg`
* [ ] Restart your server
* [ ] Test character selection

### Resource Order

```cfg
ensure ox_lib
ensure ND_Core
ensure ND_Players
```

---

## Resource Structure

The resource includes:

```text
client
data
modules
server
ui
```

The manifest also loads module client files from:

```text
modules/**/client.lua
```

---

## Compatibility

| Component           | Support  |
| ------------------- | -------- |
| **FiveM**           | Yes      |
| **ND Core**         | Required |
| **ox_lib**          | Used     |
| **Multi-character** | Yes      |
| {.dense}            |          |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Players)

---

## Credits

Created by **Andy's Development** and project contributors.

The project also credits **Lucas** for work on the earlier version of the character system.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
