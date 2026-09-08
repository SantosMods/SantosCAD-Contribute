---
title: esx_identity
description: esx_identity handles identity registration for ESX characters.
published: true
date: 2026-09-08T00:24:19.241Z
tags: ', characters, esx, identity, script
editor: markdown
dateCreated: 2026-09-07T23:32:58.420Z
---

---
title: esx_identity
description: esx_identity handles identity registration for ESX characters.
published: true
date: 2026-09-07T23:39:14.192Z
tags: ', characters, esx, identity, script
editor: markdown
dateCreated: 2026-09-07T23:32:58.420Z
---

# esx_identity [![](https://badges.5metrics.dev/esx_identity/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/esx_identity)

`esx_identity` handles identity registration for ESX characters.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information      |
| ------------- | ---------------- |
| **Name**      | `esx_identity`   |
| **Creator**   | ESX Framework    |
| **Type**      | Script           |
| **Category**  | Characters       |
| **Game**      | FiveM            |
| **Framework** | ESX Legacy       |
| **Version**   | `1.15.0`         |
| **License**   | GPL-3.0-or-later |
| {.dense}      |                  |

---

## Resource Details {.tabset}

### Overview

`esx_identity` allows players to register character identity information.

Identity data includes:

* First name
* Last name
* Date of birth
* Sex
* Height

The resource is used by `es_extended` and `esx_multicharacter`.

### Requirements

The resource declares:

* `es_extended`

The official repository also lists:

* `esx_skin`

The current manifest uses imports from:

```text
@esx_lib/imports.lua
@es_extended/imports.lua
@es_extended/locale.lua
@oxmysql/lib/MySQL.lua
```

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Install the documented `esx_skin` requirement
* [ ] Keep `esx_identity` with your ESX core resources
* [ ] Complete the ESX database setup
* [ ] Start `esx_identity`
* [ ] Restart your server
* [ ] Test identity registration with a new character

---

## Configuration

The resource includes:

```text
config.lua
```

Review the official configuration before changing identity validation or registration behavior.

---

## Usage {.tabset}

### Show Registration

Open the identity registration interface with:

```lua
TriggerEvent("esx_identity:showRegisterIdentity")
```

### Registration Event

Server resources can listen for completed identity registration:

```lua
AddEventHandler("esx_identity:completedRegistration", function(source, data)
    print(data.firstname)
    print(data.lastname)
end)
```

The returned `data` contains:

* `firstname`
* `lastname`
* `dateofbirth`
* `sex`
* `height`

### Commands

The official repository documents:

```text
/char
/chardel
```

---

## Compatibility

| Component              | Support                |
| ---------------------- | ---------------------- |
| **FiveM**              | Yes                    |
| **ESX Legacy**         | Yes                    |
| **es_extended**        | Required               |
| **esx_multicharacter** | Used with the resource |
| **esx_skin**           | Documented requirement |
| {.dense}               |                        |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/esx_identity)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/esx_identity)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created by **ESX Framework** and project contributors.

The project credits **Jérémie N'gadi** in its licensing information.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
