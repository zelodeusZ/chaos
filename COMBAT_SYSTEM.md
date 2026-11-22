# Combat System — Chaos

Last handoff: 2026-11-22. This document combines reported architecture and test status. Verify current Studio source before editing.

## Current reported source map

The latest handoff identified these modules / objects:

| Path or object | Reported responsibility |
|---|---|
| `CombatService.State` | Combat state |
| `CombatService.Weapon` | Weapon-specific combat behavior |
| `CombatService.Damage` | Damage handling |
| `CombatService.Danger` | Danger handling |
| `CombatService.WeaponEquip` | Weapon equip integration |
| `ReplicatedStorage.CombatConfig` | Weapon configuration and lookup |
| `ReplicatedStorage.CombatAnimations` | Animation resolution/configuration |
| `CombatInputClient` | Client combat input |
| `StarterPack.Sword` | Sword Tool; reported `WeaponId = "Sword"` |
| `StarterCharacter` | R6 character rig |

These are handoff-reported names, not a verified full Explorer hierarchy. Confirm actual paths and module contents in Untitled Experience before relying on them.

## Reported generic integration design

Prior work reportedly added:
- `CombatConfig.GetWeapon`.
- Fallback inheritance for weapon configuration.
- WeaponType, AnimationSet, Reach, and KnockbackMultiplier fields.
- `CombatAnimations` resolution through weapon → type → generic fallback.
- Replicated combat animation resolution.
- Weapon identity effects.
- Knockback plumbing.
- Combo reset on weapon change.
- Client animation playback integration.

The current source must be inspected to establish whether each item remains present and correct.

## Stage 3 status

**Stage 3 Generic Combat Integration is not complete.** Do not start Stage 4 until the owner accepts Stage 3 completion.

### Reported passing behavior
- Fists and Sword Swing/Block lifecycle.
- Seven weapon/non-combat transitions.
- Non-Combat state blocks Swing and Block.
- Death/respawn without combat respawn errors.
- Sword returns unequipped through StarterPack after respawn.
- Unblocked Fists hit dealt 3.5 damage to a fresh dummy (100 → 96.5).
- Blocked hit prevented HP damage and fired BlockHit.

See TEST_RESULTS.md for evidence limitations and details.

### Open issues and required verification
1. **Posture discrepancy:** blocked hit changed posture from 0 to 13.2; expected value was 11.5. Trace the actual formula and source of the expected value.
2. **Parry:** verify timing window, successful parry, damage negation, and attacker stun.
3. **Guard break:** verify trigger conditions, state transition, stun/lockout, recovery, and cleanup.
4. **Animations:** all 11 animations reportedly load, but track playback is not proven. Sword M1/Block/Parry/Critical entries were reported nil. Generic resolver reportedly resolves BlockHit, Parried, and Uppercut.
5. **Defensive/resource interactions:** stamina, armor, Danger, posture, hitstun, and movement.
6. **Resolver/inheritance:** Sharp resolver behavior, weapon → type → generic fallback, and missing-animation handling.
7. **Lifecycle/permissions:** weapon and non-combat transitions, permissions, ChildRemoved teardown.
8. **Cleanup:** remove temporary test scaffolding only after confirming production behavior does not depend on it; regression-test afterward.

## Test discipline
- Test one behavior at a time.
- Record setup, exact action, expected result, actual result, and evidence.
- Separate Studio harness/tool errors from game behavior.
- Do not infer animation playback from asset load success.
- Do not infer server-side behavior from client-only visuals.
- Do not repeat already passing checks unless code changed, a regression is suspected, or earlier evidence was inconclusive.

## Completion gate
Stage 3 is complete only when each required check has a PASS, FAIL, or BLOCKED result; unresolved discrepancies are fixed or explicitly accepted by the owner; temporary scaffolding is removed; and the final state is documented.
