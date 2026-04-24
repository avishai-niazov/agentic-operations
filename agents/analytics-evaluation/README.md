# Analytics & Evaluation — Agent Workspace

This folder is the local workspace for the **Analytics & Evaluation** agent. It holds the practical, runtime-facing assets that support the agent's day-to-day operation: review checklists, operating playbooks, and reusable output templates.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/analytics-evaluation/SKILL.md`

Treat `SKILL.md` as the source of truth. The assets in this workspace are support material; they must never contradict the SKILL file.

## What this workspace contains

- **`checklists/`** — review checklists the agent (or a reviewer) uses before, during, or after a run. Use these to verify the run meets validation rules and Definition of Done.
- **`playbooks/`** — step-by-step operating procedures for common run types (e.g., scoring a run, reviewing a trace, deciding on pattern promotion, recommending a rollback).
- **`templates/`** — reusable output formats (evaluation report, scorecard, learning-promotion decision, rollback recommendation).

## How the agent should use these assets

1. On trigger, consult `playbooks/run-playbook.md` for the operating procedure.
2. Before finalizing an output, walk through `checklists/review-checklist.md`.
3. Write the output using `templates/output-template.md` so results stay consistent and comparable across runs.
4. If a new pattern, scorecard format, or decision rule proves useful across multiple runs, raise it through the learning-promotion flow defined in `SKILL.md` rather than editing this workspace ad hoc.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not store production data, credentials, or run traces in this folder — traces belong in `runs/traces/` per the project structure.
- Keep files generic and reusable; avoid hard-coded project-specific references.
