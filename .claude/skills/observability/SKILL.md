---
name: observability
description: Parse native Claude and Codex logs into normalized usage metrics. Use when analyzing token burn, cost per task, model mix, or budget tracking. Do not use for runtime behavior changes.
---

# Observability

Parse vendor-native log files. Normalize only the metrics layer.

## Normalized fields

```
provider, session, task, role, model,
input_tokens, output_tokens, cache_write, cache_read,
total_tokens, estimated_cost, prompt_hash, outcome
```

## Workflow

1. Identify log source: `~/.claude/projects/` (JSONL).
2. Run `scripts/ingest_claude_logs.py` to extract UsageEvents.
3. Pipe output to `scripts/cost_report.py` for aggregation.

## References

- [references/claude-log-schema.md](references/claude-log-schema.md)
- [references/usage-event-schema.md](references/usage-event-schema.md)

## Key constraint

ccusage is a host-local collector, not global truth (issue #222). Use it for operational visibility and local burn rate.