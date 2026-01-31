---
title: ArkTools Commands
description: 
published: true
date: 2024-08-25T22:44:43.179Z
tags: cogs, arktools, ark, commands
editor: markdown
dateCreated: 2024-04-16T01:23:23.026Z
---



AIO server manager for Ark: Survival Evolved!

# /quickbuy (Slash Command)
Quickly buy an item from the Rshop!<br/>
 - Usage: `/quickbuy <item> [quantity] [quality] [blueprint]`
 - `item:` (Required) The item you want to buy
 - `quantity:` (Optional) The quantity of the item you want to buy
 - `quality:` (Optional) The quality of the item you want to buy
 - `blueprint:` (Optional) Whether or not the item is a blueprint

 - Checks: `Server Only`
# /bulksend (Slash Command)
…<br/>
 - Usage: `/bulksend <cluster> <server> <implant> <item> <amount> <runcount> [quality] [blueprint]`
 - `cluster:` (Required) The cluster to send the item to
 - `server:` (Required) The server to send the item to
 - `implant:` (Required) The specimen # to send the item to
 - `item:` (Required) The item to send
 - `amount:` (Required) How many items to send in each run
 - `runcount:` (Required) How many times to run the command
 - `quality:` (Optional) The quality of the item to send
 - `blueprint:` (Optional) Whether the item is a blueprint

 - Checks: `Server Only`
# .serverstatus
Server status channel settings<br/>
 - Usage: `.serverstatus`
 - Restricted to: `ADMIN`
## .serverstatus time
Set the status graph timedelta<br/>
 - Usage: `.serverstatus time <seconds>`
## .serverstatus channel
Set the status channel for your Ark servers<br/>
 - Usage: `.serverstatus channel <channel>`
# .registerplayer (Hybrid Command)
Register another user to the database.<br/>
 - Usage: `.registerplayer <member> <gameid> [overwrite=False]`
 - Slash Usage: `/registerplayer <member> <gameid> [overwrite=False]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .setplayerimplant (Hybrid Command)
Set the implant number for a player.<br/>
 - Usage: `.setplayerimplant <gameid> <implant>`
 - Slash Usage: `/setplayerimplant <gameid> <implant>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .register (Hybrid Command)
Register your in-game account with the database.<br/>
 - Usage: `.register [username]`
 - Slash Usage: `/register [username]`
 - Checks: `server_only`
# .addme
(Xbox/Win10 CROSSPLAY ONLY)Add yourself as a friend<br/>

Make the host Gamertags add you as a friend<br/>

This command requires api keys to be set for the servers<br/>
 - Usage: `.addme`
 - Checks: `server_only`
# .addplayer
(Xbox/Win10 CROSSPLAY ONLY) Add a player to a host Gamertag's friends list<br/>

This command requires api keys to be set for the servers<br/>
 - Usage: `.addplayer <player>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .unregisterplayer
Unlink the discord account from a player<br/>

The optional **player** argument can be one of the following.<br/>
- Gamertag or Steam Username<br/>
- XUID or Steam ID<br/>
- Discord ID or Username<br/>
- @mention<br/>
 - Usage: `.unregisterplayer <player>`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .unregister
Unregister yourself<br/>

Removes you from any Gamertags you have registered to<br/>
 - Usage: `.unregister`
 - Aliases: `unregisterme`
 - Checks: `server_only`
# .specimen
Set your specimen number to use the Rshop<br/>

Your specimen number (aka Implant ID) can be found in the top left of your player inventory.<br/>
 - Usage: `.specimen <specimen_number>`
 - Aliases: `implant, speciment, implantid, and specimen#`
 - Checks: `server_only`
# .viewservers
Open the main menu for server management<br/>
 - Usage: `.viewservers`
 - Restricted to: `ADMIN`
 - Aliases: `ark`
# .addcluster
Create a cluster to add servers to<br/>

**Example**:  `.addcluster mycluster #joins #leaves #admin-logs #global-chat`<br/>
 - Usage: `.addcluster <name> <join_channel> <leave_channel> <admin_log_channel> <globalchat_channel>`
 - Restricted to: `ADMIN`
# .delcluster
Delete a cluster<br/>
 - Usage: `.delcluster <cluster_name>`
 - Restricted to: `ADMIN`
 - Aliases: `remcluster`
# .addserver
Add a server to a cluster<br/>

**Example**:  `.addserver mycluster #chat`<br/>
 - Usage: `.addserver <cluster_name> <chat_channel>`
 - Restricted to: `ADMIN`
# .delserver
Delete a server<br/>
 - Usage: `.delserver <cluster_name> <server_name>`
 - Restricted to: `ADMIN`
 - Aliases: `remserver`
# .lootbox
Open a lootbox<br/>
 - Usage: `.lootbox`
 - Aliases: `lootcrate`
 - Checks: `server_only`
# .lootboxset
Setup the lootbox system<br/>
 - Usage: `.lootboxset`
 - Restricted to: `ADMIN`
 - Aliases: `lbs`
## .lootboxset simulate
Simulate opening a lootbox X times and generate a summary of selections.<br/>
 - Usage: `.lootboxset simulate [times=100]`
 - Aliases: `sim`
## .lootboxset logchannel
Set the lootbox log channel<br/>
 - Usage: `.lootboxset logchannel <channel>`
## .lootboxset template
Get an example Excel file for the lootbox system<br/>
 - Usage: `.lootboxset template`
## .lootboxset view
View general lootbox settings<br/>
 - Usage: `.lootboxset view`
## .lootboxset add
Quickly add an item to the lootbox system<br/>
 - Usage: `.lootboxset add <chance> <quality> <quantity> <blueprint> <stacksize> <path> <name>`
## .lootboxset cooldown
Set the lootbox cooldown<br/>
 - Usage: `.lootboxset cooldown <cooldown>`
## .lootboxset price
Set the price of a lootbox<br/>

0 Will make the loot box free<br/>
 - Usage: `.lootboxset price <price>`
## .lootboxset download
Get the current lootboxes as an Excel file<br/>
 - Usage: `.lootboxset download`
