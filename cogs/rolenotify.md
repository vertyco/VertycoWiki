---
title: Role Notify Commands
description: 
published: true
date: 2024-08-25T19:16:48.693Z
tags: 
editor: markdown
dateCreated: 2024-08-25T19:16:47.393Z
---

# RoleNotify Help

Notify a user when they have a Role added or removed from them<br/><br/>More detailed docs: <https://cogs.yamikaitou.dev/rolenotify.html>

# .rolenotify
Configure RoleNotify<br/>
 - Usage: `.rolenotify`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
## .rolenotify role
Configure settings for a Role<br/>
 - Usage: `.rolenotify role`
### .rolenotify role method
Set the notification method<br/>

Valid options are `dm` and `channel`<br/>
 - Usage: `.rolenotify role method <role> <method>`
### .rolenotify role info
Display the configured settings for a Role<br/>
 - Usage: `.rolenotify role info <role>`
### .rolenotify role add
Set if the notification should be sent on Role Add<br/>

<state> should be any of these combinations, `on/off`, `yes/no`, `1/0`, `true/false`<br/>
 - Usage: `.rolenotify role add <role> <state>`
### .rolenotify role message
Set the notification message<br/>

<option> can be either `add` or `remove`<br/>

Formatting options available for <message> are<br/>
{role_name} = Role Name<br/>
{role_mention} = Role Mention (will not ping)<br/>
{user_name} = User's Display Name<br/>
{user_mention} = User Mention<br/>
 - Usage: `.rolenotify role message <role> <option> <message>`
### .rolenotify role remove
Set if the notification should be sent on Role Remove<br/>

<state> should be any of these combinations, `on/off`, `yes/no`, `1/0`, `true/false`<br/>
 - Usage: `.rolenotify role remove <role> <state>`
### .rolenotify role channel
Set the channel to output Role Notifications to<br/>

Pass 0 to clear the channel and use the server defined channel<br/>
 - Usage: `.rolenotify role channel <role> <channel>`
## .rolenotify channel
Set the channel to output Role Notifications to<br/>

Pass 0 to clear the channel<br/>
Pass nothing to see the configured channel<br/>
 - Usage: `.rolenotify channel [channel=None]`
