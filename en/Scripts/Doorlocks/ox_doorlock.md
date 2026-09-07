---
title: ox_doorlock
description: A door management resource that can be used standalone or alongside ox_core, qbx_core, and es_extended.
published: true
date: 2026-09-07T19:05:53.688Z
tags: doorlock, free, overextended, script
editor: markdown
dateCreated: 2026-09-07T05:01:07.714Z
---

# ox_doorlock [![](https://badges.5metrics.dev/ox_doorlock/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_doorlock)

A FiveM door management resource that can run standalone or alongside supported frameworks.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information      |
| ------------ | ---------------- |
| **Name**     | `ox_doorlock`    |
| **Creator**  | Overextended     |
| **Type**     | Script           |
| **Category** | Door Management  |
| **Game**     | FiveM            |
| **Price**    | Free             |
| **License**  | GPL-3.0 or later |
| **Source**   | GitHub           |
| {.dense}     |                  |

---

## Resource Details {.tabset}

### Overview

`ox_doorlock` manages doors and access restrictions on FiveM servers.

Use `/doorlock` to open the management UI and configure a door.

The resource supports:

* Single and double doors
* Automatic doors
* Character access
* Group and grade access
* Item access
* Lockpicking
* Door audio
* Door indicators
* Database-backed door storage

### Requirements

Required dependencies:

* `oxmysql`
* `ox_lib`

The repository specifies `ox_lib` v2.3.0 or higher.

Optional dependency:

* `ox_target`

`ox_target` provides additional functionality such as lockpicking interactions.

### Framework Support

The official documentation states that `ox_doorlock` can run standalone or alongside:

| Framework             | Support   |
| --------------------- | --------- |
| **Standalone**        | Supported |
| **ox_core**           | Supported |
| **Qbox / qbx_core**   | Supported |
| **ESX / es_extended** | Supported |
| {.dense}              |           |

---

## Installation

### Installation Checklist

* [ ] Install `oxmysql`
* [ ] Install `ox_lib`
* [ ] Install `ox_target` if required
* [ ] Download the latest `ox_doorlock` release
* [ ] Place `ox_doorlock` in your resources folder
* [ ] Start its dependencies before `ox_doorlock`
* [ ] Start the resource
* [ ] Run `/doorlock`
* [ ] Check the server console for errors

### Building From Source

If you clone the source instead of using a release, build the UI.

```bash
git clone https://github.com/overextended/ox_doorlock.git
cd ox_doorlock/web
bun i
bun run build
```

> If `/doorlock` displays the cursor but no interface, the UI has not been built.
> {.is-warning}

---

## Usage

Run:

```text
/doorlock
```

Use the UI to configure your new door.

After confirming the settings, use your targeting resource to select the door entity or entities.

Adding an argument after `/doorlock` opens the closest door for editing.

### Command Permission

If you cannot use `/doorlock`, check the ACE permission from the server console.

```text
test_ace player.1 command.doorlock
```

Replace `1` with your server ID.

---

## nui_doorlock Conversion

Existing `nui_doorlock` configuration files can be imported into the database.

Place `.lua` files inside:

```text
ox_doorlock/convert
```

Create the directory if it does not exist.

The files are read when the resource starts.

> Conversion is not guaranteed, especially for configurations created for a modified fork of `nui_doorlock`.
> {.is-warning}

---

## Compatibility

| Component                | Compatibility        |
| ------------------------ | -------------------- |
| **FiveM**                | Supported            |
| **Standalone**           | Supported            |
| **ox_core**              | Supported            |
| **qbx_core**             | Supported            |
| **es_extended**          | Supported            |
| **oxmysql**              | Required             |
| **ox_lib**               | Required             |
| **ox_target**            | Optional             |
| **nui_doorlock configs** | Conversion available |
| {.dense}                 |                      |

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_doorlock)
* [GitHub Repository](https://github.com/overextended/ox_doorlock)
* [Latest Release](https://github.com/overextended/ox_doorlock/releases/latest)
* [Overextended](https://overextended.dev/)

---

## Before You Install

Use the latest release if you want a ready-to-use build.

If you clone the source repository, build the web UI before using the resource.

Back up your database before importing or converting existing door data.

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
