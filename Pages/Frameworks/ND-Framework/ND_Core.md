# ND_Core

ND_Core is the core resource for ND Framework.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information  |
| ------------- | ------------ |
| **Name**      | `ND_Core`    |
| **Creator**   | Andyyy       |
| **Type**      | Framework    |
| **Game**      | FiveM        |
| **Framework** | ND Framework |
| **Version**   | `2.3.2`      |
| **License**   | GPL-3.0      |
| **Source**    | GitHub       |
| {.dense}      |              |

---

## Resource Details {.tabset}

### Overview

ND_Core provides the core systems used by ND Framework resources.

The project lists addons for character selection, banking, appearance shops, dealerships, inventory, ambulance jobs, casino systems, blackjack, and nitro.

### Requirements

ND_Core declares these dependencies:

* `ox_lib`
* `oxmysql`

### Framework Support

ND_Core is the core resource for ND Framework.

The manifest contains compatibility files. Legacy `es_extended` and `qb-Core` provider declarations remain commented out because the project notes they could interfere with resources checking whether those frameworks are started.

---

## Installation

### Installation Checklist

* [ ] Install `ox_lib`
* [ ] Install `oxmysql`
* [ ] Download `ND_Core`
* [ ] Place `ND_Core` in your resources folder
* [ ] Complete the required database setup
* [ ] Add the resources to `server.cfg`
* [ ] Restart your server
* [ ] Check the server console for errors

### Resource Order

Start the declared dependencies before `ND_Core`.

```cfg
ensure ox_lib
ensure oxmysql
ensure ND_Core
```

---

## Compatibility

| Component        | Support       |
| ---------------- | ------------- |
| **FiveM**        | Yes           |
| **ND Framework** | Core resource |
| **ox_lib**       | Required      |
| **oxmysql**      | Required      |
| {.dense}         |               |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Core)
* [Official ND Framework Documentation](https://ndcore.dev/)

---

## Credits

Created by **Andyyy** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.