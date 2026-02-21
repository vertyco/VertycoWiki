---
title: Counting Commands
description: Counting game commands for Vertyco's Autto bot. Participate in the community counting channel and compete for high scores.
published: true
date: 2024-09-24T22:32:22.958Z
tags: cogs, counting, minigame, commands
editor: markdown
dateCreated: 2024-05-02T02:31:58.014Z
---

# Counting Help

Multifeatured Counting Channel<br/><br/>Create a counting channel for your server, with various additional management options!

# .counting
Multifeatured Counting Channel<br/>
 - Usage: `.counting`
 - Checks: `server_only`
## .counting leaderboard
Show the Counting leaderboard in this server.<br/>
 - Usage: `.counting leaderboard`
 - Aliases: `top and topcounters`
## .counting highscore
Show the highest count reached in this server.<br/>
 - Usage: `.counting highscore`
 - Aliases: `score`
# .countingset
Settings for Counting<br/>
 - Usage: `.countingset`
 - Restricted to: `MOD`
 - Checks: `server_only`
## .countingset starting
Set the counter to start off with.<br/>
 - Usage: `.countingset starting <num>`
## .countingset penalty
Mute users for a specified amount of time if they count wrong x times in a row (leave both values empty to turn off, requires Core `mutes` to be loaded).<br/>
 - Usage: `.countingset penalty [wrong=None] [mute_time_in_seconds=None]`
## .countingset toggle
Toggle Counting in this server.<br/>
 - Usage: `.countingset toggle <true_or_false>`
## .countingset allowrepeats
Toggle whether users can count multiple times in a row.<br/>
 - Usage: `.countingset allowrepeats <true_or_false>`
## .countingset clear
Clear & reset the current Counting settings.<br/>
 - Usage: `.countingset clear`
## .countingset assignrole
Toggle whether to assign a role to the most recent user to count (requires add/remove role perms).<br/>
 - Usage: `.countingset assignrole <true_or_false>`
## .countingset channel
Set the Counting channel.<br/>
 - Usage: `.countingset channel <channel>`
## .countingset role
Set the role to assign to the most recent user to count.<br/>
 - Usage: `.countingset role <role>`
 - Restricted to: `ADMIN`
## .countingset autoreset
Set the message to be sent on counter reset when a wrong number is sent (leave blank to turn off auto-reset).<br/>

The following variables can be included in the message:<br/>
- `{author}` for a user mention of the wrong count message's author<br/>
- `{count}` for the wrong count number<br/>
- `{correct}` for what the count should have been<br/>
 - Usage: `.countingset autoreset [message]`
## .countingset delete
Toggle whether incorrect counts should be deleted.<br/>
 - Usage: `.countingset delete <true_or_false>`
## .countingset view
View the current Counting settings.<br/>
 - Usage: `.countingset view`
## .countingset react
Toggle whether ✓ and ✗ reactions should be added to messages.<br/>
 - Usage: `.countingset react <true_or_false>`
## .countingset resetcounts
Reset the current Counting scores for all server members.<br/>
 - Usage: `.countingset resetcounts`
## .countingset allowtext
Set whether messages not starting with a number are allowed.<br/>
 - Usage: `.countingset allowtext <true_or_false>`
