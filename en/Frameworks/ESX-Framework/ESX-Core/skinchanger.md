---
title: skinchanger
description: skinchanger manages player models, clothing, accessories, and appearance components for ESX Legacy.
published: true
date: 2026-09-08T00:31:09.359Z
tags: appearance, characters, esx, script
editor: markdown
dateCreated: 2026-09-08T00:30:32.783Z
---

# skinchanger [![](https://badges.5metrics.dev/skinchanger/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/skinchanger)

`skinchanger` manages player models, clothing, accessories, and appearance components for ESX Legacy.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information   |
| ------------- | ------------- |
| **Name**      | `skinchanger` |
| **Creator**   | ESX Framework |
| **Type**      | Script        |
| **Category**  | Characters    |
| **Game**      | FiveM         |
| **Framework** | ESX Legacy    |
| **Version**   | `1.15.2`      |
| **Source**    | ESX Framework |
| {.dense}      |               |

---

## Resource Details {.tabset}

### Overview

`skinchanger` provides client-side functions for getting and changing player appearance.

It handles:

* Player models
* Clothing
* Hair
* Facial features
* Accessories
* Component variations
* Prop variations

The official documentation states that the resource is only available on the client side.

### Supported Models

The resource is designed around the FiveM freemode player models used by ESX character systems.

### ESX Integration

`esx_skin` uses `skinchanger` to apply and edit player appearance.

`esx_multicharacter` also uses `skinchanger` when loading character skins.

---

## Installation

### Installation Checklist

* [ ] Install ESX Legacy
* [ ] Install `es_extended`
* [ ] Keep `skinchanger` with your ESX core resources
* [ ] Start `skinchanger` before `esx_skin`
* [ ] Restart your server
* [ ] Test character appearance loading

### Resource Order

```cfg
ensure es_extended
ensure skinchanger
ensure esx_skin
```

---

## Developer Usage {.tabset}

### Load Default Model

Load the default male model:

```lua
TriggerEvent("skinchanger:loadDefaultModel", true)
```

The boolean controls whether the player uses the male default model.

### Load Skin

Apply appearance data with:

```lua
TriggerEvent("skinchanger:loadSkin", {
    sex = 1,
    face = 0,
    skin = 0,
    hair_1 = 0,
    hair_2 = 0,
    tshirt_1 = 0,
    tshirt_2 = 0,
    torso_1 = 0,
    torso_2 = 0,
    pants_1 = 0,
    pants_2 = 0,
    shoes_1 = 0,
    shoes_2 = 0
})
```

You can also provide only the components you want to change.

### Get Component Data

Retrieve available components and maximum values:

```lua
TriggerEvent("skinchanger:getData", function(components, maxVals)
    print(json.encode(components))
    print(json.encode(maxVals))
end)
```

### Get Current Skin

Retrieve the local player's current skin:

```lua
TriggerEvent("skinchanger:getSkin", function(skin)
    print(json.encode(skin))
end)
```

---

## Appearance Data

Skin data can include values for areas such as:

* Face
* Skin tone
* Beard
* Hair
* Shirts
* Torso
* Arms
* Pants
* Shoes
* Masks
* Body armor
* Chains
* Helmets
* Glasses

The resource configuration contains the available component definitions used by the skin system.

---

## Compatibility

| Component       | Support       |
| --------------- | ------------- |
| **FiveM**       | Yes           |
| **ESX Legacy**  | Yes           |
| **es_extended** | Used with ESX |
| **esx_skin**    | Integrated    |
| **Client-side** | Yes           |
| {.dense}        |               |

---

## Links

* [Official Documentation](https://docs.esx-framework.org/en/esx_core/skinchanger)
* [Official Source](https://github.com/esx-framework/esx_core/tree/main/%5Bcore%5D/skinchanger)
* [Official ESX Core Repository](https://github.com/esx-framework/esx_core)

---

## Credits

Created and maintained by **ESX Framework** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
