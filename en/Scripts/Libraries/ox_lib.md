---
title: ox_lib
description: A standalone library for providing easily reusable code as importable modules and exports.
published: true
date: 2026-09-08T00:21:48.597Z
tags: library, developer-tool, free, overextended
editor: markdown
dateCreated: 2026-09-07T04:12:41.850Z
---

# ox_lib [![](https://badges.5metrics.dev/ox_lib/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/ox_lib)

A standalone FiveM library providing reusable modules, exports, utilities, and interface components for Lua and JavaScript resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field         | Information    |
| ------------- | -------------- |
| **Name**      | `ox_lib`       |
| **Creator**   | Overextended   |
| **Type**      | Library        |
| **Category**  | Developer Tool |
| **Game**      | FiveM          |
| **Price**     | Free           |
| **License**   | LGPL-3.0       |
| **Framework** | Standalone     |
| **Source**    | GitHub         |
| **Status**    | Active         |
| {.dense}      |                |

---

## Resource Details {.tabset}

### Overview

`ox_lib` provides reusable code for FiveM resources through importable modules and exports.

The library includes functionality for areas such as:

* Callbacks
* Commands
* Keybinds
* Locales
* Logging
* Markers
* Points
* Zones
* Vehicle properties
* Streaming
* Raycasts
* Timers
* Interface components
* Utility functions

It provides APIs for Lua and JavaScript development.

### Framework Support

`ox_lib` is standalone.

It can be used by other FiveM resources without requiring a specific roleplay framework.

---

## Installation

### Installation Checklist

* [ ] Download the latest `ox_lib` release
* [ ] Place `ox_lib` in your resources folder
* [ ] Add `ox_lib` to your resource start configuration
* [ ] Configure required convars
* [ ] Configure ACE permissions where required
* [ ] Restart the server
* [ ] Check the console for errors

To build the resource from source:

```bash
git clone https://github.com/overextended/ox_lib.git
cd ox_lib/web
bun i
bun run build
```

Use a release build unless you need to build or modify the source.

---

## Configuration

`ox_lib` uses FiveM convars.

Example settings documented by Overextended:

```cfg
setr ox:primaryColor blue
setr ox:primaryShade 8
setr ox:userLocales 1
setr ox:progressPropLimit 2
```

The resource also requires ACE permissions for permission-management functionality:

```cfg
add_ace resource.ox_lib command.add_ace allow
add_ace resource.ox_lib command.remove_ace allow
add_ace resource.ox_lib command.add_principal allow
add_ace resource.ox_lib command.remove_principal allow
```

---

## Using ox_lib

Add `@ox_lib/init.lua` to your resource's `fxmanifest.lua`.

```lua
shared_scripts {
    '@ox_lib/init.lua',
}
```

If it is your only shared script:

```lua
shared_script '@ox_lib/init.lua'
```

You can also specify modules to import:

```lua
ox_libs {
    'locale',
    'math',
    'table',
}
```

After importing the library, `lib` can dynamically import `ox_lib` modules.

### JavaScript

Overextended also provides an npm package.

Example server import:

```js
import lib from "@overextended/ox_lib/server";
```

You can import individual functions when required:

```js
import { versionCheck } from "@overextended/ox_lib/server";
```

> The npm package does not expose every function available to Lua.
> {.is-info}

---

## Building the UI

If you modify the UI source, build it from the `web` directory.

```bash
bun i
bun run build
```

For browser development with hot reload:

```bash
bun start
```

For in-game development that writes changes to disk:

```bash
bun start:game
```

> Edit the source and rebuild it. Do not de-bundle or un-minify release CSS and JavaScript files to modify the UI.
> {.is-warning}

---

## Compatibility

| Component       | Compatibility |
| --------------- | ------------- |
| **FiveM**       | Yes           |
| **Framework**   | Standalone    |
| **Lua**         | Supported     |
| **JavaScript**  | Supported     |
| **npm package** | Available     |
| {.dense}        |               |

---

## Links

* [Official Documentation](https://overextended.dev/docs/ox_lib)
* [GitHub Repository](https://github.com/overextended/ox_lib)
* [Latest Release](https://github.com/overextended/ox_lib/releases/latest)
* [npm Package](https://www.npmjs.com/package/@overextended/ox_lib)
* [Overextended](https://overextended.dev/)

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
