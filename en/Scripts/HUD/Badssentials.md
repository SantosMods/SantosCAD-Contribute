---
title: Badssentials
description: Badssentials combines AOP, PeaceTime, postal, HUD, revive, respawn, and announcement utilities for FiveM.
published: true
date: 2026-09-09T00:19:52.453Z
tags: hud, script, aop, peacetime
editor: markdown
dateCreated: 2026-09-09T00:19:50.803Z
---

# Badssentials [![](https://badges.5metrics.dev/Badssentials/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/Badssentials)

Badssentials combines AOP, PeaceTime, postal, HUD, revive, respawn, and announcement utilities for FiveM.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                     | Information      |
| ------------------------- | ---------------- |
| **Name**                  | `Badssentials`   |
| **Creator**               | Badger           |
| **Type**                  | Script           |
| **Category**              | Server Utilities |
| **Game**                  | FiveM            |
| **Framework Requirement** | None specified   |
| **License**               | MIT              |
| **Source**                | GitHub           |
| {.dense}                  |                  |

---

## Resource Details {.tabset}

### Overview

Badssentials combines several common FiveM server utilities into one resource.

Documented systems include:

* Area of Patrol
* PeaceTime
* Postal waypointing
* Configurable HUD displays
* Placeholder-based text displays
* Revive
* Respawn
* Server announcements
* HUD toggle

### AOP

The Area of Patrol system lets permitted users change the active AOP.

Use:

```text
/aop <zone>
```

### PeaceTime

PeaceTime can be toggled with:

```text
/peacetime
```

or:

```text
/pt
```

### Postal Waypoints

Set a waypoint to a postal code:

```text
/postal <code>
```

Clear the postal waypoint with:

```text
/postal
```

### HUD

Players can toggle the Badssentials HUD with:

```text
/toggle-hud
```

The HUD supports configurable text displays and dynamic placeholders.

---

## Installation

### Installation Checklist

* [ ] Download `Badssentials`
* [ ] Place `Badssentials` in your resources folder
* [ ] Review the resource configuration
* [ ] Configure the default display elements
* [ ] Configure AOP and PeaceTime access
* [ ] Configure revive and respawn delays
* [ ] Configure announcement settings
* [ ] Add ACE permissions
* [ ] Add `Badssentials` to `server.cfg`
* [ ] Restart your server
* [ ] Test each enabled system

### server.cfg

```cfg
ensure Badssentials
```

---

## Commands

| Command           | Purpose                       |
| ----------------- | ----------------------------- |
| `/postal <code>`  | Set a waypoint to a postal    |
| `/postal`         | Cancel the postal waypoint    |
| `/aop <zone>`     | Set the current AOP           |
| `/peacetime`      | Toggle PeaceTime              |
| `/pt`             | Toggle PeaceTime              |
| `/toggle-hud`     | Toggle the HUD                |
| `/revive`         | Revive yourself when dead     |
| `/revive <id>`    | Revive a specified player     |
| `/respawn`        | Respawn yourself when dead    |
| `/announce <msg>` | Display a server announcement |
| {.dense}          |                               |

---

## Permissions

| ACE Permission                | Purpose                          |
| ----------------------------- | -------------------------------- |
| `Badssentials.AOP`            | Access to `/aop`                 |
| `Badssentials.PeaceTime`      | Access to `/peacetime` and `/pt` |
| `Badssentials.Bypass.Revive`  | Bypass the revive delay          |
| `Badssentials.Bypass.Respawn` | Bypass the respawn delay         |
| `Badssentials.Announce`       | Access to `/announce`            |
| {.dense}                      |                                  |

Grant these permissions only to the appropriate groups.

---

## Configuration {.tabset}

### General Settings

The documented configuration includes values such as:

```lua
Config = {
    Prefix = "^5[^1Badssentials^5] ^3",
    AnnouncementHeader = "~b~[~p~Server Announcement~b~]",
    AnnounceDisplayTime = 15,
    Revive_Delay = 60,
    Respawn_Delay = 30,
}
```

Change the values to match your server.

### Announcement Duration

Configure how long announcements display:

```lua
AnnounceDisplayTime = 15
```

The value is in seconds.

### Revive Delay

Set:

```lua
Revive_Delay = 60
```

Set the value to:

```lua
0
```

to disable the delay.

### Respawn Delay

Set:

```lua
Respawn_Delay = 30
```

Set it to `0` to disable the delay.

---

## HUD Displays

Badssentials supports multiple configurable display entries.

Each display can define:

* Screen position
* Display text
* Text scale
* Enabled state
* Dynamic placeholders

Example structure:

```lua
["Server Display"] = {
    x = .800,
    y = .01,
    display = "Your Server",
    textScale = .55,
    enabled = true
}
```

You can add additional displays using the same structure.

---

## Display Placeholders

The official resource supports dynamic values inside display text.

Documented examples include information for:

* Compass direction
* Street
* City or area
* Nearest postal
* Postal distance
* Time
* Date
* Current AOP
* PeaceTime status

Example:

```text
{COMPASS}
```

Example:

```text
{STREET_NAME}
```

Example:

```text
{CITY}
```

Example:

```text
{NEAREST_POSTAL}
```

Example:

```text
{CURRENT_AOP}
```

Example:

```text
{PEACETIME_STATUS}
```

These can be combined into custom HUD display strings.

---

## Example AOP Display

A display can combine AOP and PeaceTime status:

```text
Current AOP: {CURRENT_AOP} | PeaceTime: {PEACETIME_STATUS}
```

---

## Example Location Display

You can combine location placeholders:

```text
{COMPASS} | {STREET_NAME} | {CITY}
```

---

## Compatibility

| Component                 | Support        |
| ------------------------- | -------------- |
| **FiveM**                 | Yes            |
| **Framework Requirement** | None specified |
| **ACE Permissions**       | Used           |
| **Custom HUD Displays**   | Yes            |
| **Postal System**         | Included       |
| {.dense}                  |                |

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-misc.-scripts/badssentials)
* [Official GitHub Repository](https://github.com/JaredScar/Badssentials)

---

## Before You Install

Review every enabled HUD display.

Replace example community names and links.

Set your preferred AOP and PeaceTime permissions.

Configure revive and respawn delays before opening the server to players.

---

## Credits

Created by **Badger** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
