---
title: Staff Moderation Guide
description: Comprehensive moderation guide for Vertyco staff covering warnings, mutes, bans, and escalation procedures.
published: true
date: 2026-08-29T03:24:48.305Z
tags: staff, moderation, guide
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
> Do not put immature, vague, or otherwise useless reasons for actions placed.
> This reflects poorly on us and causes issues during the appeals process.
{.is-info}


# Tabs {.tabset}
## Mod Note

`.mnote <user> <note>`

Creates a `📝Mod Note` case in the user's modlog history. This is kept as a reference for future moderations.
This does not send a direct message to the user the note is applying to.
Mostly used to privately log potentially disruptive behavior.
<br>
<figure style="text-align: left;">
  <img src="/assets/mnote-example.png" alt="Description" style="width: 90%; max-width: 600px;" />
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
  <img src="/assets/player-note-example.png" alt="Description" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">The buttons are pretty self-explanatory</figcaption>
</figure>

To delete a note, first use the `show` button to get the number of the note, then you can delete it by clicking the `-` button and entering that number. It is the same concept when editing a note.

All notes are logged to the `#🛡｜mod-log` channel


## Warn

`.warn <user> <reason>`

Warnings are the first step towards remediating behavior if a stronger punishment isn't applicable. Warnings direct message the user with the reason.

<figure style="text-align: left;">
  <img src="/assets/warn-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
</figure>

The `<reason>` variable must clearly state what rule was broken and why the user is getting warned.

Discussing mod actions publicly is not allowed. If your warning results in a member complaining instead of fixing their behavior and taking the warning in stride, move immediately to mutes.

## Mute

`.warn <user> <reason>` **then** `.timeout <user> <reason> <time>`

Mutes are based off timeouts, revoking text and voice channel usage.

Do not use the built-in timeout feature by Discord, always use the command.

> `.timeout` on its own files **no modlog case and sends no direct message**.
> A mute issued that way leaves no record and never tells the user what they did.
> Always pair it with a `.warn` using the same reason: the warn creates the case and
> DMs the user, the timeout applies the mute.
{.is-warning}

Use identical reason text on both so the case and the DM match.

<figure style="text-align: left;">
  <img src="/assets/mute-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
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
  <img src="/assets/kick-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">This does not reset activity ranks, but users who rejoin the server must level up once to regain them all back.</figcaption>
</figure>

The most common reasons for kicks are:

- Inappropriate content within a user's profile.
- A newly joined user breaking rules multiple times.

## Ban

Admin Only

`.ban <user> <reason>`

Bans are a permanent suspension of the user's account from the server.
Optionally, you can provide the ban appeal Discord link in the ban: https://discord.gg/KZFbS4aJxA
<br>
<figure style="text-align: left;">
  <img src="/assets/ban-example.png" alt="Description" style="width: 65%; max-width: 600px;" />
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

# When a Moderator May Issue a Ban

This section covers the rare situations where a moderator may need to ban a
player without an admin present. Read it before ever using a ban command. In
almost every case the answer is to escalate, not to ban.

## The default rule

Moderators do not ban on their own most of the time. Bans are an admin action.

> Moderators are **not permitted to ban on PvP tickets**. Those are handled by
> the admin team.
{.is-warning}

If a ticket cannot be resolved, do not close it in the player's face and do not
reach for a ban. Post the ticket link in staff chat, mark it unresolved, and
wait for an admin.

## The two exceptions

There are only two situations where a moderator may ban with no admin around.

### 1. Direct hard-R racism

If a player uses the hard-R racial slur and no admin is online, a moderator may
issue the ban. Even then, check with another staff member first if it is at all
possible to do so.

### 2. A genuine in-game emergency

A moderator may issue an in-game ban only to stop active, catastrophic damage
that is happening right now and cannot wait. The clearest example is a player
dumping cheated or godmode tames that the foreign-tame scanner did not catch,
with a base actively being destroyed.

If that is happening:

1. Get in game and verify it yourself if you can.
2. Document it. Take screenshots.
3. Report it to the admins.
4. Ban only if you are 100% certain.

## What is NOT an emergency

- An aimbot accusation at 3am. Aimbot can wait until morning.
- "I think they are about to cheat." We do not ban before anything has happened;
  a pre-emptive ban is an admin decision.
- A player who is stubborn or argumentative but is not breaking a rule.

Suspicion is not proof. If nothing is actively being destroyed, it waits for an
admin.

## The standard you are held to

When you make a ban call like this, you are staking your mod position on it. An
accurate call will be backed by the admin team. A false ban leads to talks.

## Best practice: never decide alone

The single best piece of advice for a moderator considering a ban: do not make
the call solo. Pull in every moderator who is online and decide together. A team
decision is one the admin team can stand up and defend. A ban issued by a lone
moderator invites questioning and accusations that a group call does not.

## Escalation ladder for difficult tickets

For any hard ticket short of the emergencies above:

1. Moderator handles it.
2. If the player will not listen, bring in an admin. Post the ticket link in
   staff chat and wait.
3. NoA is a last resort, used only on repeat problem players with a history.

Never close a ticket in a player's face. The goal of support is a positive
resolution. Resolution time matters less than the quality of support.
