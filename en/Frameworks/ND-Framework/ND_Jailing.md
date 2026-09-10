---
title: ND_Jailing
description: ND_Jailing provides player jailing functionality for ND Framework.
published: true
date: 2026-09-08T00:21:33.380Z
tags: nd, police, script, jailing
editor: markdown
dateCreated: 2026-09-07T18:42:07.072Z
---

# ND_Jailing [![](https://badges.5metrics.dev/ND_Jailing/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ND_Jailing)

ND_Jailing provides player jailing functionality for ND Framework.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information  |
| ------------- | ------------ |
| **Name**      | `ND_Jailing` |
| **Creator**   | Andyyy       |
| **Type**      | Script       |
| **Category**  | Police       |
| **Game**      | FiveM        |
| **Framework** | ND Framework |
| **Version**   | `1.0.0`      |
| **Source**    | GitHub       |
| {.dense}      |              |

---

## Resource Details {.tabset}

### Overview

ND_Jailing is an ND Framework resource for sending players to jail.

The repository includes separate client and server code together with configurable job and ped data.

### Requirements

The manifest declares:

* `ND_Core`

It also loads:

```text
@ox_lib/init.lua
@ND_Core/init.lua
```

`ND_Core` is explicitly declared as a dependency.

---

## Installation

### Installation Checklist

* [ ] Install `ND_Core`
* [ ] Install `ox_lib`
* [ ] Download `ND_Jailing` from the official GitHub repository
* [ ] Place `ND_Jailing` in your resources folder
* [ ] Review job configuration
* [ ] Review ped configuration
* [ ] Add `ND_Jailing` to `server.cfg`
* [ ] Restart your server
* [ ] Test jailing functionality

### Resource Order

```cfg
ensure ox_lib
ensure ND_Core
ensure ND_Jailing
```

---

## Configuration

The manifest includes these data files:

```text
data/jobs.lua
data/peds.lua
```

Use them to review the resource's configured jobs and peds.

---

## Compatibility

| Component   | Support                |
| ----------- | ---------------------- |
| **FiveM**   | Yes                    |
| **ND Core** | Required               |
| **ox_lib**  | Loaded by the resource |
| {.dense}    |                        |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Jailing)

---

## Credits

Created by **Andyyy** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
