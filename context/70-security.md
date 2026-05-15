## Security

- Never hardcode secrets, API keys, tokens, credentials, or private URLs anywhere in code.
- Never log passwords, tokens, raw secrets, or sensitive user content.
- Validate and sanitize ALL user inputs — server side.
- Treat uploads, URLs, prompts, and external content as untrusted.
- Enforce authentication and authorization checks on all protected resources.
- Use least-privilege access patterns everywhere.
- Add rate limiting to sensitive or expensive endpoints.
- Use secure defaults — fail closed, not open.

### AI-Specific Security

- Add prompt injection resistance where LLMs process user-controlled input.
- Validate tool inputs and outputs in agentic systems.
- Restrict tool/function access by policy.
- Protect system instructions and internal configuration from leakage.
- Scan/handle unsafe model output before returning it to users.

### Infra / Security Hygiene

- Prefer environment variables and secret managers (AWS Secrets Manager, Vault, etc.).
- Avoid broad wildcard permissions in cloud/IAM configs.
- Do not expose internal services publicly unless explicitly required.
- Enforce HTTPS everywhere — never disable certificate validation.

### Do Not

- Assume client-side validation is sufficient.
- Return internal error details to end users in production.
- Store plaintext passwords or tokens in databases.
- Use default credentials or weak secrets in any environment.
- Disable HTTPS or TLS certificate validation.