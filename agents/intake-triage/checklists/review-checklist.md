# Review Checklist — Intake & Triage

Use this checklist before routing any triaged work item. A malformed item sent downstream is worse than a signal held for clarification.

## 1. Signal intake

- [ ] The signal source is named (alert, email, search-console, analytics, manual, incident).
- [ ] A timestamp is captured.
- [ ] Raw signal content is preserved (not paraphrased away).

## 2. Classification

- [ ] Task class is explicit: incident | seo | content opportunity | content refresh | monetization | technical | governance | other.
- [ ] If "other," a one-line justification is recorded — "other" should be rare.
- [ ] The classification is grounded in signal content, not guesswork.

## 3. Severity

- [ ] Severity is assigned for incidents: sev-1 | sev-2 | sev-3 | low.
- [ ] For non-incidents, priority is assigned: urgent | high | normal | low.
- [ ] The severity/priority is defensible against the signal observed.

## 4. Corpus and context

- [ ] The required corpus for downstream work is named (technical, content, SEO, monetization).
- [ ] Links or paths to relevant context are included.

## 5. Routing

- [ ] Target downstream agent is named.
- [ ] Target queue is named (`queues/triaged/` with downstream pointer).
- [ ] Routing matches `SKILL.md` downstream mapping.

## 6. Scope and risk

- [ ] The item is single-surface, or cross-surface risk is explicitly flagged.
- [ ] Any sensitive-write implication is flagged for governance awareness.
- [ ] Permission ambiguity, if any, is called out.

## 7. Prohibited-action check

- [ ] No technical fix attempted here.
- [ ] No public content written here.
- [ ] No use of market-intelligence content as style input.

## 8. Trace and handoff

- [ ] A trace record is emitted.
- [ ] The downstream agent can act on the item without coming back for clarification.

## Sign-off

- Triager: __________
- Work item id: __________
- Class / severity: __________ / __________
- Target agent: __________
- Date: __________
