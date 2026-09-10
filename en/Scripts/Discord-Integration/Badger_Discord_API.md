---
title: Badger_Discord_API
description: Badger_Discord_API provides Discord API functionality for FiveM resources.
published: true
date: 2026-09-09T00:14:36.599Z
tags: developer-tool, discord, script, api
editor: markdown
dateCreated: 2026-09-09T00:14:34.720Z
---

# Badger_Discord_API [![](https://badges.5metrics.dev/Badger_Discord_API/servers.svg?style=for-the-badge)](https://5metrics.dev/resource/Badger_Discord_API)

Badger_Discord_API provides reusable Discord REST API access for FiveM resources.

> SantosDB links to the source project. SantosDB does not own, maintain, or distribute this resource.
> {.is-info}

> Some API methods may not fully work. The creator recommends checking `example.lua` and submitting an issue or pull request when a method does not behave as expected.
> {.is-warning}

---

## Resource Information

| Field                     | Information          |
| ------------------------- | -------------------- |
| **Name**                  | `Badger_Discord_API` |
| **Creator**               | Badger               |
| **Repository Owner**      | JaredScar            |
| **Type**                  | Script               |
| **Category**              | Developer Tool       |
| **Game**                  | FiveM                |
| **Framework Requirement** | None specified       |
| **Discord Bot**           | Required             |
| **Discord Guild**         | Required             |
| **License**               | MIT                  |
| **Source**                | GitHub               |
| {.dense}                  |                      |

---

## Resource Details {.tabset}

### Overview

Badger_Discord_API provides a shared Discord API layer for FiveM resources.

It uses Discord's REST API to retrieve Discord user, member, role, and guild information.

Other FiveM resources can call its server exports instead of implementing their own Discord API requests.

The API can:

* Find Discord role IDs by role name
* Compare roles
* Retrieve a player's Discord roles
* Retrieve Discord usernames
* Retrieve Discord nicknames
* Retrieve Discord avatars
* Retrieve Discord email information
* Check Discord email verification
* Retrieve guild names
* Retrieve guild descriptions
* Retrieve guild icons
* Retrieve guild splash images
* Retrieve guild member counts
* Retrieve approximate online member counts
* Retrieve guild role lists
* Work with multiple configured Discord guilds
* Cache selected Discord data
* Add Discord roles
* Remove Discord roles
* Set Discord roles
* Change Discord nicknames
* Move Discord users between voice channels

### How It Works

The resource builds authenticated requests using your configured Discord bot token.

The server code sends requests to:

```text
https://discord.com/api/
```

The bot token is sent through the Discord authorization header.

The API then exposes reusable Lua functions to other server resources through FiveM exports.

### Resource Name Requirement

Keep the resource folder named exactly:

```text
Badger_Discord_API
```

The server code checks the current resource name and warns when it has been renamed.

Other resources also call exports through:

```lua
exports.Badger_Discord_API
```

Renaming the resource can therefore break integrations.

---

## Requirements

You need:

* A Discord account
* A Discord application
* A Discord bot
* The bot token
* Your Discord Guild ID
* The bot invited to your Discord server
* Correct Discord bot permissions for the functions you use
* FiveM server access to outbound Discord API requests

No QBCore, Qbox, ESX, ND Framework, or other FiveM framework dependency is specified by the project.

---

## Discord Bot Setup

### Create the Application

Open the Discord Developer Portal:

