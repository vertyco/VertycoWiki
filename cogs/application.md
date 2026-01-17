---
title: Application Commands
description: 
published: true
date: 2024-08-25T18:55:25.739Z
tags: 
editor: markdown
dateCreated: 2024-08-25T18:55:24.393Z
---

# Application Help

Receive and moderate staff applications with customizable questions.

# .apply
Apply to be a staff member.<br/>
 - Usage: `.apply`
 - Checks: `server_only`
# .applyset
Various Application settings.<br/>
 - Usage: `.applyset`
 - Restricted to: `ADMIN`
 - Aliases: `setapply and applicationset`
 - Checks: `server_only`
## .applyset accepter
Set the role that can accept/reject applications.<br/>

If `role` is not provided, defaults to server administrators.<br/>
 - Usage: `.applyset accepter [role=None]`
## .applyset applicant
Set the Staff Applicant role.<br/>

If `role` is not provided, applicants will not get any role.<br/>
 - Usage: `.applyset applicant [role=None]`
## .applyset settings
See current settings.<br/>
 - Usage: `.applyset settings`
## .applyset channel
Set the channel where applications will be sent.<br/>

If `channel` is not provided, applications are disabled.<br/>
 - Usage: `.applyset channel [channel=None]`
## .applyset questions
Set custom application questions.<br/>
 - Usage: `.applyset questions`
# .accept
Accept a staff applicant.<br/>

<target> can be a mention or an ID.<br/>
 - Usage: `.accept <target>`
 - Checks: `server_only`
# .deny
Deny a staff applicant.<br/>

<target> can be a mention or an ID<br/>
 - Usage: `.deny <target>`
 - Checks: `server_only`
