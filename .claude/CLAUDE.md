# Claude Forge

Claude Code project template. Uses only features from the Claude Code runtime.

## Conventions

- Map scope before changing code.
- Prefer evidence before recommendation.
- Stop when input assumptions are no longer defensible.
- Agents exchange typed JSON files (brief.json, result.json, review.json), not free-form chat.

## Agent roles

| Role | Model | Purpose |
|------|-------|---------|
| implementer | sonnet | Bounded code changes from a brief |
| reviewer | opus | Correctness, security, regressions, cost notes |
| researcher | sonnet | Gather evidence, summarize options |

## Task handoff

```
researcher -> brief.json -> implementer -> result.json -> reviewer -> review.json
```

Schemas in `contracts/`.

## Six repo laws

1. Planning produces contracts with acceptance criteria, not todo lists.
2. Hard constraints are checkers, not reviewer opinions.
3. Verify the conflict core, not the whole trajectory.
4. A retry must change the search space.
5. Verifiers run in cascade: cheap first, strong second.
6. Context hygiene is reliability: single-agent first, multi-agent only for real specialization.