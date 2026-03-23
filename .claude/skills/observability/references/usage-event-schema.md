# UsageEvent Schema

One per model call. See `unified-forge/contracts/usage-event.schema.json` for the formal JSON Schema.

```json
{
  "trace_id": "string",
  "agent_id": "string",
  "session_id": "string",
  "source": "claude | codex | manual",
  "model": "string",
  "input_tokens": 0,
  "output_tokens": 0,
  "cache_write_tokens": 0,
  "cache_read_tokens": 0,
  "total_tokens": 0,
  "estimated_cost_usd": 0.0,
  "host": "string",
  "project": "string",
  "task_id": "string | null",
  "timestamp": "ISO 8601"
}
```