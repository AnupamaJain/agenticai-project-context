# Database Schema

## Core Tables

### users
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| email | varchar | unique, indexed |
| password_hash | varchar | bcrypt |
| name | varchar | |
| role | enum | admin, user |
| created_at | timestamp | |
| updated_at | timestamp | |

### organizations
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| name | varchar | |
| slug | varchar | unique, indexed |
| plan | enum | free, pro, enterprise |
| created_at | timestamp | |
| updated_at | timestamp | |

### memberships
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| user_id | uuid | FK → users |
| organization_id | uuid | FK → organizations |
| role | enum | owner, admin, member |
| created_at | timestamp | |

### documents
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| organization_id | uuid | FK → organizations, indexed |
| filename | varchar | |
| source_type | enum | upload, url, api |
| status | enum | pending, processing, indexed, failed |
| metadata | jsonb | |
| created_at | timestamp | |
| updated_at | timestamp | |

### document_chunks
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| document_id | uuid | FK → documents |
| organization_id | uuid | FK → organizations, indexed |
| content | text | chunk text |
| chunk_index | int | position in document |
| token_count | int | |
| metadata | jsonb | page, section, title |
| created_at | timestamp | |

### embeddings_metadata
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| chunk_id | uuid | FK → document_chunks |
| model | varchar | embedding model name |
| vector_id | varchar | ID in vector store |
| created_at | timestamp | |

### chat_sessions
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| organization_id | uuid | FK → organizations, indexed |
| user_id | uuid | FK → users |
| title | varchar | auto-generated or user-set |
| created_at | timestamp | |
| updated_at | timestamp | |

### chat_messages
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| session_id | uuid | FK → chat_sessions |
| role | enum | user, assistant, system |
| content | text | |
| sources | jsonb | retrieved chunk references |
| created_at | timestamp | |

### agent_runs
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| organization_id | uuid | FK → organizations, indexed |
| user_id | uuid | FK → users |
| agent_type | varchar | |
| status | enum | pending, running, completed, failed |
| input | jsonb | |
| output | jsonb | |
| tool_calls | jsonb | array of tool call logs |
| started_at | timestamp | |
| completed_at | timestamp | |
| created_at | timestamp | |

### billing_customers
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| organization_id | uuid | FK → organizations, unique |
| stripe_customer_id | varchar | |
| plan | enum | free, pro, enterprise |
| status | enum | active, past_due, canceled |
| created_at | timestamp | |
| updated_at | timestamp | |

### usage_events
| Column | Type | Notes |
|--------|------|-------|
| id | uuid | PK |
| organization_id | uuid | FK → organizations, indexed |
| event_type | varchar | chat_query, agent_run, doc_upload |
| metadata | jsonb | tokens, model, duration |
| created_at | timestamp | indexed |

## Core Rules
- Most business data must be tenant scoped (organization_id).
- All major tables should include created_at and updated_at.
- Permission-sensitive tables should support auditable ownership.
- Use indexes on organization_id + created_at for common queries.
- Use soft-delete only where product requires undo/recovery.
- Foreign keys enforced — no orphaned records.

## Indexes
```sql
-- High-frequency queries
CREATE INDEX idx_documents_org ON documents(organization_id);
CREATE INDEX idx_chunks_org ON document_chunks(organization_id);
CREATE INDEX idx_chat_sessions_org ON chat_sessions(organization_id, created_at DESC);
CREATE INDEX idx_agent_runs_org ON agent_runs(organization_id, created_at DESC);
CREATE INDEX idx_usage_events_org ON usage_events(organization_id, created_at DESC);
```
