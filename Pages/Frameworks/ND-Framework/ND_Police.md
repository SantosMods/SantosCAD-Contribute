# ND_Police

ND_Police provides police job systems and law enforcement tools for FiveM.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                 | Information           |
| --------------------- | --------------------- |
| **Name**              | `ND_Police`           |
| **Creator**           | ND-Framework          |
| **Type**              | Script                |
| **Category**          | Police                |
| **Game**              | FiveM                 |
| **Framework Support** | ND Framework, ESX, QB |
| **License**           | GPL-3.0               |
| **Source**            | GitHub                |
| {.dense}              |                       |

---

## Resource Details {.tabset}

### Overview

ND_Police provides police interactions and law enforcement systems.

Features include:

* Hands-up interactions
* Handcuffs and zipties
* Player searching
* Player escorting
* Police shields
* Evidence
* GSR testing
* Shotspotter
* Spike strips
* Vehicle impounding
* Clothing lockers

### Requirements

The resource uses:

* `ox_lib`
* `ox_target`
* `ox_inventory`

Evidence lockers and armories use `ox_inventory`.

### Framework Support

The project provides integration for:

* ND Framework
* ESX
* QB

Some functionality is specific to ND Framework.

ND Framework users can configure police garages in `client/vehicle/data`. ND Framework integration also allows police to select an impound charge.

---

## Installation

### Installation Checklist

* [ ] Install the required dependencies
* [ ] Install and configure your supported framework
* [ ] Download `ND_Police`
* [ ] Place `ND_Police` in your resources folder
* [ ] Configure lockers and police systems
* [ ] Configure framework integration
* [ ] Add `ND_Police` to `server.cfg`
* [ ] Restart your server
* [ ] Check the server console for errors

---

## Configuration {.tabset}

### Shotspotter

Configure shotspotter locations and ranges in:

```text
data/shotspotter.lua
```

You can configure ignored jobs and ignored weapons.

Players using suppressed weapons do not trigger shotspotter.

### Police Garages

ND Framework users can configure police garages in:

```text
client/vehicle/data
```

### Evidence and Armories

Evidence lockers and armories use `ox_inventory`.

---

## Compatibility

| Component        | Support               |
| ---------------- | --------------------- |
| **FiveM**        | Yes                   |
| **ND Framework** | Yes                   |
| **ESX**          | Integration available |
| **QB**           | Integration available |
| **ox_lib**       | Used                  |
| **ox_target**    | Used                  |
| **ox_inventory** | Used                  |
| {.dense}         |                       |

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_Police)
* [Official ND Framework Documentation](https://ndcore.dev/)

---

## Credits

Created by **ND-Framework** and project contributors.

The project credits **Overextended** for `ox_police`, which ND_Police was originally based on.

The project also credits **Testaross**, **Hakko**, and **Florek** for their contributions.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.