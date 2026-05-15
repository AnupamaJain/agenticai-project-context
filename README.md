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

An `.ai/` folder at the root of your repo. 11 short Markdown
files in `.ai/rules/`. One instruction set per layer of your system.

Load them at the start of every AI session.
Pay ~1,500 tokens upfront. Save 50,000 tokens of corrections.

## The Files

| File | Layer | Purpose |
|------|-------|---------|
| `.ai/rules/00-global-architect.md` | Foundation | Architecture principles + identity |
| `.ai/rules/10-backend.md` | API Layer | Framework rules, clean architecture |
| `.ai/rules/30-database.md` | Data Layer | Schema, migrations, query rules |
| `.ai/rules/35-api-contracts.md` | Contracts | Versioning, consistency, deprecation |
| `.ai/rules/40-cache.md` | Cache Layer | TTLs, key naming, invalidation rules |
| `.ai/rules/50-rag-system.md` | AI/LLM | RAG pipeline separation + grounding |
| `.ai/rules/55-data-model-versioning.md` | ML | Dataset versioning, reproducibility |
| `.ai/rules/70-security.md` | Security | Non-negotiables, AI-specific risks |
| `.ai/rules/85-error-observability.md` | Ops | Logging, tracing, health checks |
| `.ai/rules/90-devops-deployment.md` | DevOps | Docker, CI/CD, cloud guardrails |
| `.ai/rules/99-response-style.md` | AI Behavior | How the AI responds and formats code |

> Remove `50-rag-system.md` and `55-data-model-versioning.md`
> if your project has no AI/ML component.

## Templates & Examples

The `.ai/templates/` directory provides generic starting points for common documentation and agent definitions:

- **`.ai/templates/agents/`** — Generic personas for Backend, Frontend, DB Architect, Code Reviewer, and more.
- **`.ai/templates/docs/`** — Templates for PRD, Architecture, API Spec, DB Schema, and Deployment.
- **`.ai/templates/skills/`** — Reusable automation patterns and skill templates.

## Customization Script

Use the provided script to build a custom `CLAUDE.md` tailored to your project:

```bash
# All rules
./.ai/scripts/compose.sh > CLAUDE.md

# Backend only (e.g. FastAPI/Django/Rails)
./.ai/scripts/compose.sh 00 10 30 70 85 90 99 > CLAUDE.md

# Frontend only (e.g. Next.js/React/Vue)
./.ai/scripts/compose.sh 00 20 70 85 90 99 > CLAUDE.md

# AI/ML/RAG focused
./.ai/scripts/compose.sh 00 50 55 60 70 99 > CLAUDE.md
```


## How to Use

1. Copy the `.ai/` folder into your project root
2. Fill in the `[YOUR FRAMEWORK]` placeholders (takes ~15 min)
3. Tell your AI assistant:
   > "Read CLAUDE.md and all files in the .ai/rules folder before starting."
4. Works with: Claude, Cursor, GitHub Copilot, Windsurf, Gemini (Antigravity)

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
