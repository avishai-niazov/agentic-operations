# Change Log — 2026-04-23

## What changed

### 1. Genericized public wording
- Replaced project-specific branding references with generic website-oriented language.
- Renamed `knowledge/business/website_business_model_v01.md` from the previous project-specific business-model filename.
- Updated public overview, LinkedIn summary, push instructions, and architecture HTML title/text.
- Removed the `.git` directory from the downloadable package so old repo identity and remote history are not carried over.

### 2. Added explicit supervision and critic model
- Updated `README.md`, `CLAUDE.md`, and `HARNESS.md` to make the supervisor role explicit.
- Added `docs/architecture/supervision_and_feedback_model_v01.md`.
- Clarified planner / operator / guardian / critic / presenter role mapping.

### 3. Strengthened verification discipline
- Added `docs/contracts/verification_contracts_v01.md`.
- Added `verification_bundle` to handoff and contract docs.
- Updated Definition of Done, trace contract, scorecard, and regression guidance.

### 4. Added leaf-vs-core change safety
- Added `docs/governance/change_safety_policy_v01.md`.
- Updated governance and invariant docs to reflect stronger review requirements for core work.

### 5. Tightened agent skill contracts
- Rewrote all `.claude/skills/*/SKILL.md` files to include:
  - runtime role
  - required inputs
  - required output artifacts
  - supervisor expectations
  - retry conditions
  - escalation conditions

### 6. Added verification scaffolding
- Added `tests/acceptance/README.md`
- Added `tests/golden_cases/README.md`

## Why
These changes align the framework more closely with the reviewed transcript ideas:
- explicit supervision
- explicit feedback / critic loops
- stronger verification before claiming success
- safer AI use on leaf work than on core architecture
