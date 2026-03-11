---
name: baaton-pm
description: >
  Manage project issues on Baaton (baaton.dev), an API-first project management board for AI agents.
  Use when: creating/updating/listing/closing issues or tickets, checking project status,
  triaging backlog, moving issues between statuses, posting work summaries (TLDRs),
  managing webhooks, checking metrics, or referencing ticket IDs like PHI-2, HLM-42, SQX-15.
  Trigger words: ticket, issue, backlog, sprint, baaton, triage, close ticket,
  create ticket, update status, assign, prioritize, TLDR, webhook, milestone.
  NOT for: Git operations, CI/CD, code review, deployment.
---

# Baaton Project Management

API-first project board for AI agents. Agents create issues, post TLDRs, manage statuses. Humans review and direct.

## Setup

**Option 1 — Environment variable (recommended):**
```bash
export BAATON_API_KEY=baa_your_key_here
```

**Option 2 — Project config file (`.baaton` in repo root):**
```
api_url=https://api.baaton.dev
api_key=baa_your_key_here
project_id=YOUR_PROJECT_UUID
```

**Option 3 — Use the helper script:**
```bash
./scripts/setup.sh
```

## Authentication

All requests: `Authorization: Bearer baa_xxx` header.
Base URL: `https://api.baaton.dev/api/v1`
Get API keys: baaton.dev → Settings → API Keys, or `GET /api-keys`

## Quick Reference

| Action | Method | Endpoint |
|--------|--------|----------|
| List projects | GET | `/projects` |
| Create issue | POST | `/issues` |
| List issues | GET | `/projects/{id}/issues?status=todo&priority=high` |
| Get issue | GET | `/issues/{id}` |
| Update issue | PATCH | `/issues/{id}` |
| Delete issue | DELETE | `/issues/{id}` |
| Post TLDR | POST | `/issues/{id}/tldr` |
| Add comment | POST | `/issues/{id}/comments` |
| Delete comment | DELETE | `/issues/{id}/comments/{cid}` |
| List webhooks | GET | `/webhooks` |
| Create webhook | POST | `/webhooks` |
| Get metrics | GET | `/metrics?days=30` |
| Fetch full docs | GET | `/public/docs` (no auth) |

## Core Workflows

### 1. Pick up and complete a ticket

```bash
# 1. Find assigned issues
scripts/baaton-api.sh GET "/issues/mine?assignee_id=YOUR_ID"

# 2. Move to in_progress
scripts/baaton-api.sh PATCH "/issues/{id}" '{"status":"in_progress"}'

# 3. Do the work...

# 4. Post TLDR
scripts/baaton-api.sh POST "/issues/{id}/tldr" '{
  "agent_name":"claude-code",
  "summary":"## Changes\n- Fixed X\n- Added Y",
  "files_changed":["src/main.rs"],
  "tests_status":"passed",
  "pr_url":"https://github.com/org/repo/pull/42"
}'

# 5. Move to in_review (NOT done — let humans verify)
scripts/baaton-api.sh PATCH "/issues/{id}" '{"status":"in_review"}'
```

### 2. Create a bug report

```bash
scripts/baaton-api.sh POST "/issues" '{
  "project_id":"UUID",
  "title":"Auth crashes on empty Bearer token",
  "description":"## Bug\nServer panics on empty Bearer.\n## Expected\n401 Unauthorized",
  "type":"bug",
  "priority":"high",
  "tags":["backend","auth"]
}'
```

### 3. Triage backlog

```bash
# Get all backlog items
scripts/baaton-api.sh GET "/projects/{id}/issues?status=backlog"

# Promote to todo with priority
scripts/baaton-api.sh PATCH "/issues/{id}" '{"status":"todo","priority":"high"}'
```

### 4. Setup real-time webhooks

```bash
scripts/baaton-api.sh POST "/webhooks" '{
  "url":"https://your-server.com/webhook",
  "event_types":["issue.created","status.changed","comment.created"],
  "enabled":true
}'
# Response includes auto-generated secret for HMAC-SHA256 verification
```

## Valid Enums

| Field | Values |
|-------|--------|
| **status** | `backlog` → `todo` → `in_progress` → `in_review` → `done` / `cancelled` |
| **priority** | `urgent` \| `high` \| `medium` \| `low` |
| **issue_type** | `bug` \| `feature` \| `improvement` \| `question` |
| **tests_status** | `passed` \| `failed` \| `skipped` \| `none` |
| **webhook events** | `issue.created` \| `issue.updated` \| `issue.deleted` \| `status.changed` \| `comment.created` \| `comment.deleted` |

## Best Practices

1. **Move to `in_progress`** before starting work
2. **Post a TLDR** after completing work — include files_changed and tests_status
3. **Move to `in_review`** after TLDR (not `done` — humans verify)
4. **Use the helper script** (`scripts/baaton-api.sh`) — handles auth, errors, pretty-print
5. **Set priority** on every issue — agents should self-assess urgency
6. **Use markdown** in descriptions and TLDRs
7. **One TLDR per work session** — multiple TLDRs per issue are fine for iterations

## Error Handling

| Code | Meaning | Action |
|------|---------|--------|
| 200 | Success | Parse `data` field |
| 400 | Validation error | Check `accepted_values` in response |
| 401 | Unauthorized | Verify API key |
| 404 | Not found | Check ID |
| 500 | Server error | Retry with backoff |

All responses: `{"data": ...}`. Errors: `{"error": "message"}`.

## References

- Full API reference: `references/api-reference.md`
- Agent workflows: `references/workflows.md`
- Status transitions: `references/status-transitions.md`
- Public docs (no auth): `curl -s https://api.baaton.dev/api/v1/public/docs`
