---
title: Custom Help Commands
description: 
published: true
date: 2024-08-25T19:11:52.984Z
tags: 
editor: markdown
dateCreated: 2024-08-25T19:11:51.630Z
---

# CustomHelp Help

A custom customisable help for fun and profit

# .chelp
Configure your custom help<br/>
 - Usage: `.chelp`
 - Restricted to: `BOT_OWNER`
## .chelp refresh
Force refresh the list of categories, This would reset all the uninstalled/unloaded cogs and will put them into uncategorised.<br/>
 - Usage: `.chelp refresh`
## .chelp edit
Add reactions and descriptions to the category<br/>
 - Usage: `.chelp edit [yaml_txt]`
## .chelp load
Load another preset theme.<br/>
Use `.chelp load <theme> all` to load everything from that theme<br/>
 - Usage: `.chelp load <theme> <feature>`
## .chelp reset
Resets all settings to default **custom** help <br/>
use `.chelp set 0` to revert back to the old help<br/>
 - Usage: `.chelp reset`
## .chelp info
Short info about various themes<br/>
 - Usage: `.chelp info`
## .chelp unload
Unloads the given feature, this will reset to default<br/>
 - Usage: `.chelp unload <feature>`
## .chelp listthemes
List the themes and available features<br/>
 - Usage: `.chelp listthemes`
 - Aliases: `getthemes`
## .chelp create
Create a new category to add cogs to it using yaml<br/>
 - Usage: `.chelp create [yaml_txt]`
 - Aliases: `add`
## .chelp nsfw
Add categories to nsfw, only displayed in nsfw channels<br/>
 - Usage: `.chelp nsfw`
### .chelp nsfw remove
Remove categories from the nsfw list<br/>
 - Usage: `.chelp nsfw remove <category>`
### .chelp nsfw add
Add categories to the nsfw list<br/>
 - Usage: `.chelp nsfw add <category>`
## .chelp reorder
This can be used to reorder the categories.<br/>

The categories you type are pushed forward while the rest are pushed back.<br/>
 - Usage: `.chelp reorder [categories]`
## .chelp list
Show the list of categories and the cogs in them<br/>
 - Usage: `.chelp list`
## .chelp remove
Remove categories/cogs or everything<br/>
 - Usage: `.chelp remove`
### .chelp remove category
Remove a multiple categories<br/>
 - Usage: `.chelp remove category <categories>`
 - Aliases: `categories and cat`
### .chelp remove all
This will delete all the categories<br/>
 - Usage: `.chelp remove all`
### .chelp remove cog
Remove a cog(s) from across categories<br/>
 - Usage: `.chelp remove cog <cog_raw_names>`
 - Aliases: `cogs`
## .chelp dev
Add categories to dev, only displayed to the bot owner(s)<br/>
 - Usage: `.chelp dev`
### .chelp dev add
Add categories to the dev list<br/>
 - Usage: `.chelp dev add <category>`
### .chelp dev remove
Remove categories from the dev list<br/>
 - Usage: `.chelp dev remove <category>`
## .chelp toggle
Set to toggle custom formatter or the default help formatter<br/>
`.chelp toggle 0` to turn custom off <br/>
`.chelp toggle 1` to turn it on<br/>
 - Usage: `.chelp toggle <setval>`
## .chelp set
Change various help settings<br/>
 - Usage: `.chelp set`
 - Aliases: `settings and setting`
### .chelp set thumbnail
Set your main thumbnail image here.<br/>
use `.chelp settings thumbnail` to reset this<br/>
 - Usage: `.chelp set thumbnail [url=None]`
 - Aliases: `setthumbnail`
### .chelp set type
Toggles between various menus and arrow types<br/>
 - Usage: `.chelp set type`
### .chelp set usereply
Enable/Disable replies<br/>
 - Usage: `.chelp set usereply <option>`
 - Aliases: `usereplies and reply`
### .chelp set timeout
Set how long the help menu must stay active<br/>
 - Usage: `.chelp set timeout <wait>`
### .chelp set deletemessage
Delete the user message that started the help menu.<br/>
Note: This only works if the bot has permissions to delete the user message, otherwise it's supressed<br/>
 - Usage: `.chelp set deletemessage <toggle>`
 - Aliases: `deleteusermessage`
### .chelp set arrows
Add custom arrows for fun and profit<br/>
 - Usage: `.chelp set arrows [correct_txt]`
 - Aliases: `arrow`
### .chelp set nav
Enable/Disable navigation arrows<br/>
Disabling this removes every trace of arrows and you can't move to the next page<br/>
People wanted this for some reason lol<br/>
 - Usage: `.chelp set nav <option>`
## .chelp show
Show the current help settings<br/>
 - Usage: `.chelp show`
## .chelp auto
Auto categorise cogs based on it's tags and display them<br/>
 - Usage: `.chelp auto`
# .findcategory
Get the category where the command is present<br/>
 - Usage: `.findcategory <command>`
 - Aliases: `findcat`
