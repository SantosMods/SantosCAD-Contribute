---
title: DiscordChatRoles
description: DiscordChatRoles adds Discord role-based tags and permissions to FiveM chat.
published: true
date: 2026-09-09T00:11:33.006Z
tags: script, discord, chat, roles
editor: markdown
dateCreated: 2026-09-09T00:11:30.658Z
---

# DiscordChatRoles [![](https://badges.5metrics.dev/DiscordChatRoles/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/DiscordChatRoles)

DiscordChatRoles adds Discord role-based tags and permissions to FiveM chat.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information        |
| ------------ | ------------------ |
| **Name**     | `DiscordChatRoles` |
| **Creator**  | Badger             |
| **Type**     | Script             |
| **Category** | Chat               |
| **Game**     | FiveM              |
| **Version**  | `7.0`              |
| **Source**   | GitHub             |
| {.dense}     |                    |

---

## Resource Details {.tabset}

### Overview

DiscordChatRoles connects FiveM chat functionality with Discord roles.

Documented features include:

* Discord role-based chat tags
* Chat color restrictions
* Restricted red chat
* StaffChat
* StaffChat message toggling
* Player-selectable chat tags
* Player-selectable chat colors
* Block-style chat messages

The official documentation lists version `7.0`.

### Requirements

DiscordChatRoles requires:

* `Badger_Discord_API`

Configure `Badger_Discord_API` with your Discord application before using DiscordChatRoles.

---

## Installation

### Installation Checklist

* [ ] Install and configure `Badger_Discord_API`
* [ ] Download `DiscordChatRoles`
* [ ] Place `DiscordChatRoles` in your resources folder
* [ ] Configure your Discord chat roles
* [ ] Configure chat color permissions
* [ ] Configure StaffChat permissions if needed
* [ ] Add the resource to `server.cfg`
* [ ] Restart your server
* [ ] Test role detection and chat tags

### Resource Order

Start `Badger_Discord_API` before `DiscordChatRoles`.

```cfg
ensure Badger_Discord_API
ensure DiscordChatRoles
```

---

## Configuration {.tabset}

### Chat Roles

Configure `roleList` from lowest priority to highest priority.

Higher-priority Discord roles override lower-priority entries when a player has multiple configured roles.

Keep the first entry as the fallback role.

### Chat Colors

Chat colors can be restricted using ACE permissions.

The official configuration uses permission groups such as:

```text
DiscordChatRoles.Access.Donator
DiscordChatRoles.Access.Elite
DiscordChatRoles.Access.Staff
```

### Block Messages

Version 7.0 adds optional block-style chat messages.

Enable this option in the configuration section of `server.lua`.

---

## Commands

| Command             | Purpose                      |
| ------------------- | ---------------------------- |
| `/chattag`          | List available chat tags     |
| `/chattag [id]`     | Select an available chat tag |
| `/chatcolor`        | List available chat colors   |
| `/chatcolor [id]`   | Select a chat color          |
| `/cc`               | Chat color command           |
| `/staffchat`        | Use StaffChat                |
| `/sc`               | StaffChat command            |
| `/staffchat toggle` | Toggle StaffChat messages    |
| `/sc toggle`        | Toggle StaffChat messages    |
| {.dense}            |                              |

StaffChat access uses:

```text
StaffChat.Toggle
```

The creator documents StaffChat, tag selection, and color-selection commands across versions 3.0 through 7.0.

---

## Compatibility

| Component              | Support                      |
| ---------------------- | ---------------------------- |
| **FiveM**              | Yes                          |
| **Framework**          | Not specified                |
| **Badger_Discord_API** | Required                     |
| **Discord Roles**      | Used for chat roles          |
| **ACE Permissions**    | Used for restricted features |
| {.dense}               |                              |

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-discord-scripts/discordchatroles)
* [Official GitHub Repository](https://github.com/TheWolfBadger/DiscordChatRoles)

---

## Credits

Created by **Badger** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
