# Baaton API Reference

Base URL: `https://api.baaton.dev/api/v1`

All requests require `Authorization: Bearer baa_xxx` header.
All responses wrapped in `{"data": ...}`. Errors return `{"error": "message", "accepted_values": [...]}`.

---

## Projects

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/projects` | List all projects in org |
| POST | `/projects` | Create project (`name`, `slug`, `prefix` required) |
| GET | `/projects/{id}` | Get project details |
| PATCH | `/projects/{id}` | Update project |
| DELETE | `/projects/{id}` | Delete project |

---

## Issues

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/projects/{pid}/issues` | List issues (filters: `status`, `priority`, `type`, `search`, `category`, `limit`, `offset`) |
| GET | `/issues/mine?assignee_id=X` | My assigned issues |
| POST | `/issues` | Create issue (`project_id`, `title` required) |
| GET | `/issues/{id}` | Get issue with TLDRs + comments |
| PATCH | `/issues/{id}` | Update issue (all fields optional) |
| DELETE | `/issues/{id}` | Delete issue |
| PATCH | `/issues/{id}/position` | Reorder (`status`, `position` float) |

### Create Issue Body
```json
{
  "project_id": "uuid (required)",
  "title": "string (required)",
  "description": "markdown",
  "type": "bug|feature|improvement|question",
  "status": "backlog|todo|in_progress|in_review|done|cancelled",
  "priority": "urgent|high|medium|low",
  "tags": ["backend"],
  "category": ["api"],
  "assignee_ids": ["user_id"],
  "milestone_id": "uuid",
  "parent_id": "uuid",
  "due_date": "2026-03-01"
}
```

---

## TLDRs (Agent Work Summaries)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/issues/{id}/tldr` | Post TLDR (`agent_name`, `summary` required) |

```json
{
  "agent_name": "claude-code",
  "summary": "markdown summary",
  "files_changed": ["src/main.rs"],
  "tests_status": "passed|failed|skipped|none",
  "pr_url": "https://github.com/..."
}
```

---

## Comments

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/issues/{id}/comments` | List comments |
| POST | `/issues/{id}/comments` | Add comment (`body` required; `author_id`/`author_name` auto-filled from API key) |
| DELETE | `/issues/{id}/comments/{cid}` | Delete comment |

---

## Webhooks

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/webhooks` | List webhook endpoints |
| POST | `/webhooks` | Create webhook (`url`, `event_types[]` required) |
| PATCH | `/webhooks/{id}` | Update webhook |
| DELETE | `/webhooks/{id}` | Delete webhook |

### Create Webhook Body
```json
{
  "url": "https://your-server.com/webhook",
  "event_types": ["issue.created", "status.changed"],
  "enabled": true
}
```

Response includes auto-generated `secret` for HMAC-SHA256 signature verification.
Delivery header: `X-Baaton-Signature` (hex-encoded HMAC-SHA256 of body with secret).

### Event Types
- `issue.created` — New issue created
- `issue.updated` — Issue fields changed
- `issue.deleted` — Issue deleted
- `status.changed` — Status transition (includes `old_status`, `new_status`)
- `comment.created` — New comment added
- `comment.deleted` — Comment removed

---

## Metrics

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/metrics?days=30` | Dashboard metrics (issues created/closed per day, avg resolution, breakdown by status/priority) |

---

## Milestones

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/projects/{pid}/milestones` | List milestones with issue counts |
| POST | `/projects/{pid}/milestones` | Create milestone (`name` required) |
| GET | `/milestones/{id}` | Get milestone with linked issues |
| PUT | `/milestones/{id}` | Update milestone |
| DELETE | `/milestones/{id}` | Delete milestone |

---

## Sprints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/projects/{pid}/sprints` | List sprints |
| POST | `/projects/{pid}/sprints` | Create sprint (`name` required) |
| PUT | `/sprints/{id}` | Update sprint |
| DELETE | `/sprints/{id}` | Delete sprint |

---

## Tags

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/projects/{pid}/tags` | List tags |
| POST | `/projects/{pid}/tags` | Create/upsert tag (`name` required) |
| DELETE | `/tags/{id}` | Delete tag |

---

## Activity

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/issues/{id}/activity?limit=50` | Issue activity log |
| GET | `/activity?limit=30` | Recent org activity |

---

## Public Endpoints (No Auth)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/public/docs` | Full API documentation (markdown) |
| POST | `/public/{slug}/submit` | Submit issue (rate limited: 10/hr/IP) |

### Public Submit Body
```json
{
  "title": "Bug report (required)",
  "description": "details",
  "type": "bug|feature|improvement|question",
  "reporter_name": "optional",
  "reporter_email": "optional"
}
```
