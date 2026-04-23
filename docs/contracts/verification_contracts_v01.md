# Verification Contracts v01

## Purpose

Define the minimum verification artifacts required before certain runs can be treated as complete.

## Verification principles

- verification is about observable behavior, not persuasive wording
- leaf work can use lighter checks than core work
- promotion and risky writes require stronger evidence than drafts

## Verification bundle

A `verification_bundle` should state:
- what was checked
- what passed
- what failed
- what remains uncertain
- whether the result is safe to approve, revise, or block

## Common verification types

- guardian review
- governance approval
- acceptance checks
- regression checks
- rollback readiness check
- trace completeness check

## Required cases

Use a verification bundle when:
- a risky write is requested
- a publish recommendation is made
- a cross-surface change may have regressions
- a pattern is being promoted into memory
- a run claims success after non-trivial execution
