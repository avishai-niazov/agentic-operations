# Run Playbook — Technical Health

This playbook describes how to execute a Technical Health run: diagnose, classify, propose a safe path, and route. It is a procedural companion to `.claude/skills/technical-health/SKILL.md`.

## When to run

- an incident is routed from Intake & Triage
- a scheduled health check is due
- a performance regression is detected
- a technical publish-safety check has been requested (post-publish or pre-publish)

## Pre-flight

1. Open required reads: `knowledge/technical/wordpress_stack_inventory_v01.md`, `knowledge/technical/database_map_v01.md`, `knowledge/technical/filesystem_map_v01.md`, `docs/contracts/tool_contracts_v02.md`, `docs/governance/approval_matrix_v02.md`.
2. Gather relevant logs, diagnostics, and snapshots for the affected surface.
3. Confirm the trigger type.

## Step-by-step run

### Step 1 — Capture the signal

Record the signal verbatim. Note source, timestamps, affected surfaces, and immediate user-visible symptoms.

### Step 2 — Diagnose

- Write the observation: what is true, with evidence.
- Write at least two hypotheses, ranked by likelihood.
- Choose the leading hypothesis and state what would confirm or falsify it.

Never merge observation and hypothesis into a single "probably X" sentence.

### Step 3 — Classify risk

- **Technical risk:** low | medium | high | critical.
- **Blast radius:** surfaces affected by any proposed fix.
- **Data-integrity risk:** yes / no, with reasoning.

### Step 4 — Propose the safe path

- The smallest action that addresses the leading hypothesis.
- Reversibility: exactly how the change is undone, and within what time.
- If reversibility is weak, open a rollback candidate before proposing the action.

### Step 5 — Request approval if needed

- For any production write, request governance approval. Cite the approval matrix entry.
- For read-only diagnostics or local/staging actions, approval may not be required — confirm against policy.

### Step 6 — Write the report

Use `templates/output-template.md`. Save to `runs/incidents/` for incidents, `runs/reports/` for health checks and post-change reviews.

### Step 7 — Route

- Blocker present → `queues/blocked/` with clear reason.
- Rollback candidate → `runs/rollback_candidates/`.
- Adjacent-agent notifications as relevant:
  - SEO & Crawl if canonical / sitemap / template affected
  - Analytics & Evaluation for post-incident scoring
  - Content Production if publishing flow is affected

### Step 8 — Walk the checklist and emit trace

Walk `checklists/review-checklist.md`. Emit a trace record regardless of outcome.

## Handling edge cases

- **Single observation, no clear cause** — do not guess. Open the incident, record observations, request additional diagnostics, and hold the recommendation.
- **Request to "just clean up the DB"** — never silent. Open a proposal, request approval, include rollback.
- **Performance regression after content publish** — coordinate with Content Production and SEO & Crawl; do not roll back the content without cross-agent visibility.
- **Unclear whether local fix is enough** — treat as production risk and request approval. Conservative is correct here.

## Escalation

Escalate to Governance & Security when:

- data-integrity uncertainty exists,
- any production write is required,
- cross-surface regression risk is high,
- the issue touches secrets, credentials, or access paths.

## Definition of Done

- Diagnosis is written, with observation separated from hypothesis.
- Risk level, blast radius, and reversibility are stated.
- Next action is explicit (approved / awaiting approval / blocked / resolved).
- Incident or report artifact is saved.
- A trace record is emitted.
