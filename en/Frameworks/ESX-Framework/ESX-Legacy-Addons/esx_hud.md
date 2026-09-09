---
title: esx_hud
description: esx_hud provides a configurable player and vehicle HUD for ESX Legacy.
published: true
date: 2026-09-09T20:21:02.918Z
tags: esx, hud, script, ui
editor: markdown
dateCreated: 2026-09-09T20:21:02.918Z
---

# esx_hud [![](https://badges.5metrics.dev/esx_hud/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_hud)

esx_hud provides a configurable player and vehicle HUD for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field          | Information           |
| -------------- | --------------------- |
| **Name**       | `esx_hud`             |
| **Creator**    | Gellipapa and Rav3n95 |
| **Maintainer** | ESX Framework         |
| **Type**       | Script                |
| **Category**   | HUD / UI              |
| **Game**       | FiveM                 |
| **Framework**  | ESX Legacy            |
| **License**    | GPL-3.0               |
| **Source**     | GitHub                |
| {.dense}       |                       |

---

## Features

* Mileage calculation
* Vehicle indicators with sound effects
* Weapon HUD and ammunition counter
* Online player counter
* Job label
* MPH and KMH options
* Interface color picker
* Settings panel
* Different speedometer layouts for land and air vehicles
* Seatbelt system with sound effects

---

## Requirements

| Resource            | Requirement                         |
| ------------------- | ----------------------------------- |
| `es_extended`       | Required                            |
| `esx_cruisecontrol` | Optional for seatbelt functionality |
| {.dense}            |                                     |

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `esx_hud` from the official ESX Legacy Addons repository
* [ ] Open the `web` directory
* [ ] Install the web dependencies
* [ ] Build the web interface
* [ ] Add `esx_hud` to `server.cfg`
* [ ] Restart your server
* [ ] Test the player HUD and vehicle HUD

### Build Web Interface

Run inside the `web` directory:

```bash
npm install
npm run build
```

### Resource

```cfg
ensure esx_hud
```

---

## Optional Seatbelt Support

The official documentation lists `esx_cruisecontrol` as optional and required specifically for the seatbelt functionality.

Install and start it if you want to use that integration.

---

## Compatibility

| Component             | Support  |
| --------------------- | -------- |
| **FiveM**             | Yes      |
| **ESX Legacy**        | Required |
| **es_extended**       | Required |
| **esx_cruisecontrol** | Optional |
| {.dense}              |          |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_addons/esx_hud)
* [Official Source](https://github.com/esx-framework/ESX-Legacy-Addons/tree/main/%5Besx_addons%5D/esx_hud)

---

## Credits

Developed by **Gellipapa** and **Rav3n95**.

Special thanks are given by the project to **Csoki**, **csontvazharcos**, and **Füsti**.

Maintained as part of the **ESX Framework** project.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
