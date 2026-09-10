---
title: DiscordTagIDs
description: DiscordTagIDs displays Discord role-based prefixes and IDs above FiveM players.
published: true
date: 2026-09-09T00:18:32.701Z
tags: discord, roles, script, nametags
editor: markdown
dateCreated: 2026-09-09T00:18:31.121Z
---

# DiscordTagIDs [![](https://badges.5metrics.dev/DiscordTagIDs/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/DiscordTagIDs)

DiscordTagIDs displays Discord role-based prefixes and IDs above FiveM players.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                     | Information     |
| ------------------------- | --------------- |
| **Name**                  | `DiscordTagIDs` |
| **Creator**               | Badger          |
| **Type**                  | Script          |
| **Category**              | Player Tags     |
| **Game**                  | FiveM           |
| **Version**               | `1.0`           |
| **Framework Requirement** | None specified  |
| **License**               | MIT             |
| **Source**                | GitHub          |
| {.dense}                  |                 |

---

## Resource Details {.tabset}

### Overview

DiscordTagIDs adds overhead player ID tags with prefixes determined by Discord roles.

Tags can identify groups such as:

* Staff
* Management
* Owner
* Departments
* Donators
* Community roles
* Custom server roles

The prefixes and colors are configurable.

### Requirements

DiscordTagIDs requires:

* `Badger_Discord_API`
* A configured Discord bot
* Discord role IDs

No FiveM roleplay framework dependency is documented.

### How Tags Work

DiscordTagIDs checks Discord roles and associates those roles with configured overhead prefixes.

A role configuration follows this pattern:

```lua
{DISCORD_ROLE_ID, "TAG"}
```

For example:

```lua
{111111111111111111, "~r~STAFF ~w~"}
```

FiveM formatting codes can be used inside tag text.

---

## Installation

### Installation Checklist

* [ ] Install and configure `Badger_Discord_API`
* [ ] Download `DiscordTagIDs`
* [ ] Place `DiscordTagIDs` in your resources folder
* [ ] Configure Discord role IDs
* [ ] Configure tag text and colors
* [ ] Start `Badger_Discord_API` first
* [ ] Add `DiscordTagIDs` to `server.cfg`
* [ ] Restart your server
* [ ] Test tags with multiple Discord roles

### Resource Order

```cfg
ensure Badger_Discord_API
ensure DiscordTagIDs
```

---

## Configuration

Configure your Discord role mappings in the resource configuration.

A tag list follows this structure:

```lua
roleList = {
    {0, "~w~"},
    {111111111111111111, "~r~STAFF ~w~"},
    {222222222222222222, "~p~MANAGEMENT ~w~"},
    {333333333333333333, "~o~OWNER ~w~"},
}
```

The `0` entry acts as the regular or non-staff tag in the documented example.

Replace all example role IDs with your own.

---

## Commands

| Command         | Purpose                                 |
| --------------- | --------------------------------------- |
| `/tag-toggle`   | Toggle your prefix from being displayed |
| `/tags-toggle`  | Hide or show player tags for yourself   |
| `/headtag`      | View head tags you can access           |
| `/headtag [id]` | Select an available head tag            |
| {.dense}        |                                         |

### `/tag-toggle`

Use:

```text
/tag-toggle
```

This disables or enables your configured prefix.

### `/tags-toggle`

Use:

```text
/tags-toggle
```

This hides or displays all overhead tags for you.

The official documentation notes that this is useful for streamers and screenshots.

### `/headtag`

Use:

```text
/headtag
```

to view head tags available to you.

Select one with:

```text
/headtag [id]
```

---

## Tag Colors

FiveM text formatting codes can be used in the tag configuration.

For example:

```text
~r~
```

can be used for red formatting.

A configured tag may look like:

```lua
{111111111111111111, "~r~STAFF ~w~"}
```

Use your own labels and Discord role IDs.

---

## Discord Role Integration

The current DiscordTagIDs integration uses `Badger_Discord_API`.

Make sure:

* Your Discord bot is configured
* The bot is in the correct guild
* The player's Discord account is visible to FiveM
* Your Discord role IDs are correct
* `Badger_Discord_API` starts before DiscordTagIDs

If role detection fails, verify `Badger_Discord_API` before changing tag configuration.

---

## Compatibility

| Component                 | Support        |
| ------------------------- | -------------- |
| **FiveM**                 | Yes            |
| **Badger_Discord_API**    | Required       |
| **Discord Roles**         | Used           |
| **Framework Requirement** | None specified |
| {.dense}                  |                |

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-discord-scripts/discordtagids)
* [Official GitHub Repository](https://github.com/JaredScar/DiscordTagIDs)
* [Badger_Discord_API](https://github.com/JaredScar/Badger_Discord_API)

---

## Before You Install

Configure `Badger_Discord_API` before DiscordTagIDs.

Replace all example role IDs.

Test tag priority with users who have multiple Discord roles.

Use `/tags-toggle` when you need to hide overhead tags locally.

---

## Credits

Created by **Badger** and project contributors.

The project credits **IllusiveTea** for Discord-role functionality used by the original implementation.

DiscordTagIDs was adapted from a player name-tag resource originally created by **MrDaGree**.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
