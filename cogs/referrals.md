---
title: Referrals Commands
description: 
published: true
date: 2026-01-17T17:01:48.157Z
tags: 
editor: markdown
dateCreated: 2026-01-17T17:01:48.157Z
---

Simple referral system for Discord servers.

# /referredby (Slash Command)
Claim a referral<br/>
 - Usage: `/referredby <referred_by>`
 - `referred_by:` (Required) The user who referred you

 - Checks: `Server Only`
# .referredby
Claim a referral<br/>

Claim a referral from a user who referred you<br/>

If referral rewards are enabled, you will receive the reward for being referred.<br/>
If referrer rewards are enabled, the person who referred you will also receive a reward.<br/>
 - Usage: `.referredby <referred_by>`
 - Checks: `ensure_db_connection and server_only`
# .myreferrals (Hybrid Command)
Check your referrals<br/>
 - Usage: `.myreferrals`
 - Slash Usage: `/myreferrals`
 - Checks: `ensure_db_connection and server_only`
# .whoreferred (Hybrid Command)
Check if a specific user has been referred<br/>
 - Usage: `.whoreferred <user>`
 - Slash Usage: `/whoreferred <user>`
 - Checks: `ensure_db_connection and server_only`
# .referset
Settings for the referral system<br/>
 - Usage: `.referset`
 - Restricted to: `ADMIN`
 - Aliases: `refset and referralset`
 - Checks: `server_only`
## .referset channel
Set the channel where referral events will be sent<br/>
 - Usage: `.referset channel [channel=None]`
 - Checks: `ensure_db_connection`
## .referset reward
Set the reward for referring or being referred<br/>

**Arguments:**<br/>
- `reward_type` - Either `referral` or `referred`<br/>
  - `referral` - The reward for referring someone<br/>
  - `referred` - The reward for being referred<br/>
- `amount` - The amount of currency to reward<br/>

*Set to 0 to disable the reward*<br/>
 - Usage: `.referset reward <reward_type> <amount>`
 - Checks: `ensure_db_connection`
## .referset timeout
Set the time frame for users to claim their reward after joining<br/>

- `timeout` - The time frame in the format of `30m`, `1h`, `2d12h`, etc.<br/>
 - Usage: `.referset timeout <timeout>`
 - Checks: `ensure_db_connection`
## .referset resetreferrals
Reset all referral records for the server<br/>

This keeps your settings but removes all referral history.<br/>
 - Usage: `.referset resetreferrals <confirm>`
 - Checks: `ensure_db_connection`
## .referset age
Set the minimum account age for referred users to be eligible for rewards<br/>

- `age` - The minimum account age in the format of `30m`, `1h`, `2d12h`, etc.<br/>
 - Usage: `.referset age <age>`
 - Checks: `ensure_db_connection`
## .referset view
View the current settings for the server<br/>
 - Usage: `.referset view`
 - Checks: `ensure_db_connection`
## .referset resetinitialized
Reset the list of initialized users for the server<br/>

This clears the record of which users have been initialized, allowing them<br/>
to potentially claim referrals.<br/>
 - Usage: `.referset resetinitialized <confirm>`
 - Checks: `ensure_db_connection`
## .referset toggle
Toggle the referral system on or off<br/>
 - Usage: `.referset toggle`
 - Checks: `ensure_db_connection`
## .referset resetall
Reset all referral data and settings for the server<br/>

This deletes all referrals and settings, completely starting fresh.<br/>
 - Usage: `.referset resetall <confirm>`
 - Checks: `ensure_db_connection`
## .referset resetsettings
Reset all referral settings for the server<br/>

This keeps your referral history but resets all configuration settings.<br/>
 - Usage: `.referset resetsettings <confirm>`
 - Checks: `ensure_db_connection`
## .referset listreferrals
List all referrals made in the server<br/>
 - Usage: `.referset listreferrals`
 - Checks: `ensure_db_connection`
## .referset init
Initialize all unreferred users in the server so they cannot retroactively claim rewards<br/>
 - Usage: `.referset init`
 - Aliases: `initialize`
 - Checks: `ensure_db_connection`
