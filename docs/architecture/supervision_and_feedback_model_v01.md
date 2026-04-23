# Supervision and Feedback Model v01

## Purpose

Make supervision, critique, and learning loops explicit instead of implied.

## Core idea

A useful multi-agent system is not just planners and doers.
It also needs:
- a **supervisor** that keeps work inside the rules
- **guardians** that block identity or pedagogy drift
- a **critic** that evaluates outcomes and learning eligibility

## Runtime role split

### Supervisor
The Harness supervises the run.

It decides:
- whether the run is ready to start
- whether planning is required
- whether an error should retry, revise, block, or escalate
- whether the result has enough verification to be considered done

### Guardians
Brand, pedagogy, and governance agents protect quality boundaries.

They answer:
- does this fit identity?
- does this preserve educational value?
- is this permission-safe?

### Critic
Analytics & Evaluation acts as the critic after execution.

It answers:
- did the run actually help?
- should this pattern be promoted?
- did a regression or drift signal appear?

## Feedback loop

Signal → plan → execute → guardian check → safety check → critic review → decision → learn or regress

## Why this matters

Without explicit supervision:
- retries become noisy
- agents exceed charter
- weak drafts move too far downstream
- learning writebacks become untrustworthy

Without explicit critic loops:
- the system rewards speed over correctness
- traffic can incorrectly outweigh quality
- regression memory stays weak

## Required artifacts

- plan summary when work is multi-step
- guardian review artifact when content or messaging is in scope
- verification bundle when safety or publishability matters
- evaluation scorecard before learning promotion
