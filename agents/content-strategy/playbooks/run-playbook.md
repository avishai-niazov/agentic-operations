# Run Playbook — Content Strategy

This playbook describes how to execute a Content Strategy run: turning an opportunity into an approved brief that is safe to hand to Content Production. It is a procedural companion to `.claude/skills/content-strategy/SKILL.md`.

## When to run

- a new content opportunity has been routed by Intake & Triage or SEO & Crawl
- a refresh request has been routed (decay, outdated content, guardian regression)
- a hub gap has been identified
- a seasonal planning window is open

## Pre-flight

1. Confirm the trigger and the source signal.
2. Open required reads from `SKILL.md`: brand constitution, pedagogical charter, teacher intent patterns, activity design patterns, hub strategy, growth plan summary.
3. Scan the current content library for related or overlapping pages.

## Step-by-step run

### Step 1 — Frame the opportunity

State in one sentence what the reader need is and why it fits the site's identity. If you can't state it in one sentence, the opportunity is probably too broad.

### Step 2 — Choose the content shape

Pick the template or pattern from `knowledge/content/content_templates_v01.md` and `activity_design_patterns_v01.md`. The shape drives the brief.

### Step 3 — Draft the brief

Use `templates/output-template.md`. Fill:

- audience (specific),
- learning goal (reader-facing capability),
- target surface (page type and hub position),
- teacher intent (real classroom or study use),
- no-go zones (what this will not claim or cover),
- distinctive angle,
- hub and cluster fit,
- internal-link intent,
- success signal(s) for later evaluation.

### Step 4 — Pre-route self-check

Walk `checklists/review-checklist.md`. Revise the brief until every item passes.

### Step 5 — Route to guardian reviews

- Send to **brand brief review** (Brand Steward).
- Send to **pedagogy brief review** (Pedagogical Steward).
- Emit a trace record.

### Step 6 — Respond to guardian outcomes

- **Both pass** — issue the approved brief to Content Production.
- **Conditional on one** — apply the revision; re-submit that guardian only.
- **Fail on either** — accept and revise; do not argue for exception. If the failure is structural, return to Intake & Triage to redefine the opportunity.

## Handling edge cases

- **Opportunity is strong but brand and pedagogy disagree** — do not pick a winner; escalate to Governance & Security.
- **High-scale proposal (many pages)** — slow down. Require a single exemplar brief approved by guardians before considering scale.
- **Refresh vs. retire vs. merge** — if unclear, route to Analytics & Evaluation for signal before briefing.
- **Competitor has strong version of this topic** — note it for opportunity sizing only. Do not use their shape or voice.

## Escalation

Escalate to Governance & Security when:

- brand and pedagogy disagree sharply and the tradeoff is unresolved,
- the proposal depends on risky monetization, partner, or technical assumptions,
- a high-scale plan would risk identity drift if pushed through as-is.

Escalation: open a decision request in `queues/awaiting_review/`, include the draft brief and both guardian outcomes, and hand off.

## Definition of Done

- A brief exists in the required shape.
- Both guardian reviews are recorded: pass or explicit block.
- If approved, the brief is handed to Content Production.
- A trace record is emitted.
