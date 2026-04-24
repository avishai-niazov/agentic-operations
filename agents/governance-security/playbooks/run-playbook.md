# Run Playbook — Governance, Security & Approval

This playbook describes how to execute a Governance & Security decision. It is a procedural companion to `.claude/skills/governance-security/SKILL.md`.

## When to run

- a risky write is requested
- a constitutional conflict has been flagged
- permission ambiguity has been detected
- an external action is requested
- a rollback recommendation has been routed

## Pre-flight

1. Open `docs/governance/approval_matrix_v02.md`, `docs/governance/invariant_register_v02.md`, `docs/governance/secrets_and_access_policy_v02.md`, `docs/governance/provenance_and_disclosure_policy_v01.md`, and `HARNESS.md`.
2. Read the request. If the requester did not state the action class, surface that gap first.

## Step-by-step run

### Step 1 — Classify the action

Identify the action class against the approval matrix. Common classes:

- content publish (new or refresh)
- template or schema change
- monetization experiment
- robots, canonical, or sitemap change
- database write
- external action (email, partner, purchase)
- policy change (rare; governance-change process)

If the action does not fit any class, that is a defect in the request. Block and escalate.

### Step 2 — Check invariants

Walk the relevant subset of `invariant_register_v02.md`. Any violation means block, regardless of business value.

### Step 3 — Assess blast radius

- What breaks in the worst case?
- How many surfaces are affected?
- Is the change reversible, and within what time window?

If blast radius cannot be stated with confidence, require more evidence before approving.

### Step 4 — Check evidence

- Is there a trace?
- Is there a guardian outcome (brand, pedagogy, analytics)?
- Is there a prior similar decision?

Weak evidence plus high blast radius = block or escalate to human. Weak evidence plus low blast radius can be approved with explicit scope and a rollback trigger.

### Step 5 — Decide

Choose exactly one:

- **Approve** — action is safe under policy and evidence.
- **Approve with conditions** — action is approved within named bounds and with a rollback trigger.
- **Block** — policy or invariant fails; evidence insufficient; blast radius unbounded.
- **Escalate to human** — public-trust risk, constitutional conflict unresolved, data integrity risk, or precedent-setting.

### Step 6 — Record the decision

Use `templates/output-template.md`:

- cite the rule or invariant applied,
- state the rationale,
- note rollback trigger if applicable,
- log to `knowledge/memory/decisions_log/`.

### Step 7 — Route

- Approve → `queues/approved/`.
- Block → `queues/blocked/`.
- Escalate → `queues/awaiting_review/` with a clear handoff note to the operator.

### Step 8 — Emit trace

Always emit a trace record. No exceptions.

## Handling edge cases

- **Request is low-risk but ill-formed** — do not approve. Send back for reformulation. Casual approval of malformed requests degrades the governance surface.
- **Two policies conflict** — escalate. Never silently pick which policy to apply.
- **Rollback cannot be defined** — for anything beyond trivial scope, no rollback = no approval.
- **Time pressure asserted by requester** — pressure is not evidence. Decide on policy, not urgency. If urgency is real, escalate to the human operator.

## Escalation

Escalate to the human operator when:

- blast radius is unclear,
- public-trust risk is present,
- data-integrity risk is present,
- constitutional conflict cannot be resolved by policy alone,
- the decision would set precedent not covered by the approval matrix.

Escalation: write a decision request in `queues/awaiting_review/`, attach the full trace, and pause the action.

## Definition of Done

- Decision is explicit (approve | approve-with-conditions | block | escalate).
- Rationale cites policy or invariant.
- Decision is logged in `knowledge/memory/decisions_log/`.
- Decision is routed to the correct queue.
- A trace record is emitted.
