---
title: Cluster Alpha Breakdown
description: Full breakdown of the Cluster Alpha ranking system for ARK PvP seasons - power ratings, Alpha Points, passive income, kill and raid scoring, home tribes, alliances, and season rewards.
published: true
date: 2026-09-03T00:00:00.000Z
tags: pvp, clusteralpha, ranking, alpha-points
editor: markdown
dateCreated: 2026-01-30T21:15:27.955Z
---

# Cluster Alpha System - Competitive ARK PvP Seasons

<div style="margin: 30px 0; padding: 35px; background-color: rgba(231, 76, 60, 0.15); border-radius: 10px; text-align: center;">
  <h2 style="margin-bottom: 12px;">⚔️ Raid. Conquer. Rank Up.</h2>
  <p style="font-size: 1.15em; max-width: 760px; margin: 0 auto 24px;">Cluster Alpha turns every kill and raid into points. Climb the leaderboard across the season, and the top tribes split massive VertCoin payouts and exclusive starter kits when the map wipes.</p>
  <a href="https://discord.gg/vertyco" style="display: inline-block; padding: 14px 28px; background-color: #5865F2; color: white; text-decoration: none; border-radius: 6px; font-weight: bold; font-size: 1.05em; box-shadow: 0 2px 6px rgba(0,0,0,0.2);">
    <i class="fab fa-discord" style="margin-right: 10px;"></i> Join the Battle on Discord
  </a>
</div>

## 🏆 Why Cluster Alpha?

<div style="display: flex; flex-wrap: wrap; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; min-width: 240px; padding: 18px; background-color: rgba(46, 204, 113, 0.15); border-radius: 6px;">
    <h3>💯 Zero-Sum Economy</h3>
    <p>Every point you earn is stolen from a rival. No farming, no exploits, only real PvP moves the leaderboard.</p>
  </div>

  <div style="flex: 1; min-width: 240px; padding: 18px; background-color: rgba(241, 196, 15, 0.15); border-radius: 6px;">
    <h3>🗡️ Raids That Matter</h3>
    <p>Wipe an enemy base and steal up to 75% of their points. Raiding is finally worth the C4.</p>
  </div>

  <div style="flex: 1; min-width: 240px; padding: 18px; background-color: rgba(155, 89, 182, 0.15); border-radius: 6px;">
    <h3>👑 Season Rewards</h3>
    <p>Top 3 tribes earn up to 15× their Alpha Points in VertCoin, plus a Fighter, Tamer, or Builder starter kit next wipe.</p>
  </div>
</div>

## 📡 See It Live

Every day and week, the bot auto-posts recaps to our `alpha-feed` channel: top killers, top raiders, biggest point swings, active rivalries, and the reigning alpha tribe.
<div style="margin: 20px 0; text-align: center;">
  <img src="/assets/weekly-alpha-recap.png" alt="Weekly Alpha Recap embed posted automatically in Discord" style="max-width: 480px; width: 100%; border-radius: 10px; box-shadow: 0 4px 14px rgba(0,0,0,0.3);" />
  <p style="font-size: 0.9em; opacity: 0.75; margin-top: 10px;">Live weekly recap, auto-posted every Monday at 10am Eastern.</p>
</div>

The Cluster Alpha System is a competitive ranking mechanism for ARK PvP seasons. Tribes earn **Alpha Points** through base power, PvP kills, and raiding.

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

- **A powered structure that is toggled OFF does not count.** Unpowered turrets still count if they hold ammo
- **Turrets with 100+ rounds** = Full power value
- **Turrets with 1-99 rounds** = Half power value
- **Empty turrets (0 rounds)** = No power
- **Turrets do not stack when crowded.** A turret placed within 200 units (about 2 metres) of an already-counted turret is skipped, and only one of the pair counts. The higher-value turret is the one kept, so a Heavy next to an Auto keeps the Heavy

### Turret Ammo Examples

| Turret | Full Ammo (100+) | Low Ammo (1-99) | Empty |
|--------|------------------|-----------------|-------|
| Auto Turret | 20 power | 10 power | 0 |
| Heavy Turret | 35 power | 17 power | 0 |
| Tek Turret | 55 power | 27 power | 0 |

### Base Detection

Your power comes from your **single highest-power base**, not from all your structures added together.

