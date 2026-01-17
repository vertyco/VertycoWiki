---
title: Core Commands
description: 
published: true
date: 2024-08-25T19:10:25.076Z
tags: 
editor: markdown
dateCreated: 2024-08-25T19:10:22.951Z
---

# Core Help

The Core cog has many commands related to core functions.<br/><br/>These commands come loaded with every Red bot, and cover some of the most basic usage of the bot.

# .info
Shows info about Autto.<br/>
 - Usage: `.info`
# .uptime
Shows Autto's uptime.<br/>
 - Usage: `.uptime`
# .mydata
Commands which interact with the data Autto has about you.<br/>

More information can be found in the [End User Data Documentation.](https://docs.discord.red/en/stable/red_core_data_statement.html)<br/>
 - Usage: `.mydata`
## .mydata getmydata
[Coming Soon] Get what data Autto has about you.<br/>
 - Usage: `.mydata getmydata`
 - Cooldown: `1 per 7200.0 seconds`
## .mydata ownermanagement
Commands for more complete data handling.<br/>
 - Usage: `.mydata ownermanagement`
 - Restricted to: `BOT_OWNER`
### .mydata ownermanagement deleteuserasowner
Delete data Autto has about a user.<br/>

This will cause the bot to get rid of or disassociate a lot of data about the specified user.<br/>
This may include more than just end user data, including anti abuse records.<br/>

**Arguments:**<br/>
- `<user_id>` - The id of the user whose data would be deleted.<br/>
 - Usage: `.mydata ownermanagement deleteuserasowner <user_id>`
### .mydata ownermanagement deleteforuser
Delete data Autto has about a user for a user.<br/>

This will cause the bot to get rid of or disassociate a lot of non-operational data from the specified user.<br/>
Users have access to a different command for this unless they can't interact with the bot at all.<br/>
This is a mostly safe operation, but you should not use it unless processing a request from this user as it may impact their usage of the bot.<br/>

**Arguments:**<br/>
- `<user_id>` - The id of the user whose data would be deleted.<br/>
 - Usage: `.mydata ownermanagement deleteforuser <user_id>`
### .mydata ownermanagement allowuserdeletions
Set the bot to allow users to request a data deletion.<br/>

This is on by default.<br/>
Opposite of `.mydata ownermanagement disallowuserdeletions`<br/>

**Example:**<br/>
- `.mydata ownermanagement allowuserdeletions`<br/>
 - Usage: `.mydata ownermanagement allowuserdeletions`
### .mydata ownermanagement processdiscordrequest
Handle a deletion request from Discord.<br/>

This will cause the bot to get rid of or disassociate all data from the specified user ID.<br/>
You should not use this unless Discord has specifically requested this with regard to a deleted user.<br/>
This will remove the user from various anti-abuse measures.<br/>
If you are processing a manual request from a user, you may want `.mydata ownermanagement deleteforuser` instead.<br/>

**Arguments:**<br/>
- `<user_id>` - The id of the user whose data would be deleted.<br/>
 - Usage: `.mydata ownermanagement processdiscordrequest <user_id>`
### .mydata ownermanagement setuserdeletionlevel
Sets how user deletions are treated.<br/>

**Example:**<br/>
- `.mydata ownermanagement setuserdeletionlevel 1`<br/>

**Arguments:**<br/>
- `<level>` - The strictness level for user deletion. See Level guide below.<br/>

Level:<br/>
- `0`: What users can delete is left entirely up to each cog.<br/>
- `1`: Cogs should delete anything the cog doesn't need about the user.<br/>
 - Usage: `.mydata ownermanagement setuserdeletionlevel <level>`
### .mydata ownermanagement disallowuserdeletions
Set the bot to not allow users to request a data deletion.<br/>

Opposite of `.mydata ownermanagement allowuserdeletions`<br/>

**Example:**<br/>
- `.mydata ownermanagement disallowuserdeletions`<br/>
 - Usage: `.mydata ownermanagement disallowuserdeletions`
## .mydata whatdata
Find out what type of data Autto stores and why.<br/>

**Example:**<br/>
- `.mydata whatdata`<br/>
 - Usage: `.mydata whatdata`
 - Cooldown: `1 per 600.0 seconds`
## .mydata 3rdparty
View the End User Data statements of each 3rd-party module.<br/>

This will send an attachment with the End User Data statements of all loaded 3rd party cogs.<br/>

**Example:**<br/>
- `.mydata 3rdparty`<br/>
 - Usage: `.mydata 3rdparty`
 - Cooldown: `1 per 1800.0 seconds`
## .mydata forgetme
Have Autto forget what it knows about you.<br/>

This may not remove all data about you, data needed for operation,<br/>
such as command cooldowns will be kept until no longer necessary.<br/>

Further interactions with Autto may cause it to learn about you again.<br/>

**Example:**<br/>
- `.mydata forgetme`<br/>
 - Usage: `.mydata forgetme`
 - Cooldown: `1 per 86400.0 seconds`
# .embedset
Commands for toggling embeds on or off.<br/>

This setting determines whether or not to use embeds as a response to a command (for commands that support it).<br/>
The default is to use embeds.<br/>

The embed settings are checked until the first True/False in this order:<br/>

- In server context:<br/>
  1. Channel override - `.embedset channel`<br/>
  2. Server command override - `.embedset command server`<br/>
  3. Server override - `.embedset server`<br/>
  4. Global command override - `.embedset command global`<br/>
  5. Global setting  -`.embedset global`<br/>

- In DM context:<br/>
  1. User override - `.embedset user`<br/>
  2. Global command override - `.embedset command global`<br/>
  3. Global setting - `.embedset global`<br/>
 - Usage: `.embedset`
## .embedset command
Sets a command's embed setting.<br/>

If you're the bot owner, this will try to change the command's embed setting globally by default.<br/>
Otherwise, this will try to change embed settings on the current server.<br/>

If enabled is left blank, the setting will be unset.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset command info` - Clears command specific embed settings for 'info'.<br/>
- `.embedset command info False` - Disables embeds for 'info'.<br/>
- `.embedset command "ignore list" True` - Quotes are needed for subcommands.<br/>

**Arguments:**<br/>
- `[enabled]` - Whether to use embeds for this command. Leave blank to reset to default.<br/>
 - Usage: `.embedset command <command> [enabled=None]`
 - Restricted to: `GUILD_OWNER`
### .embedset command global
Sets a command's embed setting globally.<br/>

If set, this is used instead of the global default to determine whether or not to use embeds.<br/>

If enabled is left blank, the setting will be unset.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset command global info` - Clears command specific embed settings for 'info'.<br/>
- `.embedset command global info False` - Disables embeds for 'info'.<br/>
- `.embedset command global "ignore list" True` - Quotes are needed for subcommands.<br/>

**Arguments:**<br/>
- `[enabled]` - Whether to use embeds for this command. Leave blank to reset to default.<br/>
 - Usage: `.embedset command global <command> [enabled=None]`
 - Restricted to: `BOT_OWNER`
### .embedset command server
Sets a command's embed setting for the current server.<br/>

If set, this is used instead of the server default to determine whether or not to use embeds.<br/>

If enabled is left blank, the setting will be unset and the server default will be used instead.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset command server info` - Clears command specific embed settings for 'info'.<br/>
- `.embedset command server info False` - Disables embeds for 'info'.<br/>
- `.embedset command server "ignore list" True` - Quotes are needed for subcommands.<br/>

**Arguments:**<br/>
- `[enabled]` - Whether to use embeds for this command. Leave blank to reset to default.<br/>
 - Usage: `.embedset command server <command> [enabled=None]`
 - Aliases: `server`
 - Checks: `server_only`
## .embedset showsettings
Show the current embed settings.<br/>

Provide a command name to check for command specific embed settings.<br/>

**Examples:**<br/>
- `.embedset showsettings` - Shows embed settings.<br/>
- `.embedset showsettings info` - Also shows embed settings for the 'info' command.<br/>
- `.embedset showsettings "ignore list"` - Checking subcommands requires quotes.<br/>

**Arguments:**<br/>
- `[command]` - Checks this command for command specific embed settings.<br/>
 - Usage: `.embedset showsettings [command=None]`
## .embedset channel
Set's a channel's embed setting.<br/>

If set, this is used instead of the server and command defaults to determine whether or not to use embeds.<br/>
This is used for all commands done in a channel.<br/>

If enabled is left blank, the setting will be unset and the server default will be used instead.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset channel #text-channel False` - Disables embeds in the #text-channel.<br/>
- `.embedset channel #forum-channel disable` - Disables embeds in the #forum-channel.<br/>
- `.embedset channel #text-channel` - Resets value to use server default in the #text-channel.<br/>

**Arguments:**<br/>
    - `<channel>` - The text, voice, stage, or forum channel to set embed setting for.<br/>
    - `[enabled]` - Whether to use embeds in this channel. Leave blank to reset to default.<br/>
 - Usage: `.embedset channel <channel> [enabled=None]`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .embedset user
Sets personal embed setting for DMs.<br/>

If set, this is used instead of the global default to determine whether or not to use embeds.<br/>
This is used for all commands executed in a DM with the bot.<br/>

If enabled is left blank, the setting will be unset and the global default will be used instead.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset user False` - Disables embeds in your DMs.<br/>
- `.embedset user` - Resets value to use global default.<br/>

**Arguments:**<br/>
- `[enabled]` - Whether to use embeds in your DMs. Leave blank to reset to default.<br/>
 - Usage: `.embedset user [enabled=None]`
## .embedset global
Toggle the global embed setting.<br/>

This is used as a fallback if the user or server hasn't set a preference.<br/>
The default is to use embeds.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Example:**<br/>
- `.embedset global`<br/>
 - Usage: `.embedset global`
 - Restricted to: `BOT_OWNER`
## .embedset server
Set the server's embed setting.<br/>

If set, this is used instead of the global default to determine whether or not to use embeds.<br/>
This is used for all commands done in a server.<br/>

If enabled is left blank, the setting will be unset and the global default will be used instead.<br/>

To see full evaluation order of embed settings, run `.help embedset`.<br/>

**Examples:**<br/>
- `.embedset server False` - Disables embeds on this server.<br/>
- `.embedset server` - Resets value to use global default.<br/>

**Arguments:**<br/>
- `[enabled]` - Whether to use embeds on this server. Leave blank to reset to default.<br/>
 - Usage: `.embedset server [enabled=None]`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `server`
 - Checks: `server_only`
# .traceback
Sends to the owner the last command exception that has occurred.<br/>

If public (yes is specified), it will be sent to the chat instead.<br/>

Warning: Sending the traceback publicly can accidentally reveal sensitive information about your computer or configuration.<br/>

**Examples:**<br/>
- `.traceback` - Sends the traceback to your DMs.<br/>
- `.traceback True` - Sends the last traceback in the current context.<br/>

**Arguments:**<br/>
- `[public]` - Whether to send the traceback to the current context. Leave blank to send to your DMs.<br/>
 - Usage: `.traceback [public=False]`
 - Restricted to: `BOT_OWNER`
# .invite
Shows Autto's invite url.<br/>

This will always send the invite to DMs to keep it private.<br/>

This command is locked to the owner unless `.inviteset public` is set to True.<br/>

**Example:**<br/>
- `.invite`<br/>
 - Usage: `.invite`
 - Checks: `CoreLogic`
# .inviteset
Commands to setup Autto's invite settings.<br/>
 - Usage: `.inviteset`
 - Restricted to: `BOT_OWNER`
## .inviteset public
Toggles if `.invite` should be accessible for the average user.<br/>

The bot must be made into a `Public bot` in the developer dashboard for public invites to work.<br/>

**Example:**<br/>
- `.inviteset public yes` - Toggles the public invite setting.<br/>

**Arguments:**<br/>
- `[confirm]` - Required to set to public. Not required to toggle back to private.<br/>
 - Usage: `.inviteset public [confirm=False]`
## .inviteset perms
Make the bot create its own role with permissions on join.<br/>

The bot will create its own role with the desired permissions when it joins a new server. This is a special role that can't be deleted or removed from the bot.<br/>

For that, you need to provide a valid permissions level.<br/>
You can generate one here: https://discordapi.com/permissions.html<br/>

Please note that you might need two factor authentication for some permissions.<br/>

**Example:**<br/>
- `.inviteset perms 134217728` - Adds a "Manage Nicknames" permission requirement to the invite.<br/>

**Arguments:**<br/>
- `<level>` - The permission level to require for the bot in the generated invite.<br/>
 - Usage: `.inviteset perms <level>`
## .inviteset commandscope
Add the `applications.commands` scope to your invite URL.<br/>

This allows the usage of slash commands on the servers that invited your bot with that scope.<br/>

Note that previous servers that invited the bot without the scope cannot have slash commands, they will have to invite the bot a second time.<br/>
 - Usage: `.inviteset commandscope`
# .leave
Leaves servers.<br/>

If no server IDs are passed the local server will be left instead.<br/>

Note: This command is interactive.<br/>

**Examples:**<br/>
- `.leave` - Leave the current server.<br/>
- `.leave "Red - Discord Bot"` - Quotes are necessary when there are spaces in the name.<br/>
- `.leave 133049272517001216 240154543684321280` - Leaves multiple servers, using IDs.<br/>

**Arguments:**<br/>
- `[servers...]` - The servers to leave. When blank, attempts to leave the current server.<br/>
 - Usage: `.leave <servers>`
 - Restricted to: `BOT_OWNER`
# .servers
Lists the servers Autto is currently in.<br/>

Note: This command is interactive.<br/>
 - Usage: `.servers`
 - Restricted to: `BOT_OWNER`
# .load
Loads cog packages from the local paths and installed cogs.<br/>

See packages available to load with `.cogs`.<br/>

Additional cogs can be added using Downloader, or from local paths using `.addpath`.<br/>

**Examples:**<br/>
- `.load general` - Loads the `general` cog.<br/>
- `.load admin mod mutes` - Loads multiple cogs.<br/>

**Arguments:**<br/>
- `<cogs...>` - The cog packages to load.<br/>
 - Usage: `.load <cogs>`
 - Restricted to: `BOT_OWNER`
# .unload
Unloads previously loaded cog packages.<br/>

See packages available to unload with `.cogs`.<br/>

**Examples:**<br/>
- `.unload general` - Unloads the `general` cog.<br/>
- `.unload admin mod mutes` - Unloads multiple cogs.<br/>

**Arguments:**<br/>
- `<cogs...>` - The cog packages to unload.<br/>
 - Usage: `.unload <cogs>`
 - Restricted to: `BOT_OWNER`
# .reload
Reloads cog packages.<br/>

This will unload and then load the specified cogs.<br/>

Cogs that were not loaded will only be loaded.<br/>

**Examples:**<br/>
- `.reload general` - Unloads then loads the `general` cog.<br/>
- `.reload admin mod mutes` - Unloads then loads multiple cogs.<br/>

**Arguments:**<br/>
- `<cogs...>` - The cog packages to reload.<br/>
 - Usage: `.reload <cogs>`
 - Restricted to: `BOT_OWNER`
# .slash
Base command for managing what application commands are able to be used on Autto.<br/>
 - Usage: `.slash`
 - Restricted to: `BOT_OWNER`
## .slash enablecog
Marks all application commands in a cog as being enabled, allowing them to be added to the bot.<br/>

See a list of cogs with application commands with `.slash list`.<br/>

This command does NOT sync the enabled commands with Discord, that must be done manually with `.slash sync` for commands to appear in users' clients.<br/>

**Arguments:**<br/>
    - `<cog_name>` - The cog to enable commands from. This argument is case sensitive.<br/>
 - Usage: `.slash enablecog <cog_name>`
## .slash list
List the slash commands the bot can see, and whether or not they are enabled.<br/>

This command shows the state that will be changed to when `.slash sync` is run.<br/>
Commands from the same cog are grouped, with the cog name as the header.<br/>

The prefix denotes the state of the command:<br/>
- Commands starting with `- ` have not yet been enabled.<br/>
- Commands starting with `+ ` have been manually enabled.<br/>
- Commands starting with `++` have been enabled by the cog author, and cannot be disabled.<br/>
 - Usage: `.slash list`
## .slash sync
Syncs the slash settings to discord.<br/>

Settings from `.slash list` will be synced with discord, changing what commands appear for users.<br/>
This should be run sparingly, make all necessary changes before running this command.<br/>

**Arguments:**<br/>
    - `[server]` - If provided, syncs commands for that server. Otherwise, syncs global commands.<br/>
 - Usage: `.slash sync [server=None]`
 - Cooldown: `1 per 60.0 seconds`
## .slash disablecog
Marks all application commands in a cog as being disabled, preventing them from being added to the bot.<br/>

See a list of cogs with application commands with `.slash list`.<br/>

This command does NOT sync the enabled commands with Discord, that must be done manually with `.slash sync` for commands to appear in users' clients.<br/>

**Arguments:**<br/>
    - `<cog_name>` - The cog to disable commands from. This argument is case sensitive.<br/>
 - Usage: `.slash disablecog <cog_name>`
## .slash disable
Marks an application command as being disabled, preventing it from being added to the bot.<br/>

See commands available to disable with `.slash list`.<br/>

This command does NOT sync the enabled commands with Discord, that must be done manually with `.slash sync` for commands to appear in users' clients.<br/>

**Arguments:**<br/>
    - `<command_name>` - The command name to disable. Only the top level name of a group command should be used.<br/>
    - `[command_type]` - What type of application command to disable. Must be one of `slash`, `message`, or `user`. Defaults to `slash`.<br/>
 - Usage: `.slash disable <command_name> [command_type=slash]`
## .slash enable
Marks an application command as being enabled, allowing it to be added to the bot.<br/>

See commands available to enable with `.slash list`.<br/>

This command does NOT sync the enabled commands with Discord, that must be done manually with `.slash sync` for commands to appear in users' clients.<br/>

**Arguments:**<br/>
    - `<command_name>` - The command name to enable. Only the top level name of a group command should be used.<br/>
    - `[command_type]` - What type of application command to enable. Must be one of `slash`, `message`, or `user`. Defaults to `slash`.<br/>
 - Usage: `.slash enable <command_name> [command_type=slash]`
# .shutdown
Shuts down the bot.<br/>

Allows Autto to shut down gracefully.<br/>

This is the recommended method for shutting down the bot.<br/>

**Examples:**<br/>
- `.shutdown`<br/>
- `.shutdown True` - Shutdowns silently.<br/>

**Arguments:**<br/>
- `[silently]` - Whether to skip sending the shutdown message. Defaults to False.<br/>
 - Usage: `.shutdown [silently=False]`
 - Restricted to: `BOT_OWNER`
# .restart
Attempts to restart Autto.<br/>

Makes Autto quit with exit code 26.<br/>
The restart is not guaranteed: it must be dealt with by the process manager in use.<br/>

**Examples:**<br/>
- `.restart`<br/>
- `.restart True` - Restarts silently.<br/>

**Arguments:**<br/>
- `[silently]` - Whether to skip sending the restart message. Defaults to False.<br/>
 - Usage: `.restart [silently=False]`
 - Restricted to: `BOT_OWNER`
# .bankset
Base command for bank settings.<br/>
 - Usage: `.bankset`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset toggleglobal
Toggle whether the bank is global or not.<br/>

If the bank is global, it will become per-server.<br/>
If the bank is per-server, it will become global.<br/>
 - Usage: `.bankset toggleglobal [confirm=False]`
 - Restricted to: `BOT_OWNER`
## .bankset bankname
Set the bank's name.<br/>
 - Usage: `.bankset bankname <name>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset maxbal
Set the maximum balance a user can get.<br/>
 - Usage: `.bankset maxbal <amount>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset reset
Delete all bank accounts.<br/>

Examples:<br/>
- `.bankset reset` - Did not confirm. Shows the help message.<br/>
- `.bankset reset yes`<br/>

**Arguments**<br/>

- `<confirmation>` This will default to false unless specified.<br/>
 - Usage: `.bankset reset [confirmation=False]`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset registeramount
Set the initial balance for new bank accounts.<br/>

Example:<br/>
- `.bankset registeramount 5000`<br/>

**Arguments**<br/>

- `<creds>` The new initial balance amount. Default is 0.<br/>
 - Usage: `.bankset registeramount <creds>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset prune
Base command for pruning bank accounts.<br/>
 - Usage: `.bankset prune`
 - Restricted to: `ADMIN`
 - Checks: `is_owner_if_bank_global`
### .bankset prune server
Prune bank accounts for users no longer in the server.<br/>

Cannot be used with a global bank. See `.bankset prune global`.<br/>

Examples:<br/>
- `.bankset prune server` - Did not confirm. Shows the help message.<br/>
- `.bankset prune server yes`<br/>

**Arguments**<br/>

- `<confirmation>` This will default to false unless specified.<br/>
 - Usage: `.bankset prune server [confirmation=False]`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `server and local`
 - Checks: `server_only`
### .bankset prune global
Prune bank accounts for users who no longer share a server with the bot.<br/>

Cannot be used without a global bank. See `.bankset prune server`.<br/>

Examples:<br/>
- `.bankset prune global` - Did not confirm. Shows the help message.<br/>
- `.bankset prune global yes`<br/>

**Arguments**<br/>

- `<confirmation>` This will default to false unless specified.<br/>
 - Usage: `.bankset prune global [confirmation=False]`
 - Restricted to: `BOT_OWNER`
### .bankset prune user
Delete the bank account of a specified user.<br/>

Examples:<br/>
- `.bankset prune user @Twentysix` - Did not confirm. Shows the help message.<br/>
- `.bankset prune user @Twentysix yes`<br/>

**Arguments**<br/>

- `<user>` The user to delete the bank of. Takes mentions, names, and user ids.<br/>
- `<confirmation>` This will default to false unless specified.<br/>
 - Usage: `.bankset prune user <member_or_id> [confirmation=False]`
## .bankset creditsname
Set the name for the bank's currency.<br/>
 - Usage: `.bankset creditsname <name>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `is_owner_if_bank_global`
## .bankset showsettings
Show the current bank settings.<br/>
 - Usage: `.bankset showsettings`
# .modlogset
Manage modlog settings.<br/>
 - Usage: `.modlogset`
 - Restricted to: `GUILD_OWNER`
## .modlogset modlog
Set a channel as the modlog.<br/>

Omit `[channel]` to disable the modlog.<br/>
 - Usage: `.modlogset modlog [channel=None]`
 - Aliases: `channel`
 - Checks: `server_only`
## .modlogset cases
Enable or disable case creation for a mod action.<br/>

An action can be enabling or disabling specific cases. (Ban, kick, mute, etc.)<br/>

Example: `.modlogset cases kick enabled`<br/>
 - Usage: `.modlogset cases [action=None]`
 - Checks: `server_only`
## .modlogset resetcases
Reset all modlog cases in this server.<br/>
 - Usage: `.modlogset resetcases`
 - Checks: `server_only`
# .set
Commands for changing Autto's settings.<br/>
 - Usage: `.set`
## .set errormsg
Set the message that will be sent on uncaught bot errors.<br/>

To include the command name in the message, use the `{command}` placeholder.<br/>

If you omit the `msg` argument, the message will be reset to the default one.<br/>

**Examples:**<br/>
    - `.set errormsg` - Resets the error message back to the default: "Error in command '{command}'.". If the command invoker is one of the bot owners, the message will also include "Check your console or logs for details.".<br/>
    - `.set errormsg Oops, the command {command} has failed! Please try again later.` - Sets the error message to a custom one.<br/>

**Arguments:**<br/>
    - `[msg]` - The custom error message. Must be less than 1000 characters. Omit to reset to the default one.<br/>
 - Usage: `.set errormsg [msg]`
 - Restricted to: `BOT_OWNER`
## .set locale
Changes Autto's locale in this server.<br/>

Go to [Red's Crowdin page](https://translate.discord.red) to see locales that are available with translations.<br/>

Use "default" to return to the bot's default set language.<br/>

If you want to change bot's global locale, see `.set locale global` command.<br/>

**Examples:**<br/>
- `.set locale en-US`<br/>
- `.set locale de-DE`<br/>
- `.set locale fr-FR`<br/>
- `.set locale pl-PL`<br/>
- `.set locale default` - Resets to the global default locale.<br/>

**Arguments:**<br/>
- `<language_code>` - The default locale to use for the bot. This can be any language code with country code included.<br/>
 - Usage: `.set locale <language_code>`
 - Restricted to: `GUILD_OWNER`
### .set locale global
Changes Autto's default locale.<br/>

This will be used when a server has not set a locale, or in DMs.<br/>

Go to [Red's Crowdin page](https://translate.discord.red) to see locales that are available with translations.<br/>

To reset to English, use "en-US".<br/>

**Examples:**<br/>
- `.set locale global en-US`<br/>
- `.set locale global de-DE`<br/>
- `.set locale global fr-FR`<br/>
- `.set locale global pl-PL`<br/>

**Arguments:**<br/>
- `<language_code>` - The default locale to use for the bot. This can be any language code with country code included.<br/>
 - Usage: `.set locale global <language_code>`
 - Restricted to: `BOT_OWNER`
### .set locale server
Changes Autto's locale in this server.<br/>

Go to [Red's Crowdin page](https://translate.discord.red) to see locales that are available with translations.<br/>

Use "default" to return to the bot's default set language.<br/>

**Examples:**<br/>
- `.set locale server en-US`<br/>
- `.set locale server de-DE`<br/>
- `.set locale server fr-FR`<br/>
- `.set locale server pl-PL`<br/>
- `.set locale server default` - Resets to the global default locale.<br/>

**Arguments:**<br/>
- `<language_code>` - The default locale to use for the bot. This can be any language code with country code included.<br/>
 - Usage: `.set locale server <language_code>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `local and server`
 - Checks: `server_only`
## .set deletedelay
Set the delay until the bot removes the command message.<br/>

Must be between -1 and 60.<br/>

Set to -1 to disable this feature.<br/>

This is only applied to the current server and not globally.<br/>

**Examples:**<br/>
- `.set deletedelay` - Shows the current delete delay setting.<br/>
- `.set deletedelay 60` - Sets the delete delay to the max of 60 seconds.<br/>
- `.set deletedelay -1` - Disables deleting command messages.<br/>

**Arguments:**<br/>
- `[time]` - The seconds to wait before deleting the command message. Use -1 to disable.<br/>
 - Usage: `.set deletedelay [time=None]`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .set serverfuzzy
Toggle whether to enable fuzzy command search for the server.<br/>

This allows the bot to identify potential misspelled commands and offer corrections.<br/>

Note: This can be processor intensive and may be unsuitable for larger servers.<br/>

Default is for fuzzy command search to be disabled.<br/>

**Example:**<br/>
- `.set serverfuzzy`<br/>
 - Usage: `.set serverfuzzy`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .set fuzzy
Toggle whether to enable fuzzy command search in DMs.<br/>

This allows the bot to identify potential misspelled commands and offer corrections.<br/>

Default is for fuzzy command search to be disabled.<br/>

**Example:**<br/>
- `.set fuzzy`<br/>
 - Usage: `.set fuzzy`
 - Restricted to: `BOT_OWNER`
## .set api
Commands to set, list or remove various external API tokens.<br/>

This setting will be asked for by some 3rd party cogs and some core cogs.<br/>

If passed without the `<service>` or `<tokens>` arguments it will allow you to open a modal to set your API keys securely.<br/>

To add the keys provide the service name and the tokens as a comma separated<br/>
list of key,values as described by the cog requesting this command.<br/>

Note: API tokens are sensitive, so this command should only be used in a private channel or in DM with the bot.<br/>

**Examples:**<br/>
- `.set api`<br/>
- `.set api spotify`<br/>
- `.set api spotify redirect_uri localhost`<br/>
- `.set api github client_id,whoops client_secret,whoops`<br/>

**Arguments:**<br/>
- `<service>` - The service you're adding tokens to.<br/>
- `<tokens>` - Pairs of token keys and values. The key and value should be separated by one of ` `, `,`, or `;`.<br/>
 - Usage: `.set api [service=None] [tokens]`
 - Restricted to: `BOT_OWNER`
### .set api remove
Remove the given services with all their keys and tokens.<br/>

**Examples:**<br/>
- `.set api remove spotify`<br/>
- `.set api remove github youtube`<br/>

**Arguments:**<br/>
- `<services...>` - The services to remove.<br/>
 - Usage: `.set api remove <services>`
### .set api list
Show all external API services along with their keys that have been set.<br/>

Secrets are not shown.<br/>

**Example:**<br/>
- `.set api list`<br/>
 - Usage: `.set api list`
## .set serverprefix
Sets Autto's server prefix(es).<br/>

Warning: This will override global prefixes, the bot will not respond to any global prefixes in this server.<br/>
    This is not additive. It will replace all current server prefixes.<br/>
    A prefix cannot have more than 25 characters.<br/>

**Examples:**<br/>
- `.set serverprefix !`<br/>
- `.set serverprefix "! "` - Quotes are needed to use spaces in prefixes.<br/>
- `.set serverprefix "@Autto "` - This uses a mention as the prefix.<br/>
- `.set serverprefix ! ? .` - Sets multiple prefixes.<br/>
- `.set serverprefix "Red - Discord Bot" ?` - Sets the prefix for a specific server. Quotes are needed to use spaces in the server name.<br/>

**Arguments:**<br/>
- `[server]` - The server to set the prefix for. Defaults to current server.<br/>
- `[prefixes...]` - The prefixes the bot will respond to on this server. Leave blank to clear server prefixes.<br/>
 - Usage: `.set serverprefix <server> <prefixes>`
 - Restricted to: `ADMIN`
 - Aliases: `serverprefixes`
## .set status
Commands for setting Autto's status.<br/>
 - Usage: `.set status`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status online
Set Autto's status to online.<br/>
 - Usage: `.set status online`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status playing
Sets Autto's playing status.<br/>

This will appear as `Playing <game>` or `PLAYING A GAME: <game>` depending on the context.<br/>

Maximum length for a playing status is 128 characters.<br/>

**Examples:**<br/>
- `.set status playing` - Clears the activity status.<br/>
- `.set status playing the keyboard`<br/>

**Arguments:**<br/>
- `[game]` - The text to follow `Playing`. Leave blank to clear the current activity status.<br/>
 - Usage: `.set status playing [game]`
 - Restricted to: `BOT_OWNER`
 - Aliases: `game`
 - Checks: `bot_in_a_server`
### .set status streaming
Sets Autto's streaming status to a twitch stream.<br/>

This will appear as `Streaming <stream_title>` or `LIVE ON TWITCH` depending on the context.<br/>
It will also include a `Watch` button with a twitch.tv url for the provided streamer.<br/>

Maximum length for a stream title is 128 characters.<br/>

Leaving both streamer and stream_title empty will clear it.<br/>

**Examples:**<br/>
- `.set status stream` - Clears the activity status.<br/>
- `.set status stream 26 Twentysix is streaming` - Sets the stream to `https://www.twitch.tv/26`.<br/>
- `.set status stream https://twitch.tv/26 Twentysix is streaming` - Sets the URL manually.<br/>

**Arguments:**<br/>
- `<streamer>` - The twitch streamer to provide a link to. This can be their twitch name or the entire URL.<br/>
- `<stream_title>` - The text to follow `Streaming` in the status.<br/>
 - Usage: `.set status streaming [streamer=None] [stream_title]`
 - Restricted to: `BOT_OWNER`
 - Aliases: `stream and twitch`
 - Checks: `bot_in_a_server`
### .set status custom
Sets Autto's custom status.<br/>

This will appear as `<text>`.<br/>

Maximum length for a custom status is 128 characters.<br/>

**Examples:**<br/>
- `.set status custom` - Clears the activity status.<br/>
- `.set status custom Running cogs...`<br/>

**Arguments:**<br/>
- `[text]` - The custom status text. Leave blank to clear the current activity status.<br/>
 - Usage: `.set status custom [text]`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status dnd
Set Autto's status to do not disturb.<br/>
 - Usage: `.set status dnd`
 - Restricted to: `BOT_OWNER`
 - Aliases: `donotdisturb and busy`
 - Checks: `bot_in_a_server`
### .set status listening
Sets Autto's listening status.<br/>

This will appear as `Listening to <listening>`.<br/>

Maximum length for a listening status is 128 characters.<br/>

**Examples:**<br/>
- `.set status listening` - Clears the activity status.<br/>
- `.set status listening jams`<br/>

**Arguments:**<br/>
- `[listening]` - The text to follow `Listening to`. Leave blank to clear the current activity status.<br/>
 - Usage: `.set status listening [listening]`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status competing
Sets Autto's competing status.<br/>

This will appear as `Competing in <competing>`.<br/>

Maximum length for a competing status is 128 characters.<br/>

**Examples:**<br/>
- `.set status competing` - Clears the activity status.<br/>
- `.set status competing London 2012 Olympic Games`<br/>

**Arguments:**<br/>
- `[competing]` - The text to follow `Competing in`. Leave blank to clear the current activity status.<br/>
 - Usage: `.set status competing [competing]`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status idle
Set Autto's status to idle.<br/>
 - Usage: `.set status idle`
 - Restricted to: `BOT_OWNER`
 - Aliases: `away and afk`
 - Checks: `bot_in_a_server`
### .set status watching
Sets Autto's watching status.<br/>

This will appear as `Watching <watching>`.<br/>

Maximum length for a watching status is 128 characters.<br/>

**Examples:**<br/>
- `.set status watching` - Clears the activity status.<br/>
- `.set status watching .help`<br/>

**Arguments:**<br/>
- `[watching]` - The text to follow `Watching`. Leave blank to clear the current activity status.<br/>
 - Usage: `.set status watching [watching]`
 - Restricted to: `BOT_OWNER`
 - Checks: `bot_in_a_server`
### .set status invisible
Set Autto's status to invisible.<br/>
 - Usage: `.set status invisible`
 - Restricted to: `BOT_OWNER`
 - Aliases: `offline`
 - Checks: `bot_in_a_server`
## .set prefix
Sets Autto's global prefix(es).<br/>

Warning: This is not additive. It will replace all current prefixes.<br/>

See also the `--mentionable` flag to enable mentioning the bot as the prefix.<br/>

**Examples:**<br/>
- `.set prefix !`<br/>
- `.set prefix "! "` - Quotes are needed to use spaces in prefixes.<br/>
- `.set prefix "@Autto "` - This uses a mention as the prefix. See also the `--mentionable` flag.<br/>
- `.set prefix ! ? .` - Sets multiple prefixes.<br/>

**Arguments:**<br/>
- `<prefixes...>` - The prefixes the bot will respond to globally.<br/>
 - Usage: `.set prefix <prefixes>`
 - Restricted to: `BOT_OWNER`
 - Aliases: `prefixes, globalprefix, and globalprefixes`
## .set bot
Commands for changing Autto's metadata.<br/>
 - Usage: `.set bot`
 - Restricted to: `ADMIN`
 - Aliases: `metadata`
### .set bot description
Sets the bot's description.<br/>

Use without a description to reset.<br/>
This is shown in a few locations, including the help menu.<br/>

The maximum description length is 250 characters to ensure it displays properly.<br/>

The default is "Red V3".<br/>

**Examples:**<br/>
- `.set bot description` - Resets the description to the default setting.<br/>
- `.set bot description MyBot: A Red V3 Bot`<br/>

**Arguments:**<br/>
- `[description]` - The description to use for this bot. Leave blank to reset to the default.<br/>
 - Usage: `.set bot description [description]`
 - Restricted to: `BOT_OWNER`
### .set bot avatar
Sets Autto's avatar<br/>

Supports either an attachment or an image URL.<br/>

**Examples:**<br/>
- `.set bot avatar` - With an image attachment, this will set the avatar.<br/>
- `.set bot avatar` - Without an attachment, this will show the command help.<br/>
- `.set bot avatar https://avatars.githubusercontent.com/u/23690422` - Sets the avatar to the provided url.<br/>

**Arguments:**<br/>
- `[url]` - An image url to be used as an avatar. Leave blank when uploading an attachment.<br/>
 - Usage: `.set bot avatar [url=None]`
 - Restricted to: `BOT_OWNER`
#### .set bot avatar remove
Removes Autto's avatar.<br/>

**Example:**<br/>
- `.set bot avatar remove`<br/>
 - Usage: `.set bot avatar remove`
 - Restricted to: `BOT_OWNER`
 - Aliases: `clear`
### .set bot custominfo
Customizes a section of `.info`.<br/>

The maximum amount of allowed characters is 1024.<br/>
Supports markdown, links and "mentions".<br/>

Link example: `[My link](https://example.com)`<br/>

**Examples:**<br/>
- `.set bot custominfo >>> I can use **markdown** such as quotes, ||spoilers|| and multiple lines.`<br/>
- `.set bot custominfo Join my [support server](discord.gg/discord)!`<br/>
- `.set bot custominfo` - Removes custom info text.<br/>

**Arguments:**<br/>
- `[text]` - The custom info text.<br/>
 - Usage: `.set bot custominfo [text]`
 - Restricted to: `BOT_OWNER`
### .set bot username
Sets Autto's username.<br/>

Maximum length for a username is 32 characters.<br/>

Note: The username of a verified bot cannot be manually changed.<br/>
    Please contact Discord support to change it.<br/>

**Example:**<br/>
- `.set bot username BaguetteBot`<br/>

**Arguments:**<br/>
- `<username>` - The username to give the bot.<br/>
 - Usage: `.set bot username <username>`
 - Restricted to: `BOT_OWNER`
 - Aliases: `name`
### .set bot nickname
Sets Autto's nickname for the current server.<br/>

Maximum length for a nickname is 32 characters.<br/>

**Example:**<br/>
- `.set bot nickname 🎃 SpookyBot 🎃`<br/>

**Arguments:**<br/>
- `[nickname]` - The nickname to give the bot. Leave blank to clear the current nickname.<br/>
 - Usage: `.set bot nickname [nickname]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
### .set bot banner
Sets Autto's banner<br/>

Supports either an attachment or an image URL.<br/>

**Examples:**<br/>
- `.set bot banner` - With an image attachment, this will set the banner.<br/>
- `.set bot banner` - Without an attachment, this will show the command help.<br/>
- `.set bot banner https://opengraph.githubassets.com` - Sets the banner to the provided url.<br/>

**Arguments:**<br/>
- `[url]` - An image url to be used as an banner. Leave blank when uploading an attachment.<br/>
 - Usage: `.set bot banner [url=None]`
 - Restricted to: `BOT_OWNER`
#### .set bot banner remove
Removes Autto's banner.<br/>

**Example:**<br/>
- `.set bot banner remove`<br/>
 - Usage: `.set bot banner remove`
 - Restricted to: `BOT_OWNER`
 - Aliases: `clear`
## .set showsettings
Show the current settings for Autto.<br/>

Accepts optional server parameter to allow prefix recovery.<br/>
 - Usage: `.set showsettings [server=None]`
## .set usebuttons
Set a global bot variable for using buttons in menus.<br/>

When enabled, all usage of cores menus API will use buttons instead of reactions.<br/>

This defaults to False.<br/>
Using this without a setting will toggle.<br/>

**Examples:**<br/>
    - `.set usebuttons True` - Enables using buttons.<br/>
    - `.helpset usebuttons` - Toggles the value.<br/>

**Arguments:**<br/>
    - `[use_buttons]` - Whether to use buttons. Leave blank to toggle.<br/>
 - Usage: `.set usebuttons [use_buttons=None]`
 - Restricted to: `BOT_OWNER`
## .set regionalformat
Changes the bot's regional format in this server. This is used for formatting date, time and numbers.<br/>

`language_code` can be any language code with country code included, e.g. `en-US`, `de-DE`, `fr-FR`, `pl-PL`, etc.<br/>
Pass "reset" to `language_code` to base regional formatting on bot's locale in this server.<br/>

If you want to change bot's global regional format, see `.set regionalformat global` command.<br/>

**Examples:**<br/>
- `.set regionalformat en-US`<br/>
- `.set region de-DE`<br/>
- `.set regionalformat reset` - Resets to the locale.<br/>

**Arguments:**<br/>
- `[language_code]` - The region format to use for the bot in this server.<br/>
 - Usage: `.set regionalformat <language_code>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `region`
### .set regionalformat server
Changes the bot's regional format in this server. This is used for formatting date, time and numbers.<br/>

`language_code` can be any language code with country code included, e.g. `en-US`, `de-DE`, `fr-FR`, `pl-PL`, etc.<br/>
Pass "reset" to `language_code` to base regional formatting on bot's locale in this server.<br/>

**Examples:**<br/>
- `.set regionalformat server en-US`<br/>
- `.set region local de-DE`<br/>
- `.set regionalformat server reset` - Resets to the locale.<br/>

**Arguments:**<br/>
- `[language_code]` - The region format to use for the bot in this server.<br/>
 - Usage: `.set regionalformat server <language_code>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `local and server`
 - Checks: `server_only`
### .set regionalformat global
Changes the bot's regional format. This is used for formatting date, time and numbers.<br/>

`language_code` can be any language code with country code included, e.g. `en-US`, `de-DE`, `fr-FR`, `pl-PL`, etc.<br/>
Pass "reset" to `language_code` to base regional formatting on bot's locale.<br/>

**Examples:**<br/>
- `.set regionalformat global en-US`<br/>
- `.set region global de-DE`<br/>
- `.set regionalformat global reset` - Resets to the locale.<br/>

**Arguments:**<br/>
- `[language_code]` - The default region format to use for the bot.<br/>
 - Usage: `.set regionalformat global <language_code>`
 - Restricted to: `BOT_OWNER`
## .set usebotcolour
Toggle whether to use the bot owner-configured colour for embeds.<br/>

Default is to use the bot's configured colour.<br/>
Otherwise, the colour used will be the colour of the bot's top role.<br/>

**Example:**<br/>
- `.set usebotcolour`<br/>
 - Usage: `.set usebotcolour`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `usebotcolor`
 - Checks: `server_only`
## .set colour
Sets a default colour to be used for the bot's embeds.<br/>

Acceptable values for the colour parameter can be found at:<br/>

https://discordpy.readthedocs.io/en/stable/ext/commands/api.html#discord.ext.commands.ColourConverter<br/>

**Examples:**<br/>
- `.set colour dark red`<br/>
- `.set colour blurple`<br/>
- `.set colour 0x5DADE2`<br/>
- `.set color 0x#FDFEFE`<br/>
- `.set color #7F8C8D`<br/>

**Arguments:**<br/>
- `[colour]` - The colour to use for embeds. Leave blank to set to the default value (red).<br/>
 - Usage: `.set colour [colour]`
 - Restricted to: `BOT_OWNER`
 - Aliases: `color`
## .set ownernotifications
Commands for configuring owner notifications.<br/>

Owner notifications include usage of `.contact` and available Red updates.<br/>
 - Usage: `.set ownernotifications`
 - Restricted to: `BOT_OWNER`
### .set ownernotifications optout
Opt-out of receiving owner notifications.<br/>

Note: This will only stop sending owner notifications to your DMs.<br/>
    Additional owners and destinations will still receive notifications.<br/>

**Example:**<br/>
- `.set ownernotifications optout`<br/>
 - Usage: `.set ownernotifications optout`
### .set ownernotifications removedestination
Removes a destination text channel from receiving owner notifications.<br/>

**Examples:**<br/>
- `.set ownernotifications removedestination #owner-notifications`<br/>
- `.set ownernotifications deletedestination 168091848718417920` - Accepts channel IDs.<br/>

**Arguments:**<br/>
- `<channel>` - The channel to stop sending owner notifications to.<br/>
 - Usage: `.set ownernotifications removedestination <channel>`
 - Aliases: `remdestination, deletedestination, and deldestination`
### .set ownernotifications optin
Opt-in on receiving owner notifications.<br/>

This is the default state.<br/>

Note: This will only resume sending owner notifications to your DMs.<br/>
    Additional owners and destinations will not be affected.<br/>

**Example:**<br/>
- `.set ownernotifications optin`<br/>
 - Usage: `.set ownernotifications optin`
### .set ownernotifications adddestination
Adds a destination text channel to receive owner notifications.<br/>

**Examples:**<br/>
- `.set ownernotifications adddestination #owner-notifications`<br/>
- `.set ownernotifications adddestination 168091848718417920` - Accepts channel IDs.<br/>

**Arguments:**<br/>
- `<channel>` - The channel to send owner notifications to.<br/>
 - Usage: `.set ownernotifications adddestination <channel>`
### .set ownernotifications listdestinations
Lists the configured extra destinations for owner notifications.<br/>

**Example:**<br/>
- `.set ownernotifications listdestinations`<br/>
 - Usage: `.set ownernotifications listdestinations`
## .set roles
Set server's admin and mod roles for Autto.<br/>
 - Usage: `.set roles`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
### .set roles addadminrole
Adds an admin role for this server.<br/>

Admins have the same access as Mods, plus additional admin level commands like:<br/>
 - `.set serverprefix`<br/>
 - `.addrole`<br/>
 - `.ban`<br/>
 - `.ignore server`<br/>

 And more.<br/>

**Examples:**<br/>
- `.set roles addadminrole @Admins`<br/>
- `.set roles addadminrole Super Admins`<br/>

**Arguments:**<br/>
- `<role>` - The role to add as an admin.<br/>
 - Usage: `.set roles addadminrole <role>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
### .set roles addmodrole
Adds a moderator role for this server.<br/>

This grants access to moderator level commands like:<br/>
 - `.mute`<br/>
 - `.cleanup`<br/>
 - `.customcommand create`<br/>

 And more.<br/>

**Examples:**<br/>
- `.set roles addmodrole @Mods`<br/>
- `.set roles addmodrole Loyal Helpers`<br/>

**Arguments:**<br/>
- `<role>` - The role to add as a moderator.<br/>
 - Usage: `.set roles addmodrole <role>`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
### .set roles removeadminrole
Removes an admin role for this server.<br/>

**Examples:**<br/>
- `.set roles removeadminrole @Admins`<br/>
- `.set roles removeadminrole Super Admins`<br/>

**Arguments:**<br/>
- `<role>` - The role to remove from being an admin.<br/>
 - Usage: `.set roles removeadminrole <role>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `remadmindrole, deladminrole, and deleteadminrole`
 - Checks: `server_only`
### .set roles removemodrole
Removes a mod role for this server.<br/>

**Examples:**<br/>
- `.set roles removemodrole @Mods`<br/>
- `.set roles removemodrole Loyal Helpers`<br/>

**Arguments:**<br/>
- `<role>` - The role to remove from being a moderator.<br/>
 - Usage: `.set roles removemodrole <role>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `remmodrole, delmodrole, and deletemodrole`
 - Checks: `server_only`
# .helpset
Commands to manage settings for the help command.<br/>

All help settings are applied globally.<br/>
 - Usage: `.helpset`
 - Restricted to: `BOT_OWNER`
## .helpset resetformatter
This resets Autto's help formatter to the default formatter.<br/>

**Example:**<br/>
- `.helpset resetformatter`<br/>
 - Usage: `.helpset resetformatter`
## .helpset verifychecks
Sets if commands which can't be run in the current context should be filtered from help.<br/>

Defaults to True.<br/>
Using this without a setting will toggle.<br/>

**Examples:**<br/>
- `.helpset verifychecks False` - Enables showing unusable commands in help.<br/>
- `.helpset verifychecks` - Toggles the value.<br/>

**Arguments:**<br/>
- `[verify]` - Whether to hide unusable commands in help. Leave blank to toggle.<br/>
 - Usage: `.helpset verifychecks [verify=None]`
## .helpset verifyexists
Sets whether the bot should respond to help commands for nonexistent topics.<br/>

When enabled, this will indicate the existence of help topics, even if the user can't use it.<br/>

Note: This setting on its own does not fully prevent command enumeration.<br/>

Defaults to False.<br/>
Using this without a setting will toggle.<br/>

**Examples:**<br/>
- `.helpset verifyexists True` - Enables sending help for nonexistent topics.<br/>
- `.helpset verifyexists` - Toggles the value.<br/>

**Arguments:**<br/>
- `[verify]` - Whether to respond to help for nonexistent topics. Leave blank to toggle.<br/>
 - Usage: `.helpset verifyexists [verify=None]`
## .helpset usetick
This allows the help command message to be ticked if help is sent to a DM.<br/>

Ticking is reacting to the help message with a ✅.<br/>

Defaults to False.<br/>
Using this without a setting will toggle.<br/>

Note: This is only used when the bot is not using menus.<br/>

**Examples:**<br/>
- `.helpset usetick False` - Disables ticking when help is sent to DMs.<br/>
- `.helpset usetick` - Toggles the value.<br/>

**Arguments:**<br/>
- `[use_tick]` - Whether to tick the help command when help is sent to DMs. Leave blank to toggle.<br/>
 - Usage: `.helpset usetick [use_tick=None]`
## .helpset showhidden
This allows the help command to show hidden commands.<br/>

This defaults to False.<br/>
Using this without a setting will toggle.<br/>

**Examples:**<br/>
- `.helpset showhidden True` - Enables showing hidden commands.<br/>
- `.helpset showhidden` - Toggles the value.<br/>

**Arguments:**<br/>
- `[show_hidden]` - Whether to use show hidden commands in help. Leave blank to toggle.<br/>
 - Usage: `.helpset showhidden [show_hidden=None]`
## .helpset showsettings
Show the current help settings.<br/>

Warning: These settings may not be accurate if the default formatter is not in use.<br/>

**Example:**<br/>
- `.helpset showsettings`<br/>
 - Usage: `.helpset showsettings`
## .helpset showaliases
This allows the help command to show existing commands aliases if there is any.<br/>

This defaults to True.<br/>
Using this without a setting will toggle.<br/>

**Examples:**<br/>
- `.helpset showaliases False` - Disables showing aliases on this server.<br/>
- `.helpset showaliases` - Toggles the value.<br/>

**Arguments:**<br/>
- `[show_aliases]` - Whether to include aliases in help. Leave blank to toggle.<br/>
 - Usage: `.helpset showaliases [show_aliases=None]`
## .helpset usemenus
Allows the help command to be sent as a paginated menu instead of separate<br/>
messages.<br/>

When "reactions", "buttons", "select", or "selectonly" is passed,<br/>
 `.help` will only show one page at a time<br/>
and will use the associated control scheme to navigate between pages.<br/>

 **Examples:**<br/>
- `.helpset usemenus reactions` - Enables using reaction menus.<br/>
- `.helpset usemenus buttons` - Enables using button menus.<br/>
- `.helpset usemenus select` - Enables buttons with a select menu.<br/>
- `.helpset usemenus selectonly` - Enables a select menu only on help.<br/>
- `.helpset usemenus disable` - Disables help menus.<br/>

**Arguments:**<br/>
    - `<"buttons"|"reactions"|"select"|"selectonly"|"disable">` - Whether to use `buttons`,<br/>
    `reactions`, `select`, `selectonly`, or no menus.<br/>
 - Usage: `.helpset usemenus <use_menus>`
## .helpset reacttimeout
Set the timeout for reactions, if menus are enabled.<br/>

The default is 30 seconds.<br/>
The timeout has to be between 15 and 300 seconds.<br/>

**Examples:**<br/>
- `.helpset reacttimeout 30` - The default timeout.<br/>
- `.helpset reacttimeout 60` - Timeout of 1 minute.<br/>
- `.helpset reacttimeout 15` - Minimum allowed timeout.<br/>
- `.helpset reacttimeout 300` - Max allowed timeout (5 mins).<br/>

**Arguments:**<br/>
- `<seconds>` - The timeout, in seconds, of the reactions.<br/>
 - Usage: `.helpset reacttimeout <seconds>`
## .helpset resetsettings
This resets Autto's help settings to their defaults.<br/>

This may not have an impact when using custom formatters from 3rd party cogs<br/>

**Example:**<br/>
- `.helpset resetsettings`<br/>
 - Usage: `.helpset resetsettings`
## .helpset deletedelay
Set the delay after which help pages will be deleted.<br/>

The setting is disabled by default, and only applies to non-menu help,<br/>
sent in server text channels.<br/>
Setting the delay to 0 disables this feature.<br/>

The bot has to have MANAGE_MESSAGES permission for this to work.<br/>

**Examples:**<br/>
- `.helpset deletedelay 60` - Delete the help pages after a minute.<br/>
- `.helpset deletedelay 1` - Delete the help pages as quickly as possible.<br/>
- `.helpset deletedelay 1209600` - Max time to wait before deleting (14 days).<br/>
- `.helpset deletedelay 0` - Disable deleting help pages.<br/>

**Arguments:**<br/>
- `<seconds>` - The seconds to wait before deleting help pages.<br/>
 - Usage: `.helpset deletedelay <seconds>`
## .helpset tagline
Set the tagline to be used.<br/>

The maximum tagline length is 2048 characters.<br/>
This setting only applies to embedded help. If no tagline is specified, the default will be used instead.<br/>

You can use `[​p]` in your tagline, which will be replaced by the bot's prefix.<br/>

**Examples:**<br/>
- `.helpset tagline Thanks for using the bot!`<br/>
- `.helpset tagline Use [​p]invite to add me to your server.`<br/>
- `.helpset tagline` - Resets the tagline to the default.<br/>

**Arguments:**<br/>
- `[tagline]` - The tagline to appear at the bottom of help embeds. Leave blank to reset.<br/>
 - Usage: `.helpset tagline [tagline]`
## .helpset maxpages
Set the maximum number of help pages sent in a server channel.<br/>

If a help message contains more pages than this value, the help message will<br/>
be sent to the command author via DM. This is to help reduce spam in server<br/>
text channels.<br/>

The default value is 2 pages.<br/>

**Examples:**<br/>
- `.helpset maxpages 50` - Basically never send help to DMs.<br/>
- `.helpset maxpages 0` - Always send help to DMs.<br/>

**Arguments:**<br/>
- `<limit>` - The max pages allowed to send per help in a server.<br/>
 - Usage: `.helpset maxpages <pages>`
## .helpset pagecharlimit
Set the character limit for each page in the help message.<br/>

Note: This setting only applies to embedded help.<br/>

The default value is 1000 characters. The minimum value is 500.<br/>
The maximum is based on the lower of what you provide and what discord allows.<br/>

Please note that setting a relatively small character limit may<br/>
mean some pages will exceed this limit.<br/>

**Example:**<br/>
- `.helpset pagecharlimit 1500`<br/>

**Arguments:**<br/>
- `<limit>` - The max amount of characters to show per page in the help message.<br/>
 - Usage: `.helpset pagecharlimit <limit>`
# .contact
Sends a message to the owner.<br/>

This is limited to one message every 60 seconds per person.<br/>

**Example:**<br/>
- `.contact Help! The bot has become sentient!`<br/>

**Arguments:**<br/>
- `[message]` - The message to send to the owner.<br/>
 - Usage: `.contact <message>`
 - Cooldown: `1 per 60.0 seconds`
# .dm
Sends a DM to a user.<br/>

This command needs a user ID to work.<br/>

To get a user ID, go to Discord's settings and open the 'Appearance' tab.<br/>
Enable 'Developer Mode', then right click a user and click on 'Copy ID'.<br/>

**Example:**<br/>
- `.dm 262626262626262626 Do you like me? Yes / No`<br/>

**Arguments:**<br/>
- `[message]` - The message to dm to the user.<br/>
 - Usage: `.dm <user_id> <message>`
 - Restricted to: `BOT_OWNER`
# .diagnoseissues
Diagnose issues with the command checks with ease!<br/>

If you want to diagnose the command from a text channel in a different server,<br/>
you can do so by using the command in DMs.<br/>

**Example:**<br/>
- `.diagnoseissues #general @Slime ban` - Diagnose why @Slime can't use `.ban` in #general channel.<br/>

**Arguments:**<br/>
- `[channel]` - The text channel that the command should be tested for. Defaults to the current channel.<br/>
- `<member>` - The member that should be considered as the command caller.<br/>
- `<command_name>` - The name of the command to test.<br/>
 - Usage: `.diagnoseissues [channel=operator.attrgetter('channel')] <member> <command_name>`
 - Restricted to: `BOT_OWNER`
# .allowlist
Commands to manage the allowlist.<br/>

Warning: When the allowlist is in use, the bot will ignore commands from everyone not on the list.<br/>

Use `.allowlist clear` to disable the allowlist<br/>
 - Usage: `.allowlist`
 - Restricted to: `BOT_OWNER`
 - Aliases: `whitelist`
## .allowlist add
Adds users to the allowlist.<br/>

**Examples:**<br/>
- `.allowlist add @26 @Will` - Adds two users to the allowlist.<br/>
- `.allowlist add 262626262626262626` - Adds a user by ID.<br/>

**Arguments:**<br/>
- `<users...>` - The user or users to add to the allowlist.<br/>
 - Usage: `.allowlist add <users>`
## .allowlist remove
Removes users from the allowlist.<br/>

The allowlist will be disabled if all users are removed.<br/>

**Examples:**<br/>
- `.allowlist remove @26 @Will` - Removes two users from the allowlist.<br/>
- `.allowlist remove 262626262626262626` - Removes a user by ID.<br/>

**Arguments:**<br/>
- `<users...>` - The user or users to remove from the allowlist.<br/>
 - Usage: `.allowlist remove <users>`
## .allowlist clear
Clears the allowlist.<br/>

This disables the allowlist.<br/>

**Example:**<br/>
- `.allowlist clear`<br/>
 - Usage: `.allowlist clear`
## .allowlist list
Lists users on the allowlist.<br/>

**Example:**<br/>
- `.allowlist list`<br/>
 - Usage: `.allowlist list`
# .blocklist
Commands to manage the blocklist.<br/>

Use `.blocklist clear` to disable the blocklist<br/>
 - Usage: `.blocklist`
 - Restricted to: `BOT_OWNER`
 - Aliases: `blacklist and denylist`
## .blocklist add
Adds users to the blocklist.<br/>

**Examples:**<br/>
- `.blocklist add @26 @Will` - Adds two users to the blocklist.<br/>
- `.blocklist add 262626262626262626` - Blocks a user by ID.<br/>

**Arguments:**<br/>
- `<users...>` - The user or users to add to the blocklist.<br/>
 - Usage: `.blocklist add <users>`
## .blocklist remove
Removes users from the blocklist.<br/>

**Examples:**<br/>
- `.blocklist remove @26 @Will` - Removes two users from the blocklist.<br/>
- `.blocklist remove 262626262626262626` - Removes a user by ID.<br/>

**Arguments:**<br/>
- `<users...>` - The user or users to remove from the blocklist.<br/>
 - Usage: `.blocklist remove <users>`
## .blocklist list
Lists users on the blocklist.<br/>

**Example:**<br/>
- `.blocklist list`<br/>
 - Usage: `.blocklist list`
## .blocklist clear
Clears the blocklist.<br/>

**Example:**<br/>
- `.blocklist clear`<br/>
 - Usage: `.blocklist clear`
# .localallowlist
Commands to manage the server specific allowlist.<br/>

Warning: When the allowlist is in use, the bot will ignore commands from everyone not on the list in the server.<br/>

Use `.localallowlist clear` to disable the allowlist<br/>
 - Usage: `.localallowlist`
 - Restricted to: `ADMIN`
 - Aliases: `localwhitelist`
 - Checks: `server_only`
## .localallowlist list
Lists users and roles on the server allowlist.<br/>

**Example:**<br/>
- `.localallowlist list`<br/>
 - Usage: `.localallowlist list`
## .localallowlist clear
Clears the allowlist.<br/>

This disables the local allowlist and clears all entries.<br/>

**Example:**<br/>
- `.localallowlist clear`<br/>
 - Usage: `.localallowlist clear`
## .localallowlist add
Adds a user or role to the server allowlist.<br/>

**Examples:**<br/>
- `.localallowlist add @26 @Will` - Adds two users to the local allowlist.<br/>
- `.localallowlist add 262626262626262626` - Allows a user by ID.<br/>
- `.localallowlist add "Super Admins"` - Allows a role with a space in the name without mentioning.<br/>

**Arguments:**<br/>
- `<users_or_roles...>` - The users or roles to remove from the local allowlist.<br/>
 - Usage: `.localallowlist add <users_or_roles>`
## .localallowlist remove
Removes user or role from the allowlist.<br/>

The local allowlist will be disabled if all users are removed.<br/>

**Examples:**<br/>
- `.localallowlist remove @26 @Will` - Removes two users from the local allowlist.<br/>
- `.localallowlist remove 262626262626262626` - Removes a user by ID.<br/>
- `.localallowlist remove "Super Admins"` - Removes a role with a space in the name without mentioning.<br/>

**Arguments:**<br/>
- `<users_or_roles...>` - The users or roles to remove from the local allowlist.<br/>
 - Usage: `.localallowlist remove <users_or_roles>`
# .localblocklist
Commands to manage the server specific blocklist.<br/>

Use `.localblocklist clear` to disable the blocklist<br/>
 - Usage: `.localblocklist`
 - Restricted to: `ADMIN`
 - Aliases: `localblacklist`
 - Checks: `server_only`
## .localblocklist remove
Removes user or role from local blocklist.<br/>

**Examples:**<br/>
- `.localblocklist remove @26 @Will` - Removes two users from the local blocklist.<br/>
- `.localblocklist remove 262626262626262626` - Unblocks a user by ID.<br/>
- `.localblocklist remove "Bad Apples"` - Unblocks a role with a space in the name without mentioning.<br/>

**Arguments:**<br/>
- `<users_or_roles...>` - The users or roles to remove from the local blocklist.<br/>
 - Usage: `.localblocklist remove <users_or_roles>`
## .localblocklist list
Lists users and roles on the server blocklist.<br/>

**Example:**<br/>
- `.localblocklist list`<br/>
 - Usage: `.localblocklist list`
## .localblocklist clear
Clears the server blocklist.<br/>

This disables the server blocklist and clears all entries.<br/>

**Example:**<br/>
- `.blocklist clear`<br/>
 - Usage: `.localblocklist clear`
## .localblocklist add
Adds a user or role to the local blocklist.<br/>

**Examples:**<br/>
- `.localblocklist add @26 @Will` - Adds two users to the local blocklist.<br/>
- `.localblocklist add 262626262626262626` - Blocks a user by ID.<br/>
- `.localblocklist add "Bad Apples"` - Blocks a role with a space in the name without mentioning.<br/>

**Arguments:**<br/>
- `<users_or_roles...>` - The users or roles to add to the local blocklist.<br/>
 - Usage: `.localblocklist add <users_or_roles>`
# .command
Commands to enable and disable commands and cogs.<br/>
 - Usage: `.command`
 - Restricted to: `GUILD_OWNER`
## .command disabledmsg
Set the bot's response to disabled commands.<br/>

Leave blank to send nothing.<br/>

To include the command name in the message, include the `{command}` placeholder.<br/>

**Examples:**<br/>
- `.command disabledmsg This command is disabled`<br/>
- `.command disabledmsg {command} is disabled`<br/>
- `.command disabledmsg` - Sends nothing when a disabled command is attempted.<br/>

**Arguments:**<br/>
- `[message]` - The message to send when a disabled command is attempted.<br/>
 - Usage: `.command disabledmsg [message]`
 - Restricted to: `BOT_OWNER`
## .command listdisabledcogs
List the cogs which are disabled in this server.<br/>

**Example:**<br/>
- `.command listdisabledcogs`<br/>
 - Usage: `.command listdisabledcogs`
 - Checks: `server_only`
## .command disablecog
Disable a cog in this server.<br/>

Note: This will only work on loaded cogs, and must reference the title-case cog name.<br/>

**Examples:**<br/>
- `.command disablecog Economy`<br/>
- `.command disablecog ModLog`<br/>

**Arguments:**<br/>
- `<cog>` - The name of the cog to disable on this server. Must be title-case.<br/>
 - Usage: `.command disablecog <cog>`
 - Checks: `server_only`
## .command listdisabled
List disabled commands.<br/>

If you're the bot owner, this will show global disabled commands by default.<br/>
Otherwise, this will show disabled commands on the current server.<br/>

**Example:**<br/>
- `.command listdisabled`<br/>
 - Usage: `.command listdisabled`
### .command listdisabled global
List disabled commands globally.<br/>

**Example:**<br/>
- `.command listdisabled global`<br/>
 - Usage: `.command listdisabled global`
### .command listdisabled server
List disabled commands in this server.<br/>

**Example:**<br/>
- `.command listdisabled server`<br/>
 - Usage: `.command listdisabled server`
 - Checks: `server_only`
## .command disable
Disable a command.<br/>

If you're the bot owner, this will disable commands globally by default.<br/>
Otherwise, this will disable commands on the current server.<br/>

**Examples:**<br/>
- `.command disable userinfo` - Disables the `userinfo` command in the Mod cog.<br/>
- `.command disable urban` - Disables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to disable.<br/>
 - Usage: `.command disable <command>`
### .command disable global
Disable a command globally.<br/>

**Examples:**<br/>
- `.command disable global userinfo` - Disables the `userinfo` command in the Mod cog.<br/>
- `.command disable global urban` - Disables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to disable globally.<br/>
 - Usage: `.command disable global <command>`
 - Restricted to: `BOT_OWNER`
### .command disable server
Disable a command in this server only.<br/>

**Examples:**<br/>
- `.command disable server userinfo` - Disables the `userinfo` command in the Mod cog.<br/>
- `.command disable server urban` - Disables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to disable for the current server.<br/>
 - Usage: `.command disable server <command>`
 - Aliases: `server`
 - Checks: `server_only`
## .command defaultenablecog
Set the default state for a cog as enabled.<br/>

This will re-enable the cog for all servers by default.<br/>
To override it, use `.command disablecog` on the servers you want to disallow usage.<br/>

Note: This will only work on loaded cogs, and must reference the title-case cog name.<br/>

**Examples:**<br/>
- `.command defaultenablecog Economy`<br/>
- `.command defaultenablecog ModLog`<br/>

**Arguments:**<br/>
- `<cog>` - The name of the cog to make enabled by default. Must be title-case.<br/>
 - Usage: `.command defaultenablecog <cog>`
 - Restricted to: `BOT_OWNER`
## .command enablecog
Enable a cog in this server.<br/>

Note: This will only work on loaded cogs, and must reference the title-case cog name.<br/>

**Examples:**<br/>
- `.command enablecog Economy`<br/>
- `.command enablecog ModLog`<br/>

**Arguments:**<br/>
- `<cog>` - The name of the cog to enable on this server. Must be title-case.<br/>
 - Usage: `.command enablecog <cogname>`
 - Checks: `server_only`
## .command enable
Enable a command.<br/>

If you're the bot owner, this will try to enable a globally disabled command by default.<br/>
Otherwise, this will try to enable a command disabled on the current server.<br/>

**Examples:**<br/>
- `.command enable userinfo` - Enables the `userinfo` command in the Mod cog.<br/>
- `.command enable urban` - Enables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to enable.<br/>
 - Usage: `.command enable <command>`
### .command enable server
Enable a command in this server.<br/>

**Examples:**<br/>
- `.command enable server userinfo` - Enables the `userinfo` command in the Mod cog.<br/>
- `.command enable server urban` - Enables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to enable for the current server.<br/>
 - Usage: `.command enable server <command>`
 - Aliases: `server`
 - Checks: `server_only`
### .command enable global
Enable a command globally.<br/>

**Examples:**<br/>
- `.command enable global userinfo` - Enables the `userinfo` command in the Mod cog.<br/>
- `.command enable global urban` - Enables the `urban` command in the General cog.<br/>

**Arguments:**<br/>
- `<command>` - The command to enable globally.<br/>
 - Usage: `.command enable global <command>`
 - Restricted to: `BOT_OWNER`
## .command defaultdisablecog
Set the default state for a cog as disabled.<br/>

This will disable the cog for all servers by default.<br/>
To override it, use `.command enablecog` on the servers you want to allow usage.<br/>

Note: This will only work on loaded cogs, and must reference the title-case cog name.<br/>

**Examples:**<br/>
- `.command defaultdisablecog Economy`<br/>
- `.command defaultdisablecog ModLog`<br/>

**Arguments:**<br/>
- `<cog>` - The name of the cog to make disabled by default. Must be title-case.<br/>
 - Usage: `.command defaultdisablecog <cog>`
 - Restricted to: `BOT_OWNER`
# .autoimmune
Commands to manage server settings for immunity from automated actions.<br/>

This includes duplicate message deletion and mention spam from the Mod cog, and filters from the Filter cog.<br/>
 - Usage: `.autoimmune`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .autoimmune add
Makes a user or role immune from automated moderation actions.<br/>

**Examples:**<br/>
- `.autoimmune add @Twentysix` - Adds a user.<br/>
- `.autoimmune add @Mods` - Adds a role.<br/>

**Arguments:**<br/>
- `<user_or_role>` - The user or role to add immunity to.<br/>
 - Usage: `.autoimmune add <user_or_role>`
## .autoimmune list
Gets the current members and roles configured for automatic moderation action immunity.<br/>

**Example:**<br/>
- `.autoimmune list`<br/>
 - Usage: `.autoimmune list`
## .autoimmune remove
Remove a user or role from being immune to automated moderation actions.<br/>

**Examples:**<br/>
- `.autoimmune remove @Twentysix` - Removes a user.<br/>
- `.autoimmune remove @Mods` - Removes a role.<br/>

**Arguments:**<br/>
- `<user_or_role>` - The user or role to remove immunity from.<br/>
 - Usage: `.autoimmune remove <user_or_role>`
## .autoimmune isimmune
Checks if a user or role would be considered immune from automated actions.<br/>

**Examples:**<br/>
- `.autoimmune isimmune @Twentysix`<br/>
- `.autoimmune isimmune @Mods`<br/>

**Arguments:**<br/>
- `<user_or_role>` - The user or role to check the immunity of.<br/>
 - Usage: `.autoimmune isimmune <user_or_role>`
# .ignore
Commands to add servers or channels to the ignore list.<br/>

The ignore list will prevent the bot from responding to commands in the configured locations.<br/>

Note: Owners and Admins override the ignore list.<br/>
 - Usage: `.ignore`
 - Checks: `server_only`
## .ignore channel
Ignore commands in the channel, thread, or category.<br/>

Defaults to the current thread or channel.<br/>

Note: Owners, Admins, and those with Manage Channel permissions override ignored channels.<br/>

**Examples:**<br/>
- `.ignore channel #general` - Ignores commands in the #general channel.<br/>
- `.ignore channel` - Ignores commands in the current channel.<br/>
- `.ignore channel "General Channels"` - Use quotes for categories with spaces.<br/>
- `.ignore channel 356236713347252226` - Also accepts IDs.<br/>

**Arguments:**<br/>
- `<channel>` - The channel to ignore. This can also be a thread or category channel.<br/>
 - Usage: `.ignore channel [channel=operator.attrgetter('channel')]`
## .ignore server
Ignore commands in this server.<br/>

Note: Owners, Admins, and those with Manage Server permissions override ignored servers.<br/>

**Example:**<br/>
- `.ignore server` - Ignores the current server<br/>
 - Usage: `.ignore server`
 - Restricted to: `ADMIN`
 - Aliases: `server`
## .ignore list
List the currently ignored servers and channels.<br/>

**Example:**<br/>
- `.ignore list`<br/>
 - Usage: `.ignore list`
# .unignore
Commands to remove servers or channels from the ignore list.<br/>
 - Usage: `.unignore`
 - Checks: `server_only`
## .unignore channel
Remove a channel, thread, or category from the ignore list.<br/>

Defaults to the current thread or channel.<br/>

**Examples:**<br/>
- `.unignore channel #general` - Unignores commands in the #general channel.<br/>
- `.unignore channel` - Unignores commands in the current channel.<br/>
- `.unignore channel "General Channels"` - Use quotes for categories with spaces.<br/>
- `.unignore channel 356236713347252226` - Also accepts IDs. Use this method to unignore categories.<br/>

**Arguments:**<br/>
- `<channel>` - The channel to unignore. This can also be a thread or category channel.<br/>
 - Usage: `.unignore channel [channel=operator.attrgetter('channel')]`
## .unignore server
Remove this server from the ignore list.<br/>

**Example:**<br/>
- `.unignore server` - Stops ignoring the current server<br/>
 - Usage: `.unignore server`
 - Restricted to: `ADMIN`
 - Aliases: `server`
# .licenseinfo
Get info about Red's licenses.<br/>
 - Usage: `.licenseinfo`
 - Aliases: `licenceinfo`
 - Cooldown: `1 per 180.0 seconds`
