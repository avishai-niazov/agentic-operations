# Website Agentic Operations Framework

A harness-driven, multi-agent operating system for a real website's day-to-day technical health, search growth, content operations, and revenue optimization — with constitutional safeguards for **brand distinctiveness** and **pedagogical integrity**.

## Why this exists

Most agent projects are over-centered on generation. This framework takes the opposite approach:

- governed operations rather than free-form autonomy
- narrow agents with explicit contracts
- typed handoffs instead of ad hoc agent chatter
- verification before promotion or risky writes
- supervisor and critic loops that keep runs on track
- hard protection for what makes a website distinctive
- a leaf-vs-core change policy so AI speed does not quietly damage architecture

This framework is designed for a real production website and an operator who wants leverage **without losing control**.

## Architecture at a glance

### 1) Constitutional layer
The highest authority in the system.

- Brand Constitution
- Pedagogical Charter
- Physical Learning Thesis
- Non-Negotiables
- Provenance and Disclosure Policy

### 2) Supervisor layer
The harness is the runtime supervisor.

It owns:
- stage order
- preflight checks
- routing
- retry and halt rules
- guardian and safety gates
- critic checkpoint enforcement
- decision states
- trace completeness

### 3) Specialist agents

#### Operators
- Intake & Triage
- Technical Health
- SEO & Crawl
- Content Strategy
- Content Production
- Monetization & Merchandising

#### Guardians
- Brand Steward
- Pedagogical Steward
- Governance, Security & Approval

#### Critic / evaluation role
- Analytics & Evaluation

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
   The website should not drift into generic AI output.

2. **Pedagogy before output volume**  
   Educational usefulness is a first-class constraint where education is in scope.

3. **Typed handoffs over free-form collaboration**  
   Agents communicate through contracts and queues.

4. **Supervisor and critic loops are explicit**  
   The harness supervises; guardians and evaluation critique.

5. **Evidence-based learning**  
   The system learns through traces, scorecards, and approved writebacks.

6. **Leaf vs core safety**  
   AI can move faster on isolated leaf work than on core architecture and policy files.

7. **Human authority remains intact**  
   The system extends a human operator; it does not replace judgment.

## Core folders

- `docs/architecture/` — runtime model, interaction model, supervision model, gate model
- `docs/governance/` — invariants, approvals, refusal rules, change safety, secrets policy
- `docs/contracts/` — tool contracts, handoff schemas, guardian review contracts, verification contracts
- `docs/evaluation/` — scorecards, traces, learning promotion, drift rules, regression rules
- `knowledge/` — business, technical, SEO, content, corpora, memory
- `tests/acceptance/` — acceptance checks for verifiable behavior
- `tests/golden_cases/` — representative known-good cases and edge cases
- `queues/` — task state transitions
- `runs/` — traces, reports, incidents, rollback candidates
- `.claude/skills/` — operational contracts per agent

## Suggested first implementation order

1. Read `knowledge/content/brand_constitution_v01.md`
2. Read `knowledge/content/pedagogical_charter_v01.md`
3. Read `HARNESS.md`
4. Read `docs/architecture/supervision_and_feedback_model_v01.md`
5. Read `docs/governance/change_safety_policy_v01.md`
6. Read `docs/contracts/verification_contracts_v01.md`
7. Review each agent `SKILL.md`
8. Implement one end-to-end path before expanding

## What this framework is not

- not a promise of full autonomy
- not a generic “content machine”
- not a license for agents to rewrite their own rules
- not a replacement for editorial, pedagogical, or security judgment
- not an excuse to skip verification because AI was fast

## Version

- Initial scaffold: 2026-04-22
- Genericized and supervision / verification update: 2026-04-23
