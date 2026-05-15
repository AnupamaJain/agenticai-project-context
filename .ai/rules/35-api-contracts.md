## API Contracts & Versioning

- Version APIs explicitly (e.g. /api/v1/, /api/v2/).
- Never introduce breaking changes to an existing version without deprecation.
- Document breaking vs non-breaking changes clearly.
- Use OpenAPI/Swagger specs when the project supports it.

### Schema Evolution

- Add new fields as optional — never remove or rename existing fields in-place.
- Use explicit migration paths when changing response shapes.
- Dataset/payload schema changes must be versioned alongside code.

### Contract Expectations

- Request and response schemas must be typed (Pydantic, TypeScript interfaces, Zod, etc.).
- Error responses must follow a consistent structure across ALL endpoints:
  ```json
  { "error": true, "code": "RESOURCE_NOT_FOUND", "message": "...", "details": {} }
  ```
- Pagination, filtering, and sorting must use consistent query parameter conventions.
- All public endpoints must have example request/response in docs or tests.

### Deprecation Process

- Mark deprecated endpoints with headers or response metadata.
- Set a removal timeline and communicate it.
- Log usage of deprecated endpoints to track migration.

### Do Not

- Ship breaking API changes without versioning.
- Return different response shapes from the same endpoint based on hidden logic.
- Leave undocumented endpoints in production.