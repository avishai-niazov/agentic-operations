# Tool Registry v02

## Purpose

Define which tool classes exist in the framework and what they are allowed to do.

## Tool classes

- analytics readers
- search console readers
- CMS readers
- CMS writers
- DB readers
- DB writers
- filesystem readers
- filesystem writers
- email readers
- email writers
- link and template validators
- monetization analyzers

## Rules

- Every tool must have a contract.
- Contracts must specify read/write level.
- High-risk tools require governance review before execution.
