# Session Handoff — Chaos

Updated: 2026-11-22

## Project
Sonic-inspired Roblox RPG. Shared repository: `zelodeusZ/chaos`.

## Read first
- README.md
- CLAUDE.md
- PROJECT_STATE.md
- CURRENT_TASK.md
- COMBAT_SYSTEM.md
- TEST_RESULTS.md

## Owner constraints
- The user is the final design authority.
- Target Studio experience is **Untitled Experience**.
- **Example** is reference-only; never modify it.
- Finish Stage 3 Generic Combat Integration before Stage 4.
- Do not repeat completed tests without a regression reason.
- Separate harness errors from actual game failures.
- Do not claim success without evidence.

## Current task
Finish Stage 3. The posture discrepancy (13.2 actual vs 11.5 expected), parry/attacker stun, guard break, animation track playback, stamina/armor/Danger/posture/hitstun/movement interactions, resolver behavior, permissions, ChildRemoved cleanup, and scaffolding removal remain unresolved or not fully evidenced.

## Latest reported passing checks
- Fists and Sword Swing/Block lifecycle.
- Seven weapon/non-combat transitions.
- Non-Combat blocks Swing and Block.
- Death/respawn without combat errors.
- Sword returns unequipped via StarterPack.
- Unblocked Fists damage: 3.5 (100 → 96.5).
- Blocked hit negates HP damage and fires BlockHit.

These are reported from the previous handoff, not freshly re-run by this document update.

## Reported architecture
`CombatService.State`, `CombatService.Weapon`, `CombatService.Damage`, `CombatService.Danger`, `CombatService.WeaponEquip`, `ReplicatedStorage.CombatConfig`, `ReplicatedStorage.CombatAnimations`, `CombatInputClient`, `StarterPack.Sword` (`WeaponId = "Sword"`), R6 `StarterCharacter`.

Confirm exact current paths before edits.

## Assistant responsibilities
- ChatGPT: planning, design reasoning, review, documentation, coordination.
- Claude: investigation and implementation only to the extent the current Claude interface and permissions actually allow.
- GitHub: persistent shared handoff. Read latest files before acting and avoid concurrent edits to the same file.

## End-of-session report
State what was inspected, what changed, what was tested, exact results, unresolved items, documentation updated, and the next owner decision needed.
