# DECISION-OPERATIONS-CHANGE-001 - Git-Based Change Proposal Workflow

- **ID:** DECISION-OPERATIONS-CHANGE-001
- **Status:** Working Draft
- **Created:** 2026-04-07
- **Updated:** 2026-04-07

## Intent

Define how change proposals and acceptance are implemented using Git in this repository.

## Context

`DECISION-OPERATIONS-CHANGE-000` establishes that changes to shared artifacts are introduced as proposals and accepted explicitly.

This repository uses Git as the current system for managing shared artifacts.

Git provides a mechanism for proposals and acceptance through branches and pull requests.

## Decision

Changes to shared repository artifacts should be introduced through pull requests.

A pull request represents a change proposal.

Each proposal should:

- originate from a branch
- describe what changed
- describe why the change is being made
- indicate whether meaning, structure, or only wording is affected

Direct commits to shared branches such as `main` are not the default path for change.

Pull requests should be reviewed before being merged.

Merging a pull request represents acceptance of the proposal into the shared repository state.

Merge strategies should prefer preserving a clear and understandable history.

## Consequences

This decision provides a concrete implementation of change proposals using Git.

It aligns human agents, AI agents, and system agents on a shared workflow.

It reduces implicit changes and improves auditability.

It introduces a lightweight process overhead in exchange for clarity and coordination.

More specific rules for review, automation, or enforcement may be introduced later if needed.

## Related

- `DECISION-OPERATIONS-CHANGE-000`
- `AGENTS.md`
- `README.md`