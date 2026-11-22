# Test Results — Chaos

Last updated: 2026-11-22. Entries below are **reported from the latest project handoff**, not newly executed by this documentation update. Re-run only when needed for regression, changed code, or inconclusive evidence.

## 2026-11-22 — Stage 3 lifecycle and combat handoff

### Lifecycle / weapon-state checks
- Target: Untitled Experience (reported).
- Fists and Sword Swing/Block lifecycle: **REPORTED PASS**.
- Seven weapon/non-combat transitions: **REPORTED PASS**.
- Non-Combat blocks Swing and Block: **REPORTED PASS**.
- Death/respawn: **REPORTED PASS**, with no combat respawn errors.
- Sword after respawn: returns unequipped via StarterPack; no custom inventory was reported.
- Evidence limitation: detailed step-by-step recording and screenshots/logs are not included in this handoff. Treat as reported until reproduced or supported by artifacts.

### Unblocked Fists damage
- Setup: fresh dummy at 100 HP.
- Action: one unblocked Fists hit.
- Expected: 3.5 damage.
- Actual: dummy HP 100 → 96.5 (3.5 damage).
- Result: **REPORTED PASS**.
- Evidence: latest live-test handoff.

### Blocked hit / posture discrepancy
- Setup: blocking defender and attack against a dummy.
- Action: land a hit while the defender is blocking.
- Expected: damage negated; posture increase expected to be 11.5.
- Actual: HP damage prevented; BlockHit fired; posture increased 0 → 13.2.
- Result: **PARTIAL PASS / FORMULA UNRESOLVED**.
- Follow-up: trace posture calculation and establish whether 11.5 or 13.2 is correct. Do not change expected values without tracing the source.

### Animation status
- All 11 combat animations reportedly load.
- Loading is not proof of successful playback.
- Sword-specific M1, Block, Parry, and Critical animation entries were reported nil.
- Generic resolver reportedly resolves BlockHit, Parried, and Uppercut.
- Result: **BLOCKED / PLAYBACK NOT PROVEN**.
- Follow-up: verify actual AnimationTrack playback for each relevant action and inspect the weapon → type → generic resolution path.

### Not yet verified / unresolved
- Parry success within the active window.
- Attacker stun caused by a successful parry.
- Guard break behavior.
- Actual animation track playback for relevant weapon actions.
- Stamina, armor, Danger, posture interactions beyond the blocked-hit observation, hitstun, and movement.
- Sharp resolver behavior and inheritance.
- Permissions and ChildRemoved teardown/cleanup.
- Removal of temporary scaffolding and regression check afterward.

## Test recording template

### YYYY-MM-DD — Test name
- Build / place:
- Target experience:
- Script or system under test:
- Setup:
- Steps:
- Expected:
- Actual:
- Result: PASS / FAIL / BLOCKED
- Evidence:
- Follow-up:

## Rules
- Never convert an assumption into a PASS.
- A code inspection is not a live test; label it as code inspection.
- A successful local edit is not proof that the Roblox experience works.
- Record regressions and failed tests, not just successful tests.
- Keep Roblox harness/tool errors distinct from game behavior.
