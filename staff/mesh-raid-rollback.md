---
title: Mesh-Raid Rollbacks (SOP)
description: Internal procedure for confirmed mesh-raid wipes, rollback approval, and incident recovery on Vertyco PvP servers.
published: true
date: 2026-05-14T00:00:00.000Z
tags: staff, pvp, cheating, rollback
editor: markdown
dateCreated: 2026-05-14T00:00:00.000Z
---

# Mesh-Raid Rollbacks (SOP)

## Policy Summary
This SOP applies only to **confirmed PvP mesh-raid wipes** on the **affected map/server only**. Rollback is the preferred remedy when a tribe is wiped through confirmed mesh access because trying to rebuild a season-built base by hand is inaccurate, inconsistent, and impossible to value fairly.

This policy is a narrow exception to the normal rule that Staff do not replace lost items. Outside of confirmed mesh-raid wipe cases, continue using the default guidance in [Handling Tickets](/staff/tickets).

> Do not promise a rollback, reimbursement, or recovery package before the eligibility checks and approval steps below are complete.
{.is-warning}

## Eligibility for Rollback
All of the following must be true:

- The incident is a **confirmed mesh raid** under [PvP Rule 2.2](/rules/pvp).
- The affected tribe was **wiped or effectively wiped from the inside**, making normal internal defenses irrelevant.
- The rollback can be limited to the **affected map/server only**.
- The rollback window is **6 hours or less**.
- There were **10 or fewer unique players** seen online on that map during the rollback window.
- There were **no major unrelated raids** on that same map during the rollback window.
- **Two uninvolved Admins** approve the action.

## What Counts as a Major Raid
For this SOP, a major raid is any unrelated raid on the same map during the rollback window that would make a rollback unfair to other players because it likely created a significant Alpha Point swing or wiped meaningful legitimate progress.

Use the following standard when reviewing the window:

- Start from the user-facing intent: if another tribe completed a meaningful legitimate raid during that window, the rollback should normally be denied.
- Use structure-destruction logs and raid context to judge whether the raid was significant.
- The current database does **not** expose historical raid-point transfers directly, so the staff target of **more than 1,000 Alpha Points transferred** is a **manual Admin review threshold**, not a fully automated SQL check.

> If Staff cannot confidently say that the rollback window is free of major unrelated raids, deny the rollback and move to the fallback section below.
{.is-info}

## Automatic Denials
Do **not** approve a rollback if any of the following apply:

- The report does not prove a mesh raid.
- The loss was serious but not a wipe or near-wipe caused by the mesh access.
- The required rollback window exceeds **6 hours**.
- More than **10 unique players** were online on the affected map during the rollback window.
- Another major unrelated raid happened on the same map during the rollback window.
- A clean restore point cannot be identified.
- A required approver is recused and no second uninvolved Admin review is available.

## Evidence Required
Before approving any action, gather and document all of the following that are available:

- Ticket link and reporting player
- Server/map name
- Approximate raid start time and discovery time
- GPS coordinates and tribe names
- Video or screenshot proof of the mesh access or inside-out wipe
- Names or IDs of suspected offenders
- Any tribe log or structure-destruction evidence that helps anchor the rollback window

If the initial report is credible but incomplete, keep the ticket open and continue gathering evidence. Do not fill gaps with assumptions.

## Approval Rules
- Rollbacks require **two uninvolved Admin approvals**.
- Any limited incident-recovery package also requires **two uninvolved Admin approvals**.
- Apply the recusal standards from [Conflict of Interest Policy](/staff/conflict-of-interest).
- Moderators may collect evidence and prepare the review, but they should not promise an outcome.

## Staff Procedure
1. **Acknowledge the ticket**
   - Confirm Staff are investigating a PvP cheating report.
   - Ask for timestamps, GPS, tribe names, map, and video if not already provided.
2. **Verify the exploit**
   - Confirm the raid involved mesh access under [PvP Rule 2.2](/rules/pvp).
   - Confirm the loss is a wipe or effective wipe caused by that unfair access.
