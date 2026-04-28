# AGENTS

## Intent

Make coordination assumptions explicit for agents working in this repository.

This file exists to reduce hidden context, especially when work is distributed across human agents, AI agents, and system agents.

Initial version drafted collaboratively by Chris at Milieu and Codex GPT-5.4 on 2026-04-02.

### First Principle

Prismal Space does not exist to prove its axioms. It exists to provide adaptive spaces where working axioms are tested, refined, replaced, and made visible through play, observation, implementation, and shared review.

## Coordination Context

Milieu work may be orchestrated across multiple contexts and tools by a group of agents, including:

- human agents
- AI agents
- system agents

This repository is therefore one working surface within a broader collaboration, not necessarily the only place where related discussion or planning exists.

## Context Visibility Rule

Agents operating in this repository should assume they can rely only on context that is observable in one or more of the following places:

- the current conversation or task thread
- files present in this repository
- tools explicitly exposed in the current execution environment

Unless the execution environment explicitly exposes additional context, do not assume access to:

- ChatGPT Projects context
- chats outside the current thread
- saved memory
- private planning artifacts that are not present in this repository
- external systems or documents that have not been surfaced here

If important context may exist elsewhere, ask for it or request that it be added to the repository as an explicit artifact.

## Context Access and Source References

Follow [REFERENCE-AGENTS-002 - Carried Context (Working Concept)](references/REFERENCE-AGENTS-002-Carried-Context-Working-Concept.md) for context access and source reference expectations.

A task is not ready for agent execution unless the agent can inspect the sources required to reason about that task.

When an output depends on carried context, the agent must record the sources and refs used, including repository names and branch, commit, issue, pull request, file, or record identifiers where applicable.

Do not vendor upstream archives into downstream repositories as the default context-delivery mechanism. Prefer explicit repository access, links, refs, and source manifests.

## Working Assumption

When context is missing, prefer the following interpretation:

1. the context may exist elsewhere,
2. the current agent may not be able to see it,
3. missing context should be made explicit rather than inferred.

This follows Milieu's current foundational constraint:

- nothing unbounded
- nothing implicit
- nothing unobservable

## Practical Guidance

- Do not claim awareness of Project-level context unless it is visible in the current environment.
- Do not treat absence of context in this repository as evidence that no such context exists.
- When a decision depends on off-repo context, ask for that context or record the assumption being made.
- Prefer durable repository artifacts for information future agents will need.

## Record System Guidance

When creating or editing record artifacts in this repository, the Milieu record system is the normative source of truth:

- [records/RECORD-000-Milieu-Record-System.md](records/RECORD-000-Milieu-Record-System.md)
- [records/RECORD-001-Record-Types-and-Semantics.md](records/RECORD-001-Record-Types-and-Semantics.md)
- [records/RECORD-002-Current-Markdown-Representation-for-Records.md](records/RECORD-002-Current-Markdown-Representation-for-Records.md)

This guidance applies first to record artifacts such as `RECORD`, `DECISION`, and `REFERENCE` documents. Top-level coordination docs such as `README.md` and `AGENTS.md` should align where practical, but they are not themselves the full record spec.

When working on these artifacts:

- preserve the required metadata fields and ID consistency defined in `RECORD-000`
- use the appropriate record type semantics defined in `RECORD-001`
- preserve a first H1 that begins with the record ID
- preserve the current Markdown representation conventions defined in `RECORD-002`
- avoid inventing new structure when the existing record rules already cover the case

If classification or structure is unclear, surface the uncertainty rather than guessing.

Existing documents may reflect earlier conventions. Do not treat unrelated edits as a reason to silently normalize older records unless a mismatch directly blocks the requested work.

## Git Workflow Guidance

Agents contributing changes in this repository should assume the following local Git workflow:

- each person or agent context uses a fresh clone rather than copying an existing working tree
- each clone sets its own `git config --local user.name` and `git config --local user.email`
- effective identity should be checked before the first commit with `git config user.name`, `git config user.email`, and `git remote -v`
- prefer `git pull --ff-only` unless an intentional local merge is part of the task
- do not rely on hidden machine-local hooks or unpublished Git conventions

If hook-based checks are introduced later, they should be visible in the repository and described in the contributor-facing documentation.

## Related

- [README.md](README.md)
- [decisions/DECISION-MILIEU-CORE-Foundational-Constraints.md](decisions/DECISION-MILIEU-CORE-Foundational-Constraints.md)
- [decisions/DECISION-MVM-000-Minimum-Viable-Milieu-(MVM).md](decisions/DECISION-MVM-000-Minimum-Viable-Milieu-(MVM).md)
- [decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md](decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md)
