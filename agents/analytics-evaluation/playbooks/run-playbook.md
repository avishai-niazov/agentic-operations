# Run Playbook — Analytics & Evaluation

This playbook describes how to execute a run of the Analytics & Evaluation agent end-to-end. It is a procedural companion to `.claude/skills/analytics-evaluation/SKILL.md` — read the SKILL file first; this playbook operationalizes it.

## When to run

Run the agent when one of the SKILL-defined triggers fires:

- daily summary window
- weekly review window
- post-change evaluation (a content, SEO, monetization, or technical change has just shipped)
- incident closure review

If the trigger is unclear, route the request back to Intake & Triage rather than running.

## Pre-flight

1. Confirm the trigger matches one of the allowed conditions.
2. Gather required inputs: run trace(s), KPI report, any guardian reviews, incident outcomes if relevant.
3. Open the correct reads listed in `SKILL.md` (scorecard framework, trace contract, regression tests, learning promotion policy, relevant memory).
4. Create a working record in `runs/reports/evaluation_<timestamp>/` for the output.

## Step-by-step run

### Step 1 — Score the outcome

- Apply the scorecard from `docs/evaluation/scorecard_framework_v02.md`.
- Rate each dimension: strong / acceptable / weak / reject.
- Keep performance dimensions and quality dimensions visually separated. Never collapse them into a single score.

### Step 2 — Review the trace

- Walk the trace per `docs/evaluation/trace_contract_v02.md`.
- Note any step where the trace is incomplete, missing guardian output, or inconsistent with the run result.
- Record these observations even if the overall outcome is strong.

### Step 3 — Detect regressions

- Run the checks in `docs/evaluation/regression_tests_v02.md`.
- If a regression is detected, open a regression case in `knowledge/memory/regression_cases/` regardless of overall score.

### Step 4 — Decide on learning

- Based on the scorecard plus trace review, choose one:
  - **Promote** — write an approved pattern or exemplar (only if the policy bar is met).
  - **Revise** — request a follow-up run with specific corrections.
  - **Rollback** — open a rollback candidate in `runs/rollback_candidates/`.
  - **Hold** — insufficient evidence; record observations and wait for more runs.
- State the rule from `docs/evaluation/learning_promotion_policy_v02.md` that justifies the choice.

### Step 5 — Write the output

- Use `templates/output-template.md`.
- Save to `runs/reports/evaluation_<timestamp>/evaluation.md`.
- Emit the trace record.

### Step 6 — Review against the checklist

- Walk through `checklists/review-checklist.md` before marking the run complete.
- If any item fails, fix it or escalate — do not close the run.

## Handling edge cases

- **Ambiguous evidence, high risk** — do not promote or rollback. Hold the decision and escalate to Governance & Security.
- **Conflict between guardian review and performance signal** — always defer to the guardian. Record the tension for the strategy feedback loop.
- **Trace incomplete** — treat as a process regression. Open a case and notify the upstream agent.
- **New pattern candidate appears** — do not promote on the first observation. Require repeated strong runs per the promotion policy.

## Escalation

Escalate to Governance & Security when:

- a high-impact regression has been detected
- evidence is ambiguous but the downside risk is high
- the decision would conflict with a constitutional rule

Escalation means: block the learning writeback, write the trace, open a decision request in `queues/awaiting_review/`, and hand off.

## Definition of Done

The run is done only when:

- a scorecard exists, saved to `runs/reports/evaluation_*`
- a learning decision is stated and justified
- a trace record is written
- any required memory writebacks are in allowed locations
- the review checklist has been walked and signed
