# TaskFlow API - Functional Specification

## Overview

REST API for managing tasks. Stack: Python 3.11+, Flask. Data is stored in memory.

## Data model

| Field | Type | Required | Default | Constraints |
|---|---|---|---|---|
| id | string | auto | uuid4 | Unique, generated server-side |
| title | string | yes | none | 1-200 characters |
| description | string | no | empty string | Max 2000 characters |
| priority | string | no | medium | low, medium, high |
| status | string | no | todo | todo, in_progress, done |
| due_date | string | no | null | YYYY-MM-DD |
| created_at | string | auto | now | ISO datetime |

## Endpoints

| Method | Path | Description |
|---|---|---|
| POST | `/tasks` | Create a task |
| GET | `/tasks` | List tasks, optionally filtered by status and priority |
| GET | `/tasks/{id}` | Get one task |
| PUT | `/tasks/{id}` | Update one task |
| DELETE | `/tasks/{id}` | Delete one task |

## Error handling

All errors return JSON:

```json
{ "error": "message" }
```

Expected statuses:

- 400 for validation errors
- 404 for missing task
- 405 for unsupported methods

## Constraints

- No authentication.
- In-memory storage only.
- JSON API.
- UUID identifiers.
