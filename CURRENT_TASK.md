# Current Task — Finish Stage 3 Generic Combat Integration

Status: IN PROGRESS — verification and remaining integration work  
Priority: Complete Stage 3 before beginning Stage 4.  
Owner constraint: Do not skip unresolved checks or treat reported results as freshly verified.

## Objective
Finish and verify Stage 3 Generic Combat Integration in the target Roblox experience, **Untitled Experience**. The separate **Example** experience is reference-only and must never be modified.

## Starting point from the latest handoff
Already reported as passing:
- Fists and Sword Swing/Block lifecycle.
- Seven weapon/non-combat transitions.
- Non-Combat state blocks Swing and Block.
- Death/respawn lifecycle without combat respawn errors.
- Sword returns unequipped through StarterPack after respawn.

Reported live combat observations:
- Unblocked Fists hit: 100 → 96.5 HP, exactly 3.5 damage.
- Blocked hit: no HP damage; BlockHit fired.
- Posture rose from 0 to 13.2, while expected value was 11.5. Do not silently accept or hardcode around this discrepancy; trace the actual formula and source of the expected value.

Reported unresolved:
- Parry window and attacker stun.
- Guard break.
- Actual animation track playback (asset loading alone is not proof).
- Sword-specific M1, Block, Parry, and Critical animation entries were nil in the prior handoff.
- Defensive/resource/movement interactions: stamina, armor, Danger, posture, hitstun, movement.
- Sharp resolver behavior and weapon/type/generic inheritance.
- Permissions and cleanup, including ChildRemoved teardown.
- Remove temporary test scaffolding after tests are complete.

## Required workflow
1. Read README.md, CLAUDE.md, PROJECT_STATE.md, COMBAT_SYSTEM.md, and TEST_RESULTS.md.
2. Confirm the active Studio session is Untitled Experience. Do not modify Example.
3. Inspect the current source before editing; verify that reported script/module paths still exist.
4. Reproduce each unresolved test independently. Separate harness failures from game failures.
5. Trace posture calculation from input/event through the server-side source; explain why 13.2 differs from 11.5.
6. Verify real animation playback for each relevant weapon/action. Do not infer playback from successful asset loading or resolver return values.
7. Verify parry, attacker stun, guard break, and each defensive/resource/movement interaction.
8. Check Sharp resolver/inheritance and weapon/non-combat state transitions.
9. Check death/respawn and ChildRemoved cleanup; preserve the known passing behavior.
10. Remove scaffolding only after it is no longer needed and verify no production behavior depended on it.
11. Update PROJECT_STATE.md, COMBAT_SYSTEM.md, TEST_RESULTS.md, and CHANGELOG.md with exact evidence and current status.

## Constraints
- No Stage 4 work until Stage 3 is complete.
- No unrelated refactors or gameplay features.
- Do not modify the reference-only Example experience.
- Do not claim a test passed without setup, steps, observed result, and evidence.
- Do not repeat completed tests unless checking regression, changed code, or a prior result was inconclusive.
- Ask the owner before moving to Stage 4.

## Completion criteria
Stage 3 is complete only when every required integration check has a clear PASS, FAIL, or BLOCKED result; discrepancies are resolved or explicitly accepted by the owner; temporary scaffolding is removed; and documentation reflects the verified state.
