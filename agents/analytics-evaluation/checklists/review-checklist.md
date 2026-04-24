# Review Checklist — Analytics & Evaluation

Use this checklist before finalizing any evaluation output (scorecard, trace review, promotion decision, or rollback recommendation). Every item must be answered explicitly. If an item cannot be satisfied, stop and escalate.

## 1. Scope and inputs

- [ ] The run being evaluated is clearly identified (run id, trigger, time window).
- [ ] All required inputs are present: run trace, relevant KPIs, guardian reviews.
- [ ] Inputs are from approved sources only; no ad-hoc or unverified signals were used.

## 2. Separation of performance and quality

- [ ] Performance signals (traffic, clicks, revenue) are reported separately from quality signals (brand, pedagogy, guardian outcome).
- [ ] Strong performance has not been used to excuse weak quality.
- [ ] Weak performance has not been used to reject work that passed guardian review on quality grounds.

## 3. Scorecard integrity

- [ ] The scorecard follows `docs/evaluation/scorecard_framework_v02.md`.
- [ ] Each dimension has an explicit rating: strong / acceptable / weak / reject.
- [ ] Each rating has a one-line reason grounded in an observable signal.

## 4. Learning decision

- [ ] A learning decision is stated: promote / revise / rollback / hold.
- [ ] The decision cites the rule in `docs/evaluation/learning_promotion_policy_v02.md` that supports it.
- [ ] Promotion does not violate any constitutional constraint (brand, pedagogy, governance).
- [ ] If promoting a pattern, the evidence bar (multiple strong runs, guardian pass) is met.

## 5. Regression and rollback

- [ ] Any regression signal is recorded as a regression case, not discarded.
- [ ] If a rollback is recommended, the rationale and blast radius are stated.
- [ ] Rollback candidates are written to `runs/rollback_candidates/` with enough detail to act on.

## 6. Trace and auditability

- [ ] A trace record is emitted per `docs/evaluation/trace_contract_v02.md`.
- [ ] The evaluation output is written to the correct path under `runs/reports/evaluation_*`.
- [ ] Memory writebacks (if any) go only to allowed locations: `approved_patterns`, `approved_exemplars`, `regression_cases`, `drift_cases`.

## 7. Prohibited-action check

- [ ] No pattern was promoted on intuition alone ("on vibes").
- [ ] Guardian signals were not overridden in favor of performance.
- [ ] Weak quality was not rewarded because traffic was high.

## 8. Escalation trigger review

- [ ] If any of the following are true, the output is routed to governance instead of completing silently:
  - high-impact regression detected
  - evidence ambiguous and risk high
  - constitutional or governance conflict present

## Sign-off

- Reviewer: __________
- Date: __________
- Outcome: pass / conditional / fail
- Notes: __________
