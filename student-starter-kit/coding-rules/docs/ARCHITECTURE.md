# Architecture

## High-Level Components
- Next.js frontend
- FastAPI backend
- PostgreSQL database
- Redis cache/queue
- RAG pipeline
- Agent orchestration layer
- Dockerized services
- AWS deployment

## Layering

```
┌─────────────────────────────────┐
│         Frontend (Next.js)       │
├─────────────────────────────────┤
│      API Routes / Controllers    │  ← HTTP only, no logic
├─────────────────────────────────┤
│           Services               │  ← Business logic lives here
├─────────────────────────────────┤
│         Repositories             │  ← DB access only
├─────────────────────────────────┤
│     Database (PostgreSQL)        │
├─────────────────────────────────┤
│   AI Orchestration (RAG/Agents)  │  ← Separate from business layer
├─────────────────────────────────┤
│        Infrastructure            │  ← Docker, AWS, CI/CD
└─────────────────────────────────┘
```

## Principles
- Clean architecture
- Multi-tenant safety
- Secure by default
- Observable and testable

## Data Flow

```
User → Frontend → API Route → Service → Repository → Database
                                  ↓
                           AI Orchestration
                           ├── RAG Pipeline (embed → retrieve → generate)
                           └── Agent Layer (plan → tool calls → result)
```

## Multi-Tenancy
- All business data is scoped by `organization_id`
- Tenant isolation enforced at repository layer
- No cross-tenant data leakage in queries, embeddings, or agent context

## Key Decisions
<!-- Document important architecture decisions here -->
| Decision | Choice | Reason |
|----------|--------|--------|
| Database | PostgreSQL | Mature, reliable, great for multi-tenant |
| Cache | Redis | Fast, supports queues and rate limiting |
| Frontend | Next.js | SSR, API routes, TypeScript-first |
| Backend | FastAPI | Async, typed, Pydantic validation |
| Embeddings | <!-- your choice --> | <!-- why --> |
| Vector store | <!-- your choice --> | <!-- why --> |