## .lootboxset upload
Set the lootbox items<br/>
 - Usage: `.lootboxset upload`
# .dshopset
Setup the DATA shop<br/>
 - Usage: `.dshopset`
 - Restricted to: `ADMIN`
 - Aliases: `dss`
## .dshopset datapath
Set the path where data packs are stored<br/>
 - Usage: `.dshopset datapath <path>`
 - Restricted to: `BOT_OWNER`
## .dshopset clusterpath
Set the path to a cluster folder<br/>
 - Usage: `.dshopset clusterpath <cluster_name> <path>`
## .dshopset template
Get a shop template to start adding items<br/>
 - Usage: `.dshopset template`
## .dshopset view
View dshop settings<br/>
 - Usage: `.dshopset view`
## .dshopset download
Download your existing items to an Excel file for updating the data shop<br/>
 - Usage: `.dshopset download`
## .dshopset upload
Upload your Excel file to update the data shop<br/>
 - Usage: `.dshopset upload`
# .dshop (Hybrid Command)
Open the DATA shop<br/>

**Arguments**<br/>
`search_query: `Search directly for an item<br/>
 - Usage: `.dshop [search_query]`
 - Slash Usage: `/dshop [search_query]`
 - Checks: `server_only`
# .rshopset
Setup the RCON shop<br/>
 - Usage: `.rshopset`
 - Restricted to: `ADMIN`
 - Aliases: `rss`
## .rshopset upload
Upload your Excel file to update the rshop<br/>
 - Usage: `.rshopset upload`
## .rshopset maxquality
Set the maximum quality a user can specify when buying an item<br/>
 - Usage: `.rshopset maxquality <max_quality>`
## .rshopset readstacks
Upload your Game.ini file to set any custom stack sizes your server has<br/>
 - Usage: `.rshopset readstacks`
## .rshopset delimiter
Set the delimiter for pack items in the shop (Default: `,`)<br/>

This is used to separate multiple blueprint paths or commands in a single cell for the Packs sheet<br/>
 - Usage: `.rshopset delimiter <delimiter>`
## .rshopset download
Get the current rcon shop settings as an Excel file<br/>
 - Usage: `.rshopset download`
## .rshopset discountdays
Set the discount for each day of the week<br/>
**Day**<br/>
0 - Monday<br/>
1 - Tuesday<br/>
2 - Wednesday<br/>
3 - Thursday<br/>
4 - Friday<br/>
5 - Saturday<br/>
6 - Sunday<br/>

*Set the discount to 0 for a day to disable it*<br/>
 - Usage: `.rshopset discountdays <day> <discount>`
 - Aliases: `discountday and dd`
## .rshopset discountrole
Add/Remove discounts for specific roles<br/>

*Set the discount to 0 to remove the role from the discount list*<br/>
 - Usage: `.rshopset discountrole <role> <discount>`
## .rshopset template
Get a shop template to start adding items<br/>
 - Usage: `.rshopset template`
## .rshopset reprice
Recalculate shop prices based on the provided Excel file<br/>

The excel file should have a sheet named `base_prices` with columns (resource, price)<br/>
It must consist of all items used to craft something that cannot be broken down further<br/>
 - Usage: `.rshopset reprice`
## .rshopset view
View general shop settings<br/>
 - Usage: `.rshopset view`
## .rshopset discount
Set a static discount for the shop<br/>
 - Usage: `.rshopset discount <discount>`
## .rshopset bpmultiplier
Set the blueprint multiplier for item purchases<br/>
 - Usage: `.rshopset bpmultiplier <blueprint_multiplier>`
## .rshopset qualityexp
Set the quality exponent multiplier for the rcon shop<br/>
 - Usage: `.rshopset qualityexp <exponent>`
# .rshop (Hybrid Command)
Open the RCON shop<br/>

**Arguments**<br/>
`item: `Search directly for an item<br/>
 - Usage: `.rshop [item]`
 - Slash Usage: `/rshop [item]`
 - Checks: `server_only`
# .shopstats (Hybrid Command)
Displays a user's shop purchases and statistics.<br/>

If a Discord user is specified, it will show the stats for that user.<br/>
Otherwise, it will show the stats for the author of the command.<br/>
 - Usage: `.shopstats [user=None]`
 - Slash Usage: `/shopstats [user=None]`
 - Checks: `server_only`
# .shopoverview (Hybrid Command)
Displays a comprehensive analysis of shop purchases for the server.<br/>
 - Usage: `.shopoverview`
 - Slash Usage: `/shopoverview`
 - Checks: `server_only`
# .checkpathperms
Ensure the data paths for all clusters have the correct permissions<br/>

This will check each of the Dshop data paths and ensure the bot can read/write to them<br/>
 - Usage: `.checkpathperms`
 - Restricted to: `BOT_OWNER`
# .checkdata
Check a player's in-game data<br/>

If file size is anything other than 0, then there is something in their data.<br/>

The optional **player** argument can be one of the following.<br/>
- Gamertag or Steam Username<br/>
- XUID or Steam ID<br/>
- Discord ID or Username<br/>
- @mention<br/>
 - Usage: `.checkdata <player>`
 - Restricted to: `MOD`
 - Checks: `bot_has_server_permissions`
# .wipedata
Wipe a players Ark data<br/>
 - Usage: `.wipedata <gameid>`
 - Restricted to: `ADMIN`
# .copydata
Copy a players ark data to your own.<br/>

useful for checking other players data for various reasons<br/>

**Arguments**<br/>
- `cluster_name`: the path to search in<br/>
- `gameid_to_copy`: the gameid<br/>
 - Usage: `.copydata <gameid_to_copy> <cluster_name>`
 - Restricted to: `ADMIN`
# .pulldata
Pull a players Ark data into discord as a file<br/>
 - Usage: `.pulldata <gameid> <cluster_name>`
 - Restricted to: `ADMIN`
# .insert
Insert an Ark data file into a cluster<br/>
 - Usage: `.insert <gameid> <cluster_name>`
 - Restricted to: `ADMIN`
