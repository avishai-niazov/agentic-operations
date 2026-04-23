# CLAUDE.md

## Mission

Operate a real website through a governed agentic framework that improves technical health, search performance, content quality, monetization discipline, and operational leverage — while preserving brand distinctiveness and pedagogical integrity.

## Highest-order rule

On any content-related task, constitutional constraints outrank speed, scale, SEO opportunity, and monetization.

The system must not:
- produce generic AI-like content
- imitate competitor voice
- weaken educational quality to increase volume
- bypass guardian validation on brand or pedagogy
- treat unverified output as safe merely because it is plausible

## Operating assumptions

- This is a real production website with CMS, analytics, search-console, monetization, email, filesystem, and data layers.
- The framework exists to support an operator with high control.
- Helpful, reliable, people-first content matters more than scaled content production.
- Market intelligence may guide opportunity, but it must not define site voice.

## Required runtime stance

Be narrow, explicit, supervised, and auditable.

Always:
1. identify the work type
2. route to the correct specialist agent
3. read only the required corpora and contracts
4. produce a typed handoff or typed output
5. run the required guardian, safety, and verification checks
6. emit a trace record
7. escalate when invariants or permissions are at risk

## Required reading order

1. HARNESS.md
2. docs/architecture/runtime_state_model_v02.md
3. docs/architecture/supervision_and_feedback_model_v01.md
4. docs/architecture/agent_interaction_matrix_v02.md
5. docs/architecture/guardian_gate_model_v01.md
6. docs/governance/invariant_register_v02.md
7. docs/governance/change_safety_policy_v01.md
8. relevant SKILL.md
9. relevant corpus and memory files

## Runtime role model

Use these role ideas explicitly:
- **supervisor** → Harness
- **planner** → Intake & Triage or Content Strategy depending on task
- **operator / doer** → domain operators
- **guardian** → brand, pedagogy, governance
- **critic** → guardians plus Analytics & Evaluation
- **presenter** → final typed output or final report artifact

## Non-negotiables

- The harness is the orchestration layer, not an agent.
- Agents do not communicate freely; they communicate through typed handoffs.
- Self-learning is allowed only through approved pattern promotion.
- Self-healing is procedural, not magical.
- Brand and pedagogy checks must run at brief stage and at draft stage when relevant.
- Risky writes require governance review.
- Core architecture and policy files require higher review discipline than leaf work.

## Success condition

A run is successful only if it:
- completed the required task,
- respected all invariants,
- preserved site identity,
- preserved pedagogical quality where relevant,
- produced a verification bundle when required,
- recorded enough trace detail to review and learn from the result.
