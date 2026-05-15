# AI Project Context Files

> Stop your AI assistant from hallucinating architecture.
> Give it context. Get production-ready code.

## The Problem

When you ask an AI coding assistant to build a feature without
context, it invents your architecture. It hardcodes secrets.
It mixes business logic into route handlers. It forgets migrations.

Not because the model is bad — because it has no context about
HOW your project works.

## The Solution

A `context/` folder at the root of your repo. 11 short Markdown
files. One instruction set per layer of your system.

Load them at the start of every AI session.
Pay ~1,500 tokens upfront. Save 50,000 tokens of corrections.

## The Files

| File | Layer | Purpose |
|------|-------|---------|
| `00-global-architect.md` | Foundation | Architecture principles + identity |
| `10-backend.md` | API Layer | Framework rules, clean architecture |
| `30-database.md` | Data Layer | Schema, migrations, query rules |
| `35-api-contracts.md` | Contracts | Versioning, consistency, deprecation |
| `40-cache.md` | Cache Layer | TTLs, key naming, invalidation rules |
| `50-rag-system.md` | AI/LLM | RAG pipeline separation + grounding |
| `55-data-model-versioning.md` | ML | Dataset versioning, reproducibility |
| `70-security.md` | Security | Non-negotiables, AI-specific risks |
| `85-error-observability.md` | Ops | Logging, tracing, health checks |
| `90-devops-deployment.md` | DevOps | Docker, CI/CD, cloud guardrails |
| `99-response-style.md` | AI Behavior | How the AI responds and formats code |

> Remove `50-rag-system.md` and `55-data-model-versioning.md`
> if your project has no AI/ML component.

## How to Use

1. Copy the `context/` folder into your project root
2. Fill in the `[YOUR FRAMEWORK]` placeholders (takes ~15 min)
3. Tell your AI assistant:
   > "Read all files in the /context folder before starting."
4. Works with: Claude, Cursor, GitHub Copilot, Windsurf, Gemini

## Session Workflow

```
START of session
  └─ AI reads: CLAUDE.md + context/*.md

DURING session
  └─ AI implements following all architectural rules

END of session
  └─ Ask AI: "Summarize this session for MEMORY.md"
  └─ Review summary → commit to MEMORY.md
  └─ Update CLAUDE.md "Active features" section
```

Two companion files keep memory alive across sessions:

- **`CLAUDE.md`** — your stack, active sprint, and critical decisions the AI must never re-debate
- **`MEMORY.md`** — a rolling log of what was built, decided, and deferred each session

## Adapt in 15 Minutes

Open `00-global-architect.md` and fill in your stack:
- Backend: FastAPI / Express / Django / Spring / Rails
- Database: PostgreSQL / MySQL / MongoDB / DynamoDB
- Cache: Redis / Memcached / none
- Deployment: Docker / AWS / GCP / Vercel / VPS

## Examples

See `/examples` for fully filled-in versions:
- `fastapi-postgres/` — FastAPI + PostgreSQL + Redis stack
- (more stacks coming — PRs welcome)

## Star This Repo

If this saves you time, a ⭐ helps others find it.

## Contributing

PRs welcome for:
- New stack examples (Next.js, Django, Spring Boot, etc.)
- Additional context file templates (e.g., mobile, data pipelines)
- Translations

## Author

**Anupama Jain** — AI Quality Engineering Lead | LLM Testing
[LinkedIn](https://linkedin.com/in/anupama-jain)
