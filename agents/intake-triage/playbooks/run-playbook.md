# Run Playbook — Intake & Triage

This playbook describes how to execute an Intake & Triage run: turning a raw signal into a typed, routed work item. It is a procedural companion to `.claude/skills/intake-triage/SKILL.md`.

## When to run

- a new incoming work item lands
- an alert fires
- a scheduled scan window opens
- the operator manually requests triage

## Pre-flight

1. Open `HARNESS.md`, `docs/architecture/runtime_state_model_v02.md`, and `docs/governance/invariant_register_v02.md`.
2. Capture the signal verbatim before interpreting it.

## Step-by-step run

### Step 1 — Read the signal

Do not paraphrase yet. Copy the raw signal into the work item. Note source, timestamp, and any linked artifacts.

### Step 2 — Classify the task

Pick exactly one task class:

- **incident** — production stability, data integrity, live breakage
- **seo** — crawl, indexation, canonical, sitemap, hub structure
- **content opportunity** — new content to consider
- **content refresh** — existing content showing decay or drift
- **monetization** — ad, affiliate, commerce surface
- **technical** — stack, jobs, performance, filesystem, DB
- **governance** — policy, permission, disclosure
- **other** — only when nothing fits; requires justification

### Step 3 — Assign severity / priority

- Incidents: **sev-1** (sitewide / data loss), **sev-2** (significant surface), **sev-3** (single surface), **low** (cosmetic).
- Non-incidents: **urgent** (deadline-driven), **high**, **normal**, **low**.

### Step 4 — Identify the required corpus

Name the corpus the downstream agent will need (technical, content, pedagogy, SEO, monetization). Link specific files where obvious.

### Step 5 — Route

- **incident / technical** → Technical Health
- **seo** → SEO & Crawl
- **content opportunity / refresh** → Content Strategy
- **monetization** → Monetization & Merchandising
- **governance / risky write** → Governance & Security
- **evaluation / post-change review** → Analytics & Evaluation

Write the work item to `queues/triaged/` with the downstream pointer.

### Step 6 — Walk the checklist

Walk `checklists/review-checklist.md` before routing. Fix any gaps.

### Step 7 — Emit trace

Always emit a trace record with class, severity, routing, and rationale.

## Handling edge cases

- **Multi-class signal** — split into multiple work items, each with its own class and route. Do not send one blended item.
- **Permission ambiguity** — route to Governance & Security first for disambiguation, not to the domain agent.
- **Malformed or unclear signal** — do not invent detail. Write a structured clarification request and block until answered.
- **Recurring signal pattern** — record the pattern; after three occurrences, raise a routing-clarification memory via learning-promotion flow.

## Escalation

Escalate to Governance & Security when:

- permission to act is uncertain,
- the signal implies a risky multi-surface task,
- the constitutional scope is unclear,
- the signal requires a decision that sits above the agent's routing authority.

## Definition of Done

- Work item is typed (class + severity).
- Required corpus is named.
- Target queue and agent are named.
- Trace record is emitted.
- Checklist is walked.
