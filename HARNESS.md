# HARNESS.md

## Purpose

The Harness is the orchestration contract for Website Agentic Operations.

It defines:
- stage order
- preflight checks
- read/write permissions
- validation gates
- critic checkpoints
- trace requirements
- refusal points
- retry, rollback, and escalation rules

The Harness is not a worker. It is the runtime supervisor.

## Supervisor responsibilities

The harness must:
- keep runs moving in the correct order
- stop agents from exceeding charter
- decide whether a failure should retry, revise, block, or escalate
- require verification artifacts before risky completion states
- keep audit trails complete enough for review and learning

## Runtime stages

1. **Preflight**
2. **Classification**
3. **Planning**
4. **Routing**
5. **Execution**
6. **Guardian validation**
7. **Safety validation**
8. **Critic evaluation**
9. **Decision**
10. **Writeback**
11. **Memory promotion or regression update**

## Preflight checklist

Before any run:
- confirm task type
- confirm required corpus
- confirm required skills
- confirm required permissions
- confirm whether the task is read-only or write-capable
- confirm whether brand or pedagogy are in scope
- confirm whether governance approval is required
- confirm what verification evidence will be required
- create run id

If preflight is incomplete, stop and record `preflight_failed`.

## Task classes

- `incident`
- `technical_maintenance`
- `seo_issue`
- `content_opportunity`
- `content_refresh`
- `content_generation`
- `monetization_test`
- `evaluation_request`
- `governance_review`

## Stage logic

### 1. Classification
The Intake & Triage Agent normalizes the signal into a typed work item.

### 2. Planning
A planner stage is required whenever the work is multi-step, risky, or cross-surface.

### 3. Routing
The harness routes the work item to the correct operator agent.

### 4. Execution
The assigned agent performs only work inside its charter.

### 5. Guardian validation
Required for content creation, refresh, structural content change, messaging change, or educational recommendation.

- Brand Check A: brief stage
- Pedagogy Check A: brief stage
- Brand Check B: draft stage
- Pedagogy Check B: draft stage

### 6. Safety validation
Run technical, SEO, monetization, and governance checks when relevant.

### 7. Critic evaluation
Guardians and Analytics & Evaluation act as critics.

Their job is to detect:
- unsupported claims
- drift from identity or pedagogy
- weak verification
- regressions
- unsafe promotion candidates

### 8. Decision
Possible outcomes:
- `approved`
- `approved_with_conditions`
- `blocked`
- `retry`
- `revise`
- `rollback_candidate`
- `escalate`

### 9. Writeback
Persist outputs to queue, report, memory, or incident log.

## Retry rules

Retry is allowed when:
- the contract was valid but execution was incomplete
- the failure is local and fixable
- verification revealed a repairable issue

Retry is not allowed when:
- the agent exceeded its charter
- a constitutional invariant was violated
- permissions are missing
- the same failure pattern repeated without new context

## Refusal points

The harness must refuse or block when:
- the wrong corpus is being used for the job
- an agent tries to exceed its charter
- content fails brand validation
- content fails pedagogy validation
- a risky write lacks governance approval
- a repeated regression pattern is detected without mitigation
- output quality is too low for publish or promotion
- required verification evidence is missing

## Invariant checks

Always verify:
- constitutional constraints preserved
- no unauthorized permissions used
- no output bypassed guardian gates
- trace record exists
- decision state recorded
- memory writebacks obey promotion policy
- core files were not changed under leaf-level rules

## Trace minimum

Every run must emit:
- run_id
- timestamp
- task_class
- initiating signal
- plan summary when planning was required
- agent assigned
- files and corpora read
- outputs written
- validations run
- verification bundle reference when required
- decision outcome
- escalations
- follow-up recommendations

## Self-healing controls

Allowed:
- retry with backoff
- timeout and fallback
- reopen failed task with more context
- quarantine bad output
- suggest rollback
- halt and escalate when invariant risk is high

Not allowed:
- silent rule changes
- agent self-redefinition
- automatic loosening of publish thresholds
- automatic permission expansion

## Definition of Done

A run is done only when:
- the task reached a stable end state
- all required validations were completed
- required verification evidence exists
- trace was written
- output was routed to the correct queue or report
- follow-up state is explicit
