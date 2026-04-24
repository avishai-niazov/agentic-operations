# Governance Decision — <decision_id>

> Use this template for every Governance & Security output. A decision without rationale or routing is not complete.

## Decision metadata

- **Decision id:** <id>
- **Request type:** approval | risk escalation | sensitive write | rollback
- **Requester:** <agent name>
- **Date:** <YYYY-MM-DD>

## Request summary

- **Action proposed:** <concrete description>
- **Surface(s) affected:** <pages / templates / systems>
- **Requested scope:** <one-off | recurring | sitewide>
- **Urgency stated:** <requester's framing — note it, do not weigh it>

## Classification

- **Action class:** <from approval matrix>
- **Matrix entry:** <reference to `docs/governance/approval_matrix_v02.md` section>
- **Required approval level:** <per matrix>

## Invariant check

- **Invariants reviewed:** <list of relevant invariants>
- **Violations found:** <list or "none">

## Blast radius

- **Worst case:** <one paragraph>
- **Surfaces affected:** <count and scope>
- **Reversible within:** <time window or "irreversible">
- **Rollback path:** <description or "none defined">

## Evidence review

- **Trace provided:** yes / no — <reference>
- **Guardian outcomes:** <brand / pedagogy / analytics where relevant>
- **Prior similar decisions:** <references>
- **Evidence strength:** strong | adequate | thin

## Policy citations

- <rule from approval matrix / invariant register / secrets policy / disclosure policy>

## Decision

- **Outcome:** approve | approve with conditions | block | escalate to human
- **Rationale:** <one paragraph, grounded in citations above>

## Conditions (if "approve with conditions")

- <named bounds: scope, duration, surfaces>
- <rollback trigger: the observable signal that requires immediate rollback>
- <required follow-up review: date or event>

## Block reasons (if "block")

- <failed item from the checklist>
- <specific policy or invariant>
- <what would make a future request approvable>

## Escalation (if "escalate to human")

- **Routed to:** <operator or role>
- **Reason:** <one sentence>
- **Attached evidence:** <paths>

## Routing

- Queue: `queues/approved/` | `queues/blocked/` | `queues/awaiting_review/`
- Decision log entry: `knowledge/memory/decisions_log/<file>`
- Trace record at: <path>

## Sign-off

- Reviewer: __________
- Checklist walked: yes / no
- Date: __________
