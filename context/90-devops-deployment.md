## DevOps & Deployment

<!-- Fill in your actual deployment targets below -->
Deployment targets: [Docker / AWS ECS / Lambda / GCP / Azure / Vercel / VPS / Kubernetes]

### DevOps Rules

- Applications must be container-friendly.
- Keep builds reproducible — same input = same output every time.
- Use environment-driven configuration — no hardcoded env-specific values.
- Separate build-time config from runtime config.
- Add health checks on every service.
- Keep services stateless unless statefulness is intentional and documented.
- Ensure logs are structured and production-usable from day one.

### Docker

- Keep Dockerfiles clean and layered optimally.
- Prefer multi-stage builds to minimize image size.
- Never bake secrets into images.
- Use .dockerignore to exclude: node_modules, .env, .git, model checkpoints, cache.

### CI/CD

- Run lint, tests, and build validation before merge/deploy.
- Prevent broken releases from reaching production.
- Keep deployment config version-controlled alongside application code.
- Use separate environments: dev / staging / production.
- Automate rollback capability for every deployment.

### Cloud (AWS / GCP / Azure)

- Prefer managed services where appropriate.
- Use least-privilege IAM/service-account policies.
- Make networking and environment assumptions explicit in config.
- Support observability via logs, metrics, and alerts.
- Design for rollback-safe deployments.

### VPS / Self-Hosted

- Use a process manager (systemd, PM2, Supervisor).
- Set up a reverse proxy with SSL (Nginx + Let's Encrypt / Caddy).
- Use a firewall — only expose necessary ports.
- Use SSH keys only — disable password authentication.
- Keep deployment scripted and repeatable.

### Do Not

- Hardcode cloud IDs, tokens, or server IPs in code.
- Mix deployment-only hacks into application logic.
- Assume local-only paths or config will work in production.
- Run services as root.
- Expose database ports publicly on any platform.