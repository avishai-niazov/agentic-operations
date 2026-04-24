# Technical Health — Agent Workspace

This folder is the local workspace for the **Technical Health** agent. It holds the practical assets that support incident diagnosis, rollback recommendations, and technical maintenance proposals.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/technical-health/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklist covering diagnosis discipline, rollback readiness, and approval routing for sensitive writes.
- **`playbooks/`** — step-by-step procedures for incident handling, scheduled health checks, performance regressions, and technical publish safety checks.
- **`templates/`** — reusable incident / maintenance report template covering diagnosis, risk, rollback, and next action.

## How the agent should use these assets

1. On trigger (incident, scheduled check, performance regression, publish check), consult `playbooks/run-playbook.md`.
2. Produce the report using `templates/output-template.md`.
3. Walk `checklists/review-checklist.md` before routing.
4. Request Governance & Security approval for any production write; emit a trace for every run.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not publish content, change brand or pedagogy rules, or approve risky production writes unilaterally.
- Do not perform silent DB cleanup or unapproved production writes.
- Keep files generic and reusable.
