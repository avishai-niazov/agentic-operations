# Planerium Agentic Operations Framework

A harness-driven, multi-agent operating system for Planerium's day-to-day technical health, search growth, content operations, and revenue optimization — with constitutional safeguards for **brand distinctiveness** and **pedagogical integrity**.

## Why this exists

Most agent projects are over-centered on generation. Planerium needs the opposite:

- a governed operating model rather than free-form autonomy
- narrow agents with explicit contracts
- typed handoffs instead of ad hoc agent chatter
- self-learning through traces and evaluation, not self-rewriting prompts
- self-healing through retries, quarantines, rollback, and escalation
- hard protection for what makes Planerium different:
  - its writing and printable style
  - its educational and pedagogical quality
  - its long-term bet on meaningful, hands-on learning

This framework is designed for a real production website and a one-person operator who wants leverage **without losing control**.

## Architecture at a glance

### 1) Constitutional layer
The highest authority in the system.

- Brand Constitution
- Pedagogical Charter
- Physical Learning Thesis
- Non-Negotiables
- Provenance and Disclosure Policy

### 2) Harness layer
The orchestration contract.

- runtime stages
- preflight checks
- read/write permissions
- validation gates
- refusal points
- invariant checks
- trace requirements
- rollback and escalation rules

### 3) Specialist agents

#### Operators
- Intake & Triage
- Technical Health
- SEO & Crawl
- Content Strategy
- Content Production
- Monetization & Merchandising
- Analytics & Evaluation

#### Guardians
- Brand Steward
- Pedagogical Steward
- Governance, Security & Approval

### 4) Memory and evaluation
The feedback system.

- traces
- approved patterns
- approved exemplars
- failures
- regressions
- drift cases
- scorecards
- promotion / rollback rules

## Design principles

1. **Identity before scale**  
   Planerium should not drift into generic AI content.

2. **Pedagogy before output volume**  
   Educational usefulness is a first-class constraint.

3. **Typed handoffs over free-form collaboration**  
   Agents communicate through contracts and queues.

4. **Evidence-based learning**  
   The system learns through trace review, scorecards, and approved memory writebacks.

5. **Controlled healing**  
   Retry, timeout, fallback, quarantine, resume, rollback, escalate.

6. **Human authority remains intact**  
   The system is designed to extend a human operator, not replace judgment.

## Core folders

- `docs/architecture/` — runtime model, interaction model, gate model
- `docs/governance/` — invariants, approvals, refusal rules, secrets policy
- `docs/contracts/` — tool contracts, handoff schemas, guardian review contracts
- `docs/evaluation/` — scorecards, traces, learning promotion, drift rules
- `knowledge/` — business, technical, SEO, content, corpora, memory
- `queues/` — task state transitions
- `runs/` — traces, reports, incidents, rollback candidates
- `.claude/skills/` — operational contracts per agent

## Suggested first implementation order

1. Read `knowledge/content/brand_constitution_v01.md`
2. Read `knowledge/content/pedagogical_charter_v01.md`
3. Read `HARNESS.md`
4. Read `docs/architecture/runtime_state_model_v02.md`
5. Read `docs/architecture/agent_interaction_matrix_v02.md`
6. Review each agent `SKILL.md`
7. Implement only one or two agents end-to-end before expanding

## What this framework is not

- not a promise of full autonomy
- not a generic “content machine”
- not a license for agents to rewrite their own rules
- not a replacement for editorial, pedagogical, or security judgment

## Version

- Initial repo scaffold created: 2026-04-22
- Architecture pack: v1
