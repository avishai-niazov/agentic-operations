# Evaluation Report — <run_id>

> Use this template for every Analytics & Evaluation output. Fill every section. Do not omit fields; if a field is not applicable, write "n/a" with a one-line reason.

## Run metadata

- **Run id:** <run_id>
- **Trigger:** daily | weekly | post-change | incident-closure
- **Evaluator:** <agent or reviewer>
- **Window:** <start> → <end>
- **Subject of evaluation:** <what was run / shipped / changed>

## Inputs consulted

- Trace(s): <path(s)>
- KPI report: <path>
- Guardian reviews: <path(s) or "none">
- Incident outcomes: <path(s) or "n/a">
- Prior related runs: <path(s) or "none">

## Scorecard

### Performance dimensions

| Dimension   | Rating                                 | Observed signal               | Note |
|-------------|----------------------------------------|-------------------------------|------|
| Traffic     | strong / acceptable / weak / reject    | <number or delta>             |      |
| Engagement  | strong / acceptable / weak / reject    | <metric>                      |      |
| Revenue     | strong / acceptable / weak / reject    | <metric, if applicable>       |      |

### Quality dimensions

| Dimension       | Rating                                 | Observed signal                         | Note |
|-----------------|----------------------------------------|-----------------------------------------|------|
| Brand fit       | strong / acceptable / weak / reject    | <brand guardian outcome / exemplar fit> |      |
| Pedagogy        | strong / acceptable / weak / reject    | <pedagogy guardian outcome>             |      |
| Technical       | strong / acceptable / weak / reject    | <error rate / performance>              |      |
| Disclosure / trust | strong / acceptable / weak / reject | <governance outcome>                    |      |

## Trace review

- Trace completeness: complete / partial / missing
- Gaps observed: <list or "none">
- Process regressions: <list or "none">

## Regression check

- Regression tests run: <list from `docs/evaluation/regression_tests_v02.md`>
- Regressions detected: yes / no
- If yes:
  - Signature: <short description>
  - Case opened at: `knowledge/memory/regression_cases/<file>`

## Learning decision

- **Decision:** promote | revise | rollback | hold
- **Policy rule applied:** <cite rule from `docs/evaluation/learning_promotion_policy_v02.md`>
- **Rationale:** <2–4 sentences, grounded in observed signals>
- **Evidence bar met:** yes / no (state how)

### If promote

- Artifact location: `knowledge/memory/approved_patterns/<file>` or `approved_exemplars/<file>`
- Pattern summary: <one paragraph>

### If rollback

- Rollback candidate at: `runs/rollback_candidates/<file>`
- Blast radius: <scope>
- Suggested rollback action: <one paragraph>

### If revise

- Revision ask: <specific, actionable>
- Target agent: <agent name>

### If hold

- Reason held: <one sentence>
- Next evaluation window: <date or condition>

## Escalation

- Escalated: yes / no
- If yes, to: <agent or operator>
- Reason: <one sentence>
- Reference: `queues/awaiting_review/<file>`

## Trace record

- Emitted at: <path under `runs/traces/`>
- Conforms to: `docs/evaluation/trace_contract_v02.md`

## Sign-off

- Reviewer: __________
- Outcome: pass / conditional / fail
- Review checklist walked: yes / no
