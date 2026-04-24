# Review Checklist — Technical Health

Use this checklist before routing any diagnosis, recommendation, or rollback. Production write decisions without this check are not safe.

## 1. Incident / signal intake

- [ ] The source of the signal is named (alert, log, cron, DB diagnostic, performance snapshot, manual report).
- [ ] Timestamps and affected surfaces are captured.
- [ ] Raw signal is preserved, not paraphrased.

## 2. Diagnosis discipline

- [ ] Observation is separated from hypothesis.
- [ ] At least one alternative hypothesis has been considered.
- [ ] The diagnosis cites relevant infrastructure reads (`wordpress_stack_inventory_v01.md`, `database_map_v01.md`, `filesystem_map_v01.md`).

## 3. Risk classification

- [ ] Technical risk is classified: low | medium | high | critical.
- [ ] Blast radius is stated (single surface, template class, sitewide, external system).
- [ ] Data-integrity risk is specifically addressed (yes / no, with reasoning).

## 4. Safe path proposal

- [ ] The proposed action is concrete, not "investigate further."
- [ ] Reversibility is stated, including time window.
- [ ] If reversibility is weak, a rollback candidate is opened even if approval is expected.

## 5. Approval routing

- [ ] For any production write, governance approval is requested — not assumed.
- [ ] The relevant approval-matrix entry is cited.
- [ ] For write-heavy actions, a rollback candidate is written to `runs/rollback_candidates/`.

## 6. Incident discipline

- [ ] Incident record is written to `runs/incidents/`.
- [ ] Failure signature, if recognizable, is recorded against `knowledge/memory/known_failures/`.
- [ ] Adjacent agents are notified where relevant (SEO if canonical/sitemap affected; Analytics if traffic affected).

## 7. Observability

- [ ] The signal the operator should watch after the change is named.
- [ ] A check-back time is set.
- [ ] Trace record is emitted.

## 8. Prohibited-action check

- [ ] No direct public publishing.
- [ ] No silent DB cleanup.
- [ ] No unapproved production write.

## Sign-off

- Operator: __________
- Incident / report id: __________
- Risk level: __________
- Approval status: requested / not required / granted
- Date: __________