[Discord Developer Portal](https://discord.com/developers/applications)

Create a new application for your FiveM server.

### Create the Bot

Open the application's bot section and create a bot.

Copy its bot token for use in `config.lua`.

> Treat your bot token like a password. Anyone with the token can authenticate as your bot within the permissions Discord grants it.
> {.is-danger}

Do not:

* Commit the token to a public GitHub repository
* Share it in screenshots
* Post it in Discord support channels
* Put it in public documentation
* Upload an unredacted configuration file

If your token is exposed, regenerate it through Discord's Developer Portal and update your server configuration.

### Invite the Bot

Invite the bot to the Discord guild used by your FiveM server.

The exact Discord permissions needed depend on which API functions your resources use.

For example, functions that modify roles, nicknames, or voice channels require the bot to have corresponding Discord permissions.

### Get the Guild ID

Enable Discord Developer Mode if needed.

Copy the ID of the Discord server you want to use.

This value becomes your `Guild_ID`.

---

## Installation

### Installation Checklist

* [ ] Create a Discord application
* [ ] Create a Discord bot
* [ ] Invite the bot to your Discord server
* [ ] Copy the bot token
* [ ] Copy your Discord Guild ID
* [ ] Download `Badger_Discord_API` from the official GitHub repository
* [ ] Keep the resource folder named `Badger_Discord_API`
* [ ] Place it in your FiveM resources folder
* [ ] Open `config.lua`
* [ ] Set `Guild_ID`
* [ ] Set `Bot_Token`
* [ ] Configure `RoleList` if needed
* [ ] Review optional guild and cache settings in your version
* [ ] Add the resource to `server.cfg`
* [ ] Start it before resources that use its exports
* [ ] Restart your server
* [ ] Check the server console for Discord connection errors
* [ ] Test each API export used by your dependent resources

### server.cfg

```cfg
ensure Badger_Discord_API
```

Start dependent resources after it.

For example:

```cfg
ensure Badger_Discord_API
ensure DiscordChatRoles
```

---

## Configuration {.tabset}

### Core Configuration

The main configuration file is:

```text
config.lua
```

The documented configuration includes:

```lua
Config = {
    Guild_ID = '{GUILD_ID}',
    Bot_Token = '{BOT_TOKEN}',
    RoleList = {
    },
}
```

Replace the placeholder values with your own Discord information.

### Guild_ID

`Guild_ID` defines the primary Discord guild used by the API.

```lua
Guild_ID = '{GUILD_ID}'
```

Use the numeric Discord server ID.

### Bot_Token

`Bot_Token` authenticates API requests.

```lua
Bot_Token = '{BOT_TOKEN}'
```

Do not include `Bot ` yourself.

The resource formats the authorization value internally.

### RoleList

`RoleList` is optional.

It lets you create reusable names for Discord roles.

Example structure:

```lua
RoleList = {
    ['Founder'] = 123456789012345678,
    ['Admin'] = 234567890123456789,
    ['Staff'] = 345678901234567890,
}
```

Use your own Discord role IDs.

Other Badger resources can use these keys instead of repeating role IDs everywhere.

### Role Names vs Role IDs

Badger_Discord_API can retrieve your Discord server's role list.

This makes it possible for scripts to work with a role name rather than manually storing every role ID.

Be careful when depending on names.

If someone renames the Discord role, a script checking that old role name may stop matching it.

Role IDs are more stable.

### Multiple Guilds

Current server code contains support for additional configured guilds.

The API can resolve a named guild from the configured guild list and can combine user roles across multiple guilds when multiguild support is enabled.

Resources that specify a guild explicitly can request data only from that guild.

### Discord Role Cache

The resource supports caching user Discord roles.

When role caching is enabled, recently retrieved roles can be reused instead of sending another request to Discord immediately.

The server code uses a configurable cache duration.

This reduces repeated Discord requests but means a newly added or removed Discord role may not appear until the cache expires or is cleared.

### Avatar Cache

Discord avatar URLs are cached internally.

The resource first checks its avatar cache before requesting the player's Discord user data again.

### Guild Role Cache

Guild roles are also cached.

When `GetGuildRoleList` retrieves a guild's roles, the resulting role-name-to-role-ID mapping is stored for later requests.

---

## Optional Connection Splash

The documented configuration includes an optional connection splash.

Example options include:

```lua
Config.Splash = {
    Header_IMG = 'https://example.com/header.png',
    Enabled = true,
    Wait = 10,
    Heading1 = "Welcome to your server",
    Heading2 = "Join our Discord and visit our website",
    Discord_Link = 'https://discord.gg/example',
    Website_Link = 'https://example.com',
}
```

`Enabled` controls whether the splash appears during connection.

`Wait` controls how long the connection card displays.

The official example notes a maximum value of 12 seconds.

Use your own branding and URLs.

---

## Developer API

Call exports from another server resource using:

```lua
exports.Badger_Discord_API:FunctionName(...)
```

For example:

```lua
local roleId = exports.Badger_Discord_API:GetRoleIdFromRoleName("Staff")
```

> These are server-side Discord integration functions. Validate returned values before using them for permissions or gameplay logic.
> {.is-info}

---

## Player Discord Data {.tabset}

### GetDiscordRoles

Returns the Discord role IDs assigned to a player.

```lua
local roles = exports.Badger_Discord_API:GetDiscordRoles(source)
```

The documented export is:

```text
exports.Badger_Discord_API:GetDiscordRoles(user)
```

`user` is the player's FiveM source.

On success, the function returns a table containing Discord role IDs.

Example result:

```lua
{
    597446100206616596,
    597450498060058624,
    597929446124552192
}
```

If the player's Discord account cannot be found, the documentation states that it returns:

```lua
false
```

The server implementation retrieves the player's `discord:` FiveM identifier and then requests the guild member record from Discord.

### GetDiscordName

Returns the player's Discord username.

```lua
local name = exports.Badger_Discord_API:GetDiscordName(source)
```

The documented export is:

```text
exports.Badger_Discord_API:GetDiscordName(user)
```

If found, it returns the Discord name.

If no matching Discord user is found, it returns:

```lua
nil
```

The current implementation handles newer Discord usernames with discriminator `0` by returning only the username.

For legacy discriminator-based accounts, it can return a value in the older:

```text
username#discriminator
```

format.

### GetDiscordNickname

Use `GetDiscordNickname` when you need the player's nickname within the configured Discord guild rather than their account username.

```lua
local nickname = exports.Badger_Discord_API:GetDiscordNickname(source)
```

A guild nickname is separate from the player's global Discord username.

### GetDiscordAvatar

Returns the player's Discord avatar URL.

```lua
local avatar = exports.Badger_Discord_API:GetDiscordAvatar(source)
```

The documented export is:

```text
exports.Badger_Discord_API:GetDiscordAvatar(user)
```

If the avatar is found, a Discord CDN image URL is returned.

If it is not found, the documentation states the function returns:

```lua
nil
```

The resource caches avatar results to reduce repeated API calls.

It also handles animated Discord avatars by returning a `.gif` URL when appropriate.

### GetDiscordEmail

Retrieves Discord email information where Discord makes that information available to the bot and API flow being used.

```lua
local email = exports.Badger_Discord_API:GetDiscordEmail(source)
```

Do not assume an email will always be returned.

### IsDiscordEmailVerified

Checks the Discord email verification state exposed through the relevant Discord user data.

```lua
local verified = exports.Badger_Discord_API:IsDiscordEmailVerified(source)
```

Handle missing data separately from an explicit verified or unverified state.

---

## Role API {.tabset}

### GetRoleIdFromRoleName

Converts a Discord role name to its role ID.

```lua
local roleId = exports.Badger_Discord_API:GetRoleIdFromRoleName("Staff")
```

The function uses the cached guild role list when available.

If the cache is empty, it retrieves the guild's role list and builds the mapping.

When the role cannot be found, the function can return:

```lua
nil
```

### GetGuildRoleList

Returns the guild's Discord roles as a mapping of role names to IDs.

```lua
local roles = exports.Badger_Discord_API:GetGuildRoleList()
```

Conceptually, the result resembles:

```lua
{
    ["Founder"] = "123456789012345678",
    ["Admin"] = "234567890123456789",
    ["Staff"] = "345678901234567890"
}
```

The role list is cached after retrieval.

### CheckEqual

`CheckEqual` is provided for comparing role information.

Use it with values returned by Badger_Discord_API rather than assuming role-name and role-ID values are interchangeable.

### Role Matching Example

A typical pattern is:

```lua
local roles = exports.Badger_Discord_API:GetDiscordRoles(source)
local staffRole = exports.Badger_Discord_API:GetRoleIdFromRoleName("Staff")

if roles and staffRole then
    for _, roleId in pairs(roles) do
        if tostring(roleId) == tostring(staffRole) then
            print("Player has the Staff role")
            break
        end
    end
end
```

Always handle:

```lua
false
```

or:

```lua
nil
```

before iterating returned data.

---

## Guild API {.tabset}

### GetGuildName

Returns the configured guild's Discord name.

```lua
local guildName = exports.Badger_Discord_API:GetGuildName()
```

### GetGuildDescription

Returns the guild description.

```lua
local description = exports.Badger_Discord_API:GetGuildDescription()
```

### GetGuildIcon

Returns a Discord CDN URL for the guild icon.

```lua
local icon = exports.Badger_Discord_API:GetGuildIcon()
```

The server implementation returns a `.gif` URL for an animated icon and `.png` otherwise.

### GetGuildSplash

Returns a Discord CDN URL for the guild splash image when one is available.

```lua
local splash = exports.Badger_Discord_API:GetGuildSplash()
```

### GetGuildMemberCount

Returns Discord's approximate guild member count.

```lua
local count = exports.Badger_Discord_API:GetGuildMemberCount()
```

The implementation requests the guild with:

```text
?with_counts=true
```

and reads Discord's approximate member count.

### GetGuildOnlineMemberCount

Returns Discord's approximate presence count.

```lua
local online = exports.Badger_Discord_API:GetGuildOnlineMemberCount()
```

This is an approximate Discord presence value, not a FiveM player count.

### GetGuildRoleList

Returns the Discord guild role list.

```lua
local roleList = exports.Badger_Discord_API:GetGuildRoleList()
```

The returned list is cached by the resource.

---

## Discord Modification Functions

The project's server implementation includes Discord modification functionality in addition to read-only data access.

Supported operations include:

* Changing Discord nicknames
* Adding roles
* Removing roles
* Replacing or setting roles
* Moving Discord users between voice channels

These operations require suitable Discord bot permissions.

Discord may reject a request when:

* The bot lacks the required permission
* The bot's highest role is below the target role
* The member cannot be managed by the bot
* The guild or member ID is incorrect
* The bot token is invalid
* Discord returns a rate limit
* The requested Discord resource does not exist

> Verify the exact function signature in the current repository or `example.lua` before implementing write operations. The official documentation does not document every modification method as thoroughly as the read exports.
> {.is-warning}

---

## Caching {.tabset}

### Why Caching Exists

Discord applies API rate limits.

Badger_Discord_API caches information that would otherwise cause repetitive requests.

The creator specifically identifies:

* Server role lists
* Player avatars

The current code also supports recent player-role caching.

### Avatar Cache

Avatar URLs are stored by Discord user ID.

Repeated avatar requests can return the cached value instead of making another Discord request.

### Role List Cache

Guild role lists are stored by guild ID.

This makes repeated role-name lookups more efficient.

### Player Role Cache

When enabled, Discord roles for a player can be cached for a configured amount of time.

This reduces requests to the Discord member endpoint.

### Cache Tradeoff

Caching improves API efficiency but creates a delay between a Discord change and the FiveM server seeing that change.

For example:

1. A player has the `Member` role.
2. Badger_Discord_API caches the player's roles.
3. An administrator gives the player `Staff`.
4. A script checks their roles before the cache expires.
5. The previous role list may still be returned.

Account for this when using Discord roles for administrative permissions.

---

## Discord Identifiers

Player-based functions rely on the player's FiveM identifiers.

The resource searches for an identifier beginning with:

```text
discord:
```

For example:

```text
discord:123456789012345678
```

If the player's Discord identifier is unavailable, Discord-specific player lookups cannot retrieve that player's Discord member data.

`GetDiscordRoles` reports failure when Discord is not connected to the user's FiveM account.

---

## API Responses and Errors

The server code contains handling for common Discord HTTP responses.

| Code     | Meaning                                    |
| -------- | ------------------------------------------ |
| `200`    | Request completed successfully             |
| `204`    | Request succeeded with no response content |
| `400`    | Request was invalid or malformed           |
| `401`    | Authorization was missing or invalid       |
| `403`    | Bot does not have permission               |
| `404`    | Discord resource was not found             |
| `429`    | Discord rate limit reached                 |
| `502`    | Discord API may be unavailable             |
| {.dense} |                                            |

### 401

A `401` response commonly points to an invalid bot token or invalid authorization.

Check:

* `Bot_Token`
* Whether the token was regenerated
* Whether the correct bot application is being used

### 403

A `403` response means Discord rejected the operation because the bot does not have sufficient access.

Check:

* Bot permissions
* Discord role hierarchy
* Guild membership
* Whether the bot can manage the target role or member

### 404

A `404` response means the requested resource could not be found.

Check:

* Guild ID
* Member ID
* Role ID
* Voice channel ID
* Whether the bot is in the selected guild

### 429

A `429` response means Discord's rate limit was reached.

Badger_Discord_API uses caching for some frequently requested data to reduce this problem.

Avoid repeatedly polling Discord exports every frame or at very short intervals.

---

## Multi-Guild Support

The current server implementation contains support for multiple Discord guilds.

The primary guild comes from:

```lua
Config.Guild_ID
```

Additional guilds can be referenced through the configured guild table.

When multiguild handling is enabled, `GetDiscordRoles` can combine roles retrieved from multiple configured Discord guilds.

When a specific guild is supplied to a supported function, that guild can be queried instead of combining all configured guilds.

> Check the configuration options included with the exact version you install before enabling multiguild behavior.
> {.is-info}

---

## Security

### Protect the Bot Token

Your Discord bot token authenticates requests made by Badger_Discord_API.

Never expose it.

Recommended handling:

* Keep `config.lua` out of public repositories when it contains the live token
* Replace real tokens with placeholders in examples
* Rotate compromised tokens immediately
* Limit bot permissions to what your server actually needs
* Avoid Administrator permission unless your integration genuinely requires it

### Validate Permission Checks

If another resource uses Discord roles for staff or administrative access, do not assume every API call succeeds.

Check for:

```lua
false
```

and:

```lua
nil
```

before granting access.

A failed Discord request should not accidentally become an authorization success.

### Role Hierarchy

Discord role management follows Discord's role hierarchy.

A bot cannot manage roles positioned above its highest role.

Place the bot's role appropriately if you use role modification functions.

---

## Developer Examples {.tabset}

### Get a Player's Roles

```lua
local roles = exports.Badger_Discord_API:GetDiscordRoles(source)

if not roles then
    print("Discord roles could not be retrieved")
    return
end

for _, roleId in pairs(roles) do
    print(roleId)
end
```

### Resolve a Role Name

```lua
local roleId = exports.Badger_Discord_API:GetRoleIdFromRoleName("Staff")

if roleId then
    print(("Staff role ID: %s"):format(roleId))
end
```

### Check for a Role

```lua
local roles = exports.Badger_Discord_API:GetDiscordRoles(source)
local requiredRole = exports.Badger_Discord_API:GetRoleIdFromRoleName("Staff")

if not roles or not requiredRole then
    return
end

for _, role in pairs(roles) do
    if tostring(role) == tostring(requiredRole) then
        print("Player has the required Discord role")
        break
    end
end
```

### Get Discord Username

```lua
local discordName = exports.Badger_Discord_API:GetDiscordName(source)

if discordName then
    print(discordName)
end
```

### Get Discord Avatar

```lua
local avatar = exports.Badger_Discord_API:GetDiscordAvatar(source)

if avatar then
    print(avatar)
end
```

### Get Guild Information

```lua
local guildName = exports.Badger_Discord_API:GetGuildName()
local memberCount = exports.Badger_Discord_API:GetGuildMemberCount()
local onlineCount = exports.Badger_Discord_API:GetGuildOnlineMemberCount()

print(guildName)
print(memberCount)
print(onlineCount)
```

---

## Common Integration Pattern

Dependent scripts should start after Badger_Discord_API.

```cfg
ensure Badger_Discord_API
ensure YourDiscordResource
```

Your dependent server script can then call:

```lua
local roles = exports.Badger_Discord_API:GetDiscordRoles(source)
```

Do not call the export before `Badger_Discord_API` is started.

Do not rename `Badger_Discord_API` unless you also update every integration that references that resource name.

---

## Troubleshooting {.tabset}

### No Discord Roles Returned

Check:

* The player has a `discord:` FiveM identifier
* `Guild_ID` is correct
* The bot is in the guild
* The bot token is correct
* The bot can access the member
* The resource is named `Badger_Discord_API`
* The Discord API request is not returning an error

### No Such Export

Confirm:

```text
Badger_Discord_API
```

is the exact resource folder name.

Then confirm it starts before the dependent script.

For example:

```cfg
ensure Badger_Discord_API
ensure DiscordChatRoles
```

A historical official GitHub issue for `GetDiscordRoles` was ultimately traced to a syntax error in `config.lua`, so also check your configuration for Lua syntax errors.

### Wrong Role Results

Check whether role caching is enabled.

A recently added or removed Discord role may not be visible until cached role data expires.

Also confirm that:

* You are querying the correct guild
* The role still has the same name
* Your script expects role IDs in the correct format

### Role Name Lookup Stops Working

If your script uses:

```lua
GetRoleIdFromRoleName
```

confirm the Discord role has not been renamed.

Role-name-based integrations depend on the current Discord role name.

### Discord API Permission Errors

A `403` response usually indicates insufficient bot permissions.

Check the bot's permissions and role hierarchy.

### Rate Limit Errors

A `429` response means Discord is rate limiting requests.

Avoid calling Discord API exports continuously.

Use returned data intelligently and allow the built-in caches to reduce repeated calls.

---

## Known Issues

The creator explicitly notes that some API methods may not fully work.

The project states that most functionality was tested, but not every method should be assumed to work in every environment.

Use:

```text
example.lua
```

as an implementation reference.

When an API method appears broken:

* [ ] Check your bot token
* [ ] Check your Guild ID
* [ ] Check Discord permissions
* [ ] Check the resource name
* [ ] Check `config.lua` for syntax errors
* [ ] Check whether the player has a Discord identifier
* [ ] Check the server console for the Discord HTTP response
* [ ] Check the official documentation
* [ ] Check the official GitHub issues
* [ ] Submit an issue or pull request when appropriate

---

## Compatibility

| Component                   | Support                                  |
| --------------------------- | ---------------------------------------- |
| **FiveM**                   | Yes                                      |
| **Discord REST API**        | Yes                                      |
| **Discord Bot**             | Required                                 |
| **Discord Guild**           | Required                                 |
| **Framework Requirement**   | None specified                           |
| **Role Name Lookup**        | Yes                                      |
| **Role ID Lookup**          | Yes                                      |
| **Player Role Lookup**      | Yes                                      |
| **Discord Username Lookup** | Yes                                      |
| **Discord Nickname Lookup** | Yes                                      |
| **Discord Avatar Lookup**   | Yes                                      |
| **Guild Information**       | Yes                                      |
| **Guild Role List**         | Yes                                      |
| **Multiple Guild Handling** | Present in current server implementation |
| **Data Caching**            | Yes                                      |
| {.dense}                    |                                          |

---

## Included Project Files

The official repository includes:

```text
client.lua
config.lua
example.lua
fxmanifest.lua
server.lua
version.txt
versionChecker.lua
```

It also includes the project license and README.

Use `example.lua` when you need implementation examples beyond the API documentation.

---

## Links

* [Official Documentation](https://docs.badger.store/fivem-discord-scripts/badger_discord_api)
* [Official Installation Guide](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/installation-script)
* [Official GitHub Repository](https://github.com/JaredScar/Badger_Discord_API)

### API Documentation

* [GetRoleIdFromRoleName](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getroleidfromrolename)
* [CheckEqual](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/checkequal)
* [IsDiscordEmailVerified](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/isdiscordemailverified)
* [GetDiscordEmail](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getdiscordemail)
* [GetDiscordName](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getdiscordname)
* [GetDiscordAvatar](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getdiscordavatar)
* [GetDiscordNickname](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getdiscordnickname)
* [GetDiscordRoles](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getdiscordroles)
* [GetGuildIcon](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildicon)
* [GetGuildSplash](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildsplash)
* [GetGuildName](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildname)
* [GetGuildDescription](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguilddesc)
* [GetGuildMemberCount](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildmembercount)
* [GetGuildOnlineMemberCount](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildonlinememcount)
* [GetGuildRoleList](https://docs.badger.store/fivem-discord-scripts/badger_discord_api/getguildrolelist)

---

## Before You Install

Create your Discord bot and gather your Guild ID before installing the resource.

Keep the folder name exactly:

```text
Badger_Discord_API
```

Protect your bot token.

Start the API before resources that depend on it.

Check `example.lua` when implementing exports.

Do not assume every Discord operation succeeds. Validate API return values and review server console errors.

---

## Credits

Created by **Badger**.

Project repository maintained under **JaredScar/Badger_Discord_API**, with contributions from project contributors.

SantosDB provides resource information and source references.

Resource rights belong to the project authors and rights holders.
