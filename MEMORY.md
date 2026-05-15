# MEMORY.md — Project Memory Log

> This file is the persistent memory of all AI-assisted sessions on this project.
> It is updated at the END of every session, never at the start.
> Keep entries concise. Purge entries older than 60 days unless they record a critical decision.

***

## How to Update This File

At the end of every session, ask your AI assistant:

> "Summarize this session for MEMORY.md. Include:
> what was built, what decisions were made, what was deferred,
> and any patterns or gotchas discovered. Max 10 bullet points.
> Remove any entries older than 60 days."

The AI writes the summary. You review and commit it.

***

## Memory Format (Per Session)

```
### [YYYY-MM-DD] — [1-line session description]
**Built:** [what was created or modified]
**Decided:** [architectural or product decisions]
**Deferred:** [what was explicitly not done and why]
**Gotchas:** [things that went wrong or surprised us]
**Patterns used:** [reusable patterns established in this session]
```

***

## Active Memory (Last 60 Days)

<!-- AI appends new sessions here. Oldest entries are pruned automatically. -->

### 2026-05-15 — Initial project setup & generic restructuring
**Built:** Full generic AI context system: 11 architectural rules (.ai/rules), 10 agent templates (.ai/agents), 7 doc templates (.ai/docs), and generic skills.
**Decided:** Organize all AI-related logic under `.ai/` for a clean root. Root CLAUDE.md serves as the session manager.
**Deferred:** Specific implementation examples (FastAPI/Postgres) — moved to templates to keep the core repo generic.
**Gotchas:** Git push failed initially due to RPC buffer limits; fixed with `git config http.postBuffer`.
**Patterns used:** Rule-based context loading, specialized agent personas, and `compose.sh` for custom context building.

***

<!-- Add new sessions above this line -->

***

## Permanent Memory (Never Purge)

<!-- Record decisions that must survive forever — architectural, legal, compliance -->

| Date | Decision | Context | Cannot Change Because |
|------|----------|---------|----------------------|
| [YYYY-MM-DD] | [Decision] | [Why it was made] | [Constraint] |

***

## Deferred Decisions Log

<!-- Track things explicitly NOT decided yet — prevents AI from making them unilaterally -->

| Item | Why Deferred | Revisit When |
|------|-------------|-------------|
| Multi-tenancy | Not needed for MVP | At 1000 users |
| GraphQL | REST sufficient now | If frontend complexity grows |
| [Add yours] | | |