## Database

<!-- Specify your DB: PostgreSQL / MySQL / MongoDB / DynamoDB / SQLite / other -->
Primary DB: [YOUR DATABASE] — source of truth for structured application data.

- Use migrations for all schema changes — never modify schema manually in production.
- Design tables/collections with clear ownership, timestamps, and constraints.
- Add indexes for common filters, joins, and search patterns.
- Use foreign keys / references where appropriate.
- Prefer soft-delete only when there is a real product need.

### Schema Design

- Every core entity should have: id, created_at, updated_at.
- For multi-tenant systems, include tenant/organization isolation.
- Use enums or constrained fields for finite states.
- Keep schemas normalized unless denormalization is justified by performance.

### Repository Rules

- All DB access must go through repositories/data-access layer.
- Keep query code out of routes and services unless trivial.
- Parameterize all queries — never concatenate user input into queries.
- Avoid N+1 query patterns.
- Use transactions when multiple writes must succeed together.

### Do Not

- Write raw queries inside controllers/routes.
- Make schema changes without migration files.
- Assume single-tenant if the product is or may become multi-tenant.
- Store plaintext passwords, secrets, or tokens.