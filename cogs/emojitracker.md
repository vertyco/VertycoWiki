---
title: EmojiTracker Commands
description: 
published: true
date: 2026-01-17T16:59:56.422Z
tags: cogs, emojitracker, commands
editor: markdown
dateCreated: 2024-05-02T02:33:52.625Z
---

Track emojis and view leaderboards/most emojis used ect..<br/><br/>This cog will track reactions added to other user's messages.<br/>It will ignore reactions added to a bot's message<br/>It will also only count one reaction per emoji for each user on a message so user's can't spam react/unreact

# .ignoreserver
Add/Remove a server from the blacklist<br/>

Enter a Guild ID to add it to the blacklist, to remove, simply enter it again<br/>
 - Usage: `.ignoreserver <server_id>`
 - Restricted to: `BOT_OWNER`
# .viewblacklist
View EmojiTracker Blacklist<br/>
 - Usage: `.viewblacklist`
 - Restricted to: `BOT_OWNER`
# .resetreacts
Reset reaction data for this server<br/>
 - Usage: `.resetreacts`
 - Checks: `server_only`
# .emojilb
View the emoji leaderboard<br/>
 - Usage: `.emojilb`
 - Checks: `server_only`
# .reactlb
View user leaderboard for most emojis added<br/>
 - Usage: `.reactlb`
 - Checks: `server_only`
# .emojitrackercache
Get the size of EmojiTracker cache<br/>
 - Usage: `.emojitrackercache`
 - Restricted to: `BOT_OWNER`
 - Aliases: `etc`
