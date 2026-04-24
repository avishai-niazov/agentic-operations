# Brand Steward — Agent Workspace

This folder is the local workspace for the **Brand Steward** agent. It holds the practical assets that support brand review runs: review checklists, operating playbooks, and reusable output templates.

## Where the operating contract lives

The authoritative definition of this agent — its mission, inputs, outputs, validation rules, trigger conditions, and Definition of Done — lives in:

- `.claude/skills/brand-steward/SKILL.md`

Treat `SKILL.md` as the source of truth. Everything in this workspace is support material and must never contradict it.

## What this workspace contains

- **`checklists/`** — review checklists used when judging briefs and drafts against brand and voice rules.
- **`playbooks/`** — step-by-step procedures for brand brief review, brand draft review, and identity-drift investigation.
- **`templates/`** — reusable output formats for brand review outcomes (pass / conditional / fail) with explicit reasons.

## How the agent should use these assets

1. On trigger, consult `playbooks/run-playbook.md`.
2. Review the artifact against the checklist in `checklists/review-checklist.md`.
3. Write the outcome using `templates/output-template.md`, routed to the correct queue per `SKILL.md`.
4. Surface patterns of repeated failure into `knowledge/memory/brand_failures/` via the learning-promotion flow in `SKILL.md`.

## Boundaries of this workspace

- Do not duplicate the operating contract from `SKILL.md` here.
- Do not use this workspace to rewrite constitutional files (`brand_constitution_v01.md`, `voice_and_editorial_rules_v01.md`, `non_negotiables_v01.md`) — those changes belong to governance.
- Keep files generic and reusable; speak in terms of brand voice and identity rather than any single product name.
