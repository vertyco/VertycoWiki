---
title: Miner Commands
description: 
published: true
date: 2026-01-17T17:01:35.777Z
tags: cogs, miner, vc, commands
editor: markdown
dateCreated: 2026-01-17T17:01:35.777Z
---

Pickaxe in hand, fortune awaits

# .miner (Hybrid Command)
Miner commands for users.<br/>
 - Usage: `.miner`
 - Slash Usage: `/miner`
## .miner trade (Hybrid Command)
Trade resources with another miner.<br/>
 - Usage: `.miner trade <user>`
 - Slash Usage: `/miner trade <user>`
 - Checks: `ensure_db_connection`
## .miner repair (Hybrid Command)
Repair your pickaxe.<br/>
 - Usage: `.miner repair [confirm=False]`
 - Slash Usage: `/miner repair [confirm=False]`
 - Checks: `ensure_db_connection`
## .miner lb (Hybrid Command)
View the top players for a specific resource.<br/>
 - Usage: `.miner lb`
 - Slash Usage: `/miner lb`
 - Checks: `ensure_db_connection`
## .miner upgrade (Hybrid Command)
Upgrade your mining tool if you have enough resources (with confirmation).<br/>
 - Usage: `.miner upgrade`
 - Slash Usage: `/miner upgrade`
 - Checks: `ensure_db_connection`
## .miner inventory (Hybrid Command)
View your mining inventory and tool.<br/>
 - Usage: `.miner inventory [user=None]`
 - Slash Usage: `/miner inventory [user=None]`
 - Aliases: `inv`
 - Checks: `ensure_db_connection`
## .miner guide (Hybrid Command)
Learn how Miner works, including spawns, overswing, and helpful commands.<br/>
 - Usage: `.miner guide`
 - Slash Usage: `/miner guide`
 - Checks: `ensure_db_connection`
# .minerlb (Hybrid Command)
View the top players for a specific resource.<br/>
 - Usage: `.minerlb`
 - Slash Usage: `/minerlb`
 - Checks: `ensure_db_connection`
# .minerdb
Database Commands<br/>
 - Usage: `.minerdb`
 - Restricted to: `BOT_OWNER`
## .minerdb nukedb
Delete the database for this cog and reinitialize it<br/>

THIS CANNOT BE UNDONE!<br/>
 - Usage: `.minerdb nukedb <confirm>`
 - Checks: `ensure_db_connection`
## .minerdb postgres
Set the Postgres connection info<br/>
 - Usage: `.minerdb postgres`
## .minerdb diagnose
Check the database connection<br/>
 - Usage: `.minerdb diagnose`
# .minerset
Admin commands<br/>
 - Usage: `.minerset`
 - Restricted to: `ADMIN`
## .minerset spawn
Spawn a new mining rock in the specified channel.<br/>
 - Usage: `.minerset spawn <rock_type> <channel>`
 - Checks: `ensure_db_connection`
## .minerset toggle
Toggle active mining channels<br/>
 - Usage: `.minerset toggle <channel>`
 - Checks: `ensure_db_connection`
## .minerset view
View active mining channels<br/>
 - Usage: `.minerset view`
 - Checks: `ensure_db_connection`
	- Notes: Rock spawn pacing (minimum/maximum intervals) is global and configured by the bot owner. Guild admins only control which channels are eligible for rocks and whether activity is tracked per-channel or per-guild; rare rocks remain globally rare regardless of guild-specific settings.