# .makepack
Upload/Create a pre-made pack from your ark data.<br/>

Pack name will be the actual file name<br/>
This will take your current ark data and make a pack out of it<br/>
If the pack name already exists, it will be overwritten by the new pack<br/>
 - Usage: `.makepack <packname>`
 - Restricted to: `ADMIN`
 - Aliases: `make`
# .sendpack
Send a data pack to an XUID<br/>
 - Usage: `.sendpack <gameid> <packname>`
 - Restricted to: `ADMIN`
# .renamepack
Rename a data pack<br/>
 - Usage: `.renamepack <current_name> <new_name>`
 - Restricted to: `ADMIN`
# .delpack
Delete a data pack<br/>
 - Usage: `.delpack <packname>`
 - Restricted to: `ADMIN`
# .listpacks
List data packs in the main path as well as their file size<br/>

Arguments<br/>
-unused_only: if true, only includes packs not currently in-use.<br/>
 - Usage: `.listpacks <unused_only>`
 - Restricted to: `ADMIN`
# .tribe (Hybrid Command)
Open the tribe menu!<br/>
 - Usage: `.tribe [user]`
 - Slash Usage: `/tribe [user]`
 - Aliases: `mytribe`
# .kicktribemate (Hybrid Command)
Kick a member from your tribelog thread<br/>
 - Usage: `.kicktribemate <member>`
 - Slash Usage: `/kicktribemate <member>`
 - Aliases: `kickmate and kickfromtribelogs`
# .tribeset
Configure tribe settings<br/>
 - Usage: `.tribeset`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
## .tribeset logchannel
Set master tribelogs for a cluster<br/>
 - Usage: `.tribeset logchannel <clustername> <channel>`
## .tribeset claimchannel
Set the channel that private tribelogs threads will be created from<br/>
 - Usage: `.tribeset claimchannel <channel>`
## .tribeset claimrole
Add/Remove roles that can claim their tribes<br/>
 - Usage: `.tribeset claimrole <role>`
## .tribeset view
View tribe settings<br/>
 - Usage: `.tribeset view`
## .tribeset resetclaims
Wipe the threads from the claimlog channel and reset all claimed tribes<br/>
 - Usage: `.tribeset resetclaims <confirm>`
# .viewsysinfo
View data about the system running your servers<br/>
 - Usage: `.viewsysinfo`
 - Restricted to: `ADMIN`
 - Cooldown: `1 per 60.0 seconds`
 - Checks: `server_only`
# .datadump
Get a json dump of the specified data type from ArkView<br/>
 - Usage: `.datadump <datatype>`
 - Restricted to: `ADMIN`
 - Cooldown: `1 per 10.0 seconds`
 - Checks: `server_only`
# .syncbans
Sync the banlists for all servers<br/>

- Bans from each map will be synced to all other maps related to the same game type (ASA or ASE)<br/>
- Anyone in the ban database that isn't in the server banlist will be re-banned<br/>
- Anyone in the server banlist that isn't in the database will be added<br/>

-# Ban entries will not be created for game IDs that are not in the database<br/>
 - Usage: `.syncbans`
 - Restricted to: `ADMIN`
 - Cooldown: `1 per 60.0 seconds`
 - Checks: `server_only`
# .setvalidservers
Comma separated list of valid server names for this server, any servers not in this list will be flagged when a tame is transferred to them<br/>
 - Usage: `.setvalidservers <valid_names>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .scanforeigntames
Scan all servers for tames that are from a server not in the valid server list<br/>
 - Usage: `.scanforeigntames`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .checkmassbreed
Detect if and where mass breeding is taking place<br/>

This command will detect dense clusters of dinos with mating enabled in order to<br/>
detect if players have left a bunch of dinos with breeding enabled<br/>

A list of "dino clusters" will be returned with coordinates for each cluster and a map of the locations<br/>

**Arguments**<br/>
- **threshold**: the max latitude/longitude between any two dinos<br/>
- **min_dinos**: the minimum amount of mating enabled dinos within the area to be considered "mass breeding"<br/>
 - Usage: `.checkmassbreed [threshold=0.5] [min_dinos=6]`
 - Restricted to: `ADMIN`
 - Aliases: `massbreed`
 - Checks: `server_only`
# .findplayer (Hybrid Command)
Find the location and tribe of a player in-game<br/>

`search_query` can be one of the following.<br/>
Player's in-game name<br/>
Gamertag or Username<br/>
Specimen number (exact matches only)<br/>
XUID or SteamID (exact matches only)<br/>
Tribe ID (exact matches only)<br/>
 - Usage: `.findplayer <search_query>`
 - Slash Usage: `/findplayer <search_query>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .findtribe
Find details of a tribe<br/>

`search_query` can be one of the following.<br/>
- Tribe name<br/>
- Tribe ID (exact matches only)<br/>
- Player's in-game name<br/>
- Gamertag or Username<br/>
- Specimen number (exact matches only)<br/>
- XUID or SteamID (exact matches only)<br/>

If any tribes have the player info found in them, they will be shown<br/>
 - Usage: `.findtribe <search_query>`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .structures (Hybrid Command)
Get a marker map of structures for a tribe<br/>

`search_query` can be one of the following.<br/>
- Tribe name<br/>
- Tribe ID (exact matches only)<br/>
 - Usage: `.structures <search_query>`
 - Slash Usage: `/structures <search_query>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .findstructure (Hybrid Command)
Get a marker map of specific structures for a tribe or the whole map<br/>

`structure_class` is the class name of the structure you want to search for.<br/>
- e.g. "CookingPot_C" or "StructureTurretTek_C<br/>

`search_query` can be one of the following.<br/>
- Tribe name<br/>
- Tribe ID (exact matches only)<br/>
 - Usage: `.findstructure <structure_class> [search_query=None]`
 - Slash Usage: `/findstructure <structure_class> [search_query=None]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .structuregraph
Visualize controlled areas of a server by tribe.<br/>
 - Usage: `.structuregraph`
 - Restricted to: `ADMIN`
 - Cooldown: `1 per 45.0 seconds`
 - Checks: `server_only`
