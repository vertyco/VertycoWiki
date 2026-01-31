---
title: Cluster Alpha Example Scenarios
description: 
published: true
date: 2026-01-30T21:15:27.955Z
tags: 
editor: markdown
dateCreated: 2026-01-30T21:15:27.955Z
---

# Alpha Point System - PvP & Raid Rules

This document explains how Alpha Points are awarded and blocked based on tribe memberships across servers in a cluster.

## Core Principle

**If two players share the same HOME TRIBE (highest power tribe), they are considered allies and cannot earn points from each other.**

Your "home tribe" is whichever tribe you belong to that has the highest power in the cluster. Only **active** members (seen in last 24 hours) are considered.

> **TIP:** Use `.conflicts <tribe name>` to check if raiding a tribe will earn points before you start!

---

## How Tribelogs Work

All PvP and raid information comes from parsing tribelogs. The data available determines what checks we can perform.

### PvP Kills (Player vs Player)
We check if both players have the same home tribe.

**Points:** Full points transferred (zero-sum)

Example tribelog:
```
Tribemember Lyinaro - Lvl 75 was killed by Chabelo - Lvl 74 (Chabelo's Army)!
```

### Tame Kills Player
When a tame kills a player, we award **20% of normal PvP points**.

**Points:** 20% of what a direct kill would be, transferred from victim's home tribe to attacker's tribe

Example tribelog:
```
Tribemember Verahalvanna - Lvl 67 was killed by Pteranodon - Lvl 218 (Pteranodon) (Tribe of Sr Isaac)!
```

### Tame Deaths
When your tame dies, no Alpha Points are transferred. This prevents tame farming exploits.

**Points:** None

### Structure Destruction (Raids)
We check if any **active** member of both tribes share the same home tribe.

**Points:** Transferred hourly via batch processing

Example tribelog:
```
C4 Charge (Tribe of Nick) destroyed your 'Heavy Auto Turret'!
```

---

## Example Tribe Setup

### Center Server
| Tribe | Members | Power |
|-------|---------|-------|
| SNF | bob, jane, max | 10k |
| Ruckus | dug, bret | 4k |
| Solo Steve | steve | 800 |

### Island Server
| Tribe | Members | Power |
|-------|---------|-------|
| SNF | bob, bret | 15k |
| Barker | jane, max | 11k |
| Leeto | dug | 3k |

### Ragnarok Server
| Tribe | Members | Power |
|-------|---------|-------|
| The Boys | bob, jane, dug, bret, max | 20k |

### Home Tribe Assignments
Based on highest power across all servers:

| Player | Home Tribe | Home Power |
|--------|------------|------------|
| bob | The Boys (Rag) | 20k |
| jane | The Boys (Rag) | 20k |
| max | The Boys (Rag) | 20k |
| dug | The Boys (Rag) | 20k |
| bret | The Boys (Rag) | 20k |
| steve | Solo Steve (Center) | 800 |

**Key Insight:** Despite having different tribes on Center and Island, bob/jane/max/dug/bret ALL share the same home tribe (The Boys). Only steve is truly independent.

---

## PvP Kill Scenarios

### Scenario 1: Same Home Tribe
**bob (SNF/Center) kills bret (Ruckus/Center)**

Result: **BLOCKED** ❌
- bob's home tribe = The Boys (20k power)
- bret's home tribe = The Boys (20k power)
- Same home tribe → no points

### Scenario 2: Different Home Tribes  
**jane (SNF/Center) kills steve (Solo Steve/Center)**

Result: **ALLOWED** ✅
- jane's home tribe = The Boys (20k power)
- steve's home tribe = Solo Steve (800 power)
- Different home tribes → points transfer

### Scenario 3: All Main Players Are Allied
**jane (SNF/Center) kills dug (Ruckus/Center)**

Result: **BLOCKED** ❌
- jane's home tribe = The Boys (20k power)
- dug's home tribe = The Boys (20k power)
- Same home tribe → no points

### Scenario 4: Solo vs Established
**steve (Solo Steve/Center) kills max (SNF/Center)**

Result: **ALLOWED** ✅
- steve's home tribe = Solo Steve (800 power)
- max's home tribe = The Boys (20k power)
- Different home tribes → points transfer

---

## Raid Scenarios

### Scenario 5: Allied Tribes Raiding Each Other
**SNF (Center) raids Ruckus (Center)**

Result: **BLOCKED** ❌

All active members of both tribes share The Boys as their home tribe:
- SNF members: bob, jane, max → all home = The Boys
- Ruckus members: dug, bret → both home = The Boys

### Scenario 6: Clean Raid (Solo Player)
**Solo Steve (Center) raids Ruckus (Center)**

Result: **ALLOWED** ✅

Steve's home tribe (Solo Steve) is different from dug/bret's home tribe (The Boys).

### Scenario 7: What If Steve Joins The Boys?
**Hypothetical:** Steve joins "The Boys" on Ragnarok.

Now steve's home tribe = The Boys (20k power), not Solo Steve (800 power).

**Solo Steve raids SNF** → **BLOCKED** ❌

Even though steve is raiding from Solo Steve tribe on Center, his HOME tribe is now The Boys, same as SNF's members.

---

## Summary

| Check Type | What's Checked |
|------------|----------------|
| PvP Kill | Do killer and victim share the same HOME tribe? |
| Tame Kill | Does attacker tribe's home overlap with victim's home tribe? (20% points) |
| Raid | Do any ACTIVE members of both tribes share the same HOME tribe? |

**Remember:**
- Home tribe = your highest power tribe in the cluster
- Only active members (last 24h) are considered for raid checks
- Use `.conflicts` and `.myalliances` to check before raiding!