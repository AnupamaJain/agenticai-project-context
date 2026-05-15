## Backend

<!-- Specify your framework: FastAPI / Express / Django / Spring / Rails / other -->
Stack: [YOUR FRAMEWORK], [YOUR VALIDATION LIBRARY], [YOUR ORM], [YOUR DB], [YOUR CACHE]

- Use clean architecture.
- Routes/controllers should only handle HTTP/transport concerns.
- Business logic must live in services.
- Database access must live in repositories.
- Validation must be done using typed schemas/models.
- Use dependency injection patterns where appropriate.
- Use async I/O where supported and beneficial.
- Use pagination for list endpoints.
- Use consistent response models.
- Use centralized exception handling.

### API Conventions

- Follow RESTful naming conventions.
- Version APIs when needed (e.g. /api/v1/).
- Use proper HTTP status codes.
- Return predictable, consistent response structure.
- Do not leak internal stack traces or raw database errors.

### Preferred Structure
```
[your-service]/
├── routes/          # HTTP handlers only
├── services/        # Business logic
├── repositories/    # DB access only
├── models/          # DB/ORM models
├── schemas/         # Request/response validation
├── core/            # Config, startup, middleware
├── utils/           # Shared helpers
└── tests/           # Unit + integration tests
```

### Do Not

- Put SQL or ORM-heavy logic inside route files.
- Put business logic inside validation schemas.
- Scatter environment variables across many files — centralize in config.
- Mix unrelated domains in the same service file.