## Caching

<!-- Specify your cache: Redis / Memcached / in-memory / CDN / none -->
Cache Layer: [YOUR CACHE TOOL]

Use caching for: repeated reads, rate limiting, session-like ephemeral state, queues, short-lived coordination.

- Choose TTLs intentionally — document why each TTL was chosen.
- Cache only what has a clear, measurable performance benefit.
- Make cache invalidation explicit — never let stale data silently persist.

### Rules

- Wrap cache access in dedicated utilities/services — do not scatter raw cache calls.
- Use stable, documented key naming conventions.
- Document key patterns when introducing new key families.
- Prefer idempotent worker/job behavior.
- Use retries carefully — avoid infinite retry loops.

### Caching Expectations

- Cache expensive reads and repeated metadata lookups where appropriate.
- Do not cache highly sensitive data unless encrypted and justified.
- Do not rely on cache as the only source of truth for critical persistent state.

### Do Not

- Scatter raw cache calls across the codebase.
- Store large unbounded payloads without TTL or cleanup strategy.
- Mix queue semantics and cache semantics without clarity.