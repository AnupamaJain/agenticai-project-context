# docs/ — Project Documentation Templates

Starter templates for the 5 docs that Cursor rules reference. These give your AI coding tool the full picture of your product — not just code style, but what you're building, how it's structured, and where it deploys.

## Files

| File | What it defines | Why it matters |
|------|----------------|----------------|
| [PRD.md](PRD.md) | Product requirements, users, modules, milestones | AI understands **what** to build |
| [ARCHITECTURE.md](ARCHITECTURE.md) | Layers, data flow, multi-tenancy, key decisions | AI understands **how** it's structured |
| [API_SPEC.md](API_SPEC.md) | Endpoints, request/response format, patterns | AI writes **consistent APIs** |
| [DB_SCHEMA.md](DB_SCHEMA.md) | Tables, columns, types, indexes, rules | AI writes **correct queries and migrations** |
| [DEPLOYMENT.md](DEPLOYMENT.md) | Local setup, cloud stack, CI/CD, environments | AI writes **deploy-ready code** |

## How to use

1. Copy `docs/` into your project root
2. Replace placeholder values with your product details
3. Cursor rules (specifically `00-global-architect.mdc`) will automatically reference these docs

The `00-global-architect.mdc` rule includes:
```
Change behavior:
- Before implementing, align with docs/PRD.md, docs/ARCHITECTURE.md,
  docs/API_SPEC.md, docs/DB_SCHEMA.md, and docs/DEPLOYMENT.md if present.
```

## Customization

These templates assume a typical AI SaaS product (RAG + agents + multi-tenant). Adapt them to your stack:

- **Not using RAG?** Remove knowledge base sections from PRD, API_SPEC, DB_SCHEMA
- **Not multi-tenant?** Remove organization/membership tables, simplify auth
- **Not using AWS?** Update DEPLOYMENT.md with your cloud (GCP, Azure, Railway, Fly.io)
- **Different backend?** Swap FastAPI references for Express, Django, Go, etc.

Keep these docs updated as your product evolves — they're the source of truth your AI tools read before writing code.
