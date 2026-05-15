## Frontend

Stack: [YOUR FRONTEND FRAMEWORK] (e.g. Next.js, React, Vue, Svelte)

- Prefer strict typing for all frontend logic.
- Keep components small, reusable, and focused.
- Keep presentation separate from business/data-fetching logic.
- Handle loading, error, and empty states explicitly.
- Maintain design and naming consistency.

### UI/UX
- Use accessible markup and semantic HTML.
- Prefer reusable design system components.
- Responsive, mobile-first design.
- Avoid embedding complex API/business logic directly inside visual components.

### State & Data
- Keep API clients centralized.
- Normalize repeated API access patterns.
- Handle authentication state securely.
- Validate critical inputs on both client and server.

### Do Not
- Mix too many responsibilities into one component.
- Hardcode API URLs in components.
- Duplicate UI patterns that should be shared.
