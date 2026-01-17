---
title: Staff Moderation Guide
description: 
published: true
date: 2025-01-13T19:11:57.128Z
tags: 
editor: markdown
dateCreated: 2024-08-25T20:46:39.103Z
---

Learn how to effectively moderate and use bot-assisted resources to perform them.

# Issuing Punishments

**Developer IDs**
User/Server/Message IDs provide a more accurate lookup and moderation of users. It's advisable to enable this function and use them when possible to ensure the best accuracy.

![Discord Icon](https://static.wikia.nocookie.net/discord/images/e/e6/Site-logo.png/revision/latest?cb=20220920072057&path-prefix=hr =23x20) **[Where can I find my User/Server/Message ID?](https://support.discord.com/hc/en-us/articles/206346498-Where-can-I-find-my-User-Server-Message-ID)**

**Moderation Commands**
> Ensure that every moderation with a reason field is used properly.
Do not put immature, vague, or otherwise useless reasons for actions placed.
This reflects poorly on us and causes issues during the appeals process.
{.is-info}


# Tabs {.tabset}
## Mod Note

`.mnote <user> <note>`

Creates a `📝Mod Note` case in the user's modlog history. This is kept as a reference for future moderations.
This does not send a direct message to the user the note is applying to.
Mostly used to privately log potentially disruptive behavior.
<br>
<figure style="text-align: left;">
  <img src="/mnote-example.png" alt="Description" style="width: 90%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Most useful for accusations without evidence made in Modmail against a user.</figcaption>
</figure>

**Viewing/Editing/Removing**
- `.mnote list <user>` - View notes for the user
	- This will show the index of each note for editing/removal purposes
- `.mnote remove <user> <index>` - Remove a note from the user
- `.mnote edit <user> <index> <newnote>` - Edit a note for a user

**In-Game Player Notes**
Similar to discord user notes, you can add/edit/view notes of other players.
> This should only be used if the player is not linked to a Discord account
{.is-warning}

When looking at a player's stats via the `.playerstats` command, you will see the following buttons.
<figure style="text-align: left;">
  <img src="/player-note-example.png" alt="Description" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">The buttons are pretty self-explanatory</figcaption>
</figure>

To delete a note, first use the `show` button to get the number of the note, then you can delete it by clicking the `-` button and entering that number. It is the same concept when editing a note.

All notes are logged to the `#🛡｜mod-log` channel


## Warn

`.warn <user> <reason>`

Warnings are the first step towards remediating behavior if a stronger punishment isn't applicable. Warnings direct message the user with the reason.

<figure style="text-align: left;">
  <img src="/warn-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
</figure>

The `<reason>` variable must clearly state what rule was broken and why the user is getting warned.

Discussing mod actions publicly is not allowed. If your warning results in a member complaining instead of fixing their behavior and taking the warning in stride, move immediately to mutes.

## Mute

`.timeout <user> <reason> <time>`

Mutes are based off timeouts, revoking text and voice channel usage.

Do not use the built-in timeout feature by Discord, always use the command.

<figure style="text-align: left;">
  <img src="/mute-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Time periods of 1 day or above are recommended to give time for the person to cool down.</figcaption>
</figure>

The most common reasons for mutes are:

- Where a prior warning (including verbal) has not remediated behavior.
- A rule violation that is worse than a warning, but does not warrant a ban.
- Placing an account under review.

## Kick/Softban

Admin Only

`.kick <user> <reason>`

`.softban <user> <reason>`

A kick and softban are similar in the sense that both kick the affected user from the server and remove all of their roles. Kick does not purge any messages while softban purges 7 days worth.

<figure style="text-align: left;">
  <img src="/kick-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">This does not reset activity ranks, but users who rejoin the server must level up once to regain them all back.</figcaption>
</figure>

The most common reasons for kicks are:

- Inappropriate content within a user's profile.
- A newly joined user breaking rules multiple times.

## Ban

Admin Only

`.ban <user> <reason>`

Bans are a permanent suspension of the user's account from the server.
Optionally, you can provide this appeal link in the ban: https://forms.gle/k41rwLhSxbzix3gw5
<br>
<figure style="text-align: left;">
  <img src="/ban-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
</figure>

The most common reasons for bans are:

- Advertisements
- Cheating
- Severe NSFW
- Discord ToS or Guidelines Violations (e.g. racism, terrorism ect..)
- Any situation where any lesser mod actions do not make sense (admin discretion).
- Continued violations of the rules where warns/mutes have not worked.


# Modlog Management

On every moderator action, a case is created. These cases can be individually viewed as well as seen at an overview depending on the need.

You have the ability to edit the reason in cases. However, please note that any edits made will not be visible to the user in direct messages. Therefore, it's crucial to ensure the punishment reason is accurate in the first place.

|        Action                      |       Command           |   Commonly Used?   |
|------------------------------------|-------------------------|--------------------|
| View info about the in-game user   | `.playerstats <player>` | :white_check_mark: |
| View info about the user           | `.userinfo <member>`    | :white_check_mark: |
| View a user's modlog overview      | `.listcases <member>`   | :white_check_mark: |
| View a singular case               | `.case <member>`        | :x: |
{.dense}

> Always use `.listcases` when inspecting a user
{.is-warning}


Using these commands, you can view the case number, reason, moderator, date, and (if applicable) the expiration of a timed punishment.

In order to remove punishments, use the following:

| Punishment |       Command           |    Mod can run?    |
|------------|-------------------------|--------------------|
| Warning    | `.unwarn <user_id> <warn_id>` | :white_check_mark: |
| Ban        | `.unban <user_id>`      | :x:                      |
{.dense}











