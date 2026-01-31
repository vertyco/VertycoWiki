---
title: LevelUp Commands
description: 
published: true
date: 2026-01-17T17:00:13.749Z
tags: [cogs, levelup, commands]
editor: markdown
dateCreated: 2024-05-02T02:37:48.377Z
---

Your friendly neighborhood leveling system<br/><br/>Earn experience by chatting in text and voice channels, compare levels with your friends, customize your profile and view various leaderboards!

# .weekly
View Weekly Leaderboard<br/>
 - Usage: `.weekly [stat=exp] [displayname=True]`
 - Aliases: `week`
 - Checks: `server_only`
# .lastweekly
View Last Week's Leaderboard<br/>
 - Usage: `.lastweekly`
 - Checks: `server_only`
# .weeklyset
Configure Weekly LevelUp Settings<br/>
 - Usage: `.weeklyset`
 - Restricted to: `ADMIN`
 - Aliases: `wset`
 - Checks: `server_only`
## .weeklyset bonus
Set bonus exp for top weekly winners<br/>
 - Usage: `.weeklyset bonus <bonus>`
## .weeklyset day
Set day for weekly stats reset<br/>
0 = Monday<br/>
1 = Tuesday<br/>
2 = Wednesday<br/>
3 = Thursday<br/>
4 = Friday<br/>
5 = Saturday<br/>
6 = Sunday<br/>
 - Usage: `.weeklyset day <day>`
## .weeklyset toggle
Toggle weekly stat tracking<br/>
 - Usage: `.weeklyset toggle`
## .weeklyset autoremove
Remove role from previous winner when new one is announced<br/>
 - Usage: `.weeklyset autoremove`
## .weeklyset autoreset
Toggle auto reset of weekly stats<br/>
 - Usage: `.weeklyset autoreset`
## .weeklyset roleall
Toggle whether all winners get the role<br/>
 - Usage: `.weeklyset roleall`
## .weeklyset winners
Set number of winners to display<br/>

Due to Discord limitations with max embed field count, the maximum number of winners is 25<br/>
 - Usage: `.weeklyset winners <count>`
## .weeklyset role
Set role to award top weekly winners<br/>
 - Usage: `.weeklyset role <role>`
## .weeklyset ping
Toggle whether to ping winners in announcement<br/>
 - Usage: `.weeklyset ping`
## .weeklyset hour
Set hour for weekly stats reset<br/>
 - Usage: `.weeklyset hour <hour>`
## .weeklyset reset
Reset the weekly leaderboard manually and announce winners<br/>
 - Usage: `.weeklyset reset <yes_or_no>`
## .weeklyset channel
Set channel to announce weekly winners<br/>
 - Usage: `.weeklyset channel <channel>`
## .weeklyset view
View the current weekly settings<br/>
 - Usage: `.weeklyset view`
# .leveltop (Hybrid Command)
View the LevelUp leaderboard<br/>

**Arguments**<br/>
`stat` - The stat to view the leaderboard for, defaults to `exp` but can be any of the following:<br/>
- `xp` - Experience<br/>
- `level` - Level<br/>
- `voice` - Voicetime<br/>
- `messages` - Messages<br/>
- `stars` - Stars<br/>
`globalstats` - View the global leaderboard instead of the server leaderboard<br/>
`displayname` - Use display names instead of usernames<br/>
 - Usage: `.leveltop [stat=xp] [globalstats=False] [displayname=True]`
 - Slash Usage: `/leveltop [stat=xp] [globalstats=False] [displayname=True]`
 - Aliases: `lvltop, topstats, membertop, and topranks`
 - Checks: `server_only`
# .roletop
View the leaderboard for roles<br/>
 - Usage: `.roletop`
 - Checks: `server_only`
# .profiledata
View a user's profile by ID<br/>

Useful if user has left the server<br/>
 - Usage: `.profiledata <user_id>`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .profile (Hybrid Command)
View User Profile<br/>
 - Usage: `.profile [user]`
 - Slash Usage: `/profile [user]`
 - Aliases: `pf`
 - Cooldown: `3 per 10.0 seconds`
 - Checks: `server_only`
# .lvlupnotify (Hybrid Command)
Toggles level up notifications for a user
- Usage: `.lvlupnotify`
- Slash Usage: `/lvlupnotify`
- Aliases: `notify`
- Checks: `server_only`
# .prestige (Hybrid Command)
Prestige your rank!<br/>
Once you have reached this servers prestige level requirement, you can<br/>
reset your level and experience to gain a prestige level and any perks associated with it<br/>

If you are over level and xp when you prestige, your xp and levels will carry over<br/>
 - Usage: `.prestige`
 - Slash Usage: `/prestige`
 - Checks: `server_only`
