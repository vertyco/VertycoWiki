---
title: Rich Color Broadcasts
description: 
published: true
date: 2024-08-25T23:18:14.497Z
tags: [staff, wiki, formatting]
editor: markdown
dateCreated: 2024-08-25T23:18:13.144Z
---

You can use the following format to give in-game broadcasts color.
The following uses **[Ark Markup Language](https://ark.fandom.com/wiki/ArkML)**


## Making RCON Broadcasts With Color

`.rcon <cluster> <map> broadcast <message>`

`.rcon pvp rag broadcast <Rich Color="0.5,0,0.5,1">Hello World!</>`


|                 Color                |                Format                |
|--------------------------------------|-------------------------------------|
| <span style="color: red;">Red</span> | `<RichColor Color="1,0,0,1">Red</>` |
| <span style="color: green;">Green</span> | `<RichColor Color="0,1,0,1">Green</>` |
| <span style="color: orange;">Orange</span> | `<RichColor Color="1,0.65,0,1">Orange</>` |
| <span style="color: black;">Black</span> | `<RichColor Color="0,0,0,1">Black</>` |
| <span style="color: yellow;">Yellow</span> | `<RichColor Color="1,1,0,1">Yellow</>` |
| <span style="color: fuchsia;">Fuchsia</span> | `<RichColor Color="1,0,1,1">Fuchsia</>` |
| <span style="color: purple;">Purple</span> | `<RichColor Color="0.5,0,0.5,1">Purple</>` |
| <span style="color: teal;">Blue</span> | `<RichColor Color="0,0.5,0.5,1">blue</>` |
{.dense}
