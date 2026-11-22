# Project State — Chaos

Last updated: 2026-11-22

This is the shared source of truth for the user's Sonic-inspired Roblox RPG. It distinguishes user-decided design from implementation reported or verified in Roblox Studio.

## Project identity
- Project: Sonic-inspired Roblox RPG.
- Repository: zelodeusZ/chaos (private).
- Platform: Roblox.
- Owner: User; final design authority.
- Target Studio experience: **Untitled Experience**.
- Reference-only Studio experience: **Example**. Never modify it.
- Character rig: R6 StarterCharacter (reported in the current project handoff).
- Roblox place/source files are not stored in this repository. This repository is development memory and coordination, not the game itself.

## User-decided design

### Races and Race Traits
- Character identity is a combination of **Race + Race Trait**.
- Current race roster: Hedgehog, Fox, Echidna, Rabbit, Cat, Chameleon, Bat, Bird, Wolf, Android.
- The former Robot race is replaced by **Android**.
- Android Race Traits: **Bioroid** and **Mechadroid**.
- Fox Race Traits: **1-Tailed** (default) and **2-Tailed** (alternate).
- Example identity format: Android — Mechadroid.
- Race Traits are a distinct layer from race; do not collapse them into separate races.

### Seven primary stats and Chaos Emeralds
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

The seven-stat model is retained. Emeralds grant greater access to Chaos / Chaos Energy as well as their respective stat; Green is the strongest association for Chaos because it represents Chaos itself.

Keep this design separate from current combat, visuals, and implementation work unless the owner explicitly connects them.

### Chaos-energy system and equipment
- **Chaos Shards:** Naturally occurring crystallized excess Chaos Energy; absorbed through the skin.
- **Chaos Cores:** Artificial concentrations refined and compressed from Chaos Shards.
- **Chaos Emeralds:** Seven globally unique legendary artifacts; see mapping above.
- **Chaos Capacitor:** Old World sternum implant that absorbs and stores ambient Chaos Energy. Enables artificial Chaos Control and environmental/body manipulation. It has limited durability, wears from charging and use, and can break in combat.
- **Control Gloves:** Exact user-chosen name. Specialized gloves used alongside a Chaos Capacitor to direct and manipulate the Chaos Energy it harnesses. Do not rename either item without approval.
- **Pseudo-Super:** Artificial transformation requiring sufficient Chaos Energy; it is not itself a Chaos Capacitor.
- **True Super:** Naturally achieved counterpart to Pseudo-Super.
- Still undecided: exact True Super requirements/mechanics and whether/how additional Capacitors affect Pseudo-Super power or duration.

### Movement / identity
- Superspeed is universally bound to **Q**.
- Superspeed behavior varies by character class; the input is universal, the movement behavior is class-specific.

## Reported implementation architecture (requires fresh inspection before treating as verified code facts)
The latest project handoff identified these paths and objects:
- `CombatService.State`
- `CombatService.Weapon`
- `CombatService.Damage`
- `CombatService.Danger`
- `CombatService.WeaponEquip`
- `ReplicatedStorage.CombatConfig`
- `ReplicatedStorage.CombatAnimations`
- `CombatInputClient`
- `StarterPack.Sword`, with `WeaponId = "Sword"`
- `StarterCharacter` uses R6.

These are recorded as reported project structure, not independently inspected by this repository. Confirm exact hierarchy and source before changing code.

## Combat implementation status — latest handoff
Stage 3 Generic Combat Integration is **incomplete**.
- Reported passing lifecycle checks: Fists and Sword Swing/Block; seven weapon/non-combat transitions; Non-Combat blocks Swing and Block; death/respawn without combat errors; Sword returns unequipped via StarterPack.
- Reported combat tests: unblocked Fists hit deals 3.5 damage (dummy 100 → 96.5); blocked hit prevented damage and fired BlockHit.
- Unresolved: blocked-hit posture increased 0 → 13.2 while expected value was 11.5; formula/source discrepancy remains open.
- Parry/attacker stun, guard break, actual animation track playback, and remaining defensive/resource/movement checks are not confirmed complete.
- All 11 combat animations reportedly load, but successful playback is not thereby proven.
- Sword-specific M1/Block/Parry/Critical animation entries were reported nil; generic resolver can resolve BlockHit/Parried/Uppercut.
- See COMBAT_SYSTEM.md and TEST_RESULTS.md for detail.

## Roblox Studio safeguards
- Untitled Experience is the target.
- Example is reference-only and must never be modified.
- Confirm the active Studio instance before edits if ambiguous.
- Do not infer implementation from design notes.
- Keep harness/tool errors separate from actual game test outcomes.

## Unknown / needs direct inspection
- Current exact Roblox place hierarchy and source paths.
- Whether the reported combat paths and resolver are still current.
- Exact seven-stat definitions beyond the Emerald mapping, and complete stat formulas.
- Full class roster and class-specific superspeed behavior.
- Full skill, progression, world, rail, and pole implementation state.
- Current status of stamina, armor, Danger, posture, hitstun, and movement interactions.
- Exact implementation status of Races, Race Traits, Emeralds, Chaos Shards/Cores, Capacitors, and Control Gloves.

## Evidence labels
Use these labels consistently:
- **USER-DECIDED:** explicitly selected by the owner.
- **REPORTED:** stated in a handoff or prior session but not independently re-inspected in the current session.
- **CONFIRMED:** directly inspected or tested with evidence.
- **PROPOSED:** suggestion not yet approved.
- **UNKNOWN:** not established.
