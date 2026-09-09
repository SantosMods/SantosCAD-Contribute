---
title: BadgerTools
description: BadgerTools provides staff administration, spectating, and voice tools for FiveM.
published: true
date: 2026-09-09T00:09:20.252Z
tags: script, admin, spectate, voice-chat
editor: markdown
dateCreated: 2026-09-09T00:09:20.252Z
---

# BadgerTools [![](https://badges.5metrics.dev/BadgerTools/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/BadgerTools)

BadgerTools provides staff administration, spectating, and voice tools for FiveM.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information    |
| ------------ | -------------- |
| **Name**     | `BadgerTools`  |
| **Creator**  | Badger         |
| **Type**     | Script         |
| **Category** | Administration |
| **Game**     | FiveM          |
| **Source**   | GitHub         |
| {.dense}     |                |

---

## Resource Details {.tabset}

### Overview

BadgerTools provides staff administration tools for FiveM.

Documented functionality includes:

* Player spectating
* Cycling between players while spectating
* Spectated-player voice interaction
* Custom proximity voice
* Teleporting to players
* Summoning players
* Freezing players
* Discord-based voice tags
* Voice color restrictions

### Requirements

The official documentation lists:

* `Badger_Discord_API`
* `DiscordTagIDs`

The documentation also warns that vMenu voice chat must be disabled to avoid conflicts.

### Permissions

Spectate access uses:

```text
BadgerTools.Commands.Spectate
```

Voice chat colors use:

```text
BadgerTools.Colors
```

---

## Installation

### Installation Checklist

* [ ] Install `Badger_Discord_API`
* [ ] Install `DiscordTagIDs`
* [ ] Download `BadgerTools` from the official source
* [ ] Place `BadgerTools` in your resources folder
* [ ] Configure your Discord role tags
* [ ] Configure ACE permissions
* [ ] Disable conflicting vMenu voice chat functionality
* [ ] Add the resource to `server.cfg`
* [ ] Restart your server
* [ ] Test staff commands and voice functionality

> Disable vMenu voice chat when using the BadgerTools custom voice system. The official documentation warns that leaving both enabled causes problems.
> {.is-warning}

---

## Configuration

The main configuration is stored in:

```text
config.lua
```

`RoleList` controls Discord-linked voice tags.

The first role entry acts as the default role.

`EnableVoiceOOC` controls the OOC voice functionality.

---

## Commands

| Command                 | Purpose                    |
| ----------------------- | -------------------------- |
| `/proximity [distance]` | Change voice proximity     |
| `/voicetag`             | List available voice tags  |
| `/voicetag [index]`     | Select a voice tag         |
| `/spectate`             | Start or stop spectating   |
| `/spectate [id]`        | Spectate a specific player |
| `/tp [id]`              | Teleport to a player       |
| `/summon [id]`          | Summon a player            |
| `/freeze [id]`          | Freeze a player            |
| {.dense}                |                            |

These commands are documented by the creator.

---

## Compatibility

| Component              | Support                     |
| ---------------------- | --------------------------- |
| **FiveM**              | Yes                         |
| **Framework**          | Not specified               |
| **Badger_Discord_API** | Required                    |
| **DiscordTagIDs**      | Required                    |
| **vMenu Voice Chat**   | Conflicts with custom voice |
| {.dense}               |                             |

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-discord-scripts/badgertools)
* [Official GitHub Repository](https://github.com/JaredScar/BadgerTools)

---

## Credits

Created by **Badger** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
