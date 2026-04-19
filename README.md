# ax

AI development workflow plugin for Claude Code. Tracer-bullet pipeline from free-form plan to final audit.

## Installation

```
/plugin marketplace add ekadetov/ax
/plugin install ax@ax
```

## Skills

| Skill | When to use |
|---|---|
| `ax:write-a-prd` | Turn a free-form plan into a structured PRD via user interview and codebase exploration |
| `ax:prd-to-issues` | Break a PRD into vertical-slice issues (HITL/AFK), each with Given/When/Then acceptance criteria |
| `ax:issue-to-tasks` | Break a single issue into session-sized AI tasks in dependency order |
| `ax:code-review` | Six-pass review: logic errors, operation ordering, bad practices, security, magic values, patterns |
| `ax:final-audit` | Cross-cutting post-merge audit across all files touched by a feature |

## Workflow

```
Free-form plan → PRD → Issues → Tasks → Code → Review → Final Audit
```

The real work happens before coding starts. Each step: AI produces something, you review it, it gets created.

## Development

```bash
/push          # commit and push skill changes
/bump [patch|minor|major]  # bump version in plugin.json and push
```

## Credits

Workflow adapted from [maiobarbero/my-ai-workflow](https://github.com/maiobarbero/my-ai-workflow), which was itself adapted from [mattpocock/skills](https://github.com/mattpocock/skills).
