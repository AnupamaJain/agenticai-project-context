# CLAUDE.md — AI Assistant Configuration

> This file is read automatically by Claude Code and most AI assistants
> at the start of every session. Keep it current. Keep it concise.

***

## Project Overview

**Project:** [Your Project Name]
**Type:** [Web App / API / LLM System / Data Pipeline / Mobile]
**Stage:** [MVP / Beta / Production]
**Last Updated:** [YYYY-MM-DD] — [brief note on what changed]

***

## Stack (Fill In)

| Layer | Technology |
|-------|-----------|
| Backend | [FastAPI / Express / Django] |
| Database | [PostgreSQL / MongoDB / MySQL] |
| Cache | [Redis / none] |
| Frontend | [React / Next.js / none] |
| AI/LLM | [OpenAI / Anthropic / Bedrock / none] |
| Deployment | [Docker / AWS / Vercel / VPS] |
| CI/CD | [GitHub Actions / GitLab CI / Jenkins] |

***

## Architecture Context Files

All architectural rules live in `.ai/rules/`. Load them all before implementing:

```
.ai/rules/
├── 00-global-architect.md   ← Start here always
├── 10-backend.md
├── 30-database.md
├── 35-api-contracts.md
├── 40-cache.md
├── 50-rag-system.md         ← Only if AI/LLM in stack
├── 55-data-model-versioning.md  ← Only if model training
├── 70-security.md
├── 85-error-observability.md
├── 90-devops-deployment.md
└── 99-response-style.md
```

***

## Current Sprint / Active Work

<!-- Update this section at the end of every session -->

**Active features being built:**
- [ ] [Feature 1 — brief description]
- [ ] [Feature 2 — brief description]

**Recently completed (last 2 weeks):**
- [x] [Completed feature — brief note on approach used]

**Known issues / tech debt:**
- [Issue 1 — brief description]

***

## Critical Decisions Made

<!-- Record decisions here so AI never re-debates them -->

| Decision | Choice | Reason |
|----------|--------|--------|
| Auth strategy | [JWT / Session / OAuth] | [Why] |
| Multi-tenancy | [Yes / No] | [Why] |
| Soft delete | [Yes / No] | [Why] |
| API versioning | [/api/v1/] | [Why] |

***

## Do Not Touch (Stable Modules)

<!-- List files/modules the AI must not modify unless explicitly asked -->

- `core/config.py` — finalized, do not refactor
- `migrations/` — never edit manually
- `[Add your stable files here]`

***

## Environment & Config Notes

- All secrets via environment variables — see `.env.example`
- Never hardcode any value from `.env` in code
- Staging environment: [describe any differences from production]

***

## Session End Checklist

At the end of each session, ask the AI to update:
1. "Active features" above — check off completed items
2. "Recently completed" — add what was finished today
3. "Critical decisions" — add any new architectural choices made
4. `MEMORY.md` — add session summary (see MEMORY.md)