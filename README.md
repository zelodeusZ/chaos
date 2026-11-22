# Chaos — Sonic RPG Development Hub

This private repository is the shared source of truth for development of the user's Sonic-inspired Roblox RPG.

It is a development-memory and coordination repository, not the Roblox place file. The Roblox experience remains in Roblox Studio unless the owner explicitly decides to version source exports here.

## Start here
1. Read CLAUDE.md before doing any work.
2. Read PROJECT_STATE.md for user-decided design and current implementation status.
3. Read CURRENT_TASK.md for the active assignment.
4. Read COMBAT_SYSTEM.md for the combat architecture and unresolved Stage 3 checks.
5. Read GAME_DESIGN.md for consolidated design systems.
6. Check TEST_RESULTS.md before repeating tests.
7. Use DEVELOPMENT_ROADMAP.md for planned sequencing.
8. Read SESSION_HANDOFF.md when continuing work from another assistant/session.

## Collaboration model
- The user is the project owner and final decision-maker.
- ChatGPT primarily helps plan, reason, review, document, and coordinate.
- Claude helps investigate and implement in the tools/workflows the user makes available.
- GitHub is the persistent shared handoff point between assistants and sessions.

## Ground-truth rules
- Distinguish USER-DECIDED, CONFIRMED, REPORTED, PROPOSED, and UNKNOWN.
- Never claim a feature works unless there is test evidence.
- Never invent file paths, code structure, Roblox Studio state, test results, or implementation details.
- Preserve decisions recorded in PROJECT_STATE.md unless the user explicitly changes them.
- Update documentation when decisions or verified implementation status change.
- Never upload credentials, API keys, private tokens, or personal data.
