# Runtime State Model v02

## Purpose

Define allowed work states and transitions across queues.

## States

- `incoming`
- `triaged`
- `approved`
- `blocked`
- `in_progress`
- `awaiting_review`
- `awaiting_guardian_review`
- `done`
- `rollback_candidate`
- `archived`

## Transition rules

### incoming → triaged
Performed by Intake & Triage when task is typed and normalized.

### triaged → approved
Performed when scope, corpus, permissions, and verification expectations are valid.

### triaged → blocked
Performed when prerequisites, permissions, or quality thresholds are not met.

### approved → in_progress
Performed when the assigned agent begins execution.

### in_progress → awaiting_guardian_review
Required for content tasks and messaging changes.

### awaiting_guardian_review → awaiting_review
Performed after Brand Steward and Pedagogical Steward pass.

### awaiting_guardian_review → blocked
Performed when either guardian fails the output.

### awaiting_review → done
Performed after safety, governance, and required verification checks pass.

### any_state → rollback_candidate
Performed when an executed change created regressions or quality risk.

### blocked → triaged
Allowed only after a meaningful revision.

## State meanings

### blocked
The task cannot proceed safely or constitutionally.

### awaiting_guardian_review
The output is not publishable until identity and pedagogy checks are completed.

### awaiting_review
The output passed operator work and now needs safety, governance, or verification confirmation.

### rollback_candidate
The change was executable, but post-change evidence indicates it should be reverted or reviewed.

## Terminal states

- `done`
- `archived`

## Notes

A task is not done merely because content or code exists. It is done when:
- required gates passed
- required verification exists
- writes are recorded
- evaluation routing is complete
