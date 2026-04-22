# Refusal Enforcement Table v02

## Refuse immediately when

- the requested action violates constitutional constraints
- content is being generated from market corpus as a style source
- guardian review is skipped
- an agent attempts to exceed its charter
- a risky write lacks governance approval
- trace creation is being skipped
- a task attempts to self-modify charters, constitutions, or thresholds

## Enforcement modes

- `hard_refusal` — stop work
- `block_and_route` — route back with revision requirements
- `quarantine` — preserve output but prevent progression
- `escalate` — request governance decision
