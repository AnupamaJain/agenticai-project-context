# API Specification

## Conventions
- Base URL: `/api/v1`
- Format: JSON
- Auth: [YOUR AUTH METHOD] (e.g. JWT in Authorization header)

## Error Format
```json
{
  "error": true,
  "code": "ERROR_CODE",
  "message": "Human readable message",
  "details": {}
}
```

## Endpoints

### [ENTITY NAME]

#### GET / [LIST]
- Query Params: page, limit, sort, filter
- Response: Array of [ENTITY]

#### POST / [CREATE]
- Body: [ENTITY_CREATE_SCHEMA]
- Response: [ENTITY]

#### GET /:id [DETAIL]
- Response: [ENTITY]

#### PATCH /:id [UPDATE]
- Body: [ENTITY_UPDATE_SCHEMA]
- Response: [ENTITY]

#### DELETE /:id [DELETE]
- Response: 204 No Content
