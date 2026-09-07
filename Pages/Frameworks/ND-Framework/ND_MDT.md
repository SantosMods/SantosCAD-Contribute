# ND_MDT

ND_MDT is a police mobile data terminal for ND_Core.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field                 | Information  |
| --------------------- | ------------ |
| **Name**              | `ND_MDT`     |
| **Creator**           | ND-Framework |
| **Type**              | Script       |
| **Category**          | Police       |
| **Game**              | FiveM        |
| **Primary Framework** | ND_Core      |
| **ESX Integration**   | Available    |
| **License**           | GPL-3.0      |
| **Source**            | GitHub       |
| {.dense}              |              |

---

## Resource Details {.tabset}

### Overview

ND_MDT provides police MDT and dispatch functionality.

Features include:

* Officer status
* Dispatch calls
* Officer live chat
* Call attachment and detachment
* Call waypoints
* Panic button
* Person searching
* Plate searching
* Weapon searching
* BOLOs
* Person records
* Notes
* License management
* Reports
* Employee management

### Inventory

The project provides an `ox_inventory` tablet item using:

```lua
export = "ND_MDT.useTablet"
```

### Reports

Supported report types include:

* Crime
* Traffic
* Arrest
* Incident
* Use of Force

Reports receive unique case IDs for use with `ox_inventory` evidence lockers.

---

## Installation

### Installation Checklist

* [ ] Install and configure the required framework
* [ ] Install the required supporting resources
* [ ] Download `ND_MDT`
* [ ] Place `ND_MDT` in your resources folder
* [ ] Complete the required database setup
* [ ] Add the MDT inventory item
* [ ] Add `ND_MDT` to `server.cfg`
* [ ] Restart your server
* [ ] Check the MDT and server console

> ESX users must use the SQL files in `bridge/esx/database`. The project states that the ESX integration will not work without them.
> {.is-warning}

---

## Features {.tabset}

### Dashboard

The dashboard supports:

* Officer status
* Dispatch calls
* Automatic status changes
* Attaching and detaching from calls
* Call waypoints
* Panic button with TTS

### Person Search

Officers can:

* View person information
* View registered weapons
* View vehicles
* Create BOLOs
* Create records
* Add notes
* Manage licenses

### Vehicle and Weapon Search

Plate searching supports owner lookup and stolen vehicle marking.

Weapon searching supports serial numbers, owner lookup, and stolen weapon marking.

Legal weapons purchased through supported `ox_inventory` shops can be registered automatically.

### Employee Management

Boss ranks can:

* Manage employee ranks
* Manage callsigns
* Hire employees
* Fire employees

---

## Developer Usage

Create a dispatch call from another resource:

```lua
exports["ND_MDT"]:createDispatch({
    caller = "John Doe",
    location = "Sandy shores",
    callDescription = "Whiteness bank robbery",
    coords = vec3(x, y, z)
})
```

`location` is optional. When coordinates are provided without a location, the MDT can display the location from those coordinates.

---

## ESX Integration

The repository documents ESX support.

Use the SQL files located in:

```text
bridge/esx/database
```

The project notes that some custom phone, property, and billing functionality still requires additional integration.

---

## Links

* [Official GitHub Repository](https://github.com/ND-Framework/ND_MDT)
* [Official ND Framework Documentation](https://ndcore.dev/)

---

## Credits

Created by **ND-Framework** and project contributors.

The project credits **Maximus7474** for ESX support.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
