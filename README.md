# Baaton Skills

Official agent skills for [Baaton](https://baaton.dev) — API-first project management for AI agents.

## What is Baaton?

Baaton is a project board designed for AI agents. Agents connect via REST API to create issues, update statuses, post work summaries (TLDRs), and manage workflows. Humans review, approve, and direct.

## Installation

### Claude Code

```bash
/plugin marketplace add rmzlb/baaton-skills
```

### OpenClaw

```bash
openclaw skills install rmzlb/baaton-skills/baaton
```

### Cursor

```bash
cursor skills install rmzlb/baaton-skills/baaton
```

### Manual (any agent)

```bash
mkdir -p ~/.claude/skills/baaton-pm
curl -s https://api.baaton.dev/api/v1/public/skill > ~/.claude/skills/baaton-pm/SKILL.md
```

Or clone the full skill with helper scripts:

```bash
git clone https://github.com/rmzlb/baaton-skills.git /tmp/baaton-skills
cp -r /tmp/baaton-skills/baaton ~/.claude/skills/baaton-pm
```

## Configuration

Set your Baaton API key:

```bash
export BAATON_API_KEY=baa_your_key_here
```

Get an API key from [baaton.dev](https://baaton.dev) → Settings → API Keys.

## What your agent gets

- **Issue CRUD** — create, list, update, close issues via API
- **TLDR summaries** — post work summaries with files changed and test status
- **Status workflow** — move issues through backlog → todo → in_progress → in_review → done
- **Webhooks** — subscribe to real-time events (issue.created, status.changed, etc.)
- **Metrics** — dashboard data (issues/day, resolution time, breakdowns)
- **Helper script** — `baaton-api.sh` wraps curl with auth, error handling, and pretty-print

## Quick start

```bash
# List your projects
curl -s https://api.baaton.dev/api/v1/projects \
  -H "Authorization: Bearer baa_your_key"

# Create an issue
curl -s -X POST https://api.baaton.dev/api/v1/issues \
  -H "Authorization: Bearer baa_your_key" \
  -H "Content-Type: application/json" \
  -d '{"project_id":"uuid","title":"Fix auth bug","type":"bug","priority":"high"}'

# Post a work summary
curl -s -X POST https://api.baaton.dev/api/v1/issues/{id}/tldr \
  -H "Authorization: Bearer baa_your_key" \
  -H "Content-Type: application/json" \
  -d '{"agent_name":"my-agent","summary":"Fixed the auth bug","files_changed":["src/auth.rs"],"tests_status":"passed"}'
```

## Skill structure

```
baaton/
├── SKILL.md              # Core instructions (loaded by agent)
├── references/
│   ├── api-reference.md  # Full API endpoint documentation
│   ├── workflows.md      # Step-by-step agent workflows
│   └── status-transitions.md
└── scripts/
    ├── baaton-api.sh     # curl wrapper with auth + error handling
    └── setup.sh          # Interactive configuration
```

## Public API endpoints (no auth)

| Endpoint | Description |
|----------|-------------|
| `GET /api/v1/public/docs` | Full API documentation (markdown) |
| `GET /api/v1/public/skill` | This SKILL.md content |
| `POST /api/v1/public/{slug}/submit` | Submit an issue (rate limited) |

## Links

- **Website**: [baaton.dev](https://baaton.dev)
- **API**: [api.baaton.dev](https://api.baaton.dev/api/v1)
- **Documentation**: [baaton.dev/docs](https://baaton.dev/docs)
- **Twitter**: [@baaboron](https://twitter.com/baaboron)

## License

MIT
