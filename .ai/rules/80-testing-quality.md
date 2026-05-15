## Testing & Code Quality

### Testing Philosophy
- Write production-quality code with tests for critical behavior.
- Prefer deterministic unit tests for business logic.
- Add integration tests for APIs, repositories, and workflows crossing boundaries.
- Mock external services and cloud dependencies.

### Testing Expectations
- Add tests for non-trivial service methods and auth flows.
- Add tests for RAG/agent logic at the orchestration level.
- Cover validation, failure, and edge cases.
- Keep tests readable, isolated, and fast.

### Code Quality
- Use linting and formatting consistently.
- Use strict typing/definitions wherever the stack supports them.
- Keep functions focused and refactor repeated logic.

### Do Not
- Add major logic without at least basic tests.
- Create brittle tests tied to unstable implementation details.
- Depend on live external APIs in normal test flows.