# .territory
Visualize controlled areas of a server by tribe.<br/>
 - Usage: `.territory [include_other=False] [dotsize=15]`
 - Restricted to: `ADMIN`
 - Cooldown: `1 per 45.0 seconds`
 - Checks: `server_only`
# .findexpired
Get a list of tribes that haven't been active for more than X days<br/>

Example: .findexpired 60<br/>
this will show tribes inactive for 60 days or more that have at least 1 structure or tame<br/>
 - Usage: `.findexpired <days>`
 - Restricted to: `MOD`
 - Aliases: `expired`
 - Checks: `server_only`
# .wipetribes
Wipe all tribes that haven't been active for X days or more<br/>

This will delete all their tames, structures, and players<br/>
 - Usage: `.wipetribes <days>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .sortdinos
Find all dinos above or equal to the specified level<br/>
 - Usage: `.sortdinos <level> [dino_name]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .tribesize
Visualize a tribe's controlled territory along with their types of structures and area they take up.<br/>
 - Usage: `.tribesize <search_query>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .finditem
Search for a specific item on a map<br/>
 - Usage: `.finditem <item_blueprint> [tribe_id=None]`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .itemsearch
Find information about an item across all maps<br/>
 - Usage: `.itemsearch <item_blueprint> [tribe_id=None]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .tamestatcheck
Find tames over a certain stat level for a given stat<br/>

**Arguments**<br/>
    - `<stat>` The stat to search for (hp, stam, melee, weight, speed, food, oxy)<br/>
    - `<points>` The number of points to search for<br/>
    - `[stat_type]` The type of stat to search for (wild or tamed)<br/>
 - Usage: `.tamestatcheck <stat> <points> [stat_type=tamed]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .uncryocheck
Get a list of tribes who's uncryo'd tame count is above the specified amount<br/>
 - Usage: `.uncryocheck <amount>`
 - Restricted to: `ADMIN`
 - Aliases: `cryocheck`
 - Checks: `server_only`
# .playerheat
Get a heatmap of player locations<br/>
 - Usage: `.playerheat`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .hunt (Hybrid Command)
Hunt for a dino!<br/>

Use the slash version of this command to make it private!<br/>
 - Usage: `.hunt <dino>`
 - Slash Usage: `/hunt <dino>`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .mytames
Check your tribe's tames on a map<br/>
 - Usage: `.mytames`
 - Cooldown: `1 per 20.0 seconds`
 - Checks: `server_only`
# .findtame (Hybrid Command)
Find tames by tame name, imprinter, tamer, or tribe name<br/>

`search_query` can be one of the following.<br/>
The dino's name.<br/>
The name of the person who tamed the dino.<br/>
The name of the person who imprinted on the tame.<br/>
The name of the tribe that owns the dino.<br/>
The ID of the tribe that tamed the dino.<br/>

*You can search for unclaimed dinos by specifying `unclaimed`*<br/>
 - Usage: `.findtame <search_query>`
 - Slash Usage: `/findtame <search_query>`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .mapstats
Get detailed stats for a map<br/>
 - Usage: `.mapstats`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .creaturepie
Get a pie chart of wild dinos on a map<br/>
 - Usage: `.creaturepie [count=10]`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .structurepie
Get pie chart of structures<br/>
 - Usage: `.structurepie [count=10]`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .tamepie
Get a pie chart of tamed dinos on a map<br/>
 - Usage: `.tamepie [count=10]`
 - Cooldown: `1 per 5.0 seconds`
 - Checks: `server_only`
# .arkset
ArkTools configuration<br/>
 - Usage: `.arkset`
 - Restricted to: `ADMIN`
 - Aliases: `arktools`
## .arkset autowelcomemessage
Set the welcome message sent when a new player is found<br/>

Placeholders<br/>
- `{username}` - Player's username<br/>
- `{gameid}` - Player's game ID<br/>
 - Usage: `.arkset autowelcomemessage [message]`
 - Aliases: `welcomemsg`
## .arkset ingame
Configure in-game settings<br/>
 - Usage: `.arkset ingame`
### .arkset ingame setkitpaths
Set the kit paths for a cluster<br/>

Upload a .txt file with the blueprint paths separated by a new line.<br/>

Include the quantity/quality/blueprint numbers after the strings.<br/>

**Example**<br/>
`<blueprint_path> <quantity> <quality> <blueprint 1 or 0>`<br/>
`some/ark_bluerints/to/path/organic_poly_c 5 1 0`<br/>

Do NOT include "cheat" or "admincheat" or "senditemtoplayer" in front of the strings<br/>
 - Usage: `.arkset ingame setkitpaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame payday
Toggle payday rewards for a cluster<br/>
 - Usage: `.arkset ingame payday <cluster_name>`
### .arkset ingame getpaydaypaths
Get the current payday paths for a cluster<br/>
 - Usage: `.arkset ingame getpaydaypaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame paydayrandom
Toggle randomization of payday rewards<br/>
 - Usage: `.arkset ingame paydayrandom <cluster_name>`
 - Aliases: `randompayday`
### .arkset ingame imstuckcooldown
Set cooldown seconds for the imstuck command<br/>
 - Usage: `.arkset ingame imstuckcooldown <seconds> <cluster_name>`
### .arkset ingame setimstuckpaths
Set the imstuck paths for a cluster<br/>
Upload a .txt file with the blueprint paths separated by a new line.<br/>

Include the quantity/quality/blueprint numbers after the strings.<br/>

**Example**<br/>
`<blueprint_path> <quantity> <quality> <blueprint 1 or 0>`<br/>
`some/ark_bluerints/to/path/organic_poly_c 5 1 0`<br/>

Do NOT include "cheat" or "admincheat" or "senditemtoplayer" in front of the strings<br/>
 - Usage: `.arkset ingame setimstuckpaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame getkitpaths
