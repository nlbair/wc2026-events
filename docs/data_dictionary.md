# Data Dictionary

Complete column definitions for WC 2026 event CSVs in `data/raw/`.

---

## Match Metadata Columns

These six columns are prepended to every row and are identical across all events in a file.

| Column | Type | Example | Description |
|--------|------|---------|-------------|
| `away_score` | int | `1` | Away team final score (full time) |
| `home_score` | int | `1` | Home team final score (full time) |
| `away_team` | str | `Bosnia and Herzegovina` | Away team name as returned by WhoScored |
| `home_team` | str | `Canada` | Home team name as returned by WhoScored |
| `match_date` | str | `2026-06-12` | Match date in YYYY-MM-DD format |
| `match_id` | int | `1976989` | WhoScored internal match ID (also in the URL) |

---

## Core Event Columns

| Column | Type | Example | Description |
|--------|------|---------|-------------|
| `id` | int | `1` | Sequential event ID within the match |
| `eventId` | int | `1` | WhoScored event type ID (numeric) |
| `minute` | int | `23` | Match minute, 0-indexed. Minute 0 = kick-off. Add 1 for display. |
| `second` | int | `14` | Second within the minute (0–59) |
| `expandedMinute` | int | `23` | Accounts for stoppage time; use this for sorting in extra time |
| `teamId` | int | `4` | WhoScored internal team ID |
| `playerId` | int | `12345` | WhoScored internal player ID |
| `x` | float | `74.3` | X coordinate on the pitch (0–100). 0 = left end, 100 = right end. Opta coordinate system. |
| `y` | float | `51.2` | Y coordinate on the pitch (0–100). 0 = bottom, 100 = top. Opta coordinate system. |

---

## Derived / Decoded Columns

These are decoded from WhoScored's nested JSON into human-readable strings.

| Column | Type | Values / Example | Description |
|--------|------|-----------------|-------------|
| `team` | str | `Canada` | Team name, decoded from `teamId` |
| `player` | str | `Alphonso Davies` | Player name, decoded from `playerId` |
| `event` | str | `Pass`, `Goal`, `SavedShot`, `MissedShots`, `BlockedShot`, `Tackle`, `Interception`, `Clearance`, `Foul`, `CornerAwarded`, `BallRecovery`, `Dispossessed`, `TakeOn`, `Aerial`, `OffsidePassed`, `Error`, `GoodSkill`, `KeeperPickup`, `KeeperSweeper` | Event type display name |
| `outcome` | str | `Successful`, `Unsuccessful` | Event outcome |
| `period_name` | str | `FirstHalf`, `SecondHalf`, `ExtraTimeFirstHalf`, `ExtraTimeSecondHalf`, `PenaltyShootout` | Match period |
| `period_value` | int | `1`, `2`, `3`, `4`, `5` | Numeric period (1=first half, 5=shootout) |
| `cardType` | str | `Yellow`, `Red`, `SecondYellow` \| `None` | Card type if event is a card, else absent/null |

---

## Boolean Flag Columns

| Column | Type | Description |
|--------|------|-------------|
| `isShot` | bool | `True` if the event is any shot attempt (Goal, SavedShot, MissedShots, BlockedShot) |
| `isGoal` | bool | `True` if the event resulted in a goal |
| `isTouch` | bool | `True` if the event involves a ball touch (used for touch maps) |

---

## Qualifier Columns (`qual_*`)

Qualifiers are additional attributes attached to events. They are expanded from WhoScored's nested qualifier list into flat boolean or value columns. **Not all qualifier columns appear in every match** — a column only appears if at least one event in that match had that qualifier.

Boolean qualifiers are `True` if present, `False` (or absent) otherwise.

### Shot Qualifiers

| Column | Type | Description |
|--------|------|-------------|
| `qual_Head` | bool | Shot taken with the head |
| `qual_RightFoot` | bool | Shot taken with the right foot (left foot if absent and not header) |
| `qual_Penalty` | bool | Shot is a penalty kick. Note: xG for penalties is hard-coded to 0.76 |
| `qual_BigChance` | bool | WhoScored flagged this as a big chance |
| `qual_FastBreak` | bool | Shot came from a fast break / counter-attack |
| `qual_SetPiece` | bool | Shot came from a set piece situation |
| `qual_FreekickTaken` | bool | Shot was a direct free kick attempt |
| `qual_Assisted` | bool | Shot was assisted (preceded by a key pass) |
| `qual_Blocked` | bool | Shot was blocked by an outfield player |
| `qual_OwnGoal` | bool | Event was an own goal |

### Pass Qualifiers

| Column | Type | Description |
|--------|------|-------------|
| `qual_KeyPass` | bool | Pass that directly led to a shot |
| `qual_IntentionalGoalAssist` | bool | WhoScored-designated assist |
| `qual_Cross` | bool | Pass was a cross |
| `qual_CornerTaken` | bool | Pass was taken from a corner |
| `qual_FreekickTaken` | bool | Pass was taken from a free kick |
| `qual_Zone` | str | Pitch zone the pass originated from |
| `qual_PassEndX` | float | X coordinate of pass destination |
| `qual_PassEndY` | float | Y coordinate of pass destination |
| `qual_Length` | float | Pass length in pitch units |
| `qual_Angle` | float | Pass angle in degrees |

### Other Qualifiers

| Column | Type | Description |
|--------|------|-------------|
| `qual_GoalMouthY` | float | Y position in the goal mouth where a shot was aimed (shots only) |
| `qual_GoalMouthZ` | float | Z (height) position in goal mouth |
| `qual_RelatedEventId` | int | ID of a related event (e.g. the pass before a shot) |
| `qual_Type` | str | Sub-type detail for certain events |

> This list covers the most common qualifiers observed across WC 2026 matches. Additional `qual_*` columns may appear as the tournament progresses.

---

## Coordinate System

All coordinates use the **Opta system**:

- `x`: 0 (own goal line) → 100 (opponent goal line)
- `y`: 0 (bottom touchline) → 100 (top touchline)
- Pitch center: (50, 50)
- The attacking direction is always left-to-right (x increases toward opponent goal) — **teams do not swap sides between halves in this data**

For shot maps, the attacking half is x > 50. For `mplsoccer` VerticalPitch with `pitch_type="opta"`, pass `y` as the horizontal axis and `x` as the vertical axis.

---

## File Naming Convention

```
wc2026_{home_team}_vs_{away_team}_{date}_events.csv
```

- Team names are lowercased, spaces replaced with `_`, hyphens replaced with `_`
- Date is YYYY-MM-DD
- Example: `wc2026_canada_vs_bosnia_and_herzegovina_2026-06-12_events.csv`
