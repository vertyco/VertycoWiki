---
title: Custom Commands
description: 
published: true
date: 2024-08-25T19:11:24.100Z
tags: 
editor: markdown
dateCreated: 2024-08-25T19:11:22.787Z
---

# CustomCommands Help

This cog contains commands for creating and managing custom commands that display text.<br/><br/>These are useful for storing information members might need, like FAQ answers or invite links.<br/>Custom commands can be used by anyone by default, so be careful with pings.<br/>Commands can only be lowercase, and will not respond to any uppercase letters.

# .customcom
Base command for Custom Commands management.<br/>
 - Usage: `.customcom`
 - Aliases: `cc`
 - Checks: `server_only`
## .customcom raw
Get the raw response of a custom command, to get the proper markdown.<br/>

This is helpful for copy and pasting.<br/>

**Arguments:**<br/>

- `<command>` The custom command to get the raw response of.<br/>
 - Usage: `.customcom raw <command>`
## .customcom search
Searches through custom commands, according to the query.<br/>

Uses fuzzy searching to find close matches.<br/>

**Arguments:**<br/>

- `<query>` The query to search for. Can be multiple words.<br/>
 - Usage: `.customcom search <query>`
 - Checks: `server_only`
## .customcom show
Shows a custom command's responses and its settings.<br/>

**Arguments:**<br/>

- `<command_name>` The custom command to show.<br/>
 - Usage: `.customcom show <command_name>`
## .customcom create
Create custom commands.<br/>

If a type is not specified, a simple CC will be created.<br/>
CCs can be enhanced with arguments, see the guide<br/>
[here](https://docs.discord.red/en/stable/cog_customcom.html).<br/>
 - Usage: `.customcom create <command> <text>`
 - Restricted to: `MOD`
 - Aliases: `add`
### .customcom create random
Create a CC where it will randomly choose a response!<br/>

Note: This command is interactive.<br/>

**Arguments:**<br/>

- `<command>` The command executed to return the text. Cast to lowercase.<br/>
 - Usage: `.customcom create random <command>`
 - Restricted to: `MOD`
### .customcom create simple
Add a simple custom command.<br/>

Example:<br/>
- `.customcom create simple yourcommand Text you want`<br/>

**Arguments:**<br/>

- `<command>` The command executed to return the text. Cast to lowercase.<br/>
- `<text>` The text to return when executing the command. See guide for enhanced usage.<br/>
 - Usage: `.customcom create simple <command> <text>`
 - Restricted to: `MOD`
## .customcom list
List all available custom commands.<br/>

The list displays a preview of each command's response, with<br/>
markdown escaped and newlines replaced with spaces.<br/>
 - Usage: `.customcom list`
 - Checks: `bot_can_react`
## .customcom cooldown
Set, edit, or view the cooldown for a custom command.<br/>

You may set cooldowns per member, channel, or server. Multiple<br/>
cooldowns may be set. All cooldowns must be cooled to call the<br/>
custom command.<br/>

Examples:<br/>
- `.customcom cooldown pingrole`<br/>
- `.customcom cooldown yourcommand 30`<br/>
- `.cc cooldown mycommand 30 server`<br/>

**Arguments:**<br/>

- `<command>` The custom command to check or set the cooldown.<br/>
- `[cooldown]` The number of seconds to wait before allowing the command to be invoked again. If omitted, will instead return the current cooldown settings.<br/>
- `[per]` The group to apply the cooldown on. Defaults to per member. Valid choices are server / server, user / member, and channel.<br/>
 - Usage: `.customcom cooldown <command> [cooldown=None] [per]`
 - Restricted to: `MOD`
## .customcom edit
Edit a custom command.<br/>

Example:<br/>
- `.customcom edit yourcommand Text you want`<br/>

**Arguments:**<br/>

- `<command>` The custom command to edit.<br/>
- `<text>` The new text to return when executing the command.<br/>
 - Usage: `.customcom edit <command> [text]`
 - Restricted to: `MOD`
## .customcom delete
Delete a custom command.<br/>

Example:<br/>
- `.customcom delete yourcommand`<br/>

**Arguments:**<br/>

- `<command>` The custom command to delete.<br/>
 - Usage: `.customcom delete <command>`
 - Restricted to: `MOD`
 - Aliases: `del and remove`
