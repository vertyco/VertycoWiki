---
title: Embed Tool Commands
description: 
published: true
date: 2024-08-25T19:12:34.328Z
tags: 
editor: markdown
dateCreated: 2024-05-02T02:33:23.380Z
---

# EmbedUtils Help

Create, post, and store embeds.

# .embed
Post a simple embed.<br/>

Put the title in quotes if it is multiple words.<br/>
 - Usage: `.embed <channel> <color> <title> <description>`
 - Restricted to: `MOD`
 - Checks: `server_only`
## .embed download
Download a JSON file for a message's embed.<br/>
 - Usage: `.embed download <message> [index=0]`
## .embed post
Post stored embeds.<br/>
 - Usage: `.embed post <channel> <embed_names>`
 - Aliases: `view, drop, and show`
### .embed post global
Post global stored embeds.<br/>
 - Usage: `.embed post global <channel> <embed_names>`
## .embed store
Store embeds for server use.<br/>
 - Usage: `.embed store`
 - Restricted to: `MOD`
### .embed store json
Store an embed from valid JSON on this server.<br/>
 - Usage: `.embed store json <name> <data>`
 - Aliases: `fromjson and fromdata`
### .embed store simple
Store a simple embed on this server.<br/>

Put the title in quotes if it is multiple words.<br/>
 - Usage: `.embed store simple <name> <color> <title> <description>`
### .embed store pastebin
Store an embed from valid JSON or YAML from a pastebin link on this server.<br/>
 - Usage: `.embed store pastebin <name> <data>`
 - Aliases: `frompaste`
### .embed store fromfile
Store an embed from a valid JSON file on this server.<br/>
 - Usage: `.embed store fromfile <name>`
 - Aliases: `fromjsonfile and fromdatafile`
### .embed store yamlfile
Store an embed from a valid YAML file on this server.<br/>
 - Usage: `.embed store yamlfile <name>`
 - Aliases: `fromyamlfile`
### .embed store list
View stored embeds.<br/>
 - Usage: `.embed store list`
### .embed store yaml
Store an embed from valid YAML on this server.<br/>
 - Usage: `.embed store yaml <name> <data>`
 - Aliases: `fromyaml`
### .embed store remove
Remove a stored embed on this server.<br/>
 - Usage: `.embed store remove <name>`
 - Aliases: `delete, rm, and del`
### .embed store download
Download a JSON file for a stored embed.<br/>
 - Usage: `.embed store download <embed>`
### .embed store message
Store an embed from a message on this server.<br/>
 - Usage: `.embed store message <name> <message> [index=0]`
 - Aliases: `frommsg and frommessage`
## .embed fromfile
Post an embed from a valid JSON file.<br/>
 - Usage: `.embed fromfile [channel=None]`
 - Aliases: `fromjsonfile and fromdatafile`
## .embed edit
Edit a message sent by Autto's embeds.<br/>
 - Usage: `.embed edit <message> <color> <title> <description>`
 - Restricted to: `MOD`
### .embed edit store
Edit a message's embed using an embed that's stored on this server.<br/>
 - Usage: `.embed edit store <message> <name>`
 - Aliases: `stored`
#### .embed edit store global
Edit a message's embed using an embed that's stored globally.<br/>
 - Usage: `.embed edit store global <message> <name>`
### .embed edit yamlfile
Edit a message's embed using a valid YAML file.<br/>
 - Usage: `.embed edit yamlfile <message>`
 - Aliases: `fromyamlfile`
### .embed edit message
Edit a message's embed using another message's embed.<br/>
 - Usage: `.embed edit message <source> <target> [index=0]`
 - Aliases: `frommsg and frommessage`
### .embed edit fromfile
Edit a message's embed using a valid JSON file.<br/>
 - Usage: `.embed edit fromfile <message>`
 - Aliases: `fromjsonfile and fromdatafile`
### .embed edit pastebin
Edit a message's embed using a pastebin link which contains valid JSON or YAML.<br/>
 - Usage: `.embed edit pastebin <message> <data>`
 - Aliases: `frompaste`
### .embed edit yaml
Edit a message's embed using valid YAML.<br/>
 - Usage: `.embed edit yaml <message> <data>`
 - Aliases: `fromyaml`
