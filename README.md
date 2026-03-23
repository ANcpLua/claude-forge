# Claude Forge

Claude Code project template. Uses only features from the Claude Code runtime.

## Structure

```
claude-forge/
├── .claude/
│   ├── CLAUDE.md                      # Root instructions + six repo laws
│   ├── rules/                         # Always-loaded policy
│   │   ├── execution-discipline.md
│   │   └── output-shape.md
│   ├── commands/                      # Slash commands
│   │   └── quality-wall.md
│   ├── agents/                        # Role definitions (.md + frontmatter)
│   │   ├── implementer.md
│   │   ├── reviewer.md
│   │   └── researcher.md
│   ├── skills/
│   │   └── observability/SKILL.md
│   └── hooks/hooks.json               # Real CC hook events (PreToolUse)
├── contracts/                         # Policy: TaskContract, ArtifactEnvelope, UsageEvent
├── docs/operating-model.md            # Six laws, anti-patterns, research refs
├── tests/skills/prompts/
├── LICENSE
└── README.md
```

## What is here and why

| Path | Claude Code reads it? | Purpose |
|------|:-:|---|
| `.claude/CLAUDE.md` | Yes — loaded into system context | Instructions, conventions, laws |
| `.claude/rules/*.md` | Yes — always loaded | Hard policy constraints |
| `.claude/commands/*.md` | Yes — as slash commands | Reusable workflows |
| `.claude/agents/*.md` | Yes — via Agent tool | Role definitions with model + output contract |
| `.claude/skills/*/SKILL.md` | Yes — via Skill tool | Skill discovery |
| `.claude/hooks/hooks.json` | Yes — at hook events | PreToolUse, PostToolUse, SessionStart gates |

## Task handoff

```
researcher -> brief.json -> implementer -> result.json -> reviewer -> review.json
```

Schemas in `contracts/` (self-contained — same schemas also live in unified-forge and codex-forge as shared policy).

## Validation

```bash
bash scripts/validate-contracts.sh    # Contract schema integrity
```

## Sources

- [Claude Code MCP](https://docs.anthropic.com/en/docs/claude-code/mcp)
- [Anthropic Advanced Tool Use](https://www.anthropic.com/engineering/advanced-tool-use)
- [MCP Architecture](https://modelcontextprotocol.io/docs/learn/architecture)
- [OpenTelemetry](https://opentelemetry.io/docs/)
