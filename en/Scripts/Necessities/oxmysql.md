---
title: oxmysql
description: A FiveM database resource for communicating with MySQL-compatible databases through node-mysql2.
published: true
date: 2026-09-07T06:10:41.171Z
tags: free, library, overextended, database
editor: markdown
dateCreated: 2026-09-07T05:04:50.394Z
---

# oxmysql

A FiveM database resource for communicating with MySQL-compatible databases through `node-mysql2`.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

---

## Resource Information

| Field        | Information  |
| ------------ | ------------ |
| **Name**     | `oxmysql`    |
| **Creator**  | Overextended |
| **Type**     | Library      |
| **Category** | Database     |
| **Game**     | FiveM        |
| **Price**    | Free         |
| **License**  | LGPL-3.0     |
| **Source**   | GitHub       |
| {.dense}     |              |

---

## Resource Details {.tabset}

### Overview

`oxmysql` provides database access for FXServer resources.

It is designed as a replacement for `mysql-async` and `ghmattimysql` with an expanded API and improved MySQL 8 compatibility.

Features include:

* Promise and async query handling
* Awaitable queries
* Named and unnamed placeholders
* URI connection strings
* Semicolon-separated connection values
* Parameter validation
* Error handling
* Lua integration
* JavaScript integration
* TypeScript support through its npm package
* Compatibility APIs for older database resources

### Database

The official documentation recommends MariaDB for FiveM compatibility and performance.

It notes that resources originally designed for MySQL 5.7 can encounter compatibility issues with MySQL 8.

> Overextended recommends installing MariaDB directly instead of setting up XAMPP solely to run your FiveM database.
> {.is-info}

---

## Installation

### Installation Checklist

* [ ] Install MariaDB
* [ ] Create your server database
* [ ] Download the latest `oxmysql` release
* [ ] Place `oxmysql` in your resources folder
* [ ] Configure `mysql_connection_string`
* [ ] Start `oxmysql` before resources that use it
* [ ] Start the server
* [ ] Check the console for database errors

### Resource Order

Place `oxmysql` near the top of your resource list.

```cfg
start oxmysql
```

Set the connection string before starting dependent resources.

### Connection String

URI format:

```cfg
set mysql_connection_string "mysql://username:password@localhost:3306/database"
```

Semicolon-separated format:

```cfg
set mysql_connection_string "user=username;password=password;host=localhost;port=3306;database=database"
```

Use `set`, not `setr`, for the database connection string.

> Do not publish your production database credentials in documentation, screenshots, repositories, or support messages.
> {.is-warning}

Certain special characters can cause connection-string problems. Check the official documentation if your credentials contain reserved characters.

---

## Configuration {.tabset}

### Slow Queries

Configure the slow-query warning threshold:

```cfg
set mysql_slow_query_warning 150
```

A slow-query warning does not always mean the database itself has a problem. Server hitches and startup activity can affect query timing.

### Debugging

Enable query debugging:

```cfg
set mysql_debug true
```

You can restrict debug output to specific resources:

```cfg
set mysql_debug [
    "ox_core",
    "ox_inventory"
]
```

Temporarily change the debug resource list with:

```text
oxmysql_debug remove ox_core
oxmysql_debug add ox_core
```

> Debug output can produce significant console output. Enable it when you need to diagnose database queries.
> {.is-info}

---

## Usage {.tabset}

### Lua

Add the `oxmysql` library above your resource's other server scripts in `fxmanifest.lua`.

```lua
server_script '@oxmysql/lib/MySQL.lua'
```

This makes the `MySQL` API available to the resource.

### JavaScript

JavaScript resources can use raw exports or the official npm package.

```bash
npm install @overextended/oxmysql
```

Import it into your resource:

```js
import { oxmysql as MySQL } from "@overextended/oxmysql";
```

The package provides additional TypeScript and IntelliSense support.

---

## Compatibility

`oxmysql` can provide compatibility functionality for resources that previously depended on:

* `mysql-async`
* `ghmattimysql`

The official documentation states these resources can be removed when `oxmysql` provides their functionality.

| Component            | Compatibility                               |
| -------------------- | ------------------------------------------- |
| **FiveM / FXServer** | Supported                                   |
| **MariaDB**          | Recommended                                 |
| **MySQL 8**          | Supported with compatibility considerations |
| **mysql-async**      | Compatibility functionality                 |
| **ghmattimysql**     | Compatibility functionality                 |
| **Lua**              | Supported                                   |
| **JavaScript**       | Supported                                   |
| **TypeScript**       | npm package support                         |
| {.dense}             |                                             |

---

## Database Notes

MySQL 8 can introduce compatibility problems for older FiveM resources.

Examples documented by Overextended include:

* Additional reserved keywords
* Differences involving `LONGTEXT` and JSON default values

Use MariaDB when you want the database platform recommended by the project.

---

## Links

* [Official Documentation](https://overextended.dev/docs/oxmysql)
* [GitHub Repository](https://github.com/overextended/oxmysql)
* [Latest Release](https://github.com/overextended/oxmysql/releases/latest)
* [npm Package](https://www.npmjs.com/package/@overextended/oxmysql)
* [Overextended](https://overextended.dev/)

---

## Before You Install

Install your database server before configuring `oxmysql`.

Set `mysql_connection_string` before `oxmysql` and other database-dependent resources start.

Do not install XAMPP solely to provide the database. The official documentation recommends installing MariaDB directly.

---

## Credits

Created by **Overextended** and project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