Get the current kit paths for a cluster<br/>
 - Usage: `.arkset ingame getkitpaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame paydaycooldown
Set cooldown seconds for paydays<br/>
 - Usage: `.arkset ingame paydaycooldown <seconds> <cluster_name>`
### .arkset ingame getimstuckpaths
Get the current imstuck paths for a cluster<br/>
 - Usage: `.arkset ingame getimstuckpaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame setpaydaypaths
Set the payday paths for a cluster<br/>
Upload a .txt file with the blueprint paths separated by a new line.<br/>

Include the quantity/quality/blueprint numbers after the strings.<br/>

**Example**<br/>
`<blueprint_path> <quantity> <quality> <blueprint 1 or 0>`<br/>
`some/ark_bluerints/to/path/organic_poly_c 5 1 0`<br/>

Do NOT include "cheat" or "admincheat" or "senditemtoplayer" in front of the strings<br/>
 - Usage: `.arkset ingame setpaydaypaths <cluster_name>`
 - Restricted to: `ADMIN`
### .arkset ingame kit
Toggle new player kit claiming for a cluster<br/>
 - Usage: `.arkset ingame kit <cluster_name>`
### .arkset ingame imstuck
Toggle the imstuck command for a cluster<br/>
 - Usage: `.arkset ingame imstuck <cluster_name>`
## .arkset clustertype
Set the type of ark servers you host<br/>

Valid arguments are `xbox, steam, both`<br/>
 - Usage: `.arkset clustertype <cluster_type>`
## .arkset refundclusterdelta
Refund all purchases made between two times for a cluster<br/>

Time is in ISO format `YYYY-MM-DDTHH:MM:SS`<br/>

**Example**<br/>
`.arkset refundclusterdelta 2024-04-03T20:00:00 2024-05-05T18:00:00 pvp`<br/>
 - Usage: `.arkset refundclusterdelta <start_time> <end_time> <cluster_name>`
## .arkset eventlog
Set the event log<br/>

The logs include the following events:<br/>
- New players that are added to the database<br/>
- Welcome messages sent to new players(if enabled)<br/>
- Old players that are unfriended for inactivity(if enabled)<br/>
- Players that are unfriended for leaving the Discord(if enabled)<br/>
- Players that are unfriended due to unfriending a host Gamertag<br/>
 - Usage: `.arkset eventlog <channel>`
## .arkset initroles
Initialize playtime roles<br/>
 - Usage: `.arkset initroles`
 - Cooldown: `1 per 900.0 seconds`
## .arkset toggleshop
Toggle the shop on/off<br/>
 - Usage: `.arkset toggleshop`
## .arkset commandblacklist
Set forbidden commands<br/>
 - Usage: `.arkset commandblacklist <command>`
## .arkset retention
Set the days worth of playercount data to keep<br/>
 - Usage: `.arkset retention <days>`
## .arkset viewranks
View playtime roles<br/>
 - Usage: `.arkset viewranks`
## .arkset wipeclustertribes
Reset all player tribes for a cluster<br/>
 - Usage: `.arkset wipeclustertribes <cluster_name>`
## .arkset linkrole
Add a playtime role<br/>
 - Usage: `.arkset linkrole <hours> <role>`
## .arkset alertchannel
Set a channel to receive alerts<br/>

The following alerts are sent here:<br/>
- Server goes down<br/>
- Unauthorized admin command in-game<br/>
- Tribe auto-banned for foreign tames<br/>

**These events will fall back to the event log if no alert channel is set**<br/>
 - Usage: `.arkset alertchannel <channel>`
## .arkset unlinkrole
Remove a playtime role<br/>
 - Usage: `.arkset unlinkrole <hours>`
## .arkset wipeclusterstats
Reset all player stats like kills/tames/deaths for a cluster<br/>
 - Usage: `.arkset wipeclusterstats <cluster_name>`
## .arkset wipeclusterimplants
Reset all player's set specimen numbers for a cluster<br/>
 - Usage: `.arkset wipeclusterimplants <cluster_name>`
## .arkset autowelcome
Toggle auto welcoming of new players discovered in-game<br/>
 - Usage: `.arkset autowelcome`
## .arkset view
View ark settings<br/>
 - Usage: `.arkset view`
 - Restricted to: `MOD`
## .arkset regenkey
Generate a new ArkView API key<br/>

**This will overwrite the current key!**<br/>
 - Usage: `.arkset regenkey`
 - Restricted to: `GUILD_OWNER`
## .arkset imposterwhitelist
Whitelist certain game IDs from triggering imposter bans<br/>
 - Usage: `.arkset imposterwhitelist <player_id>`
## .arkset banimposters
Protect your server if anyone discovers your admin password<br/>
 - Usage: `.arkset banimposters`
## .arkset countdown
Set the `doexit` and `dorestartlevel` countdowns<br/>
 - Usage: `.arkset countdown <seconds>`
## .arkset characternameblacklist
Character name blacklist<br/>
 - Usage: `.arkset characternameblacklist <name>`
 - Aliases: `charnameblacklist, charbl, and badname`
## .arkset autoremoverole
Toggle auto-removal of previous playtime role<br/>
 - Usage: `.arkset autoremoverole`
## .arkset refundserverdelta
Refund all purchases made between two times for a server<br/>

Time is in ISO format `YYYY-MM-DDTHH:MM:SS`<br/>

**Example**<br/>
`.arkset refundserverdelta 2024-04-03T20:00:00 2024-05-05T18:00:00 pvp`<br/>
 - Usage: `.arkset refundserverdelta <start_time> <end_time> <server_name> <cluster_name>`
## .arkset shoplog
Set the shop log channel<br/>

All purchases will be logged here<br/>
 - Usage: `.arkset shoplog <channel>`
## .arkset timezone
Set your server's timezone<br/>
 - Usage: `.arkset timezone <timezone>`
## .arkset modcommands
Mod command allow list<br/>
 - Usage: `.arkset modcommands <command>`
 - Aliases: `modcmd`
## .arkset toggleshopcluster
Disable the shop for a specific cluster<br/>
 - Usage: `.arkset toggleshopcluster <cluster_name>`
