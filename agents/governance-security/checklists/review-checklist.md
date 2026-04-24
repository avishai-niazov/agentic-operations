# Review Checklist — Governance, Security & Approval

Use this checklist for every approval or escalation decision. Every item must be answered explicitly. When in doubt, block and escalate to a human operator.

## 1. Request intake

- [ ] The request type is explicit: approval | risk escalation | sensitive write | rollback.
- [ ] The requester agent is identified.
- [ ] The underlying action is described in concrete terms (not "make changes").

## 2. Approval matrix

- [ ] The action has been located in `docs/governance/approval_matrix_v02.md`.
- [ ] The required approval level matches the action class.
- [ ] If the action is not in the matrix, that is itself a reason to escalate.

## 3. Invariant check

- [ ] The action has been checked against `docs/governance/invariant_register_v02.md`.
- [ ] No invariant is violated. If one is, the action is blocked regardless of business pressure.
- [ ] Constitutional constraints (brand, pedagogy) are checked.

## 4. Blast radius

- [ ] Surfaces affected are listed (single page, template, sitewide, external).
- [ ] The worst-case outcome is stated plainly.
- [ ] A rollback path is named, or the lack of one is called out.

## 5. Evidence and rationale

- [ ] The requester provided evidence (trace, guardian outcome, incident, report).
- [ ] The rationale is not "it seems fine" or "we need to move fast."
- [ ] If evidence is thin but risk is low, the decision is time-boxed or scoped.

## 6. Disclosure and trust

- [ ] The action has been reviewed against disclosure policy (`provenance_and_disclosure_policy_v01.md`).
- [ ] No implicit disclosure requirement is bypassed.
- [ ] Public trust impact is considered.

## 7. Secrets and access

- [ ] The action does not expose secrets, credentials, or sensitive paths.
- [ ] Access requests respect `docs/governance/secrets_and_access_policy_v02.md`.

## 8. Decision discipline

- [ ] The decision is one of: **approve** | **block** | **approve with conditions** | **escalate to human**.
- [ ] The decision has a one-paragraph rationale grounded in cited policy.
- [ ] The decision is written to the correct queue (`queues/approved/` or `queues/blocked/`).
- [ ] A decision log entry is written to `knowledge/memory/decisions_log/`.
- [ ] A trace record is emitted.

## 9. Prohibited-action check

- [ ] No casual approval without policy citation.
- [ ] No implicit permission granted.
- [ ] No trace or disclosure requirement bypassed.

## Sign-off

- Reviewer: __________
- Request id: __________
- Decision: approve / approve with conditions / block / escalate
- Date: __________