3. **Set the rollback window**
   - Choose the smallest workable rollback window.
   - Never exceed **6 hours**.
4. **Check map activity**
   - Count unique players seen online on that map during the proposed rollback window.
   - Review whether any major unrelated raid happened on that same map during that window.
5. **Choose the remedy**
   - If all rollback requirements are met, approve the rollback.
   - If any requirement fails, deny the rollback and evaluate the fallback section.
6. **Execute and document**
   - Record the final decision, approvers, rollback window, and reimbursement output.
   - Keep the SQL results or screenshots with the ticket notes.

## Reimbursement After an Approved Rollback
If a rollback is approved, reimburse **every player who was online on the affected map during the rollback window** at **200 VC per minute of lost playtime**.

Use these rules consistently:

- Reimbursement is based on time online **during the rollback window only**.
- Count overlapping time on the **affected map/server only**.
- **Round partial minutes up** to the next whole minute so players are not underpaid.
- If a player is unlinked in the database, record the gamertag and resolve identity before paying VC.

## SQL Reference
### 1. Identify the Server UUID
```sql
SELECT id, name
FROM public.server
ORDER BY name;
```

### 2. Count Unique Players Seen Online During the Rollback Window
```sql
WITH params AS (
    SELECT
        s.id AS server_id,
        s.guild_id,
        TIMESTAMPTZ '2026-05-14 00:00:00+00' AS window_start,
        TIMESTAMPTZ '2026-05-14 03:00:00+00' AS window_end
    FROM public.server s
    WHERE s.id = 'PUT_SERVER_UUID_HERE'::uuid
),
ordered AS (
    SELECT
        jl.server,
        jl.gameid,
        jl.username,
        jl.event_at,
        jl.action,
        LEAD(jl.event_at) OVER (
            PARTITION BY jl.server, jl.gameid
            ORDER BY jl.event_at
        ) AS next_event_at
    FROM public.join_leave jl
    JOIN params p
        ON jl.server = p.server_id
       AND jl.guild_id = p.guild_id
    WHERE jl.event_at < p.window_end
),
overlap AS (
    SELECT
        o.gameid,
        GREATEST(o.event_at, p.window_start) AS online_from,
        LEAST(COALESCE(o.next_event_at, p.window_end), p.window_end) AS online_to
    FROM ordered o
    CROSS JOIN params p
    WHERE o.action = 1
      AND COALESCE(o.next_event_at, p.window_end) > p.window_start
)
SELECT COUNT(DISTINCT gameid) AS unique_players_seen_online
FROM overlap
WHERE online_to > online_from;
```

### 3. Calculate Per-Player VC Reimbursement
```sql
WITH params AS (
    SELECT
        s.id AS server_id,
        s.guild_id,
        TIMESTAMPTZ '2026-05-14 00:00:00+00' AS window_start,
        TIMESTAMPTZ '2026-05-14 03:00:00+00' AS window_end
    FROM public.server s
    WHERE s.id = 'PUT_SERVER_UUID_HERE'::uuid
),
ordered AS (
    SELECT
        jl.server,
        jl.gameid,
        jl.username,
        jl.event_at,
        jl.action,
        LEAD(jl.event_at) OVER (
            PARTITION BY jl.server, jl.gameid
            ORDER BY jl.event_at
        ) AS next_event_at
    FROM public.join_leave jl
    JOIN params p
        ON jl.server = p.server_id
       AND jl.guild_id = p.guild_id
    WHERE jl.event_at < p.window_end
),
overlap AS (
    SELECT
        o.gameid,
        o.username,
        GREATEST(o.event_at, p.window_start) AS online_from,
        LEAST(COALESCE(o.next_event_at, p.window_end), p.window_end) AS online_to
    FROM ordered o
    CROSS JOIN params p
    WHERE o.action = 1
      AND COALESCE(o.next_event_at, p.window_end) > p.window_start
),
player_minutes AS (
    SELECT
        gameid,
        MAX(username) AS username,
        SUM(EXTRACT(EPOCH FROM (online_to - online_from)) / 60.0) AS minutes_online
    FROM overlap
    WHERE online_to > online_from
    GROUP BY gameid
)
SELECT
    pm.gameid,
    pm.username,
    pl.discord_id,
    ROUND(pm.minutes_online::numeric, 2) AS exact_minutes,
    CEIL(pm.minutes_online)::int AS reimbursed_minutes,
    CEIL(pm.minutes_online)::int * 200 AS vc_reimbursement
FROM player_minutes pm
JOIN params p
    ON TRUE
LEFT JOIN public.player pl
    ON pl.guild_id = p.guild_id
   AND pl.gameid = pm.gameid
ORDER BY vc_reimbursement DESC, pm.username;
```

