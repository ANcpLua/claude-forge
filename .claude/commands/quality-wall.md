---
description: Run before commit — checks correctness risks, missing tests, cost efficiency
argument-hint: [path or branch]
---

# Quality Wall

## Phase 1: Cheap checks

Run linters, type checks, and format validation on $ARGUMENTS (or changed files).

## Phase 2: Contract verification

For each changed file:
1. Does it have a covering test?
2. Does any claim lack evidence?
3. Does the diff exceed the task scope from brief.json?

## Phase 3: Verdict

Write review.json with: verdict (accept|reject|retry), findings[], cost_notes.