---
title: Cluster Alpha Breakdown — Competitive PvP Ranking System
description: Complete breakdown of the Cluster Alpha competitive ranking system for Vertyco PvP. Learn how Alpha Points, power ratings, kills, and raids determine tribe rankings.
published: true
date: 2026-01-30T21:15:27.955Z
tags: clusteralpha, pvp, ranking, competitive
editor: markdown
dateCreated: 2026-01-30T21:15:27.955Z
---

# Cluster Alpha System - Full Breakdown

The Cluster Alpha System is a competitive ranking mechanism for ARK PvP seasons. Tribes earn "Alpha Points" through base power, PvP kills, and raiding.

> **See Also:** [PvP Scenarios & Examples](/clusteralpha/scenarios)

---

## Design Philosophy

**Problem:** ARK's default meta is defensive. Tribes transfer loot off-server during raids, making raiding feel unrewarding.

**Solution:** Make *points* the reward. The system uses a **zero-sum economy** where all PvP points are transferred from victim to killer. This makes every kill and raid meaningful.

---

## Power Rating

Power represents your tribe's base strength, calculated from defensive structures.

### Structure Power Values

| Structure | Power |
|-----------|-------|
| Electric Generator | 1 |
| Plant Species-Z | 2 |
| Plant X / Plant-X Turret | 5 |
| Tek Generator | 8 |
| Ballista/Catapult Turret | 9 |
| Auto Turret | 20 |
| Heavy Turret | 35 |
| Tek Turret | 55 |
| Tek Forcefield | 100 |

### Requirements

- **Turrets must be powered ON**
- **Turrets must have ammo:**
  - Heavy turrets: 2,900+ rounds
  - Tek turrets: 2,500+ element shards
  - Other turrets: 50+ ammo

### Base Detection

Your power comes from your **single largest qualifying base**, not all structures.

**How it works:**
1. Structures are grouped by density clustering (10+ structures within 2.1 lat/lon)
2. Each cluster must have: 2+ foundations, 2+ walls, 1+ door
3. Only the highest-power cluster counts

**This means:**
- FOBs and outposts don't add to your power
- Scattered turrets around the map don't count
- Only your main, defended base matters

### Power Cap

Power is capped at **10,000** for passive point calculations. Tribes above this still benefit from better defense, but won't earn more passive points.

---

## Alpha Points

Points determine rankings. The tribe with the most points at season end wins.

### Point Sources

| Source | Type | Description |
|--------|------|-------------|
| Passive (hourly) | **Minted** | Only source of new points |
| PvP Kills | **Zero-Sum** | Transferred from victim to killer |
| Bounty Board | **Zero-Sum** | Extra points from top 3 tribes |
| Most Wanted | **Zero-Sum** | Extra points for killing top killers |
| Raiding | **Zero-Sum** | Proportional to power destroyed |

---

## Passive Income

Every hour, active tribes earn: **power^0.23** points

| Power | Points/Hour |
|-------|-------------|
| 500 | ~4 pts |
| 1,000 | ~5 pts |
| 5,000 | ~7 pts |
| 10,000 | ~8 pts |

### Activity Requirement

**You must have PvP activity within the last 7 days to earn passive points.**

Activity means:
- At least 1 PvP kill (as killer), OR
- At least 1 enemy structure destroyed

Tribes that "turtle" (sit in base without fighting) earn nothing.

### Zero-Power Decay

Tribes with 0 power lose **10% of their points per hour**. Build a base or lose everything.

---

## PvP Kill Points

When you kill an enemy player, you **steal points from their tribe**.

### Base Formula

```
base_points = 5 + log₁₀(victim_tribe_power) × 2
```

| Victim Tribe Power | Base Points |
|--------------------|-------------|
| 100 | 9 pts |
| 500 | 10 pts |
| 1,000 | 11 pts |
| 5,000 | 12 pts |
| 10,000+ | 13 pts (capped) |

### Tame Kills

When your tame kills an enemy player, you earn **20%** of normal PvP kill points.

