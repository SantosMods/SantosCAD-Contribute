---
title: DiscordAcePerms
description: DiscordAcePerms assigns FiveM ACE permission groups from Discord roles.
published: true
date: 2026-09-09T00:17:49.088Z
tags: discord, script, permissions, ace
editor: markdown
dateCreated: 2026-09-09T00:17:49.088Z
---

# DiscordAcePerms [![](https://badges.5metrics.dev/DiscordAcePerms/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/DiscordAcePerms)

DiscordAcePerms assigns FiveM ACE permission groups from Discord roles.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                     | Information       |
| ------------------------- | ----------------- |
| **Name**                  | `DiscordAcePerms` |
| **Creator**               | Badger            |
| **Type**                  | Script            |
| **Category**              | Permissions       |
| **Game**                  | FiveM             |
| **Version**               | `1.0`             |
| **Framework Requirement** | None specified    |
| **License**               | MIT               |
| **Source**                | GitHub            |
| {.dense}                  |                   |

---

## Resource Details {.tabset}

### Overview

DiscordAcePerms connects Discord roles to FiveM ACE permission groups.

When a player joins, the resource can use their Discord roles to assign configured ACE principals.

This allows Discord roles to control FiveM permission groups such as:

* Member
* Donator
* Moderator
* Administrator
* Management
* Owner
* Custom server groups

The exact groups are configured by you.

### Requirements

DiscordAcePerms requires:

* `Badger_Discord_API`
* A Discord bot configured for `Badger_Discord_API`
* Discord role IDs
* FiveM ACE permission groups

No ESX, QBCore, Qbox, ND Framework, or other FiveM framework dependency is documented.

### How Permissions Work

DiscordAcePerms maps a Discord role ID to a FiveM principal.

A mapping follows this structure:

```lua
{DISCORD_ROLE_ID, "group.permission"}
```

For example:

```lua
{778074943824592916, "group.moderator"}
```

When the player has the configured Discord role, DiscordAcePerms can assign the corresponding FiveM permission group.

---

## Installation

### Installation Checklist

* [ ] Install and configure `Badger_Discord_API`
* [ ] Download `DiscordAcePerms`
* [ ] Place `DiscordAcePerms` in your resources folder
* [ ] Open `config.lua`
* [ ] Replace example Discord role IDs
* [ ] Configure your ACE group names
* [ ] Add the required `add_ace` permissions
* [ ] Start `Badger_Discord_API` before `DiscordAcePerms`
* [ ] Restart your server
* [ ] Test permissions with a Discord member

### Required ACE Permissions

DiscordAcePerms needs permission to add and remove principals.

Add:

```cfg
add_ace resource.DiscordAcePerms command.add_principal allow
add_ace resource.DiscordAcePerms command.remove_principal allow
```

### Resource Order

Start `Badger_Discord_API` first.

```cfg
ensure Badger_Discord_API
ensure DiscordAcePerms
```

---

## Configuration {.tabset}

### General Configuration

The current repository uses `config.lua`.

Configuration options include:

```lua
Config = {
    Server_Name = "[SERVER_NAME]",
    Discord_Link = "https://discord.gg/",
    Website_Link = "https://badger.store/",
    Allow_Refresh_Command = true,
    DebugScript = false,
    Print_Perm_Grants_And_Removals = true,
    Refresh_Throttle = 600,
    roleList = {
    },
}
```

Replace the example values with your server information.

### Role Mapping

Configure Discord roles under:

```lua
roleList = {
}
```

Example structure:

```lua
roleList = {
    {111111111111111111, "group.member"},
    {222222222222222222, "group.moderator"},
    {333333333333333333, "group.admin"},
    {444444444444444444, "group.owner"},
}
```

Use your own Discord role IDs.

Use ACE groups that exist in your server configuration.

### Server_Name

`Server_Name` sets the server name used by the resource where applicable.

```lua
Server_Name = "[SERVER_NAME]"
```

### Discord_Link

Set your Discord invite:

```lua
Discord_Link = "https://discord.gg/"
```

### Website_Link

Set your server or community website:

```lua
Website_Link = "https://example.com/"
```

### Permission Refresh

The current configuration includes:

```lua
Allow_Refresh_Command = true
```

This controls whether the permission refresh command is enabled.

The configuration also includes:

```lua
Refresh_Throttle = 600
```

The repository describes this value as a ten-minute refresh throttle.

### Debugging

Enable additional debugging with:

```lua
DebugScript = true
```

Permission grant and removal messages can be controlled with:

```lua
Print_Perm_Grants_And_Removals = true
```

---

## ACE Permissions

DiscordAcePerms manages principals rather than replacing FiveM's ACE system.

Your other permissions can continue using normal ACE entries.

For example:

```cfg
add_ace group.moderator command.kick allow
add_ace group.admin command allow
```

DiscordAcePerms is responsible for assigning the configured player to the appropriate `group.*` principal.

---

## Permission Refresh

The current resource includes permission refresh functionality.

When enabled in `config.lua`, players can refresh Discord-based permissions without requiring a full server restart.

The refresh throttle limits repeated refresh requests.

This is useful after changing a player's Discord roles.

---

## Important Setup Notes

> Replace every example Discord role ID with the ID from your own Discord server.
> {.is-warning}

> Do not configure a Discord role to grant more ACE access than that role should have.
> {.is-warning}

DiscordAcePerms only assigns the principals you configure.

Review your complete ACE configuration before giving Discord roles to users.

---

## Compatibility

| Component                 | Support        |
| ------------------------- | -------------- |
| **FiveM**                 | Yes            |
| **Badger_Discord_API**    | Required       |
| **Discord Roles**         | Required       |
| **ACE Permissions**       | Required       |
| **Framework Requirement** | None specified |
| {.dense}                  |                |

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-discord-scripts/discordaceperms)
* [Official GitHub Repository](https://github.com/JaredScar/DiscordAcePerms)
* [Badger_Discord_API](https://github.com/JaredScar/Badger_Discord_API)

---

## Before You Install

Configure `Badger_Discord_API` first.

Verify every Discord role ID in `roleList`.

Verify every mapped `group.*` principal exists in your ACE configuration.

Add the required `command.add_principal` and `command.remove_principal` permissions for the resource.

Start `Badger_Discord_API` before DiscordAcePerms.

---

## Credits

Created by **Badger** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
