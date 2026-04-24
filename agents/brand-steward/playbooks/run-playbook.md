# Run Playbook — Brand Steward

This playbook describes how to execute a Brand Steward review. It is a procedural companion to `.claude/skills/brand-steward/SKILL.md`.

## When to run

- brief review requested (upstream: Content Strategy)
- draft review requested (upstream: Content Production)
- drift investigation requested (upstream: Analytics & Evaluation or Governance)

## Pre-flight

1. Confirm the trigger type.
2. Open the artifact (brief or draft) and any referenced upstream context.
3. Open required reads: `brand_constitution_v01.md`, `non_negotiables_v01.md`, `voice_and_editorial_rules_v01.md`, and relevant items in `knowledge/corpora/brand/`.
4. Review a recent approved exemplar for comparison, if available.

## Step-by-step run

### Step 1 — Read for identity

Read the artifact once through, without note-taking, as a reader of the site. Ask:

- Does this sound like us or could it be anyone?
- What makes this distinctly ours? If nothing, that is the finding.

### Step 2 — Read for failure modes

Read again, with the checklist open, looking specifically for:

- **Genericity** — phrasing or structure that would read identically on a competitor site.
- **Filler** — content that adds length without adding value.
- **Competitor echo** — vocabulary, hook patterns, or framings imported from the market-intelligence corpus.
- **Claim integrity** — over-promising, vague expertise claims, unsupported authority signals.

### Step 3 — Decide the outcome

Choose exactly one:

- **Pass** — identity intact, no material issues.
- **Conditional** — small, specific fixes required; revision guidance fits in a short list.
- **Fail** — structural issues with voice, filler, or competitor-echo; the artifact must be redrafted, not patched.

### Step 4 — Write the output

Use `templates/output-template.md`. For every finding, include:

- the passage or structural element,
- the rule or constitution reference it violates,
- the concrete revision ask.

### Step 5 — Route and trace

- Route the outcome to the correct queue per `SKILL.md`.
- Emit a trace record.
- If the failure pattern is repeated across runs, write it to `knowledge/memory/brand_failures/`.

### Step 6 — Walk the checklist

Walk through `checklists/review-checklist.md` before signing off. Do not close the review if any item is unresolved.

## Handling edge cases

- **The artifact is excellent but slightly off-brand** — this is still a conditional, not a pass. Identity drift compounds.
- **The artifact is generic but factually strong** — fail. Factual strength is a pedagogy/technical win, not a brand win.
- **The artifact deliberately experiments with voice** — acceptable only if the brief explicitly authorized the experiment. Otherwise, fail.
- **Pressure to pass for volume reasons** — do not pass. Escalate instead.

## Escalation

Escalate to Governance & Security when:

- identity drift is repeated across multiple briefs or drafts,
- there is pressure (explicit or implicit) to weaken brand standards for scale, speed, or SEO opportunity,
- a brand finding conflicts with a monetization or search recommendation and the tradeoff is not clearly decided.

Escalation: write a decision request in `queues/awaiting_review/`, emit a trace, and hand off.

## Definition of Done

- The review outcome is explicit: pass / conditional / fail.
- Each finding is reasoned against a named rule or exemplar.
- The output is routed to the correct queue.
- A trace record is emitted.
- Repeat failure patterns, if any, are recorded in memory.
