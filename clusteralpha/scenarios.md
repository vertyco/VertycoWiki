---
title: Cluster Alpha Example Scenarios
description: 
published: true
date: 2026-01-30T21:15:27.955Z
tags: [cluster-alpha, scenarios]
editor: markdown
dateCreated: 2026-01-30T21:15:27.955Z
---

# Alpha Point System - PvP & Raid Rules

This document explains how Alpha Points are awarded and blocked based on tribe memberships across servers in a cluster.

## Core Principle

**If two players share ANY tribe membership ANYWHERE in the cluster, they are considered allies and cannot earn points from each other.**

This prevents exploitation through "shell tribes" or cross-server alliances.

---

## How Tribelogs Work

All PvP and raid information comes from parsing tribelogs. The data available determines what checks we can perform.

### PvP Kills (Player vs Player)
We know exactly WHO killed WHO (character names), so we check if those two specific players share a tribe anywhere in the cluster.

**Points:** Full points transferred (zero-sum)

Example tribelog:
```
Tribemember Lyinaro - Lvl 75 was killed by Chabelo - Lvl 74 (Chabelo's Army)!
```

### Tame Kills Player
When a tame kills a player, we know the victim's name and the attacker's TRIBE, but not which specific player owns the tame.

**Points:** 20% of what a PvP kill would be, transferred from victim's home tribe to attacker's tribe

Example tribelog:
```
Tribemember Verahalvanna - Lvl 67 was killed by Pteranodon - Lvl 218 (Pteranodon) (Tribe of Sr Isaac)!
```

### Tame Deaths
When your tame dies, no Alpha Points are transferred. This prevents tame farming exploits.

**Points:** None

### Structure Destruction (Raids)
We only know which TRIBE destroyed a structure, not which player. Therefore we check if ANY member of the attacker tribe shares a tribe with ANY member of the victim tribe.

**Points:** Transferred hourly and using a cascade percentage system via batch processing since not all logs come through properly

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

### Key Observations
- **bob** and **bret** appear to be enemies on Center (SNF vs Ruckus) but are tribemates on Island (both in SNF)
- **steve** is truly solo - he only exists on Center in his own tribe
- On Ragnarok, all main players except steve share "The Boys" tribe

---

## PvP Kill Scenarios

### Scenario 1: Hidden Alliance
**bob (SNF/Center) kills bret (Ruckus/Center)**

Result: **BLOCKED** ❌
- bob and bret share SNF on Island
- Cross-server friendly fire detected
- No points transfer (kill still counts for stats)

### Scenario 2: Truly Independent Player  
**jane (SNF/Center) kills steve (Solo Steve/Center)**

Result: **ALLOWED** ✅
- jane and steve share no tribes anywhere
- jane's home tribe = Barker (Island, 11k power)
- steve's home tribe = Solo Steve (Center, 800 power)
- Points: Barker gains, Solo Steve loses

### Scenario 3: Shared Tribe on Different Server
**jane (SNF/Center) kills bret (Ruckus/Center)**

Result: **BLOCKED** ❌
- jane and bret both share "The Boys" on Ragnarok
- Even though they're in "enemy" tribes on Center, they're allies elsewhere

### Scenario 4: Solo vs Established
**steve (Solo Steve/Center) kills max (SNF/Center)**

Result: **ALLOWED** ✅
- steve and max share no tribes
- Points: Solo Steve gains, Barker loses (max's home tribe)

---

## Raid Scenarios

### Scenario 5: Allied Tribes Raiding Each Other
**SNF (Center) raids Ruckus (Center)**

Result: **BLOCKED** ❌

Every member of SNF shares "The Boys" with every member of Ruckus on Ragnarok:

| Attacker | vs dug | vs bret |
|----------|--------|---------|
| bob | The Boys ❌ | SNF + The Boys ❌ |
| jane | The Boys ❌ | The Boys ❌ |
| max | The Boys ❌ | The Boys ❌ |

### Scenario 6: Clean Raid (Solo Player)
**Solo Steve (Center) raids Ruckus (Center)**

Result: **ALLOWED** ✅

No shared tribes between steve and any Ruckus member:

| Attacker | vs dug | vs bret |
|----------|--------|--------|
| steve | ✅ | ✅ |

### Scenario 7: Hypothetical - Colluding Solo Player
**Hypothetical:** What if steve secretly joined "The Boys" on Ragnarok?

**Solo Steve raids SNF** would now be **BLOCKED** ❌

| Attacker | vs bob | vs jane | vs max |
|----------|--------|---------|--------|
| steve | The Boys ❌ | The Boys ❌ | The Boys ❌ |

Even a solo player raid gets blocked if they share tribes with their target.

---

## Summary

| Check Type | What's Checked |
|------------|----------------|
| PvP Kill | Killer player ↔ Victim player share any tribe? |
| Tame Kill | Any attacker tribe member ↔ Victim player share any tribe? |
| Raid | Any attacker tribe member ↔ Any victim tribe member share any tribe? |

The more players involved, the more likely a collision will be found and the action blocked.

