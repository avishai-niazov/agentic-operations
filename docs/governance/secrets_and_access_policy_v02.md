# Secrets and Access Policy v02

## Principle

Access should be minimal, explicit, and logged.

## Rules

- Secrets are never stored in prompt text, memory writebacks, or public artifacts.
- Tool contracts must define read/write scope.
- DB, filesystem, admin, email, analytics, and search-console actions must be scoped by the active task class.
- Risky tools require governance approval.
- Outputs should reference actions taken, not raw secrets used.

## Access classes

- `read_only`
- `limited_write`
- `sensitive_write`
- `external_action`

## Sensitive surfaces

- production WordPress admin
- database write operations
- filesystem write operations
- robots and canonical controls
- ad placement changes
- external email actions
