---
title: EconomyTrack Commands
description: EconomyTrack commands for Vertyco's Autto bot. View VertCoin balance graphs and track economy trends over time.
published: true
date: 2026-01-17T16:59:53.581Z
tags: cogs, economytrack, vc, commands
editor: markdown
dateCreated: 2024-05-02T02:32:36.918Z
---

Track your economy's total balance over time<br/><br/>Also track you server's member count!

# .economytrack
Configure EconomyTrack<br/>
 - Usage: `.economytrack`
 - Aliases: `ecotrack`
 - Checks: `server_only`
## .economytrack view
View EconomyTrack Settings<br/>
 - Usage: `.economytrack view`
## .economytrack togglebanktrack
Enable/Disable economy tracking for this server<br/>
 - Usage: `.economytrack togglebanktrack`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .economytrack togglemembertrack
Enable/Disable member tracking for this server<br/>
 - Usage: `.economytrack togglemembertrack`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
## .economytrack timezone
Set your desired timezone for the graph<br/>

**Arguments**<br/>
`<timezone>` A string representing a valid timezone<br/>

**Example:** `.ecotrack timezone US/Eastern`<br/>

Use this command without the argument to get a huge list of valid timezones.<br/>
 - Usage: `.economytrack timezone <timezone>`
## .economytrack maxpoints
Set the max amount of data points the bot will store<br/>

**Arguments**<br/>
`<max_points>` Maximum amount of data points to store<br/>

The loop runs every 2 minutes, so 720 points equals 1 day<br/>
The default is 21600 (30 days)<br/>
Set to 0 to store data indefinitely (Not Recommended)<br/>
 - Usage: `.economytrack maxpoints <max_points>`
 - Restricted to: `BOT_OWNER`
# .remoutliers
Cleanup data that falls outside a specified range<br/>

**Arguments**<br/>
`[min_value]` - Minimum value to keep (optional)<br/>
`[max_value]` - Maximum value to keep (optional)<br/>
`[datatype]` - Either `bank` or `member` (defaults to bank)<br/>

At least one of min_value or max_value must be provided.<br/>

**Examples:**<br/>
`.remoutliers 0 50000 bank` - Remove bank points outside 0-50000 range<br/>
`.remoutliers 500 10000 member` - Remove member counts outside 500-10000 range<br/>
`.remoutliers None 8000 member` - Remove only data points above 8000 members<br/>
`.remoutliers 5000 None member` - Remove only data points below 5000 members<br/>
 - Usage: `.remoutliers [min_value=None] [max_value=None] [datatype=bank]`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
# .bankgraph
View bank status over a period of time.<br/>
**Arguments**<br/>
`<timespan>` How long to look for, or `all` for all-time data. Defaults to 1 day.<br/>
Must be at least 1 hour.<br/>
**Examples:**<br/>
    - `.bankgraph 3w2d`<br/>
    - `.bankgraph 5d`<br/>
    - `.bankgraph all`<br/>
 - Usage: `.bankgraph [timespan=1d]`
 - Aliases: `bgraph`
 - Cooldown: `5 per 60.0 seconds`
 - Checks: `server_only`
# .membergraph
View member count over a period of time.<br/>
**Arguments**<br/>
`<timespan>` How long to look for, or `all` for all-time data. Defaults to 1 day.<br/>
Must be at least 1 hour.<br/>
**Examples:**<br/>
    - `.membergraph 3w2d`<br/>
    - `.membergraph 5d`<br/>
    - `.membergraph all`<br/>
 - Usage: `.membergraph [timespan=1d]`
 - Aliases: `memgraph`
 - Cooldown: `5 per 60.0 seconds`
 - Checks: `server_only`
# .autoremoutliers
Automatically detect and remove outliers in your data using statistical methods<br/>

**Arguments**<br/>
`[datatype]` - Either `bank` or `member` (defaults to bank)<br/>
`[multiplier]` - IQR multiplier for outlier detection sensitivity (default: 1.5)<br/>
    - Higher values = more lenient (keeps more data)<br/>
    - Lower values = more strict (removes more outliers)<br/>
`[confirm]` - Whether to actually remove the outliers<br/>
    - Set to False for a dry run that shows what would be removed without actually removing anything<br/>

This command uses the Interquartile Range (IQR) method to detect outliers:<br/>
- Calculates Q1 (25th percentile) and Q3 (75th percentile)<br/>
- Any value outside [Q1 - multiplier*IQR, Q3 + multiplier*IQR] is considered an outlier<br/>

**Examples:**<br/>
`.autoremoutliers true member` - Automatically remove member count outliers<br/>
`.autoremoutliers true bank 2.0` - Remove bank outliers with higher tolerance<br/>
`.autoremoutliers false member 1.0` - Show outliers that would be removed without actually removing them<br/>
 - Usage: `.autoremoutliers <confirm> [datatype=bank] [multiplier=1.5]`
 - Restricted to: `GUILD_OWNER`
 - Checks: `server_only`