**Example:** If killing a player from a 5,000 power tribe normally gives 12 points, your tame killing them gives **2.4 points**.

This rewards tame-based kills while keeping direct player kills more valuable.

### Kill Streak Multiplier

Consecutive kills against the **same tribe** within 1 hour stack:

| Kill # | Multiplier |
|--------|------------|
| 1st | 1.0x |
| 2nd | 1.5x |
| 3rd | 2.0x |
| 4th+ | 2.5x |

### Defense Bonus

**1.5x multiplier** when your structures were damaged in the last 30 minutes.

This rewards defending your base against raiders rather than logging off.

### Underdog Bonus

Smaller tribes get bonus points (up to 50%) when killing players from stronger tribes.

**Formula:** `bonus = min(50%, (victim_power - killer_power) / victim_power × 25%)`

**Example:**
- Your tribe: 1,000 power
- Victim's tribe: 5,000 power
- Bonus: (5000-1000)/5000 × 25% = **20% bonus**

### Multi-Kill Medals

Kill multiple **unique players** within 2.5 minutes for bonus points:

| Kills | Medal | Bonus |
|-------|-------|-------|
| 2 | Double Kill | +25% |
| 3 | Triple Kill | +50% |
| 4 | Overkill | +75% |
| 5 | Killtacular | +100% |
| 6 | Killtrocity | +125% |
| 7 | Killimanjaro | +150% |
| 8 | Killtastrophe | +175% |
| 9 | Killpocalypse | +200% |
| 10+ | Killionaire | +250% |

**Note:** Kills must be against different players (you can't farm the same person).

### Bounty Board

The top 3 tribes by points have bounties on their heads:

| Rank | Bonus When Killed |
|------|-------------------|
| #1 Tribe | +15% |
| #2 Tribe | +10% |
| #3 Tribe | +5% |

The bonus comes FROM the victim tribe's points (zero-sum).

### Most Wanted

The top 3 players by total kills have personal bounties:

| Rank | Bonus When Killed |
|------|-------------------|
| #1 Killer | +15% |
| #2 Killer | +10% |
| #3 Killer | +5% |

---

## Raiding

Destroy enemy structures to steal their accumulated points.

### How It Works

1. When you destroy a power-contributing structure (turret, generator, forcefield), it's logged
2. Every hour, the system calculates how much power each tribe lost
3. Points are stolen based on how much power you dropped them

### Points Stolen Formula

**Simple linear scaling:**
```
Points Stolen = Power Loss % × 75%
```

| Power Loss | Points Stolen |
|------------|---------------|
| 25% wipe | 18.75% of their points |
| 50% wipe | 37.5% of their points |
| 75% wipe | 56.25% of their points |
| 100% wipe | 75% of their points |

**Example:** Tribe B has 1,000 points and 5,000 power. You wipe them completely (100% power loss).
- Points stolen: `100% × 75% = 75%` of their points
- You gain **750 points**, they lose **750 points**

### Multi-Tribe Raids

When multiple tribes raid together, points are split based on **power destroyed**.

**Example:** Tribe A destroys 3,000 power worth of structures, Tribe B destroys 1,000 power worth.
- Tribe A gets **75%** of the stolen points
- Tribe B gets **25%** of the stolen points

### Home Tribe Attribution

Points always go to your **"home tribe"** — the tribe you belong to with the highest power in the cluster.

**Why this matters:**
- You can't abuse FOB tribes to hide points
- If you're in "FOB Tribe" (300 power) but also in "Main Tribe" (5,000 power), your main tribe gets the points
- Prevents shell tribe abuse

### Requirements

For raid points to transfer:
- Victim tribe must be 48+ hours old
- Victim tribe must have 200+ power
- Attacker tribe must have 200+ power

### Why Can't I Steal More Than 75%?

Once you've wiped a tribe (0 power), they have nothing left to lose power-wise. The remaining 25% of their points will naturally decay over time while they're at 0 power.

This prevents "foundation wiping" from being too rewarding - you get the majority of points from the wipe, but there's diminishing returns for continued aggression against a tribe that's already been destroyed.

### Raid Alerts

When a tribe destroys 10+ structures in 5 minutes, a live alert is sent to the alpha channel.

---

## Home Tribe System

Your "home tribe" is your tribe with the **highest power** in the cluster.

**All points (kills and raids) go to your home tribe.**

This prevents:
- Using alt accounts to farm points
- Creating shell tribes to stockpile points
- FOB abuse where small tribes accumulate points

**Minimum Power:** Your home tribe must have 200+ power to receive any points.

### Alliance Detection

Two tribes are considered "allied" if any **active** members share the same home tribe.

**How it works:**
1. System checks each active member's home tribe (highest power tribe)
2. If a member from Tribe A and a member from Tribe B both call Tribe C "home", A and B are allied
3. Allied tribes **cannot earn points** from interactions with each other

**Activity Requirement:** Only members active within the last **24 hours** are considered. Inactive alts don't count.

**Example:**
- Player "Bob" is in both "Alpha Raiders" (5,000 power) and "Beach Bobs" (200 power)
- Bob's home tribe is "Alpha Raiders" (highest power)
- "Alpha Raiders" and "Beach Bobs" are now allied through Bob
- Kills and raids between them award **zero points**

### Visibility Commands

Use these commands to check alliance conflicts BEFORE raiding:

| Command | Description |
|---------|-------------|
| `.conflicts <tribe>` | Check if raiding a specific tribe will earn points |
| `.myalliances` | View all tribes you're connected to (can't earn points from) |

