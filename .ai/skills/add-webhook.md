---
name: add-webhook
description: Pattern for adding secure webhook receivers (Stripe, GitHub, etc.).
---

# Skill: Add Webhook Receiver

## Goal
Implement a secure, idempotent endpoint to receive and process external events.

## Steps
1. **Route**: Create a new POST route (e.g., `/api/webhooks/[service]`).
2. **Schema**: Define the expected payload schema using the service's documentation.
3. **Security**: Implement signature verification (never process unverified webhooks).
4. **Idempotency**: Ensure the event hasn't been processed before (check event ID in DB).
5. **Background**: Offload heavy processing to a background worker/queue.
6. **Response**: Return a 200 OK quickly to the sender.

## Security Rule
Refer to `.ai/rules/70-security.md` for input validation rules.
