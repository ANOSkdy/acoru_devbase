# Screen Spec: [Screen Name]

## Purpose
[Why this screen exists.]

## Users
- [Who can access this screen.]

## Route
`/[path]`

## Access Control
- Authentication required: [yes/no]
- Role restriction: [none/admin/operator/etc.]

## Main UI Elements
- [page title]
- [filters]
- [table/list/cards]
- [form]
- [action buttons]
- [pagination]
- [modal/drawer if needed]

## Display Fields
| Field | Source | Format | Notes |
|---|---|---|---|
| [name] | [API/DB/UI state] | [text/date/status] | [notes] |

## User Actions
- [create]
- [update]
- [delete]
- [search]
- [filter]
- [download/export]

## Validation / Constraints
- [required fields]
- [max lengths]
- [uniqueness assumptions]
- [forbidden states]

## States
- initial
- loading
- empty
- validation error
- server error
- success

## API Dependencies
- `GET /api/...`
- `POST /api/...`
- `PATCH /api/...`
- `DELETE /api/...`

## Notes
[Business rules or implementation caveats.]

## Acceptance Criteria
- [user can perform the main task]
- [invalid input is blocked]
- [errors are shown safely]
- [mobile layout remains usable]