**How it works:**
1. Structures are grouped by density clustering: 10 or more structures within 2.1 lat/lon of each other
2. Only the highest-power cluster counts toward your rating

**This means:**
- Only one base counts. A second base, a FOB or an outpost adds nothing, unless it out-powers your main and becomes the one that counts
- Isolated turrets and thin scatter are ignored. They never reach the density needed to form a cluster
- There is **no** foundation, wall or door requirement. Density is the only test

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

**Your tribe must have PvP activity within the last 2 days to earn passive points.**

Activity means any of these, and it counts in **either direction**:
- A PvP kill, whether your tribe made it or took it
- A structure destroyed, whether you blew up theirs or they blew up yours
- An enemy tame killed

**Being attacked counts.** If someone raids you or kills your members, your activity timer refreshes
exactly as if you had gone on the offensive yourself. A tribe under regular attack keeps earning.

### Zero-Power Decay

A tribe sitting at **exactly 0 power** loses **10% of its points per hour**. Build a base or lose everything.

Any power at all stops the decay, and a tribe inside its wipe grace window does not decay either
(see Wipe Grace below).

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

### Kill Streak Multiplier

Consecutive kills against the **same tribe** within 1 hour stack:

| Kill # | Multiplier |
|--------|------------|
| 1st | 1.0x |
| 2nd | 1.1x |
| 3rd | 1.2x |
| 4th+ | 1.3x |

> This is deliberately the smallest kill bonus. The window is a full hour, so a streak is much easier to hold than a Multi-Kill chain, and it pays less for it. If you want the big multipliers, chain kills fast rather than grinding one tribe.
{.is-info}

### Underdog Bonus

Smaller tribes get bonus points when killing players from stronger tribes, up to **+25%**.

**Formula:** `bonus = (1 - killer_power / victim_power / 0.75) × 25%`

You qualify only while your tribe holds **less than 75%** of the victim tribe's power. At 75% or above
the bonus is zero. There is no partial credit near the line, it cuts off cleanly.

| Your power vs theirs | Bonus |
|----------------------|-------|
| 10% | +21.7% |
| 20% | +18.3% |
| 25% | +16.7% |
| 50% | +8.3% |
| 75% or more | none |

**Example:**
- Your tribe: 1,000 power
- Victim's tribe: 5,000 power
- You hold 20% of their power: `(1 - 0.20 / 0.75) × 25%` = **+18.3% bonus**

### Multi-Kill Medals

Kill multiple players within 3 minutes of each other for bonus points:

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
| 10 | Killionaire | +250% |

**Note:** The 3 minute window is measured **between consecutive kills**, not from the first kill. Every new kill restarts the clock, so a long chain can run well past 3 minutes end to end. One kill every 2 minutes for 10 minutes is a 5-kill chain.

Each kill has to be against a **different player than the one right before it**. Killing the same player twice in a row ends the chain and starts a new one. Alternating is fine: Player A, then B, then A again counts as 3.

Killionaire is the top of the ladder. Once you hit it the chain ends, and your next kill starts a fresh chain from the beginning, so the 12th kill in a row is a Double Kill again.

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

Points always go to your **"home tribe"**, the tribe you belong to with the highest power in the cluster.

**Why this matters:**
- You can't abuse FOB tribes to hide points
- If you're in "FOB Tribe" (300 power) but also in "Main Tribe" (5,000 power), your main tribe gets the points
- Prevents shell tribe abuse

### Requirements

There is **no** minimum tribe age and **no** minimum power, on either side. Two rules can stop a raid from paying:

**The 30% rule.** You earn nothing for raiding a tribe holding less than **30% of your alpha points** *and* less than **30% of your power**. Both have to be under the line. If the defender clears 30% on either one, the raid pays as normal. This stops the leaders from farming the bottom of the board.

**The bottom-of-the-board exception.** If the 30% rule leaves you with fewer than **5** legal targets in the cluster, you can still raid the **5 tribes directly below you** on the points leaderboard. Nobody gets locked out of raiding just for being on top.

Punching up is always allowed. There is no cap on raiding a tribe bigger than you.

> Use `.conflicts <tribe>` before you spend the C4. It runs every one of these checks, plus alliance detection, and tells you whether the raid will actually pay.
{.is-info}

### Why Can't I Steal More Than 75%?

