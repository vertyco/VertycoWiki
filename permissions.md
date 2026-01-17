---
title: Permissions Commands
description: 
published: true
date: 2024-08-25T19:23:53.832Z
tags: 
editor: markdown
dateCreated: 2024-08-25T19:23:52.486Z
---

# Permissions Help

Customise permissions for commands and cogs.

# .permissions
Command permission management tools.<br/>
 - Usage: `.permissions`
## .permissions addserverrule
Add a rule to a command in this server.<br/>

`<allow_or_deny>` should be one of "allow" or "deny".<br/>

`<cog_or_command>` is the cog or command to add the rule to.<br/>
This is case sensitive.<br/>

`<who_or_what...>` is one or more users, channels or roles the rule is for.<br/>
 - Usage: `.permissions addserverrule <allow_or_deny> <cog_or_command> <who_or_what>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `addserverrule`
 - Checks: `server_only`
## .permissions clearserverrules
Reset all rules in this server.<br/>
 - Usage: `.permissions clearserverrules`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `clearserverrules`
 - Checks: `server_only`
## .permissions addglobalrule
Add a global rule to a command.<br/>

`<allow_or_deny>` should be one of "allow" or "deny".<br/>

`<cog_or_command>` is the cog or command to add the rule to.<br/>
This is case sensitive.<br/>

`<who_or_what...>` is one or more users, channels or roles the rule is for.<br/>
 - Usage: `.permissions addglobalrule <allow_or_deny> <cog_or_command> <who_or_what>`
 - Restricted to: `BOT_OWNER`
## .permissions removeglobalrule
Remove a global rule from a command.<br/>

`<cog_or_command>` is the cog or command to remove the rule<br/>
from. This is case sensitive.<br/>

`<who_or_what...>` is one or more users, channels or roles the rule is for.<br/>
 - Usage: `.permissions removeglobalrule <cog_or_command> <who_or_what>`
 - Restricted to: `BOT_OWNER`
## .permissions acl
Manage permissions with YAML files.<br/>
 - Usage: `.permissions acl`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `yaml`
### .permissions acl updateserver
Update rules for this server with a YAML file.<br/>

This won't touch any rules not specified in the YAML<br/>
file.<br/>
 - Usage: `.permissions acl updateserver`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `updateserver`
 - Checks: `server_only`
### .permissions acl setglobal
Set global rules with a YAML file.<br/>

**WARNING**: This will override reset *all* global rules<br/>
to the rules specified in the uploaded file.<br/>

This does not validate the names of commands and cogs before<br/>
setting the new rules.<br/>
 - Usage: `.permissions acl setglobal`
 - Restricted to: `BOT_OWNER`
### .permissions acl getglobal
Get a YAML file detailing all global rules.<br/>
 - Usage: `.permissions acl getglobal`
 - Restricted to: `BOT_OWNER`
### .permissions acl yamlexample
Sends an example of the yaml layout for permissions<br/>
 - Usage: `.permissions acl yamlexample`
### .permissions acl updateglobal
Update global rules with a YAML file.<br/>

This won't touch any rules not specified in the YAML<br/>
file.<br/>
 - Usage: `.permissions acl updateglobal`
 - Restricted to: `BOT_OWNER`
### .permissions acl getserver
Get a YAML file detailing all rules in this server.<br/>
 - Usage: `.permissions acl getserver`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `getserver`
 - Checks: `server_only`
### .permissions acl setserver
Set rules for this server with a YAML file.<br/>

**WARNING**: This will override reset *all* rules in this<br/>
server to the rules specified in the uploaded file.<br/>
 - Usage: `.permissions acl setserver`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `setserver`
 - Checks: `server_only`
## .permissions removeserverrule
Remove a server rule from a command.<br/>

`<cog_or_command>` is the cog or command to remove the rule<br/>
from. This is case sensitive.<br/>

`<who_or_what...>` is one or more users, channels or roles the rule is for.<br/>
 - Usage: `.permissions removeserverrule <cog_or_command> <who_or_what>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `removeserverrule`
 - Checks: `server_only`
## .permissions clearglobalrules
Reset all global rules.<br/>
 - Usage: `.permissions clearglobalrules`
 - Restricted to: `BOT_OWNER`
## .permissions explain
Explain how permissions works.<br/>
 - Usage: `.permissions explain`
## .permissions canrun
Check if a user can run a command.<br/>

This will take the current context into account, such as the<br/>
server and text channel.<br/>
 - Usage: `.permissions canrun <user> <command>`
## .permissions setdefaultglobalrule
Set the default global rule for a command.<br/>

This is the rule a command will default to when no other rule<br/>
is found.<br/>

`<allow_or_deny>` should be one of "allow", "deny" or "clear".<br/>
"clear" will reset the default rule.<br/>

`<cog_or_command>` is the cog or command to set the default<br/>
rule for. This is case sensitive.<br/>
 - Usage: `.permissions setdefaultglobalrule <allow_or_deny> <cog_or_command>`
 - Restricted to: `BOT_OWNER`
## .permissions setdefaultserverrule
Set the default rule for a command in this server.<br/>

This is the rule a command will default to when no other rule<br/>
is found.<br/>

`<allow_or_deny>` should be one of "allow", "deny" or "clear".<br/>
"clear" will reset the default rule.<br/>

`<cog_or_command>` is the cog or command to set the default<br/>
rule for. This is case sensitive.<br/>
 - Usage: `.permissions setdefaultserverrule <allow_or_deny> <cog_or_command>`
 - Restricted to: `GUILD_OWNER`
 - Aliases: `setdefaultserverrule`
 - Checks: `server_only`
