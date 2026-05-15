# API Specification

Base URL: `/api/v1`

All endpoints return:
```json
{
  "data": {},
  "error": null,
  "message": "success"
}
```

Error responses:
```json
{
  "data": null,
  "error": "VALIDATION_ERROR",
  "message": "Email is required"
}
```

## Auth
- `POST /api/v1/auth/login` — Login with email/password, returns JWT
- `POST /api/v1/auth/refresh` — Refresh access token
- `POST /api/v1/auth/logout` — Invalidate session

## Organizations
- `GET /api/v1/organizations` — List user's organizations
- `POST /api/v1/organizations` — Create organization
- `GET /api/v1/organizations/:id` — Get organization details
- `PATCH /api/v1/organizations/:id` — Update organization
- `POST /api/v1/organizations/:id/invite` — Invite member
- `GET /api/v1/organizations/:id/members` — List members

## Knowledge Base
- `POST /api/v1/kb/upload` — Upload document(s)
- `POST /api/v1/kb/index` — Trigger indexing/embedding
- `GET /api/v1/kb/documents` — List documents
- `GET /api/v1/kb/documents/:id` — Get document details
- `DELETE /api/v1/kb/documents/:id` — Remove document

## Chat / RAG
- `POST /api/v1/chat/query` — Ask question, get RAG-grounded answer
- `GET /api/v1/chat/sessions` — List chat sessions
- `GET /api/v1/chat/sessions/:id` — Get session with message history

## Agents
- `POST /api/v1/agents/run` — Trigger agent task
- `GET /api/v1/agents/runs/:id` — Get agent run status and result
- `GET /api/v1/agents/runs` — List agent runs

## Admin
- `GET /api/v1/admin/usage` — Usage analytics
- `GET /api/v1/admin/billing` — Billing overview
- `GET /api/v1/admin/health` — System health check

## Common Patterns
- **Pagination:** `?page=1&limit=20`
- **Filtering:** `?status=active&created_after=2026-01-01`
- **Sorting:** `?sort_by=created_at&order=desc`
- **Auth:** Bearer token in `Authorization` header
- **Tenant:** Organization resolved from token, not URL
