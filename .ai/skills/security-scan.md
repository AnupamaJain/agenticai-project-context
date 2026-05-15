---
name: security-scan
description: Run a suite of checks to find common security vulnerabilities.
---

# Skill: Security Health Scan

## Goal
Perform an automated audit to catch low-hanging security risks.

## Steps
1. **Secrets**: Search for hardcoded keys, tokens, or passwords in the source.
2. **Dependencies**: Run `npm audit` or `pip-audit` to find known CVEs.
3. **Inputs**: Check for missing validation/sanitization on user-facing endpoints.
4. **Config**: Verify that debug modes are disabled and CORS is not overly broad.
5. **Permissions**: Audit database RLS/policies if applicable.

## Security Rule
Refer to `.ai/rules/70-security.md` for the full non-negotiable list.