## .arkset recentlycreated
Get a list of players created after a certain date<br/>

Time is in ISO format `YYYY-MM-DDTHH:MM:SS`<br/>

**Example**<br/>
`.arkset recentlycreated 2024-04-03T20:00:00`<br/>
 - Usage: `.arkset recentlycreated <created_after>`
 - Aliases: `rc`
## .arkset registerrole
Set the role required to register<br/>
 - Usage: `.arkset registerrole [role]`
## .arkset ucstats
View Upgrade.Chat purchases by cluster<br/>
 - Usage: `.arkset ucstats`
 - Restricted to: `GUILD_OWNER`
# .clusterlb
View the cluster leaderboard<br/>
**Arguments**<br/>
- sort_by: Sort the leaderboard by the following<br/>
 - `playtime` - Sort by total playtime<br/>
 - `tamed` - Sort by total tamed dinos<br/>
 - `kills` - Sort by total PvP kills<br/>
 - `tamekills` - Sort by total tame kills<br/>
 - Usage: `.clusterlb [sort_by=kills]`
 - Checks: `server_only`
# .players
View the playtime leaderboard<br/>
 - Usage: `.players [cluster=None]`
 - Aliases: `arkleaderboard, arklb, and arktop`
 - Checks: `server_only`
# .tribelb
View leaderboard for all tribes<br/>
**Arguments**<br/>
`sort_by` - Sort the leaderboard by kills, dinos tamed, or structures destroyed<br/>

**Examples**<br/>
`.tribelb kills` - Tribe kill leaderboard<br/>
`.tribelb tamed` - Tribe tame leaderboard<br/>
`.tribelb destroyed` - Tribe destruction leaderboard<br/>

*Also accepted: `k`, `t`, or `d`*<br/>
 - Usage: `.tribelb <sort_by> [cluster=None]`
 - Aliases: `tribetop`
 - Checks: `server_only`
# .findsurvivor
Find info about a particular survivor name<br/>
 - Usage: `.findsurvivor <survivor_name>`
 - Aliases: `findcharname`
 - Checks: `server_only`
# .dbstats
Stats about the ArkTools database<br/>
 - Usage: `.dbstats [showglobal=False]`
 - Checks: `server_only`
# .servergraph (Hybrid Command)
View a graph of player count over a set time<br/>
**Arguments**<br/>
`<timespan>` How long to look for, or `all` for all-time data. Defaults to 1 hour.<br/>
Must be at least 1 hour.<br/>

**Optional Arguments**<br/>
`clusters_only:` (True/False) Only show playercounts by cluster, default is False<br/>
`include_total:` (True/False) Include another line representing the Total<br/>
`search_query: ` Filter by a specific map, cluster, or both<br/>

Example: .servergraph 4h<br/>
Example: .servergraph 12d<br/>
Example: .servergraph 3w2d<br/>
Example: .servergraph 7w<br/>
 - Usage: `.servergraph [timespan=1h] [clusters_only=False] [include_total=False] [search_query]`
 - Slash Usage: `/servergraph [timespan=1h] [clusters_only=False] [include_total=False] [search_query]`
 - Cooldown: `3 per 30.0 seconds`
 - Checks: `server_only`
# .playerstats (Hybrid Command)
View info about a player<br/>

The optional **player** argument can be one of the following.<br/>
- Gamertag or Username<br/>
- XUID, Steam ID, PSN ID, or EOS ID<br/>
- Discord ID or Username<br/>
- @mention<br/>
 - Usage: `.playerstats [player]`
 - Slash Usage: `/playerstats [player]`
 - Aliases: `player`
 - Checks: `server_only`
# .susrating
Get a rating for how likely an xbox account is to be an alt<br/>
 - Usage: `.susrating <player>`
 - Restricted to: `MOD`
# .xdm (Hybrid Command)
DM a player on Xbox<br/>

The message sender will be the host Gamertag of the last server they were on.<br/>
 - Usage: `.xdm <player> <message>`
 - Slash Usage: `/xdm <player> <message>`
 - Restricted to: `MOD`
 - Cooldown: `1 per 10.0 seconds`
# .xsapi
Xbox crossplay tools/settings<br/>
 - Usage: `.xsapi`
 - Restricted to: `ADMIN`
## .xsapi setcreds
Set Client ID and Secret for the bot to use<br/>
 - Usage: `.xsapi setcreds`
 - Restricted to: `BOT_OWNER`
## .xsapi authenticate
Authenticate a host gamertag (MS Crossplay Only)<br/>
 - Usage: `.xsapi authenticate`
 - Aliases: `auth`
## .xsapi autofriend
Auto host gamertag friend/unfriend system<br/>
 - Usage: `.xsapi autofriend`
 - Aliases: `smartmanage`
### .xsapi autofriend unfriendtime
Set days of inactivity to auto-unfriend<br/>

This is the number of days of inactivity for the host Gamertags to unfriend a player.<br/>

This keeps the xbox host Gamertag friends lists clean since the max you can have is 1000.<br/>
 - Usage: `.xsapi autofriend unfriendtime <days>`
### .xsapi autofriend toggle
Toggle the auto-friend system<br/>

This will enable automatically adding new players as a friend by the host Gamertag<br/>
and automatically unfriending them after the set number of days of inactivity (Default is 30).<br/>
The Gamertags will also unfriend anyone that isn't following them back<br/>
or leaves the discord after registering.<br/>

You must have Autto Premium to use this!<br/>
 - Usage: `.xsapi autofriend toggle`
## .xsapi gettokens
Get a payload dump of your server tokens (Careful not to do in public channel)<br/>
 - Usage: `.xsapi gettokens <cluster> <server>`
## .xsapi testmasterauth
Test master tokens<br/>
 - Usage: `.xsapi testmasterauth`
 - Restricted to: `BOT_OWNER`
## .xsapi view
View settings related to the xbox api<br/>
 - Usage: `.xsapi view`
## .xsapi masterauth
Authenticate master tokens<br/>
 - Usage: `.xsapi masterauth`
 - Restricted to: `BOT_OWNER`
