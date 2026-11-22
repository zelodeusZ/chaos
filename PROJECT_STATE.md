# Project State — Chaos

Last initialized: 2026-11-22

This file separates user-approved design decisions from implementation claims. Only details available in the shared project context are recorded.

## Project identity
- Project: Sonic-inspired Roblox RPG.
- Repository: zelodeusZ/chaos (private).
- Engine/platform: Roblox.
- Owner: User.
- Implementation status: UNKNOWN from this repository alone. The repository does not contain the Roblox place or source export.

## Confirmed design decisions

### Race system
- The system is structured around Races and Race Traits.
- Replace the former Robot race with Android.
- Android Race Traits: Bioroid and Mechadroid.
- Foxes have a default 1-Tailed Race Trait and an alternate 2-Tailed Race Trait.
- A character is identified by both race and trait, e.g. Android — Mechadroid.

### Chaos Emeralds
There are seven globally unique Chaos Emeralds. Each represents one primary stat and its associated fundamental principle.

| Emerald | Primary stat | Principle |
|---|---|---|
| Red | Power | Physical force |
| Blue | Speed | Motion |
| Yellow | Durability | Resilience |
| Green | Chaos | Chaos Energy |
| Purple | Control | Precision and manipulation |
| Cyan | Output | Energy release and amplification |
| White | Intelligence | Cognition and perception |

Keep this design separate from current combat, visuals, and implementation work unless the user explicitly connects them.

### Chaos-energy equipment
- Chaos Capacitor: implanted near the sternum; absorbs and stores ambient Chaos Energy; enables artificial Chaos Control.
- Control Gloves: exact user-chosen name. Specialized gloves used alongside a Chaos Capacitor to direct and manipulate the Chaos Energy it harnesses.
- Do not rename either item without the user's approval.

## Roblox Studio safeguards
- Untitled Experience is the target experience.
- Example is reference-only and must never be modified.
- Confirm the active Studio instance before making changes if ambiguous.

## Implementation status
No implementation details are verified by this repository yet. Do not assume the race system, emeralds, Chaos Capacitor, Control Gloves, combat systems, or related mechanics are implemented merely because their designs are recorded here.

Populate this section only with inspected code or direct Roblox Studio test evidence. Include relevant script paths and verification dates.

## Unknown / needs project inspection
- Current Roblox place file and source layout.
- Current implemented features and exact script/module locations.
- Current combat and progression implementation status.
- Immediate development priority beyond the initial inventory task.
- Additional race, trait, stat, skill, world, or progression decisions not listed above.
