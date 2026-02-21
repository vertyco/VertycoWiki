---
title: Trivia Commands
description: Trivia commands for Vertyco's Autto bot. Play trivia games with friends and test your knowledge across various categories.
published: true
date: 2024-08-25T19:25:13.790Z
tags: cogs, trivia, minigame, commands
editor: markdown
dateCreated: 2024-08-25T19:25:12.461Z
---

# Trivia Help

Play trivia with friends!

# .triviaset
Manage Trivia settings.<br/>
 - Usage: `.triviaset`
 - Restricted to: `MOD`
 - Checks: `server_only`
## .triviaset timelimit
Set the maximum seconds permitted to answer a question.<br/>
 - Usage: `.triviaset timelimit <seconds>`
## .triviaset maxscore
Set the total points required to win.<br/>
 - Usage: `.triviaset maxscore <score>`
## .triviaset override
Allow/disallow trivia lists to override settings.<br/>
 - Usage: `.triviaset override <enabled>`
## .triviaset showsettings
Show the current trivia settings.<br/>
 - Usage: `.triviaset showsettings`
## .triviaset stopafter
Set how long until trivia stops due to no response.<br/>
 - Usage: `.triviaset stopafter <seconds>`
## .triviaset revealanswer
Set whether or not the answer is revealed.<br/>

If enabled, the bot will reveal the answer if no one guesses correctly<br/>
in time.<br/>
 - Usage: `.triviaset revealanswer <enabled>`
## .triviaset custom
Manage Custom Trivia lists.<br/>
 - Usage: `.triviaset custom`
 - Restricted to: `BOT_OWNER`
### .triviaset custom upload
Upload a trivia file.<br/>
 - Usage: `.triviaset custom upload`
 - Restricted to: `BOT_OWNER`
 - Aliases: `add`
### .triviaset custom delete
Delete a trivia file.<br/>
 - Usage: `.triviaset custom delete <name>`
 - Restricted to: `BOT_OWNER`
 - Aliases: `remove`
### .triviaset custom list
List uploaded custom trivia.<br/>
 - Usage: `.triviaset custom list`
## .triviaset botplays
Set whether or not the bot gains points.<br/>

If enabled, the bot will gain a point if no one guesses correctly.<br/>
 - Usage: `.triviaset botplays <enabled>`
## .triviaset payout
Set the payout multiplier.<br/>

This can be any positive decimal number. If a user wins trivia when at<br/>
least 3 members are playing, they will receive credits. Set to 0 to<br/>
disable.<br/>

The number of credits is determined by multiplying their total score by<br/>
this multiplier.<br/>
 - Usage: `.triviaset payout <multiplier>`
 - Restricted to: `ADMIN`
 - Checks: `is_owner_if_bank_global`
## .triviaset usespoilers
Set if bot will display the answers in spoilers.<br/>

If enabled, the bot will use spoilers to hide answers.<br/>
 - Usage: `.triviaset usespoilers <enabled>`
# .trivia
Start trivia session on the specified category.<br/>

You may list multiple categories, in which case the trivia will involve<br/>
questions from all of them.<br/>
 - Usage: `.trivia <categories>`
 - Checks: `server_only`
## .trivia stop
Stop an ongoing trivia session.<br/>
 - Usage: `.trivia stop`
## .trivia leaderboard
Leaderboard for trivia.<br/>

Defaults to the top 10 of this server, sorted by total wins. Use<br/>
subcommands for a more customised leaderboard.<br/>
 - Usage: `.trivia leaderboard`
 - Aliases: `lboard`
### .trivia leaderboard server
Leaderboard for this server.<br/>

`<sort_by>` can be any of the following fields:<br/>
 - `wins`  : total wins<br/>
 - `avg`   : average score<br/>
 - `total` : total correct answers<br/>
 - `games` : total games played<br/>

`<top>` is the number of ranks to show on the leaderboard.<br/>
 - Usage: `.trivia leaderboard server [sort_by=wins] [top=10]`
 - Checks: `server_only`
### .trivia leaderboard global
Global trivia leaderboard.<br/>

`<sort_by>` can be any of the following fields:<br/>
 - `wins`  : total wins<br/>
 - `avg`   : average score<br/>
 - `total` : total correct answers from all sessions<br/>
 - `games` : total games played<br/>

`<top>` is the number of ranks to show on the leaderboard.<br/>
 - Usage: `.trivia leaderboard global [sort_by=wins] [top=10]`
## .trivia list
List available trivia categories.<br/>
 - Usage: `.trivia list`
## .trivia info
Get information about a trivia category.<br/>
 - Usage: `.trivia info <category>`
