# Pedagogical Steward — Agent Workspace

This folder is the local workspace for the **Pedagogical Steward** agent. It holds the practical assets that support pedagogy review runs: review checklists, operating playbooks, and reusable output templates.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/pedagogical-steward/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklist for judging briefs and drafts on learning goal clarity, audience fit, meaningfulness, and teacher usability.
- **`playbooks/`** — step-by-step procedures for pedagogy brief review, pedagogy draft review, and pedagogical drift investigation.
- **`templates/`** — reusable output format for pedagogy review outcomes with explicit educational reasoning.

## How the agent should use these assets

1. On trigger, consult `playbooks/run-playbook.md`.
2. Review the artifact against `checklists/review-checklist.md`.
3. Write the outcome using `templates/output-template.md`.
4. Record recurring failure patterns in `knowledge/memory/pedagogy_failures/` via the learning-promotion flow.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not rewrite constitutional files (`pedagogical_charter_v01.md`, `physical_learning_thesis_v01.md`).
- Do not write final content — Content Production owns drafts.
- Keep files generic and reusable.
