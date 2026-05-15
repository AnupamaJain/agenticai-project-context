# Deployment

## Local

### Prerequisites
- Docker and Docker Compose
- Node.js 18+
- Python 3.11+

### Setup
```bash
cp .env.example .env        # Fill in your values
docker compose up -d         # Start postgres, redis
cd backend && pip install -r requirements.txt && uvicorn main:app --reload
cd frontend && npm install && npm run dev
```

### Services
| Service | Port | URL |
|---------|------|-----|
| Frontend | 3000 | http://localhost:3000 |
| Backend | 8000 | http://localhost:8000 |
| PostgreSQL | 5432 | localhost:5432 |
| Redis | 6379 | localhost:6379 |

## Cloud

### Provider
- AWS (primary)
- Vercel (frontend alternative)

### AWS Stack
| Component | Service |
|-----------|---------|
| Backend | ECS Fargate |
| Frontend | S3 + CloudFront (or Vercel) |
| Database | RDS PostgreSQL |
| Cache | ElastiCache Redis |
| Storage | S3 |
| Secrets | Secrets Manager |
| Logs | CloudWatch |
| CI/CD | GitHub Actions → ECR → ECS |

### Vercel (Frontend)
| Setting | Value |
|---------|-------|
| Framework | Next.js |
| Build command | `npm run build` |
| Output dir | `.next` |
| Env vars | Set via Vercel dashboard |
| Preview deploys | On every PR |
| Production | On merge to main |

### VPS Alternative
| Component | Tool |
|-----------|------|
| Process manager | systemd or PM2 |
| Reverse proxy | Nginx or Caddy |
| SSL | Let's Encrypt (auto-renew) |
| Firewall | UFW (ports 22, 80, 443 only) |
| Auth | SSH keys only |
| Updates | unattended-upgrades |
| Deploy | Git pull + restart script |

## Environments
| Env | Purpose | Branch |
|-----|---------|--------|
| dev | Local development | feature/* |
| staging | Pre-production testing | develop |
| production | Live users | main |

## CI/CD Pipeline
```
Push → Lint → Test → Build → Deploy
  │                            │
  ├── feature/* → staging      │
  └── main → production ───────┘
```

### Checks before deploy
- [ ] All tests pass
- [ ] Lint clean
- [ ] Build succeeds
- [ ] No hardcoded secrets
- [ ] Migrations reviewed

## Non-Functional Goals
- Scalable (horizontal scaling via containers)
- Secure (least privilege, encrypted at rest/transit)
- Observable (structured logs, metrics, alerts)
- Rollback-friendly (blue-green or rolling deploys)