---

## Zero-Sum Economy

The most important anti-abuse feature: **all PvP points are transfers, not created**.

### Why Zero-Sum Prevents Abuse

| Abuse Attempt | Result |
|---------------|--------|
| Kill trading between friends | Net zero — you gain what they lose |
| Farming your own alt | Net zero — your alt's tribe loses what you gain |
| Creating shell tribes | Can't accumulate without fighting |
| Bounty farming | Bounty comes from victim, not created |

**The only way to add points to the economy is passive income**, which requires both power AND activity.

---

## Rivalries

When two tribes have 10+ combined kills against each other within 7 days, they become **RIVALS**.

Kill notifications show the rivalry score:
```
🔥 RIVALS (TribeA 6 - 4 TribeB)
```

Rivalries add narrative to the competition without affecting point calculations.

---

## Announcements

### Milestones
Tribes are announced when reaching: 100, 500, 1K, 5K, 10K, 25K, 50K, 100K points

### Daily Recap (10am UTC)
- Top killer of the day
- Top raider of the day
- Biggest point swings
- New rivalries formed

### Weekly Recap (Mondays 10am UTC)
- Top 5 killers
- Top 5 raiders
- Active rivalries
- Current alpha tribe
- Weekly totals

### Season Warnings
Countdown announcements at: 7d, 3d, 1d, 12h, 6h, 3h, 1h before season end

---

## Commands

| Command | Description |
|---------|-------------|
| `.power` | View power leaderboard |
| `.alpha` | View alpha points leaderboard |
| `.mystats` | View your personal statistics |
| `.mostwanted` | View top 3 killers with bounties |
| `.rivalries` | View active tribal rivalries |
| `.conflicts <tribe>` | Check if raiding a tribe will earn points |
| `.myalliances` | View tribes you're connected to through shared memberships |

---

## Season Rewards

24 hours before wipe, the top 3 tribes receive virtual currency:

| Place | Reward |
|-------|--------|
| 1st | 20x their alpha points |
| 2nd | 10x their alpha points |
| 3rd | 5x their alpha points |

**Example:** 1st place with 10,000 points = 200,000 VC split among members

### 1st Place Bonus

Each member of the winning tribe gets a starter pack next wipe:

**Fighter Kit:** Max microraptor, flak armor, shotgun, ammo, medbrews, shadowsteak, bolas, whip, bear traps

**Tamer Kit:** Max gallimimus + asc saddle, cryopods, kibble, tranq gear, mutagen, nets

**Builder Kit:** Max parasaur + asc saddle, resources, crafting materials