## .xsapi altdetection
Alt detection for newly discovered players in-game<br/>

Get alerts in the event log when a suspicious account joins a server,<br/>
and optionally Auto-ban them or send a warning message based on customizable settings<br/>

Autto Premium is required to use this system<br/>
 - Usage: `.xsapi altdetection`
 - Aliases: `alt`
### .xsapi altdetection autoban
Toggle alt detection autoban on/off<br/>
 - Usage: `.xsapi altdetection autoban`
### .xsapi altdetection threshold
Set the threshold for alt detection<br/>
 - Usage: `.xsapi altdetection threshold <threshold>`
### .xsapi altdetection channel
Set the channel for alt detection alerts<br/>
 - Usage: `.xsapi altdetection channel <channel>`
### .xsapi altdetection toggle
Toggle alt detection system on/off<br/>

Autto Premium is required to use this system<br/>
 - Usage: `.xsapi altdetection toggle`
## .xsapi viewhosts
View XSAPI info of your servers<br/>
 - Usage: `.xsapi viewhosts`
## .xsapi cleanfriends
Clean up the host gamertags friends list<br/>

**Arguments:**<br/>
- `<cluster>` The cluster name<br/>
- `<server>` The server name<br/>
- `[days]` The number of days of inactivity to unfriend (Default is 30)<br/>

Anyone whos last map was not the server withing the time specified will be unfriended<br/>
 - Usage: `.xsapi cleanfriends <cluster> <server> [days=30]`
# .rcon (Hybrid Command)
Run an RCON command<br/>

Note that `.doexit`, `.dorestartlevel`, `.banplayer` and `.unbanplayer`<br/>
are standalone commands, running these commands with pure rcon will not execute<br/>
the extra steps associated with these commands like countdowns,<br/>
saving, or player blocking.<br/>
 - Usage: `.rcon <cluster> <server> <command>`
 - Slash Usage: `/rcon <cluster> <server> <command>`
 - Restricted to: `MOD`
 - Aliases: `run`
 - Checks: `server_only`
# .bulksend
Bulk send an item to a player<br/>

The `count` specifies how many times to run the command, this is useful for filling an inventory with an item<br/>
that has a small stack size.<br/>
the blueprint string should include the amount, quality, and blueprint numbers at the end too.<br/>

**Example**<br/>
`"Blueprint'/Game/PrimalEarth/CoreBlueprints/SomePathToItem.PrimalItemResource_Polymer'" 100 1 0`<br/>
This would is how a full blueprint path looks.<br/>
Specifying a count of 50 would send you 100 polymer 50 times.<br/>
 - Usage: `.bulksend <cluster> <server> <implant> <count> <blueprint_string>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .banplayer (Hybrid Command)
Ban a player from all servers<br/>
 - Usage: `.banplayer <player_id> [reason]`
 - Slash Usage: `/banplayer <player_id> [reason]`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .unbanplayer (Hybrid Command)
Unban a player from all servers<br/>
 - Usage: `.unbanplayer <player_id>`
 - Slash Usage: `/unbanplayer <player_id>`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .doexit (Hybrid Command)
Fully shut down a server<br/>
 - Usage: `.doexit <cluster> <server> [countdown=None]`
 - Slash Usage: `/doexit <cluster> <server> [countdown=None]`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .dorestartlevel (Hybrid Command)
Restart a server<br/>
 - Usage: `.dorestartlevel <cluster> <server> [countdown=None]`
 - Slash Usage: `/dorestartlevel <cluster> <server> [countdown=None]`
 - Restricted to: `MOD`
 - Checks: `server_only`
# .resetkit
Reset a players claimed kit<br/>

If per-server kits are enabled, this will reset the kit for all servers in the cluster.<br/>
 - Usage: `.resetkit <gameid>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .cleantribelogs
Delete tribelog threads that arent associated with a tribe<br/>
 - Usage: `.cleantribelogs`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .resetclusterkits
Reset all player kits for a cluster<br/>

If per-server kits are enabled, this will reset all kits for all servers in the cluster.<br/>
 - Usage: `.resetclusterkits <cluster_name>`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .remreacts
