---
title: Pixl Commands
description: 
published: true
date: 2026-01-17T17:00:17.024Z
tags: cogs, pixl, commands
editor: markdown
dateCreated: 2024-08-25T19:15:40.317Z
---

Guess pictures for points<br/><br/>Pixl is an image guessing game that reveals parts of an image over time while users race to guess the correct answer first.<br/><br/>**Images are split up into 192 blocks and slowly revealed over time.**<br/>The score of the game is based on how many blocks are left when the image is guessed.

# .pixlboard
View the Pixl leaderboard!<br/>

**Arguments**<br/>
`show_global`: show the global leaderboard<br/>

example: `.pixlb true`<br/>
 - Usage: `.pixlboard <show_global>`
 - Aliases: `pixlb, pixelb, pixlelb, and pixleaderboard`
 - Checks: `server_only`
# .pixl
Start a Pixl game!<br/>
Guess the image as it is slowly revealed<br/>
 - Usage: `.pixl`
 - Aliases: `pixle, pixlguess, pixelguess, and pixleguess`
 - Checks: `server_only`
# .pixlset
Configure the Pixl game<br/>
 - Usage: `.pixlset`
 - Aliases: `pixelset and pixleset`
 - Checks: `server_only`
## .pixlset fuzzy
Set the fuzzy matching threshold for answer checking (0.0 to 1.0)<br/>

A lower value means more lenient matching (more answers accepted)<br/>
A higher value requires more accurate spelling<br/>

Examples:<br/>
- 0.92 (default) accepts answers that are 92% similar<br/>
- 0.7 would accept answers that are roughly 70% similar<br/>
- 1.0 would require exact matching<br/>
- 0 would disable fuzzy matching entirely<br/>
 - Usage: `.pixlset fuzzy <threshold>`
## .pixlset image
Add/Remove images<br/>
 - Usage: `.pixlset image`
### .pixlset image view
View the server images<br/>
 - Usage: `.pixlset image view`
### .pixlset image viewdefault
View the default images<br/>
 - Usage: `.pixlset image viewdefault`
### .pixlset image testglobal
Test the global images to ensure they are valid urls<br/>
 - Usage: `.pixlset image testglobal`
 - Restricted to: `BOT_OWNER`
### .pixlset image addglobal
Add a global image for all servers to use<br/>

**Arguments**<br/>
`url:     `the url of the image<br/>
`answers: `a list of possible answers separated by a comma<br/>

**Alternative**<br/>
If args are left blank, a text file can be uploaded with the following format for bulk image adding.<br/>
Each line starts with the url followed by all the possible correct answers separated by a comma<br/>

Example: `url, answer, answer, answer...`<br/>
```
https://some_url.com/example.png, answer1, answer two, another answer
https://yet_another_url.com/another_example.jpg, answer one, answer 2, another answer
```
 - Usage: `.pixlset image addglobal <url> <answers>`
 - Restricted to: `BOT_OWNER`
### .pixlset image viewglobal
View the global images<br/>
 - Usage: `.pixlset image viewglobal`
### .pixlset image add
Add an image for your server to use<br/>

**Arguments**<br/>
`url:     `the url of the image<br/>
`answers: `a list of possible answers separated by a comma<br/>

**Alternative**<br/>
If args are left blank, a text file can be uploaded with the following format for bulk image adding.<br/>
Each line starts with the url followed by all the possible correct answers separated by a comma<br/>

Example: `url, answer, answer, answer...`<br/>
```
https://some_url.com/example.png, answer1, answer two, another answer
https://yet_another_url.com/another_example.jpg, answer one, answer 2, another answer
```
 - Usage: `.pixlset image add <url> <answers>`
### .pixlset image deleteall
Delete all custom images for this server<br/>

This will remove all custom images that have been added to this server.<br/>
Default and global images will remain available if enabled.<br/>
 - Usage: `.pixlset image deleteall <confirm>`
### .pixlset image cleanup
Clean up invalid or dead image links<br/>

**Arguments**<br/>
`scope`: The scope to clean up - "server", "global", or "all"<br/>

This command will test all images and remove any that are no longer accessible<br/>
 - Usage: `.pixlset image cleanup [scope=server]`
### .pixlset image testserver
Test the server images to ensure they are valid urls<br/>
 - Usage: `.pixlset image testserver`
## .pixlset blocks
Set the amount of blocks to reveal after each delay<br/>
 - Usage: `.pixlset blocks <amount>`
## .pixlset reset
Reset the Pixl scoreboard<br/>

**Arguments**<br/>
`user`: (Optional) A specific user to reset scores for. If not provided, resets scores for all users.<br/>

Examples:<br/>
- `.pixlset reset` - Resets scores for all users<br/>
- `.pixlset reset @user` - Resets scores for the specified user<br/>
 - Usage: `.pixlset reset [user=None]`
 - Restricted to: `ADMIN`
 - Checks: `server_only`
## .pixlset timelimit
Set the time limit for Pixl games<br/>
 - Usage: `.pixlset timelimit <seconds>`
## .pixlset ratio
Set the point to credit conversion ratio (points x ratio = credit reward)<br/>
Points are calculated based on how many hidden blocks are left at the end of the game<br/>

Ratio can be a decimal<br/>
Set to 0 to disable credit rewards<br/>
 - Usage: `.pixlset ratio <ratio>`
## .pixlset delay
(Owner Only)Set the delay between block reveals<br/>

**Warning**<br/>
Setting this too low may hit rate limits, default is 5 seconds.<br/>
 - Usage: `.pixlset delay <seconds>`
 - Restricted to: `BOT_OWNER`
## .pixlset usedefault
(Toggle) Whether to use the default hardcoded images in this server<br/>
 - Usage: `.pixlset usedefault`
## .pixlset showanswer
(Toggle) Showing the answer after a game over<br/>
 - Usage: `.pixlset showanswer`
## .pixlset useglobal
(Toggle) Whether to use global images in this server<br/>
 - Usage: `.pixlset useglobal`
## .pixlset view
View the current settings<br/>
 - Usage: `.pixlset view`
## .pixlset participants
Set the minimum amount of participants for the game to reward users credits<br/>
 - Usage: `.pixlset participants <amount>`