### 4. Review Other Raid Activity on the Same Map During the Window
```sql
WITH params AS (
    SELECT
        TIMESTAMPTZ '2026-05-14 00:00:00+00' AS window_start,
        TIMESTAMPTZ '2026-05-14 03:00:00+00' AS window_end,
        'PUT_SERVER_UUID_HERE'::uuid AS server_id
)
SELECT
    attacker_tribe,
    victim_tribe,
    SUM(power_value) AS total_power_destroyed,
    COUNT(*) AS structures_destroyed
FROM public.structure_destroy_event s
JOIN params p
    ON s.server = p.server_id
WHERE s.created_on >= p.window_start
  AND s.created_on < p.window_end
GROUP BY attacker_tribe, victim_tribe
HAVING SUM(power_value) > 0
ORDER BY total_power_destroyed DESC, structures_destroyed DESC;
```

### 5. Review PvP Kill Activity on the Same Map During the Window
```sql
WITH params AS (
    SELECT
        TIMESTAMPTZ '2026-05-14 00:00:00+00' AS window_start,
        TIMESTAMPTZ '2026-05-14 03:00:00+00' AS window_end,
        'PUT_SERVER_UUID_HERE'::uuid AS server_id
)
SELECT
    killer_tribe,
    victim_tribe,
    SUM(points_awarded) AS total_kill_points,
    COUNT(*) AS kill_events
FROM public.pvp_event e
JOIN params p
    ON e.server = p.server_id
WHERE e.created_on >= p.window_start
  AND e.created_on < p.window_end
GROUP BY killer_tribe, victim_tribe
ORDER BY total_kill_points DESC, kill_events DESC;
```

> `public.join_leave` supports the player-count and reimbursement checks directly. Historical raid-point transfer totals are not exposed directly in the current schema, so use the raid-activity queries above as part of the Admin review for the major-raid gate.
{.is-info}

## Fallback When Rollback Is Denied
If the rollback requirements are not met, do **not** attempt to rebuild the wiped base or calculate the full value of a season-built tribe in VC.

The fallback policy is:

- Punish the offender under the normal mesh-raiding and cheating rules.
- Do **not** promise full restoration of structures, tames, inventory, or raid progress.
- Admins may approve a **limited incident-recovery measure** only when the mesh raid is confirmed and the loss is severe.
- Any incident-recovery measure must be **one-time, tightly capped, and clearly documented as goodwill rather than full reimbursement**.
- Incident-recovery measures may include a modest VC grant, a limited essentials package, or both, but they must stay small enough that they do not function as a full rebuild.

### Recovery Cap Rules
- Limited incident recovery is **optional**, not automatic.
- It requires **two uninvolved Admin approvals**.
- Use **one tribe-level package per incident**, not per-player claims.
- Do **not** run item-by-item claim reviews for a wiped base.
- If Staff cannot keep the package modest and consistent, deny it.

## Suggested Staff Response
> Thanks for the report. We are investigating this as a possible PvP cheating case. If Staff confirm a mesh-raid wipe, we will review whether a rollback on the affected map is possible. We cannot promise a rollback or item replacement while that review is in progress.
> {.is-info}