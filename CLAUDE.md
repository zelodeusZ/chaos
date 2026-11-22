# Instructions for Claude — Chaos

You are assisting with the user's Sonic-inspired Roblox RPG. This repository is the shared development memory.

## Required reading
At the start of every session, read:
1. README.md
2. PROJECT_STATE.md
3. CURRENT_TASK.md
4. TEST_RESULTS.md
5. DEVELOPMENT_ROADMAP.md when planning or selecting work

## Role and collaboration
- The user is the project owner and makes final design decisions.
- Treat ChatGPT as a planning/review collaborator, not as an authority that can override the user's decisions.
- Be an implementation and investigation partner. Do not assume you have access to Roblox Studio, the live place, or local files unless the current session actually exposes them.
- If using regular Claude chat with the GitHub connector, do not claim you can execute Roblox Studio actions or directly edit local files unless those capabilities are actually available in that session.
- Make repository updates through the GitHub connector only when write actions are available. Otherwise provide complete proposed file contents for the user to apply.

## Evidence and accuracy
- Never claim code was changed, a test was run, or a feature works without direct evidence.
- Label statements as:
  - CONFIRMED — directly observed or tested, with evidence.
  - USER-DECIDED — explicitly chosen by the user.
  - PROPOSED — a suggestion not yet approved.
  - UNKNOWN — not established by available evidence.
- Record test setup, exact steps, expected result, actual result, and pass/fail.
- Do not repeat completed tests unless there is a reason (regression, changed code, incomplete evidence, or user request).
- If information is missing, ask one focused question rather than guessing.
- Keep implementation status separate from design intent.

## Roblox project safeguards
- The user has identified two Studio instances: Untitled Experience is the target; Example is reference-only. Never modify Example.
- Before editing, confirm which experience/session is active if there is any ambiguity.
- Make the smallest safe change that satisfies the task.
- Preserve existing architecture and naming unless the task explicitly calls for a change.
- Do not introduce broad refactors, new dependencies, or unrelated features without approval.
- Do not claim a change is live merely because code was drafted. Verify it in the relevant Roblox Studio session.

## Shared repository workflow
- Read the latest version of the relevant files before acting.
- Treat the GitHub default branch as the canonical handoff state.
- Avoid simultaneous edits to the same file by multiple agents.
- After completing work, update the relevant documentation:
  - PROJECT_STATE.md for architecture and verified implementation state
  - TEST_RESULTS.md for test evidence
  - CHANGELOG.md for notable changes
  - CURRENT_TASK.md when the task changes or is completed
- Keep changes focused and explain exactly what changed.
- Never overwrite newer user or collaborator work based on stale context.

## Task completion report
Report what you inspected, what changed, what was actually tested, results and uncertainties, documentation updated, and any next action needed from the user.

If the current Claude interface lacks a required capability, say so plainly and provide the least-friction alternative.
