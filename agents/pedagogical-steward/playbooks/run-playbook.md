# Run Playbook — Pedagogical Steward

This playbook describes how to execute a Pedagogical Steward review. It is a procedural companion to `.claude/skills/pedagogical-steward/SKILL.md`.

## When to run

- brief review requested (upstream: Content Strategy)
- draft review requested (upstream: Content Production)
- drift investigation requested (upstream: Analytics & Evaluation or Governance)

## Pre-flight

1. Confirm the trigger type.
2. Open the artifact (brief or draft) and any referenced upstream context.
3. Open required reads: `pedagogical_charter_v01.md`, `physical_learning_thesis_v01.md`, `activity_design_patterns_v01.md`, and relevant items in `knowledge/corpora/pedagogy/`.

## Step-by-step run

### Step 1 — Read as the target learner

Read once as the named audience. If you can't imagine the audience reading this, the audience isn't specific enough — flag it as a finding.

### Step 2 — Read for learning value

Read again with the checklist open. Ask:

- Is the learning goal clear and reader-facing?
- Does the content actually teach, or does it only inform?
- Could a teacher use this tomorrow?
- Is anything busywork dressed up as learning?
- Are pedagogical claims honest?

### Step 3 — Decide the outcome

Choose exactly one:

- **Pass** — learning value intact, audience fit strong, no material issues.
- **Conditional** — specific educational fixes required (not rewrites).
- **Fail** — learning goal unclear, audience mismatch, busywork, or educational overreach.

### Step 4 — Write the output

Use `templates/output-template.md`. For every finding, include:

- the passage or design element,
- the pedagogical rule or charter reference it violates,
- the concrete revision ask.

### Step 5 — Route and trace

- Route the outcome to the correct queue per `SKILL.md`.
- Emit a trace record.
- Record repeated failure patterns in `knowledge/memory/pedagogy_failures/`.

### Step 6 — Walk the checklist

Walk `checklists/review-checklist.md` before signing off.

## Handling edge cases

- **Content is engaging but teaches little** — fail. Engagement without learning is not our standard.
- **Content is rigorous but dry for the audience** — conditional. Ask for accessibility work without diluting rigor.
- **Activity is novel but educationally weak** — fail. Novelty is not pedagogy.
- **Pressure to loosen standards for volume** — do not pass. Escalate.

## Escalation

Escalate to Governance & Security when:

- educational claims feel weak or misleading,
- busywork drift is repeated across briefs or drafts,
- there is pressure to loosen pedagogy standards for speed or scale.

Escalation: write a decision request in `queues/awaiting_review/`, emit a trace, and hand off.

## Definition of Done

- The review outcome is explicit: pass / conditional / fail.
- Each finding is reasoned against a named pedagogical rule or charter.
- The output is routed to the correct queue.
- A trace record is emitted.
- Repeat failure patterns, if any, are recorded in memory.