### .embed edit json
Edit a message's embed using valid JSON.<br/>
 - Usage: `.embed edit json <message> <data>`
 - Aliases: `fromjson and fromdata`
## .embed yaml
Post embeds from valid YAML.<br/>
 - Usage: `.embed yaml [channel=None] <data>`
 - Aliases: `fromyaml`
## .embed message
Post an embed from a message.<br/>
 - Usage: `.embed message <message> [index=0] [channel=None]`
 - Aliases: `frommsg and frommessage`
## .embed info
Get info about an embed that is stored on this server.<br/>
 - Usage: `.embed info <name>`
## .embed global
Store embeds for global use.<br/>
 - Usage: `.embed global`
 - Restricted to: `BOT_OWNER`
### .embed global fromfile
Store an embed from a valid JSON file globally.<br/>

The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global fromfile <name> <locked>`
 - Aliases: `fromjsonfile and fromdatafile`
### .embed global yamlfile
Store an embed from a valid YAML file globally.<br/>

The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global yamlfile <name> <locked>`
 - Aliases: `fromyamlfile`
### .embed global json
Store an embed from valid JSON globally.<br/>

The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global json <name> <locked> <data>`
 - Aliases: `fromjson and fromdata`
### .embed global simple
Store a simple embed globally.<br/>

Put the title in quotes if it is multiple words.<br/>
The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global simple <name> <locked> <color> <title> <description>`
### .embed global info
Get info about an embed that is stored globally.<br/>
 - Usage: `.embed global info <name>`
### .embed global pastebin
Store an embed from valid JSON or YAML globally using a pastebin link.<br/>

The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global pastebin <name> <locked> <data>`
 - Aliases: `frompaste`
### .embed global list
View global embeds.<br/>
 - Usage: `.embed global list`
### .embed global remove
Remove a global embed.<br/>
 - Usage: `.embed global remove <name>`
 - Aliases: `delete, rm, and del`
### .embed global lock
Lock/unlock a global embed.<br/>
 - Usage: `.embed global lock <name> [true_or_false=None]`
### .embed global message
Store an embed from a message globally.<br/>

The `locked` argument specifies whether the embed should be locked to owners only.<br/>
 - Usage: `.embed global message <name> <message> <locked> [index=0]`
 - Aliases: `frommsg and frommessage`
## .embed webhook
Send embeds through webhooks.<br/>

Running this command with stored embed names will send up to 10 embeds through a webhook.<br/>
 - Usage: `.embed webhook <embeds>`
 - Restricted to: `ADMIN`
 - Checks: `webhook_check`
### .embed webhook json
Send embeds through webhooks using JSON.<br/>
 - Usage: `.embed webhook json <embeds>`
 - Aliases: `fromjson and fromdata`
### .embed webhook global
Send global embeds through webhooks.<br/>

Running this command with global stored embed names will send up to 10 embeds through a webhook.<br/>
 - Usage: `.embed webhook global <embeds>`
### .embed webhook message
Send embeds through webhooks.<br/>
 - Usage: `.embed webhook message <message> [index=0]`
 - Aliases: `frommsg and frommessage`
### .embed webhook yamlfile
Send embeds through webhooks, using JSON files.<br/>
 - Usage: `.embed webhook yamlfile`
 - Aliases: `fromyamlfile`
### .embed webhook pastebin
Send embeds through webhooks using a pastebin link with valid YAML or JSON.<br/>
 - Usage: `.embed webhook pastebin <embeds>`
 - Aliases: `frompaste`
### .embed webhook fromfile
Send embeds through webhooks, using JSON files.<br/>
 - Usage: `.embed webhook fromfile`
 - Aliases: `fromjsonfile and fromdatafile`
### .embed webhook yaml
Send embeds through webhooks using YAML.<br/>
 - Usage: `.embed webhook yaml <embeds>`
 - Aliases: `fromyaml`
## .embed pastebin
Post embeds from a pastebin link containing valid JSON or YAML.<br/>
 - Usage: `.embed pastebin [channel=None] <data>`
 - Aliases: `frompaste`
## .embed json
Post embeds from valid JSON.<br/>
 - Usage: `.embed json [channel=None] <data>`
 - Aliases: `fromjson and fromdata`
## .embed yamlfile
Post an embed from a valid YAML file.<br/>
 - Usage: `.embed yamlfile [channel=None]`
 - Aliases: `fromyamlfile`
