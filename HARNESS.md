# HARNESS.md

## Purpose

The Harness is the orchestration contract for Planerium Agentic Operations.

It defines:
- stage order
- preflight checks
- read/write permissions
- validation gates
- trace requirements
- refusal points
- rollback and escalation rules

The Harness is not a worker. It is the execution and governance layer that coordinates workers.

## Runtime stages

1. **Preflight**
2. **Classification**
3. **Routing**
4. **Execution**
5. **Guardian validation**
6. **Safety validation**
7. **Decision**
8. **Writeback**
9. **Evaluation**
10. **Memory promotion or regression update**

## Preflight checklist

Before any run:
- confirm task type
- confirm required corpus
- confirm required skills
- confirm required permissions
- confirm whether the task is read-only or write-capable
- confirm whether brand or pedagogy are in scope
- confirm whether governance approval is required
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

### 2. Routing
The harness routes the work item to the correct operator agent.

### 3. Execution
The assigned agent performs only work inside its charter.

### 4. Guardian validation
Required for all content creation, refresh, structural content change, messaging change, or educational recommendation.

- Brand Check A: brief stage
- Pedagogy Check A: brief stage
- Brand Check B: draft stage
- Pedagogy Check B: draft stage

### 5. Safety validation
Run technical, SEO, monetization, and governance checks when relevant.

### 6. Decision
Possible outcomes:
- `approved`
- `approved_with_conditions`
- `blocked`
- `retry`
- `rollback_candidate`
- `escalate`

### 7. Writeback
Persist outputs to queue, report, memory, or incident log.

### 8. Evaluation
Analytics & Evaluation scores the run if applicable.

## Refusal points

The harness must refuse or block when:
- the wrong corpus is being used for the job
- an agent tries to exceed its charter
- content fails brand validation
- content fails pedagogy validation
- a risky write lacks governance approval
- a repeated regression pattern is detected without mitigation
- output quality is too low for publish or promotion

## Invariant checks

Always verify:
- constitutional constraints preserved
- no unauthorized permissions used
- no output bypassed guardian gates
- trace record exists
- decision state recorded
- memory writebacks obey promotion policy

## Trace minimum

Every run must emit:
- run_id
- timestamp
- task_class
- initiating signal
- agent assigned
- files and corpora read
- outputs written
- validations run
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
- trace was written
- output was routed to the correct queue or report
- follow-up state is explicit
