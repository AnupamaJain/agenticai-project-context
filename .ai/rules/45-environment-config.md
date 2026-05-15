## Environment & Config

- All environment-specific values must come from environment variables or config files.
- Use a single config module/service that validates all required env vars at startup.
- Fail fast on missing or invalid configuration — do not silently use defaults for critical values.
- Maintain .env.example with every required variable documented (no real values).

### Environment Parity
- dev, staging, and production must use the same config structure.
- Environment-specific behavior must be controlled by explicit flags, not implicit detection.
- Database URLs, API keys, and model endpoints must be configurable per environment.

### Secrets Management
- Never commit .env, credentials.json, or any file with real secrets.
- Use .gitignore to block secret files.
- In production, prefer secret managers over local env files.
- Rotate secrets on a schedule or after any exposure.

### Validation
- Validate config at application startup, not at first use.
- Type-check config values (ports as int, URLs as valid URLs, etc.).
- Log which config keys are loaded (never log values) for debugging.

### Do Not
- Hardcode API keys, tokens, passwords, or URLs in source code.
- Commit .env files or any sensitive file to version control.
