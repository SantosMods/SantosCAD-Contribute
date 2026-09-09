# SantosDB

[![Stars](https://img.shields.io/github/stars/SantosMods/SantosDB-Contribute?style=for-the-badge\&logo=github\&label=Stars)](https://github.com/SantosMods/SantosDB-Contribute/stargazers)
[![Forks](https://img.shields.io/github/forks/SantosMods/SantosDB-Contribute?style=for-the-badge\&logo=github\&label=Forks)](https://github.com/SantosMods/SantosDB-Contribute/forks)
[![Watchers](https://img.shields.io/github/watchers/SantosMods/SantosDB-Contribute?style=for-the-badge\&logo=github\&label=Watchers)](https://github.com/SantosMods/SantosDB-Contribute/watchers)
[![Contributors](https://img.shields.io/github/contributors/SantosMods/SantosDB-Contribute?style=for-the-badge\&logo=github\&label=Contributors)](https://github.com/SantosMods/SantosDB-Contribute/graphs/contributors)

[![Issues](https://img.shields.io/github/issues/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Issues)](https://github.com/SantosMods/SantosDB-Contribute/issues)
[![Pull Requests](https://img.shields.io/github/issues-pr/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Pull%20Requests)](https://github.com/SantosMods/SantosDB-Contribute/pulls)
![Last Commit](https://img.shields.io/github/last-commit/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Last%20Commit)
![Commit Activity](https://img.shields.io/github/commit-activity/m/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Monthly%20Commits)
![Repo Size](https://img.shields.io/github/repo-size/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Size)
![Top Language](https://img.shields.io/github/languages/top/SantosMods/SantosDB-Contribute?style=flat-square\&logo=github\&label=Top%20Language)
![License](https://img.shields.io/github/license/SantosMods/SantosDB-Contribute?style=flat-square\&label=License)

SantosDB is a FiveM resource directory for scripts, EUP, vehicles, MLOs, YMAPs, tools, libraries, and related resources.

SantosDB does not host or redistribute listed resources. Pages link users to official or authorized sources.

**Website:** https://santosdb.net/

SantosDB is affiliated with [SantosMods.dev](https://santosmods.dev/).

## Contributing

Contributions are accepted through pull requests.

1. Fork this repository.
2. Make your changes.
3. Review the page for accuracy.
4. Submit a pull request.

Only submit resources from official or authorized sources.

Do not submit:

* Leak sites
* Cracked resources
* Stolen content
* Unauthorized mirrors
* Reuploaded paid resources

Keep writing short and factual. Check spelling, links, framework support, requirements, creator information, and pricing before submitting.

## Page Structure

SantosDB uses Wiki.js Markdown.

Keep paths simple and consistent.

```text
/Scripts/Libraries/ox_lib
/Scripts/Inventory/ox_inventory
/EUP/Developer-Name/Type/Name
/Vehicles/Developer-Name/Type/Name
/MLOs/Developer-Name/Name
/YMAPs/Developer-Name/Name
```

Use tags for important resource information such as:

```text
free
qbox
overextended
github
```

Keep tags relevant. Avoid unnecessary or duplicate tags.

Use existing SantosDB pages as the main formatting reference.

## Example Page

````md
# ox_lib

A standalone FiveM library providing reusable modules, exports, utilities, and interface components for Lua and JavaScript resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

## Resource Information

| Field         | Information    |
| ------------- | -------------- |
| **Name**      | `ox_lib`       |
| **Creator**   | Overextended   |
| **Type**      | Library        |
| **Category**  | Developer Tool |
| **Game**      | FiveM          |
| **Price**     | Free           |
| **Framework** | Standalone     |
| **Source**    | GitHub         |
| {.dense}      |                |

## Installation

Download the resource from its official source and place `ox_lib` in your resources folder.

Add it to your resource startup order:

```cfg
ensure ox_lib
```

## Links

- [Documentation](https://overextended.dev/docs/ox_lib)
- [GitHub](https://github.com/overextended/ox_lib)

## Credits

Created by **Overextended** and project contributors.
````

Use this as a guide. Resource pages do not need to follow the example line for line.
