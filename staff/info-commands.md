---
title: Information Gathering
description: 
published: true
date: 2024-08-26T00:14:46.465Z
tags: 
editor: markdown
dateCreated: 2024-08-26T00:14:45.111Z
---

There are several non-mod commands at your disposal to help make finding information easier.

# Info Commands

# Tabs {.tabset}
## XUID

`.xuid <gamertag>`

Returns the Xbox ID of a given Gamertag.
<figure style="text-align: left;">
  <img src="/xuid-example.png" alt="Description" style="width: 30%; max-width: 600px;" />
</figure>

## Playerstats

`.playerstats <search_query>`

`search_query` can be the following:

> Username, ID, or @mention of a Discord account.
> • In-game Gamertag or Username
> • XUID, Steam ID, PSN ID, or EOS ID
> • In-game character name of the player.
{.is-info}

Shows a detailed breakdown of the following
<figure style="text-align: left;">
  <img src="/playerstats-example.png" alt="Description" style="width: 30%; max-width: 600px;" />
</figure>

### DM a player through Xbox

By clicking the Xbox DM button you can send a DM on behalf of the Host Gamertag of the last map the player was on

<figure style="text-align: left;">
  <img src="/playerstats-xbox-dm-button.png" alt="Description" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">This button will ONLY be available on ASE players</figcaption>
</figure>
<br>
<figure style="text-align: left;">
  <img src="/playerstats-xbox-dm-modal.png" alt="Description" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Messages can be up to 500 characters</figcaption>
</figure>

## Profile (Leveling)

`.pf <user>`

View someones Discord activity profile

<figure style="text-align: left;">
  <img src="/pf-example1.png" alt="select" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">OR</figcaption>
  <img src="/pf-example2.png" alt="select" style="width: 30%; max-width: 600px;" />
</figure>

<figure style="text-align: left;">
  <img src="/pf-example3.png" alt="select" style="width: 40%; max-width: 600px;" />
</figure>

## Userinfo

`.userinfo <member>`

View details about a Discord account in the server.

<figure style="text-align: left;">
  <img src="/userinfo1.png" alt="select" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Alternatively, you can use their User ID</figcaption>
</figure>
<br>
<figure style="text-align: left;">
  <img src="/userinfo2.png" alt="select" style="width: 30%; max-width: 600px;" />
</figure>

## Xbox Profile

`.xprofile <gamertag>`

View a player's Xbox profile.
<figure style="text-align: left;">
  <img src="/xprofile-example.png" alt="select" style="width: 30%; max-width: 600px;" />
</figure>

# Search Commands

# Tabs {.tabset}
## Xbox Friends

`.xfriends <gamertag>`

View the friends list of the given gamertag
<figure style="text-align: left;">
  <img src="/xfriends-example.png" alt="select" style="width: 30%; max-width: 600px;" />
</figure>

## Find Tribe

`.findtribe <search_query>`

Find details of a tribe like their in-game members, tame/structure count, when they were last active ect...

`search_query` can be any of the following:

- Tribe name or ID
- Player username or ID
- Player specimen number or character name

After running the command, you will be asked to select the server you want to search via drop-down.

<figure style="text-align: left;">
  <img src="/findtribe1.png" alt="select" style="width: 30%; max-width: 600px;" />
  <img src="/findtribe2.png" alt="select" style="width: 30%; max-width: 600px;" />
</figure>

## Find Tame

`.findtame <search_query>`

Find tames by tame name, imprinter, tamer, or tribe name.

`search_query` can be one of the following:

- The dino's name. 
- The name of the person who tamed the dino. 
- The name of the person who imprinted on the tame. 
- The name of the tribe that owns the dino. 
- The ID of the tribe that tamed the dino.
    
> You can search for unclaimed dinos by specifying <span style="color: magenta;">unclaimed</span>
{.is-info}


You will be asked to select a server to search for via drop-down.

<figure style="text-align: left;">
  <img src="/findtame-select.png" alt="select" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Select which map you want to search</figcaption>
</figure>

<br>
<figure style="text-align: left;">
  <img src="/findtam-yesno.png" alt="yesno" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Decide if you want to include cryopodded dinos</figcaption>
</figure>

<br>
<figure style="text-align: left;">
  <img src="/findtame-results.png" alt="results" style="width: 30%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">Menu will show two results per page</figcaption>
</figure>

> You can use the <span style="color: cyan;">search</span> button to find specific results within that search
{.is-info}



