# .setprofile (Hybrid Command)
Customize your profile<br/>
 - Usage: `.setprofile`
 - Slash Usage: `/setprofile`
 - Aliases: `myprofile, mypf, and pfset`
 - Checks: `server_only`
## .setprofile backgrounds (Hybrid Command)
View the all available backgrounds<br/>
 - Usage: `.setprofile backgrounds`
 - Slash Usage: `/setprofile backgrounds`
 - Cooldown: `1 per 5.0 seconds`
## .setprofile namecolor (Hybrid Command)
Set a color for your username<br/>

For a specific color, try **[Google's hex color picker](https://htmlcolorcodes.com/)**<br/>

Set to `default` to randomize the color each time your profile is generated<br/>
 - Usage: `.setprofile namecolor <color>`
 - Slash Usage: `/setprofile namecolor <color>`
 - Aliases: `name`
## .setprofile barcolor (Hybrid Command)
Set a color for your level bar<br/>

For a specific color, try **[Google's hex color picker](https://htmlcolorcodes.com/)**<br/>

Set to `default` to randomize the color each time your profile is generated<br/>
 - Usage: `.setprofile barcolor <color>`
 - Slash Usage: `/setprofile barcolor <color>`
 - Aliases: `levelbar, lvlbar, and bar`
## .setprofile font (Hybrid Command)
Set a font for your profile<br/>

To view available fonts, type `.myprofile fonts`<br/>
To revert to the default font, use `default` for the `font_name` argument<br/>
 - Usage: `.setprofile font <font_name>`
 - Slash Usage: `/setprofile font <font_name>`
## .setprofile view (Hybrid Command)
View your profile settings<br/>
 - Usage: `.setprofile view`
 - Slash Usage: `/setprofile view`
## .setprofile rembackground (Hybrid Command)
Remove a default background from the cog's backgrounds folder<br/>
 - Usage: `.setprofile rembackground <filename>`
 - Slash Usage: `/setprofile rembackground <filename>`
 - Restricted to: `BOT_OWNER`
## .setprofile fonts (Hybrid Command)
View the available fonts you can use<br/>
 - Usage: `.setprofile fonts`
 - Slash Usage: `/setprofile fonts`
 - Cooldown: `1 per 5.0 seconds`
## .setprofile addbackground (Hybrid Command)
Add a custom background to the cog from discord<br/>

**Arguments**<br/>
`preferred_filename` - If a name is given, it will be saved as this name instead of the filename<br/>

**DISCLAIMER**<br/>
- Do not replace any existing file names with custom images<br/>
- If you add broken or corrupt images it can break the cog<br/>
- Do not include the file extension in the preferred name, it will be added automatically<br/>
 - Usage: `.setprofile addbackground [preferred_filename=None]`
 - Slash Usage: `/setprofile addbackground [preferred_filename=None]`
 - Restricted to: `BOT_OWNER`
## .setprofile addfont (Hybrid Command)
Add a custom font to the cog from discord<br/>

**Arguments**<br/>
`preferred_filename` - If a name is given, it will be saved as this name instead of the filename<br/>
**Note:** do not include the file extension in the preferred name, it will be added automatically<br/>
 - Usage: `.setprofile addfont [preferred_filename=None]`
 - Slash Usage: `/setprofile addfont [preferred_filename=None]`
 - Restricted to: `BOT_OWNER`
## .setprofile statcolor (Hybrid Command)
Set a color for your server stats<br/>

For a specific color, try **[Google's hex color picker](https://htmlcolorcodes.com/)**<br/>

Set to `default` to randomize the color each time your profile is generated<br/>
 - Usage: `.setprofile statcolor <color>`
 - Slash Usage: `/setprofile statcolor <color>`
 - Aliases: `stat`
## .setprofile shownick (Hybrid Command)
Toggle whether your nickname or username is shown in your profile<br/>
 - Usage: `.setprofile shownick`
 - Slash Usage: `/setprofile shownick`
## .setprofile background (Hybrid Command)
Set a background for your profile<br/>

This will override your profile banner as the background<br/>

**WARNING**<br/>
The default profile style is wide (1050 by 450 pixels) with an aspect ratio of 21:9.<br/>
Portrait images will be cropped.<br/>

Tip: Googling "dual monitor backgrounds" gives good results for the right images<br/>

Here are some good places to look.<br/>
[dualmonitorbackgrounds](https://www.dualmonitorbackgrounds.com/)<br/>
[setaswall](https://www.setaswall.com/dual-monitor-wallpapers/)<br/>
[pexels](https://www.pexels.com/photo/panoramic-photography-of-trees-and-lake-358482/)<br/>
[teahub](https://www.teahub.io/searchw/dual-monitor/)<br/>

**Additional Options**<br/>
 - Leave `url` blank or specify `default` to reset back to using your profile banner (or random if you don't have one)<br/>
 - `random` will randomly select from a pool of default backgrounds each time<br/>
 - `filename` run `.mypf backgrounds` to view default options you can use by including their filename<br/>
 - Usage: `.setprofile background [url=None]`
 - Slash Usage: `/setprofile background [url=None]`
 - Aliases: `bg`
## .setprofile blur (Hybrid Command)
Toggle a slight blur effect on the background image where the text is displayed.<br/>
 - Usage: `.setprofile blur`
 - Slash Usage: `/setprofile blur`
## .setprofile fontpath (Hybrid Command)
Get folder paths for this cog's fonts<br/>
 - Usage: `.setprofile fontpath`
 - Slash Usage: `/setprofile fontpath`
 - Restricted to: `BOT_OWNER`
## .setprofile remfont (Hybrid Command)
Remove a default font from the cog's fonts folder<br/>
 - Usage: `.setprofile remfont <filename>`
 - Slash Usage: `/setprofile remfont <filename>`
 - Restricted to: `BOT_OWNER`
## .setprofile style (Hybrid Command)
Set your profile image style<br/>

- `default` is the default profile style, very customizable<br/>
- `runescape` is a runescape style profile, less customizable but more nostalgic<br/>
- (WIP) - more to come<br/>
 - Usage: `.setprofile style <style>`
 - Slash Usage: `/setprofile style <style>`
## .setprofile bgpath (Hybrid Command)
Get the folder paths for this cog's backgrounds<br/>
 - Usage: `.setprofile bgpath`
 - Slash Usage: `/setprofile bgpath`
 - Restricted to: `BOT_OWNER`
# .stars (Hybrid Command)
Reward a good noodle<br/>
 - Usage: `.stars [user]`
 - Slash Usage: `/stars [user]`
 - Aliases: `givestar, addstar, and thanks`
 - Checks: `server_only`
# .startop
View the Star Leaderboard<br/>
 - Usage: `.startop [globalstats=False] [displayname=True]`
 - Aliases: `topstars, starleaderboard, and starlb`
 - Checks: `server_only`
# .starset
Configure LevelUp Star Settings<br/>
 - Usage: `.starset`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
## .starset mention
Toggle star reaction mentions<br/>
 - Usage: `.starset mention`
## .starset cooldown
Set the star cooldown<br/>
 - Usage: `.starset cooldown <cooldown>`
## .starset view
View Star Settings<br/>
 - Usage: `.starset view`
## .starset mentiondelete
Toggle whether the bot auto-deletes the star mentions<br/>

Set to 0 to disable auto-delete<br/>
 - Usage: `.starset mentiondelete <delete_after>`
# .levelowner
Owner Only LevelUp Settings<br/>
 - Usage: `.levelowner`
 - Restricted to: `BOT_OWNER`
 - Aliases: `lvlowner`
 - Checks: `server_only`
## .levelowner externalapi
Set the external API URL for image generation<br/>

Set to an `none` to disable the external API<br/>

**Notes**<br/>
- If the API fails, the cog will fall back to the default image generation method.<br/>
 - Usage: `.levelowner externalapi <url>`
## .levelowner ignorebots
Toggle ignoring bots for XP and profiles<br/>

**USE AT YOUR OWN RISK**<br/>
Allowing your bot to listen to other bots is a BAD IDEA and should NEVER be enabled on public bots.<br/>
 - Usage: `.levelowner ignorebots`
## .levelowner rendergifs
Toggle rendering of GIFs for animated profiles<br/>
 - Usage: `.levelowner rendergifs`
 - Aliases: `rendergif and gif`
## .levelowner ignore
Add/Remove a server from the ignore list<br/>
 - Usage: `.levelowner ignore <server_id>`
## .levelowner autoclean
Toggle purging of config data for servers the bot is no longer in<br/>
 - Usage: `.levelowner autoclean`
## .levelowner cache
Set the cache time for user profiles<br/>
 - Usage: `.levelowner cache <seconds>`
## .levelowner forceembeds
Toggle enforcing profile embeds<br/>

If enabled, profiles will only use embeds on all servers.<br/>
This disables image generation globally.<br/>
 - Usage: `.levelowner forceembeds`
 - Aliases: `forceembed`
## .levelowner view
View Global LevelUp Settings<br/>
 - Usage: `.levelowner view`
## .levelowner internalapi
Enable internal API for parallel image generation<br/>

Setting a port will spin up a detatched but cog-managed FastAPI server to handle image generation.<br/>
The process ID will be attached to the bot object and persist through reloads.<br/>

**USE AT YOUR OWN RISK!!!**<br/>
Using the internal API will spin up multiple subprocesses to handle bulk image generation.<br/>
If your bot crashes, the API subprocess will not be killed and will need to be manually terminated!<br/>
It is HIGHLY reccommended to host the api separately!<br/>

Set to 0 to disable the internal API<br/>

**Notes**<br/>
- This will spin up a 1 worker per core on the bot's cpu.<br/>
- If the API fails, the cog will fall back to the default image generation method.<br/>
 - Usage: `.levelowner internalapi <port>`
# .leveldata
Admin Only Data Commands<br/>
 - Usage: `.leveldata`
 - Restricted to: `ADMIN`
 - Aliases: `lvldata and ldata`
 - Checks: `server_only`
## .leveldata resetglobal
Reset user data for all servers<br/>
 - Usage: `.leveldata resetglobal`
 - Restricted to: `BOT_OWNER`
## .leveldata backup
Backup this server's data<br/>
 - Usage: `.leveldata backup`
## .leveldata restore
Restore this server's data<br/>
 - Usage: `.leveldata restore`
## .leveldata restorecog
Restore the cog's data<br/>
 - Usage: `.leveldata restorecog`
 - Restricted to: `BOT_OWNER`
## .leveldata importmee6
Import levels and exp from MEE6<br/>

**Arguments**<br/>
➣ `import_by` - Import by level or exp<br/>
• If `level`, it will import their level and calculate exp from that.<br/>
• If `exp`, it will import their exp directly and calculate level from that.<br/>
➣ `replace` - Replace existing data (True/False)<br/>
➣ `include_settings` - Include MEE6 settings (True/False)<br/>
➣ `all_users` - Import all users regardless of if they're in the server (True/False)<br/>
 - Usage: `.leveldata importmee6 <import_by> <replace> <include_settings> <all_users>`
 - Restricted to: `GUILD_OWNER`
## .leveldata importpolaris
Import levels and exp from Polaris<br/>

**Make sure your server's leaderboard is public!**<br/>

**Arguments**<br/>
➣ `replace` - Replace existing data (True/False)<br/>
➣ `include_settings` - Include Polaris settings (True/False)<br/>
➣ `all_users` - Import all users regardless of if they're in the server (True/False)<br/>

[Polaris](https://gdcolon.com/polaris/)<br/>
 - Usage: `.leveldata importpolaris <replace> <include_settings> <all_users>`
 - Restricted to: `GUILD_OWNER`
## .leveldata cleanup
Cleanup the database<br/>

Performs the following actions:<br/>
- Delete data for users no longer in the server<br/>
- Removes channels and roles that no longer exist<br/>
 - Usage: `.leveldata cleanup`
## .leveldata importamari
Import levels and exp from AmariBot<br/>
**Arguments**<br/>
➣ `import_by` - Import by level or exp<br/>
• If `level`, it will import their level and calculate exp from that.<br/>
• If `exp`, it will import their exp directly and calculate level from that.<br/>
➣ `replace` - Replace existing data (True/False)<br/>
• If True, it will replace existing data.<br/>
➣ `api_key` - Your [AmariBot API key](https://docs.google.com/forms/d/e/1FAIpQLScQDCsIqaTb1QR9BfzbeohlUJYA3Etwr-iSb0CRKbgjA-fq7Q/viewform?usp=send_form)<br/>
➣ `all_users` - Import all users regardless of if they're in the server (True/False)<br/>
 - Usage: `.leveldata importamari <import_by> <replace> <api_key> <all_users>`
 - Restricted to: `GUILD_OWNER`
## .leveldata importmalarne
Import levels and exp from Malarne's Leveler cog<br/>

**Arguments**<br/>
➣ `import_by` - Import by level or exp<br/>
• If `level`, it will import their level and calculate exp from that.<br/>
• If `exp`, it will import their exp directly and calculate level from that.<br/>
➣ `replace` - Replace existing data (True/False)<br/>
• If True, it will replace existing data.<br/>
➣ `all_users` - Import all users regardless of if they're in the server (True/False)<br/>
 - Usage: `.leveldata importmalarne <import_by> <replace> <all_users>`
 - Restricted to: `BOT_OWNER`
## .leveldata resetcog
Reset the ENTIRE cog's data<br/>
 - Usage: `.leveldata resetcog`
 - Restricted to: `BOT_OWNER`
## .leveldata reset
Reset all user data in this server<br/>
 - Usage: `.leveldata reset`
## .leveldata backupcog
Backup the cog's data<br/>
 - Usage: `.leveldata backupcog`
 - Restricted to: `BOT_OWNER`
## .leveldata importfixator
Import data from Fixator's Leveler cog<br/>

This will overwrite existing LevelUp level data and stars<br/>
It will also import XP range level roles, and ignored channels<br/>

*Obviously you will need MongoDB running while you run this command*<br/>
 - Usage: `.leveldata importfixator`
 - Restricted to: `BOT_OWNER`
# .levelset
Configure LevelUp Settings<br/>
 - Usage: `.levelset`
 - Restricted to: `ADMIN`
 - Aliases: `lvlset and lset`
 - Checks: `server_only`
## .levelset toggle
Toggle the LevelUp system<br/>
 - Usage: `.levelset toggle`
## .levelset voice
Voice settings<br/>
 - Usage: `.levelset voice`
### .levelset voice streambonus
Add a range of bonus XP to users who are Discord streaming<br/>

This bonus applies to voice time xp<br/>

Set both min and max to 0 to remove the bonus<br/>
 - Usage: `.levelset voice streambonus <min_xp> <max_xp>`
### .levelset voice xp
Set voice XP gain<br/>
Sets the amount of XP gained per minute in a voice channel (default is 2)<br/>
 - Usage: `.levelset voice xp <voice_xp>`
### .levelset voice deafened
Ignore deafened voice users<br/>
Toggle whether deafened users in a voice channel can gain voice XP<br/>
 - Usage: `.levelset voice deafened`
### .levelset voice channelbonus
Add a range of bonus XP to apply to certain channels<br/>

This bonus applies to voice time xp per minute.<br/>
Example: 2 minutes in a channel with a 1-2 bonus will give 2-4 XP<br/>

Set both min and max to 0 to remove the channel bonus.<br/>
 - Usage: `.levelset voice channelbonus <channel> <min_xp> <max_xp>`
### .levelset voice muted
Ignore muted voice users<br/>
Toggle whether self-muted users in a voice channel can gain voice XP<br/>
 - Usage: `.levelset voice muted`
### .levelset voice appbonus
Add a range of bonus XP to users running a specific application/game in voice channels<br/>

This bonus applies to voice time xp<br/>

Set both min and max to 0 to remove the application bonus<br/>

**Examples:**<br/>
• `.levelset voice appbonus VALORANT 5 10` - Users playing VALORANT get 5-10 bonus XP per minute<br/>
• `.levelset voice appbonus "Visual Studio Code" 2 4` - Use quotes for names with spaces<br/>
• `.levelset voice appbonus VALORANT 0 0` - Remove the bonus for VALORANT<br/>
 - Usage: `.levelset voice appbonus <application_name> <min_xp> <max_xp>`
### .levelset voice invisible
Ignore invisible voice users<br/>
Toggle whether invisible users in a voice channel can gain voice XP<br/>
 - Usage: `.levelset voice invisible`
### .levelset voice rolebonus
Add a range of bonus XP to apply to certain roles<br/>

This bonus applies to voice time xp<br/>

Set both min and max to 0 to remove the role bonus<br/>
 - Usage: `.levelset voice rolebonus <role> <min_xp> <max_xp>`
### .levelset voice solo
Ignore solo voice users<br/>
Toggle whether solo users in a voice channel can gain voice XP<br/>
 - Usage: `.levelset voice solo`
## .levelset levelnotify
Send levelup message in the channel the user is typing in<br/>

Send a message in the channel a user is typing in when they level up<br/>
 - Usage: `.levelset levelnotify`
## .levelset starmentiondelete
Toggle whether the bot auto-deletes the star mentions<br/>
Set to 0 to disable auto-delete<br/>
 - Usage: `.levelset starmentiondelete <deleted_after>`
## .levelset defaultbackground
Set the default background for all users in the server<br/>

This background will be used when a user hasn't set their own background.<br/>
You can specify:<br/>
- A URL to an image<br/>
- The name of a background from the backgrounds folder<br/>
- "random" for a random background each time<br/>
- "default" to use Discord banner or random (system default)<br/>

If no background is specified, shows the current default background.<br/>
 - Usage: `.levelset defaultbackground [background]`
## .levelset removexp
Remove XP from a user or role<br/>
 - Usage: `.levelset removexp <user_or_role> <xp>`
## .levelset dm
Toggle DM notifications<br/>

Determines whether LevelUp messages are DM'd to the user<br/>
 - Usage: `.levelset dm`
## .levelset embeds
Toggle using embeds or generated pics<br/>
 - Usage: `.levelset embeds`
## .levelset prestige
Prestige settings<br/>
 - Usage: `.levelset prestige`
### .levelset prestige keeproles
Keep level roles after prestiging<br/>
 - Usage: `.levelset prestige keeproles`
### .levelset prestige remove
Remove a prestige level<br/>
 - Usage: `.levelset prestige remove <prestige>`
 - Aliases: `rem and del`
### .levelset prestige add
Add a role to a prestige level<br/>
 - Usage: `.levelset prestige add <prestige> <role> <emoji>`
 - Checks: `bot_has_server_permissions`
### .levelset prestige stack
Toggle stacking roles on prestige<br/>

**If using dmrole or msgrole**<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages`
 - Aliases: `lvlalerts, levelalerts, lvlmessages, and lvlmsg`
### .levelset levelupmessages msgrole
Set the message sent when a user levels up and recieves a role.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages msgrole [message]`
### .levelset levelupmessages msg
Set the message sent when a user levels up.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
 - Usage: `.levelset levelupmessages msg [message]`
### .levelset levelupmessages dmrole
Set the DM a user gets when they level up and recieve a role.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages dmrole [message]`
### .levelset levelupmessages dm
Set the DM a user gets when they level up (Without recieving a role).<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
 - Usage: `.levelset levelupmessages dm [message]`
### .levelset levelupmessages view
View the current level up alert messages<br/>
 - Usage: `.levelset levelupmessages view`
## .levelset lvlreq
Manage level requirement for commands
### .levelset lvlreq add
Add a level requirement to the command
- Usage: `.levelset lvlreq add <level> <command>`
### .levelset lvlreq del
Remove a level requirement for a command
- Usage: `.levelset lvlreq del <command>`
### .levelset lvlreq list
List all commands and their level requirements
- Usage: `.levelset lvlreq list`
## .levelset cooldowns
Manage per level command cooldowns
### .levelset cooldowns add
Add a cooldown for a command based on level
Multiple cooldown levels can be set, the cooldown will be applied to members at the specified level and under
Warning: This will override any default cooldowns for the command

Example:
.lset cooldowns add 5 15 mycommand
.lset cooldowns add 10 5 mycommand
Members who are level [0, 5] will have a cooldown of 15 seconds for mycommand (including members at level 5)
Members who are level (5, 10] will have a cooldown of 5 seconds (level 6 to level 10)
Members above level 10 will have no cooldown
- Usage: `.levelset cooldowns add <level> <cooldown> <command>`
### .levelset cooldowns del
Remove a level cooldown for a command
- Usage: `.levelset cooldowns del <level> <command>`
### .levelset cooldowns list
List all commands and their cooldowns per level
- Usage: `.levelset cooldowns list`
## .levelset view
View all LevelUP settings<br/>
 - Usage: `.levelset view`
## .levelset addxp
Add XP to a user or role<br/>
 - Usage: `.levelset addxp <user_or_role> <xp>`
## .levelset setlevel
Set a user's level<br/>

Use the command with a role already in the ignore list to remove it<br/>
 - Usage: `.levelset ignore role <role>`
### .levelset ignore channel
Add/Remove a channel in the ignore list<br/>
Channels in the ignore list don't gain XP<br/>

Use the command with a channel already in the ignore list to remove it<br/>
 - Usage: `.levelset ignore channel <channel>`
### .levelset ignore user
Add/Remove a user in the ignore list<br/>
Members in the ignore list don't gain XP<br/>

Use the command with a user already in the ignore list to remove them<br/>
 - Usage: `.levelset ignore user <user>`
## .levelset seelevels
Test the level algorithm<br/>
View the first 20 levels using the current algorithm to test experience curve<br/>
 - Usage: `.levelset seelevels`
## .levelset starcooldown
Set the star cooldown<br/>

Users can give another user a star every X seconds<br/>
 - Usage: `.levelset starcooldown <seconds>`
## .levelset resetemojis
Reset the emojis to default<br/>
 - Usage: `.levelset resetemojis`
## .levelset setprestige
Set a user to a specific prestige level<br/>

Prestige roles will need to be manually added/removed when using this command<br/>
 - Usage: `.levelset setprestige <user> <prestige>`
## .levelset messages
Message settings<br/>
 - Usage: `.levelset messages`
 - Aliases: `message and msg`
### .levelset messages length
Set minimum message length for XP<br/>
Minimum length a message must be to count towards XP gained<br/>

Set to 0 to disable<br/>
 - Usage: `.levelset messages length <length>`
### .levelset messages xp
Set message XP range<br/>

Set the Min and Max amount of XP that a message can gain<br/>
Default is 3 min and 6 max<br/>
 - Usage: `.levelset messages xp <min_xp> <max_xp>`
### .levelset messages channelbonus
Add a range of bonus XP to apply to certain channels<br/>

This bonus applies to message xp<br/>

Set both min and max to 0 to remove the channel bonus<br/>
 - Usage: `.levelset messages channelbonus <channel> <min_xp> <max_xp>`
### .levelset messages rolebonus
Add a range of bonus XP to apply to certain roles<br/>

This bonus applies to message xp<br/>

Set both min and max to 0 to remove the role bonus<br/>
 - Usage: `.levelset messages rolebonus <role> <min_xp> <max_xp>`
### .levelset messages appbonus
Add a range of bonus XP to users running a specific application/game<br/>

This bonus applies to message xp<br/>

Set both min and max to 0 to remove the application bonus<br/>

**Examples:**<br/>
• `.levelset messages appbonus VALORANT 5 10` - Users playing VALORANT get 5-10 bonus XP per message<br/>
• `.levelset messages appbonus "Visual Studio Code" 2 4` - Use quotes for names with spaces<br/>
• `.levelset messages appbonus VALORANT 0 0` - Remove the bonus for VALORANT<br/>
 - Usage: `.levelset messages appbonus <application_name> <min_xp> <max_xp>`
### .levelset messages cooldown
Cooldown threshold for message XP<br/>

When a user sends a message they will have to wait X seconds before their message<br/>
counts as XP gained<br/>
 - Usage: `.levelset messages cooldown <cooldown>`
## .levelset rolegroup
Add or remove a role to the role group<br/>

These roles gain their own experience points as a group<br/>
When a member gains xp while having this role, the xp they earn is also added to the role group<br/>
 - Usage: `.levelset rolegroup <role>`
## .levelset levelnotify
Send levelup message in the channel the user is typing in<br/>

Send a message in the channel a user is typing in when they level up<br/>
 - Usage: `.levelset levelnotify`
## .levelset commandxp
Toggle whether users can gain Exp from running commands<br/>
 - Usage: `.levelset commandxp`
## .levelset allowed
Base command for all allowed lists<br/>
 - Usage: `.levelset allowed`
### .levelset allowed role
Add/Remove a role in the allowed list<br/>
If the allow list is not empty, only roles in the list will gain XP<br/>

Use the command with a role already in the allowed list to remove it<br/>
 - Usage: `.levelset allowed role <role>`
### .levelset allowed channel
Add/Remove a channel in the allowed list<br/>
If the allow list is not empty, only channels in the list will gain XP<br/>

Use the command with a channel already in the allowed list to remove it<br/>
 - Usage: `.levelset allowed channel <channel>`
## .levelset dm
Toggle DM notifications<br/>

Determines whether LevelUp messages are DM'd to the user<br/>
 - Usage: `.levelset dm`
## .levelset starmention
Toggle star reaction mentions<br/>
Toggle whether the bot mentions that a user reacted to a message with a star<br/>
 - Usage: `.levelset starmention`
## .levelset seelevels
Test the level algorithm<br/>
View the first 20 levels using the current algorithm to test experience curve<br/>
 - Usage: `.levelset seelevels`
## .levelset ignore
Base command for all ignore lists<br/>
 - Usage: `.levelset ignore`
### .levelset ignore channel
Add/Remove a channel in the ignore list<br/>
Channels in the ignore list don't gain XP<br/>

Use the command with a channel already in the ignore list to remove it<br/>
 - Usage: `.levelset ignore channel <channel>`
### .levelset ignore notify
Add/Remove a channel in the notify ignore list<br/>
Channels in the notify ignore list will have level up notifications suppressed<br/>

Use the command with a channel already in the notify ignore list to remove it<br/>
 - Usage: `.levelset ignore notify <channel>`
### .levelset ignore role
Add/Remove a role in the ignore list<br/>
Members with roles in the ignore list don't gain XP<br/>

Use the command with a role already in the ignore list to remove it<br/>
 - Usage: `.levelset ignore role <role>`
### .levelset ignore user
Add/Remove a user in the ignore list<br/>
Members in the ignore list don't gain XP<br/>

This command is for if you added level roles after users have achieved that level,<br/>
it will apply all necessary roles to a user according to their level and prestige<br/>
 - Usage: `.levelset roles initialize`
 - Aliases: `init`
 - Cooldown: `1 per 240.0 seconds`
### .levelset roles autoremove
Automatic removal of previous level roles<br/>
 - Usage: `.levelset roles autoremove`
### .levelset roles remove
Unassign a role from a level<br/>
 - Usage: `.levelset roles remove <level>`
 - Aliases: `rem and del`
### .levelset roles add
Assign a role to a level<br/>
 - Usage: `.levelset roles add <level> <role>`
## .levelset algorithm
Customize the leveling algorithm for your server<br/>
• Default base is 100<br/>
• Default exp is 2<br/>

**Equation**<br/>
➣ Getting required XP for a level<br/>
• `base * (level ^ exp) = XP`<br/>
➣ Getting required level for an XP value<br/>
• `level = (XP / base) ^ (1 / exp)`<br/>

**Arguments**<br/>
➣ `part` - The part of the algorithm to change<br/>
➣ `value` - The value to set it to<br/>
 - Usage: `.levelset algorithm <part> <value>`
 - Aliases: `algo`
## .levelset rolegroup
Add or remove a role to the role group<br/>

These roles gain their own experience points as a group<br/>
When a member gains xp while having this role, the xp they earn is also added to the role group<br/>
 - Usage: `.levelset rolegroup <role>`
## .levelset forcestyle
Force a profile style for all users<br/>

Specify `none` to disable the forced style<br/>
 - Usage: `.levelset forcestyle <style>`
## .levelset levelchannel
Set LevelUp log channel<br/>

Set a channel for all level up messages to send to.<br/>

If level notify is off and mention is on, the bot will mention the user in the channel<br/>
 - Usage: `.levelset levelchannel [channel=None]`
## .levelset mention
Toggle whether to mention the user in the level up message<br/>

If level notify is on AND a log channel is set, the user will only be mentioned in the channel they are in.<br/>
 - Usage: `.levelset mention`
## .levelset starmention
Toggle star reaction mentions<br/>
Toggle whether the bot mentions that a user reacted to a message with a star<br/>
 - Usage: `.levelset starmention`
## .levelset presencebonus
Presence status bonus settings<br/>
 - Usage: `.levelset presencebonus`
 - Aliases: `statusbonus`
### .levelset presencebonus voice
Add a range of bonus XP to users with a specific presence status<br/>

This bonus applies to voice time XP<br/>

Set both min and max to 0 to remove the status bonus<br/>

**Examples:**<br/>
• `.levelset presencebonus voice online 2 5` - Users with online status get 2-5 bonus XP per minute in voice<br/>
• `.levelset presencebonus voice idle 1 3` - Users with idle status get 1-3 bonus XP per minute in voice<br/>
• `.levelset presencebonus voice dnd 0 0` - Remove the bonus for dnd status<br/>
 - Usage: `.levelset presencebonus voice <status> <min_xp> <max_xp>`
### .levelset presencebonus view
View all presence status bonuses<br/>
 - Usage: `.levelset presencebonus view`
### .levelset presencebonus message
Add a range of bonus XP to users with a specific presence status<br/>

This bonus applies to message XP<br/>

Set both min and max to 0 to remove the status bonus<br/>

**Examples:**<br/>
• `.levelset presencebonus message online 2 5` - Users with online status get 2-5 bonus XP per message<br/>
• `.levelset presencebonus message idle 1 3` - Users with idle status get 1-3 bonus XP per message<br/>
• `.levelset presencebonus message dnd 0 0` - Remove the bonus for dnd status<br/>
 - Usage: `.levelset presencebonus message <status> <min_xp> <max_xp>`
 - Aliases: `msg`
## .levelset view
View all LevelUP settings<br/>
 - Usage: `.levelset view`
## .levelset addxp
Add XP to a user or role<br/>
 - Usage: `.levelset addxp <user_or_role> <xp>`
## .levelset emojis
Set the emojis used to represent each stat type<br/>
 - Usage: `.levelset emojis <level> <prestige> <star> <chat> <voicetime> <experience> <balance>`
## .levelset setlevel
Set a user's level<br/>

**Arguments**<br/>
• `user` - The user to set the level for<br/>
• `level` - The level to set the user to<br/>
 - Usage: `.levelset setlevel <user> <level>`
## .levelset allowed
Base command for all allowed lists<br/>
 - Usage: `.levelset allowed`
### .levelset allowed channel
Add/Remove a channel in the allowed list<br/>
If the allow list is not empty, only channels in the list will gain XP<br/>

Use the command with a channel already in the allowed list to remove it<br/>
 - Usage: `.levelset allowed channel <channel>`
### .levelset allowed role
Add/Remove a role in the allowed list<br/>
If the allow list is not empty, only roles in the list will gain XP<br/>

Use the command with a role already in the allowed list to remove it<br/>
 - Usage: `.levelset allowed role <role>`
## .levelset commandxp
Toggle whether users can gain Exp from running commands<br/>
 - Usage: `.levelset commandxp`
## .levelset levelupmessages
Level up alert messages<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>

**If using dmrole or msgrole**<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages`
 - Aliases: `lvlalerts, levelalerts, lvlmessages, and lvlmsg`
### .levelset levelupmessages dm
Set the DM a user gets when they level up (Without recieving a role).<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
 - Usage: `.levelset levelupmessages dm [message]`
### .levelset levelupmessages msg
Set the message sent when a user levels up.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
 - Usage: `.levelset levelupmessages msg [message]`
### .levelset levelupmessages msgrole
Set the message sent when a user levels up and recieves a role.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages msgrole [message]`
### .levelset levelupmessages dmrole
Set the DM a user gets when they level up and recieve a role.<br/>

**Arguments**<br/>
The following placeholders can be used:<br/>
• `{username}`: The user's name<br/>
• `{mention}`: Mentions the user<br/>
• `{displayname}`: The user's display name<br/>
• `{level}`: The level the user just reached<br/>
• `{server}`: The server the user is in<br/>
• `{role}`: The role the user just recieved<br/>
 - Usage: `.levelset levelupmessages dmrole [message]`
### .levelset levelupmessages view
View the current level up alert messages<br/>
 - Usage: `.levelset levelupmessages view`
## .levelset showbalance
Toggle whether to show user's economy credit balance in their profile<br/>
 - Usage: `.levelset showbalance`
 - Aliases: `showbal`
