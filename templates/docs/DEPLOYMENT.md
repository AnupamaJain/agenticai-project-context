# Deployment

## Platforms
- [PRIMARY PLATFORM] (e.g. AWS, Vercel, Docker)
- [SECONDARY PLATFORM]

## Configuration
- Environment Variables: See `.env.example`
- Secrets: [WHERE SECRETS ARE STORED]

## Environments
| Env | Purpose | Branch |
|-----|---------|--------|
| dev | Development | main / develop |
| staging | Pre-production | staging |
| production | Live | production |

## CI/CD Pipeline
<!-- Describe the CI/CD steps -->
1. Push to branch
2. Run Linters & Tests
3. Build Image/Bundle
4. Deploy to [PLATFORM]

## Health Checks
- Endpoint: `/health`
- Frequency: [X] seconds
