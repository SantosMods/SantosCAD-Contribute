---
title: ox_fuel
description: A FiveM fuel resource designed as an alternative to LegacyFuel and as an example of using petrol cans as inventory items.
published: true
date: 2026-09-07T19:07:56.751Z
tags: free, fuel, overextended, script
editor: markdown
dateCreated: 2026-09-07T05:02:32.445Z
---

# ox_fuel [![](https://badges.5metrics.dev/ox_fuel/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_fuel)


A FiveM fuel resource designed as an alternative to LegacyFuel and as an example of using petrol cans as inventory items.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information  |
| ------------ | ------------ |
| **Name**     | `ox_fuel`    |
| **Creator**  | Overextended |
| **Type**     | Script       |
| **Category** | Vehicles     |
| **Game**     | FiveM        |
| **Price**    | Free         |
| **License**  | GPL-3.0      |
| **Source**   | GitHub       |
| {.dense}     |              |

---

## Resource Details {.tabset}

### Overview

`ox_fuel` is a basic fuel resource intended for use with `ox_inventory`.

It can replace LegacyFuel and demonstrates the use of petrol cans as inventory items.

### Requirements

Required dependencies:

* `ox_lib`
* `ox_inventory`

Optional dependency:

* `ox_target`

`ox_target` provides additional functionality but is not required.

---

## Installation

### Installation Checklist

* [ ] Install `ox_lib`
* [ ] Install `ox_inventory`
* [ ] Install `ox_target` if required
* [ ] Download the latest `ox_fuel` release
* [ ] Place `ox_fuel` in your resources folder
* [ ] Start its dependencies before `ox_fuel`
* [ ] Start the resource
* [ ] Check the server console for errors

### Clone From Source

```bash
git clone https://github.com/overextended/ox_fuel.git
```

Use the latest release when you do not need the repository source.

---

## Usage {.tabset}

### Fuel Level

FiveM's native fuel functionality can be used to retrieve a vehicle's fuel level.

The resource also exposes fuel through an entity statebag:

```lua
Entity(entity).state.fuel
```

Set the statebag value to change the fuel level:

```lua
Entity(entity).state.fuel = fuelAmount
```

### Payment Integration

`ox_fuel` provides `setPaymentMethod` for replacing the standard payment method.

```lua
exports.ox_fuel:setPaymentMethod(function(playerId, amount)
    -- Your payment logic.
end)
```

This allows another system to handle payment instead of the default inventory money item.

### Money Check

The client-side `setMoneyCheck` export can replace the standard inventory search for money.

```lua
exports.ox_fuel:setMoneyCheck(function()
    -- Return the available amount.
end)
```

Use this when another account or framework system manages the player's money.

---

## Compatibility

| Component        | Compatibility              |
| ---------------- | -------------------------- |
| **FiveM**        | Supported                  |
| **ox_lib**       | Required                   |
| **ox_inventory** | Required                   |
| **ox_target**    | Optional                   |
| **LegacyFuel**   | Intended as an alternative |
| {.dense}         |                            |

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_fuel)
* [GitHub Repository](https://github.com/overextended/ox_fuel)
* [Latest Release](https://github.com/overextended/ox_fuel/releases/latest)
* [Overextended](https://overextended.dev/)

---

## Before You Install

Install and start `ox_lib` and `ox_inventory` before `ox_fuel`.

Install `ox_target` only if you want the additional functionality it provides.

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
