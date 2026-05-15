---
name: deploy-app
description: Standardized deployment workflow for moving code to production.
argument-hint: "[target-environment]"
---

# Skill: Deploy Application

## Goal
Safely deploy the application to a cloud environment (AWS, Vercel, Docker, etc.) ensuring all checks pass.

## Steps
1. **Pre-flight**: Run linters and type checkers.
2. **Testing**: Execute the full test suite; fail on any error.
3. **Build**: Generate the production build/image.
4. **Environment**: Verify all required production environment variables are set.
5. **Database**: Run any pending database migrations.
6. **Push**: Deploy the build to the target platform.
7. **Verify**: Perform a health check on the live URL.

## Configuration
- See `.ai/rules/90-devops-deployment.md` for platform-specific rules.