Remove reactions from a message based on the following.<br/>
- `min_playtime`: Minimum playtime required in hours<br/>
- `min_joined`: Minimum time in discord in hours<br/>
- `min_age`: Minimum age of discord account in hours<br/>
 - Usage: `.remreacts <message> [min_playtime=0] [min_joined=0] [min_age=0]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .bans
Manage player bans<br/>
 - Usage: `.bans`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
# .globalbans
View global player bans<br/>
 - Usage: `.globalbans`
 - Restricted to: `MOD`
 - Aliases: `allbans`
 - Checks: `server_only`
# .ownerset
Owner-only ark configuration<br/>
 - Usage: `.ownerset`
 - Restricted to: `BOT_OWNER`
## .ownerset blacklist
Add/Remove server IDs from the blacklist<br/>
 - Usage: `.ownerset blacklist <server_id>`
## .ownerset cleandupes
Reset discord_id to 0 for users registered to more than one player account within the same server.<br/>
 - Usage: `.ownerset cleandupes`
## .ownerset premium
Premium server settings<br/>
 - Usage: `.ownerset premium`
### .ownerset premium view
View premium settings<br/>
 - Usage: `.ownerset premium view`
### .ownerset premium submsg
Set the DM message the bot sends a user when they sub<br/>
 - Usage: `.ownerset premium submsg [sub_message]`
### .ownerset premium mainserver
Set the main server for ArkTools<br/>
 - Usage: `.ownerset premium mainserver`
### .ownerset premium unsubmsg
Set the DM message the bot sends a user when they unsub<br/>
 - Usage: `.ownerset premium unsubmsg [unsub_message]`
### .ownerset premium toggle
Toggle premium check<br/>
 - Usage: `.ownerset premium toggle`
### .ownerset premium lockedmsg
Set the DM message the bot sends a user when a premium feature is locked<br/>
 - Usage: `.ownerset premium lockedmsg <locked_message>`
### .ownerset premium mainchannel
Set the main channel for ArkTools premium subs<br/>
 - Usage: `.ownerset premium mainchannel`
### .ownerset premium role
Add/Remove premium roles<br/>
 - Usage: `.ownerset premium role <role>`
### .ownerset premium whitelist
Add/Remove premium whitelisted servers<br/>
 - Usage: `.ownerset premium whitelist <server_id>`
## .ownerset deleteinactive
Delete servers that havent been online in X days<br/>
 - Usage: `.ownerset deleteinactive <days>`
## .ownerset deleteplayerdupes
Delete player objects with the same server_id and gameid<br/>
 - Usage: `.ownerset deleteplayerdupes`
## .ownerset checkinactive
Check servers that havent been online in X days<br/>
 - Usage: `.ownerset checkinactive <days>`
## .ownerset shopbuttons
Set the number emojis<br/>
 - Usage: `.ownerset shopbuttons <cart> <search> <home> <buy> <delete> <back>`
## .ownerset togglesettingswipe
Wipe server data when bot leaves<br/>
 - Usage: `.ownerset togglesettingswipe`
## .ownerset resetsession
Reset the signed session<br/>
 - Usage: `.ownerset resetsession`
## .ownerset queuetime
Set queue time for servers<br/>
 - Usage: `.ownerset queuetime <seconds>`
## .ownerset mainserver
Set queue time for servers<br/>
 - Usage: `.ownerset mainserver <server_id>`
## .ownerset togglepresence
Toggle the bot's status updates<br/>
 - Usage: `.ownerset togglepresence`
## .ownerset checkplayerdupes
Check if there are any player objects with the same server_id and gameid<br/>
 - Usage: `.ownerset checkplayerdupes`
## .ownerset autoleavedays
Set days of inactivity for bot to auto leave<br/>
 - Usage: `.ownerset autoleavedays <days>`
## .ownerset checkdupes
Check if any users are registered to more than one player account<br/>
 - Usage: `.ownerset checkdupes`
## .ownerset viewbuttons
View current buttons<br/>
 - Usage: `.ownerset viewbuttons`
## .ownerset restore
Restore the database<br/>
 - Usage: `.ownerset restore`
## .ownerset wipeplayers
Wipe ALL players<br/>
 - Usage: `.ownerset wipeplayers <confirm>`
## .ownerset datapath
Set the data path<br/>
 - Usage: `.ownerset datapath <path>`
 - Restricted to: `BOT_OWNER`
## .ownerset postgres
Configure your postgres connection<br/>
 - Usage: `.ownerset postgres`
## .ownerset validatenames
Validate server and cluster names to ensure they are alphanumeric.<br/>
*hyphens and spaces are fine*<br/>
 - Usage: `.ownerset validatenames [prune=False]`
## .ownerset arrows
Set the arrow emojis<br/>
 - Usage: `.ownerset arrows <left10> <left> <right> <right10>`
## .ownerset errorlog
Set the master error log channel<br/>
 - Usage: `.ownerset errorlog <channel>`
## .ownerset validategameids
Prune invalid game IDs<br/>

- Game IDs that are integers must be between 15 and 21 characters long.<br/>
- Game IDs that are strings must be between 29 and 33 characters long.<br/>
 - Usage: `.ownerset validategameids [prune=False]`
## .ownerset toggleautoleave
Auto leave servers after X days of not adding an active server<br/>
 - Usage: `.ownerset toggleautoleave`
## .ownerset backup
Backup the database<br/>
 - Usage: `.ownerset backup`
## .ownerset numbers
Set the number emojis<br/>
 - Usage: `.ownerset numbers <one> <two> <three> <four>`
## .ownerset test
Test<br/>
 - Usage: `.ownerset test`
# .commandtimes
Check Command Execution Times<br/>
 - Usage: `.commandtimes`
 - Restricted to: `BOT_OWNER`
# .looptimes
Check Task Execution Times<br/>
 - Usage: `.looptimes`
 - Restricted to: `BOT_OWNER`
# .checkpremium
Check if a server is premium<br/>
 - Usage: `.checkpremium <server_id>`
 - Restricted to: `BOT_OWNER`
# .premiumservers
View all premium servers<br/>
 - Usage: `.premiumservers`
 - Restricted to: `BOT_OWNER`
# .getnoimages
Get item classes with no image URL<br/>
 - Usage: `.getnoimages`
 - Restricted to: `BOT_OWNER`
# .resetnoimages
Reset item classes with no image URL<br/>
 - Usage: `.resetnoimages`
 - Restricted to: `BOT_OWNER`
# .rawquery
Run a raw query<br/>
 - Usage: `.rawquery <query>`
 - Restricted to: `BOT_OWNER`
# .dbperf
Expanded stats about the ArkTools database, including cache hits, index usage, etc.<br/>
 - Usage: `.dbperf`
 - Restricted to: `BOT_OWNER`
# .vacuumdb
Runs a verbose VACUUM operation on the database<br/>
 - Usage: `.vacuumdb`
 - Restricted to: `BOT_OWNER`
# .getobj
Get a dump of a table object entry<br/>
 - Usage: `.getobj <entry_id>`
 - Restricted to: `BOT_OWNER`
# .playercounts
View player counts either globally or locally<br/>
 - Usage: `.playercounts [local=False]`
 - Cooldown: `1 per 10.0 seconds`
# .alltasks
View all tasks<br/>
 - Usage: `.alltasks`
 - Restricted to: `BOT_OWNER`
# .cachesizes
View the current cache sizes<br/>
 - Usage: `.cachesizes`
 - Restricted to: `BOT_OWNER`
# .cleanupbans
Cleanup bad bans<br/>
 - Usage: `.cleanupbans`
 - Restricted to: `BOT_OWNER`
# .toggleloop
Toggle a loop<br/>
 - Usage: `.toggleloop <loop_name>`
 - Restricted to: `BOT_OWNER`
# .disabledloops
View disabled loops<br/>
 - Usage: `.disabledloops`
 - Restricted to: `BOT_OWNER`
