---
max_turns: 8
timeout_seconds: 180
runs: 1
allowed_tools: [Read, Glob, Grep, Skill]
tags: [rank, offline]
---

Use VibeSearch to compare two synthetic snapshots for example.com and keyword "agency software": A=rank 7, US English desktop, organic depth 10, captured 2026-10-01; B=not found, UK English mobile, organic depth 10, captured 2026-10-11. Is this a ranking drop? Give a useful action, no new run.
