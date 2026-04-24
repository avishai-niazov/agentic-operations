# Work Item — <item_id>

> Use this template for every Intake & Triage output. A work item without class, severity, or routing is not ready to leave this agent.

## Item metadata

- **Item id:** <id>
- **Source:** alert | email | search-console | analytics | manual | incident report | scheduled scan
- **Source reference:** <link, id, or path>
- **Timestamp:** <ISO datetime>
- **Triager:** <agent or operator>

## Raw signal

> Copy verbatim. Do not paraphrase.

```
<raw signal text>
```

## Classification

- **Task class:** incident | seo | content opportunity | content refresh | monetization | technical | governance | other
- **If "other," justification:** <one line>

## Severity / priority

- **Severity (incidents):** sev-1 | sev-2 | sev-3 | low | n/a
- **Priority (non-incidents):** urgent | high | normal | low | n/a
- **Rationale:** <one line>

## Scope

- **Surfaces implicated:** <pages, templates, systems, or "single page">
- **Cross-surface risk:** yes / no — <note if yes>
- **Sensitive-write implied:** yes / no

## Required corpus

- <list of corpora, policies, or knowledge files the downstream agent will need>

## Routing

- **Target agent:** <agent name>
- **Target queue:** `queues/triaged/<subpath>`
- **Downstream hint:** <one line to speed up downstream triage>

## Flags

- Permission ambiguity: yes / no — <note>
- Governance touch required: yes / no — <note>
- Multi-class: yes / no — <if yes, list split items>

## Trace

- Trace record at: <path under `runs/traces/`>

## Sign-off

- Triager: __________
- Checklist walked: yes / no
- Date: __________
