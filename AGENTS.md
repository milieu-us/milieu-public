# AGENTS

## Intent

Make coordination assumptions explicit for agents working in this repository.

This file exists to reduce hidden context, especially when work is distributed across human agents, AI agents, and system agents.

Initial version drafted collaboratively by Chris at Milieu and Codex GPT-5.4 on 2026-04-02.

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

## Related

- [README.md](README.md)
- [decisions/DECISION-MILIEU-CORE-Foundational-Constraints.md](decisions/DECISION-MILIEU-CORE-Foundational-Constraints.md)
- [decisions/DECISION-MVM-000-Minimum-Viable-Milieu-(MVM).md](decisions/DECISION-MVM-000-Minimum-Viable-Milieu-(MVM).md)
- [decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md](decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md)
