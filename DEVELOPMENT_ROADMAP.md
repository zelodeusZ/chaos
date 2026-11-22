# Development Roadmap — Chaos

This roadmap records sequencing and known priorities. It is not permission to begin every unchecked item. Follow CURRENT_TASK.md and the owner's latest instruction.

## Stage 0 — Shared baseline
- [x] Establish private shared repository and collaboration instructions.
- [ ] Inspect the target Roblox experience, Untitled Experience, and verify the current source hierarchy.
- [ ] Keep Example reference-only.
- [ ] Build a source map of major systems and scripts.
- [ ] Separate verified implementation from reported history and design intent.

## Stage 1 — Design consolidation
- [x] Record the ten-race roster and Race Trait structure.
- [x] Record seven globally unique Chaos Emeralds and stat mapping.
- [x] Record Chaos Shards → Chaos Cores → Chaos Capacitor / Pseudo-Super design.
- [ ] Consolidate remaining owner-approved class, skill, progression, world, and movement systems.
- [ ] Resolve open design questions only with the owner's input.

## Stage 2 — Combat foundation
- [x] Generic combat architecture and weapon integration have been developed in prior sessions (reported; inspect current source before relying on it).
- [x] Basic damage and block behavior have partial live-test evidence (see TEST_RESULTS.md).
- [ ] Establish a fully verified, current source baseline.

## Stage 3 — Generic Combat Integration
<badge-placeholder>
- [ ] Verify posture calculation; resolve 13.2 actual vs 11.5 expected.
- [ ] Verify parry window, successful parry, and attacker stun.
- [ ] Verify guard break.
- [ ] Verify actual animation playback, including Sword-specific actions and generic fallback.
- [ ] Verify stamina, armor, Danger, posture, hitstun, and movement interactions.
- [ ] Verify Sharp resolver, inheritance, and weapon/non-combat transitions.
- [ ] Verify permissions and ChildRemoved teardown.
- [ ] Remove temporary test scaffolding and regression-test.
- [ ] Update docs with evidence and obtain owner acceptance.
  
**Current priority:** Finish Stage 3. Do not begin Stage 4 until the owner confirms Stage 3 completion.

## Stage 4 — Movement and traversal follow-up
- [ ] Address rail and pole issues after Stage 3, as previously identified by the owner.
- [ ] Define bounded tasks and acceptance criteria before implementation.

## Later stages — Owner-directed
- [ ] Progression, classes, race/trait mechanics, Chaos systems, Emeralds, skills, world content, and additional systems.
- [ ] Establish sequencing with the owner; no assumptions about priority or completion.

## Prioritization rule
Do not start a roadmap item simply because it is unchecked. CURRENT_TASK.md is the active assignment.
