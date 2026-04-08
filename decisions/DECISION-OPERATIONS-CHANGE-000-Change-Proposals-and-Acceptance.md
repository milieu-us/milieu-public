# DECISION-OPERATIONS-CHANGE-000 - Change Proposals and Acceptance

- **ID:** DECISION-OPERATIONS-CHANGE-000
- **Status:** Working Draft
- **Created:** 2026-04-07
- **Updated:** 2026-04-07

## Intent

Make the process of proposing, reviewing, and accepting change explicit for human agents, AI agents, and system agents.

Establish a shared model for how change enters and becomes part of the Milieu system.

## Context

Milieu artifacts such as `RECORD`, `DECISION`, `REFERENCE`, and related documents represent shared state.

These artifacts evolve over time through contributions from multiple agents operating across different contexts.

Without an explicit model for change, updates may be introduced implicitly, making it difficult to understand:

- what changed
- why it changed
- whether meaning or structure was affected
- how the change became accepted

Milieu already emphasizes explicit structure and observable context.

Change itself must follow the same principle.

## Decision

Changes to shared artifacts are introduced as proposals.

A proposal is an explicit description of a change that may affect one or more shared artifacts.

Proposals should include:

- what is changing
- why the change is being made
- whether the change affects meaning, structure, or only wording

Proposals should be reviewed before acceptance.

Acceptance incorporates the proposal into the shared state of the system.

Acceptance is a semantic act, not only a technical operation.

Agents should not introduce significant changes implicitly or without a proposal.

If the mechanism for proposing or accepting change is unclear, agents should surface that uncertainty rather than invent process.

## Consequences

This decision makes change explicit rather than implicit.

It creates a shared model for coordination across human agents, AI agents, and system agents.

It improves traceability of how shared artifacts evolve over time.

It separates the concept of change from any specific tool or implementation.

Specific mechanisms for implementing proposals and acceptance may be defined separately.

## Related

- `DECISION-RECORDS-000`
- `AGENTS.md`
- `README.md`