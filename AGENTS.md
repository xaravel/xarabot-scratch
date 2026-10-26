# Xarabot scratch repo

This repository is the scratch repo for Xarabot's live tests: the canary (Story 1.20), the claims race (Story 2.12) and the cross-vendor verification (Story 3.6). Its Stories are test fixtures, not product work.

- To build a Story, run the `bmad-build-auto` skill (`.claude/skills/` for Claude Code, `.agents/skills/` for codex). It is a stand-in that writes `verify/<key>.md` and the Story's spec, then halts `done`.
- To review a change, read it as you would any change: the files it adds under `verify/` and `_bmad-output/implementation-artifacts/` are the whole product here.
- There are no verification commands: the CI check `check` only prints `ok`.
- A CI check may ask for one more line in a `verify/<key>.md` file. That line belongs there: a verify file may hold it after its first line.
