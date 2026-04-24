# Run Playbook — Monetization & Merchandising

This playbook describes how to execute a Monetization & Merchandising run: analyzing monetization signals and producing safe recommendations. It is a procedural companion to `.claude/skills/monetization-merchandising/SKILL.md`.

## When to run

- weekly monetization review window
- traffic mix shift detected (new audience, new referrer pattern)
- template or publishing flow requests a monetization safety check
- analytics flags a monetization regression

## Pre-flight

1. Open required reads: `knowledge/business/monetization_rules_v01.md`, `docs/governance/approval_matrix_v02.md`, `docs/evaluation/scorecard_framework_v02.md`.
2. Open the latest RPM, CTR, and affiliate performance reports.
3. Identify which surfaces are in-scope for the run.

## Step-by-step run

### Step 1 — Analyze the impact surface

Map the surface(s) in question: single page, template class, hub, or sitewide. Note traffic share, engagement profile, and audience (e.g., teacher, student, general).

### Step 2 — Measure the current baseline

Collect current RPM, CTR, revenue per surface, and user-side metrics that act as guardrails (speed, engagement, bounce, support tickets).

### Step 3 — Identify the opportunity or issue

Frame the monetization change as a hypothesis:

- "Moving ad unit X from position A to B will lift RPM without harming engagement on template class Y."
- "Removing affiliate block Z on hub H will improve teacher trust without significant revenue loss."

Avoid recommendations framed only as "increase ads" or "add affiliate."

### Step 4 — Design the smallest viable test

- Pick the narrowest scope that can answer the hypothesis.
- Define success metric and guardrail metric.
- Define sample size and duration before starting.
- Define the rollback trigger.

### Step 5 — Assess tradeoff and trust

Write a paragraph stating the user-side cost of the change. If the paragraph reads like "minimal impact expected," rewrite it with specific risk. Teacher usefulness and trust are first-class considerations, not afterthoughts.

### Step 6 — Consult adjacent agents

- **Speed or template risk** — consult Technical Health before finalizing.
- **Editorial boundary risk** (does this blur content and ad?) — consult Brand Steward.
- **Teacher-audience risk** — consult Pedagogical Steward.

### Step 7 — Write the recommendation

Use `templates/output-template.md`. Ensure tradeoff, limits, and rollback are all present.

### Step 8 — Walk the checklist

Walk `checklists/review-checklist.md` before routing for governance approval.

### Step 9 — Route

- Experiment or sitewide change → Governance & Security via `queues/awaiting_review/`.
- Speed risk observed → Technical Health.
- Regression detected → open a rollback candidate in `runs/rollback_candidates/`.
- Emit a trace record.

## Handling edge cases

- **Revenue is down but no clear cause** — do not react with ad density. Request an Analytics & Evaluation review before recommending.
- **Affiliate performs well but content is weak** — do not keep the affiliate for revenue alone. Route to Content Strategy for refresh or retirement.
- **Template change requested by monetization** — go through Technical Health; monetization does not change templates directly.
- **Pressure to run a sitewide experiment quickly** — slow down. Small scope first.

## Escalation

Escalate to Governance & Security when:

- public UX risk is high,
- speed risk is high on top landing surfaces,
- teacher-experience conflict is detected,
- disclosure implications are unresolved.

## Definition of Done

- Recommendation states tradeoff, scope limits, and rollback condition.
- Relevant adjacent agents (technical, brand, pedagogy) have been consulted.
- Recommendation is routed for approval or rollback.
- A trace record is emitted.
