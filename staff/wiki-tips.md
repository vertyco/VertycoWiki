---
title: Wiki Tips
description: 
published: true
date: 2024-08-26T00:09:55.948Z
tags: staff, wiki, formatting
editor: markdown
dateCreated: 2024-08-25T20:07:34.798Z
---

This page contains useful formatting tips when editing pages.
Full documentation can be found [Here](https://docs.requarks.io/en/editors/markdown#content-tabs)

# Dot Unicode Character
Instead of 
- one
- two
- three

You can do 
• one
• two
• three

Just copy/paste the dot, doing it this way helps issues where normal bullets break the formatted quote boxes.

# Using highlighting
The following inline code blocks represent how to make text different colors.
<span style="color: red;">Red</span>: `<span style="color: red;">Red</span>`
<span style="color: blue;">Blue</span>: `<span style="color: blue;">Blue</span>`
<span style="color: green;">Green</span>: `<span style="color: green;">Green</span>`
<span style="color: yellow;">Yellow</span>: `<span style="color: yellow;">Yellow</span>`
<span style="color: purple;">Purple</span>: `<span style="color: purple;">Purple</span>`
<span style="color: orange;">Orange</span>: `<span style="color: orange;">Orange</span>`
<span style="color: pink;">Pink</span>: `<span style="color: pink;">Pink</span>`
<span style="color: brown;">Brown</span>: `<span style="color: brown;">Brown</span>`
<span style="color: black;">Black</span>: `<span style="color: black;">Black</span>`
<span style="color: gray;">Gray</span>: `<span style="color: gray;">Gray</span>`
<span style="color: white;">White</span>: `<span style="color: white;">White</span>`
<span style="color: cyan;">Cyan</span>: `<span style="color: cyan;">Cyan</span>`
<span style="color: magenta;">Magenta</span>: `<span style="color: magenta;">Magenta</span>`
<span style="color: lime;">Lime</span>: `<span style="color: lime;">Lime</span>`
<span style="color: teal;">Teal</span>: `<span style="color: teal;">Teal</span>`
<span style="color: indigo;">Indigo</span>: `<span style="color: indigo;">Indigo</span>`
<span style="color: violet;">Violet</span>: `<span style="color: violet;">Violet</span>`
<span style="color: maroon;">Maroon</span>: `<span style="color: maroon;">Maroon</span>`
<span style="color: navy;">Navy</span>: `<span style="color: navy;">Navy</span>`
<span style="color: gold;">Gold</span>: `<span style="color: gold;">Gold</span>`
<span style="color: silver;">Silver</span>: `<span style="color: silver;">Silver</span>`
<span style="color: beige;">Beige</span>: `<span style="color: beige;">Beige</span>`
<span style="color: salmon;">Salmon</span>: `<span style="color: salmon;">Salmon</span>`
<span style="color: tomato;">Tomato</span>: `<span style="color: tomato;">Tomato</span>`
<span style="color: khaki;">Khaki</span>: `<span style="color: khaki;">Khaki</span>`
<span style="color: lavender;">Lavender</span>: `<span style="color: lavender;">Lavender</span>`
<span style="color: mistyrose;">MistyRose</span>: `<span style="color: mistyrose;">MistyRose</span>`
<span style="color: coral;">Coral</span>: `<span style="color: coral;">Coral</span>`
<span style="color: orchid;">Orchid</span>: `<span style="color: orchid;">Orchid</span>`
<span style="color: wheat;">Wheat</span>: `<span style="color: wheat;">Wheat</span>`

# Making tabbed sections
```
# Tabs {.tabset}
## First Tab

Any content here will go into the first tab...

## Second Tab

Any content here will go into the second tab...

## Third Tab

Any content here will go into the third tab...
```
Result:

# Tabs {.tabset}
## First Tab

Any content here will go into the first tab...

## Second Tab

Any content here will go into the second tab...

## Third Tab

Any content here will go into the third tab...


# Creating tables
```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Foo      | Bar      | Xyz      |
| Abc      | Def      | 123      |
{.dense}
```
Result:
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Foo      | Bar      | Xyz      |
| Abc      | Def      | 123      |
{.dense}

the `{.dense}` part makes the table compact.


# Creating task lists
```markdown
- [x] Checked task item
- [x] Another checked task item
- [ ] Unchecked task item
```
Result:
- [x] Checked task item
- [x] Another checked task item
- [ ] Unchecked task item

# Attaching images
There are two ways to attach images
1. Markdown
2. HTML

### Markdown
```markdown
![mnote-example.png](https://i.imgur.com/opvTLoo.png)
If you want to resize it: add ` =100x100` to the end of the link
Example (make sure to include the space!)
![mnote-example.png](https://i.imgur.com/opvTLoo.png =100x100)
```
![mnote-example.png](https://i.imgur.com/opvTLoo.png =100x100)

### HTML
```markdown
<figure style="text-align: center;">
  <img src="https://i.imgur.com/opvTLoo.png" alt="Description" style="width: 100%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">You can place a caption here</figcaption>
</figure>
# With this its easier to center the image (or align it differently)
```
<figure style="text-align: center;">
  <img src="https://i.imgur.com/opvTLoo.png" alt="Description" style="width: 10%; max-width: 600px;" />
  <figcaption style="color: #b9bbbe;">You can place a caption here</figcaption>
</figure>

# Making footnotes
```
This sentence[^1] needs a few footnotes.[^2]

[^1]: A string of syntactic words.
[^2]: A useful example sentence.
```
Result:
This sentence[^1] needs a few footnotes.[^2]

[^1]: A string of syntactic words.
[^2]: A useful example sentence.

