# API Spec: [METHOD] [PATH]

## Purpose
[What this endpoint does.]

## Runtime
- nodejs

## Auth
- [public/authenticated/role-based]

## Request

### Params
| Name | Type | Required | Notes |
|---|---|---:|---|
| [id] | [string] | [yes/no] | [uuid etc.] |

### Query
| Name | Type | Required | Validation | Notes |
|---|---|---:|---|---|
| [limit] | [number] | no | [min/max] | [notes] |

### Body
```json
{
  "example": "value"
}
```

## Validation
- [use zod]
- [validate param/query/body]
- [safe bounds]
- [parameterized SQL only]

## Response

### Success
```json
{
  "ok": true,
  "data": {}
}
```

### Error
```json
{
  "ok": false,
  "error": "ERROR_CODE"
}
```

## DB Behavior
- [table touched]
- [sort order]
- [limit rules]
- [rowCount handling if relevant]

## Notes
- [dynamic handling if DB-backed GET]
- [secret safety]
- [implementation caveats]