Once you've wiped a tribe to 0 power, they have nothing left to lose power-wise. The remaining 25% of their points decays away while they sit at 0 power, though not straight away: see Wipe Grace below.

This prevents "foundation wiping" from being too rewarding - you get the majority of points from the wipe, but there's diminishing returns for continued aggression against a tribe that's already been destroyed.

### Wipe Grace

A tribe that loses **90% or more of its power in a single hour** to a real raid gets **48 hours of grace**.

While grace is active:
- **No raid points can be taken from them.** Hitting what is left of their base earns you nothing
- **Their points do not decay**, even sitting at 0 power

Grace only fires if structures were actually destroyed. A tribe that powers down its own turrets, or relocates its base, does not get it.

This is why a freshly wiped tribe can hold 0 power for two days without bleeding points, and why flattening the same tribe twice in one night only pays once.

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

**Minimum Power:** none. Your home tribe is simply whichever of your tribes holds the most power. If every tribe you belong to is at 0 power, you have no home tribe at all and your kills credit nobody until you rebuild. Use `.mystats` to see which tribe you are currently credited to.

### Alliance Detection

Two tribes are considered "allied" if any **active** members share the same home tribe.

**How it works:**
1. System checks each active member's home tribe (highest power tribe)
2. If a member from Tribe A and a member from Tribe B both call Tribe C "home", A and B are allied
3. Allied tribes **cannot earn points** from interactions with each other

**Activity Requirement:** The check looks for tribe members seen in the last hour first, then widens the window until it finds somebody: 1 hour, 24 hours, 7 days, then 60 days. A tribe nobody has logged into for weeks still has "active" members for this purpose, so parking an alt tribe and leaving it dormant does **not** get you out of alliance detection.

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
| Kill trading between friends | Net zero, you gain what they lose |
| Farming your own alt | Net zero, your alt's tribe loses what you gain |
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

### Daily Recap (10am Eastern)
- Top killer of the day
- Top raider of the day
- Biggest point swings
- New rivalries formed

### Weekly Recap (Mondays 10am Eastern)
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
| `.mypower` | Break down your own tribe's power, including what was not counted and why |
| `.mostwanted` | View top 3 killers with bounties |
| `.rivalries` | View active tribal rivalries |
| `.conflicts <tribe>` | Check if raiding a tribe will earn points |
| `.targets` | List which tribes you can raid for points, and who is off limits |
| `.myalliances` | View tribes you're connected to through shared memberships |

---

## Season Rewards

24 hours before wipe, the top 3 tribes receive virtual currency:

| Place | Reward |
|-------|--------|
| 1st | 15x their alpha points |
| 2nd | 10x their alpha points |
| 3rd | 5x their alpha points |

**Example:** 1st place with 80,000 points = 1,200,000 VC

The payout goes to the tribe owner, who distributes it among the members.

### 1st Place Bonus

Each member of the winning tribe gets a starter pack next wipe:

**Fighter Kit:** 10 bolas, wyvern chibi, microraptor, 1 set of mid flak, 1 set of prim flak, 10 bear traps, shotgun (double barrel), 35 shells, slingshot, prim whip

**Tamer Kit:** 5 cryopods, stego chibi, gallimimus with saddle, harpoon and 35 nets, 10 large bear traps, 105.5 longneck, 35 tranq darts, 100 mutagel, 50 mutagen, 100 narcotics, 10 dino gateways and 5 gates, 5 wooden billboards, wooden club

**Builder Kit:** Raft and stone base with smithy, regular forge, cooking pot, 2 simple beds, and a parasaur

---

<div style="margin: 40px 0; padding: 35px; background-color: rgba(88, 101, 242, 0.15); border-radius: 10px; text-align: center;">
  <h2 style="margin-bottom: 12px;">Ready to claim the top spot?</h2>
  <p style="font-size: 1.1em; max-width: 700px; margin: 0 auto 24px;">Pick a tribe, build your power, and start stealing points. The next season is waiting.</p>
  <a href="https://discord.gg/vertyco" style="display: inline-block; padding: 14px 28px; background-color: #5865F2; color: white; text-decoration: none; border-radius: 6px; font-weight: bold; font-size: 1.05em; box-shadow: 0 2px 6px rgba(0,0,0,0.2);">
    <i class="fab fa-discord" style="margin-right: 10px;"></i> Join the Vertyco Discord
  </a>
</div>
