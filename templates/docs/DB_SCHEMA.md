# Database Schema

## Core Tables

### users
| Column | Type | Notes |
|--------|------|-------|
| id | [TYPE] | PK |
| email | [TYPE] | unique, indexed |
| created_at | timestamp | |
| updated_at | timestamp | |

### [ENTITY_1]
| Column | Type | Notes |
|--------|------|-------|
| id | [TYPE] | PK |
| user_id | [TYPE] | FK -> users |
| [FIELD_1] | [TYPE] | |
| created_at | timestamp | |
| updated_at | timestamp | |

## Core Rules
- All tables must have ID, created_at, updated_at.
- Foreign keys must be enforced with appropriate constraints.
- Sensitive data must be encrypted or properly handled.
- Indexes should be added for frequent query patterns.

## Migrations
- Tool: [YOUR MIGRATION TOOL]
- Command: [COMMAND TO RUN MIGRATIONS]
