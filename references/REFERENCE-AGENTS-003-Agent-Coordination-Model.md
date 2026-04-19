# REFERENCE-AGENTS-003 — Agent Coordination Model

- **ID:** REFERENCE-AGENTS-003
- **Status:** Working Draft
- **Created:** 2026-04-19
- **Updated:** 2026-04-19

## Intent

Capture the working coordination model for how human agents, AI agents, and system agents refine shared understanding together.

This reference sits alongside REFERENCE-AGENTS-001 (which describes the dimensions of an agentic ecosystem) and adds the practical coordination layer: how artifacts move across surfaces, what gates mean, and when system agents emerge.

## Core Framing

Milieu artifacts are not pipeline deliverables passed between specialists.

They are shared artifacts that may be refined by any agent type.

What changes over time is not which class of agent is allowed to act. What changes is:

- the role the artifact is currently playing
- the surface on which it is exposed
- the audience that can observe or act on it
- what that audience has consented to receive

The actual distribution of work at any moment reflects current capability, not fixed role assignment. Today an AI agent may draft the bulk of an ARCHITECTURE document because that is where it can contribute most. A human agent may catch a constraint the AI missed. A system agent may enforce a boundary the build system understands and no one thought to specify explicitly. Tomorrow those distributions may shift.

## Artifacts, Surfaces, and Gates

### Artifact

An artifact is anything that carries meaning or behavior in the ecosystem.

Examples include documents, code, scripts, configuration, feature flags, tests, notes, issues, and observations from running systems.

### Surface

A surface is the context in which an artifact is exposed.

A surface determines:

- who can observe it
- who can refine it
- how directly they can act on it
- what level of ambiguity, incompleteness, or breakage they have consented to receive

A working branch, an issue thread, a private test harness, a shared reference repository, and a public release are different surfaces.

### Gate

A gate is the point at which an artifact moves to a new surface or becomes visible to a new audience.

The purpose of a gate is not supervision. The purpose of a gate is to make the transition explicit before new agents inherit the artifact.

A pull request merge, a feature flag change, a publication step, or an invitation to an internal alpha group can all function as gates.

## Record Roles Within This Model

The Milieu record system still matters. REFERENCE, DECISION, and ARCHITECTURE are not being discarded.

In this model, they are understood as specialized artifact roles with distinct semantics, not as a strict pipeline with handoffs.

### Proposal

A need, observation, or idea that has not yet been refined into a shared commitment.

A proposal does not require a specific record type. A GitHub Issue, a REFERENCE document, a conversation thread, a test result, or a quick note may all carry a proposal.

What must survive this role:

- what is being observed or proposed
- who has standing over it
- known constraints arriving with it
- pointers to related existing records

### DECISION

The role in which impacted stakeholders refine a proposal into a shared commitment: what will be done and why, including what was explicitly left out.

A DECISION is not defined by who authored the draft. It is defined by acceptance from the agents with standing over the problem.

What must survive this role:

- the reasoning, not just the conclusion
- the constraints that propagate forward
- what was weighed and set aside
- which version was accepted and when

### ARCHITECTURE

The role in which an accepted commitment is translated into structural and technical constraints sufficient for agents to begin implementation without reconstructing intent.

ARCHITECTURE artifacts are often the primary carried context for implementation work. If an agent cannot observe the relevant ARCHITECTURE artifact, it should ask for it rather than invent its own constraints.

What must survive this role:

- the DECISION it implements
- module or structural boundaries
- what is host-specific versus genuinely general
- open questions that remain unresolved

### Implementation

The role in which behavior actually exists and can be exercised.

Implementation may be code, scripts, data transformations, feature flags, configuration, or other executable artifacts.

Implementation is not automatically final or public. It may exist on a working surface, an internal surface, or a broader exposure surface depending on what audience has consented to receive.

What must survive this role:

- which context versions (REFERENCE, DECISION, ARCHITECTURE, or equivalent) it was built against
- what was tried and why
- test or observation results as evidence
- open questions the implementation revealed

## The Loops Are Tight

These roles are not fixed phases with handoffs between them.

Artifacts may move between roles and surfaces continuously. A build result may immediately refine ARCHITECTURE. A newly observed constraint may immediately refine DECISION. A discussion in a working surface may become REFERENCE. An implementation artifact behind a feature flag may still be serving a working function.

The loop may run in seconds. The record system provides structure; it does not impose process latency.

## Working Surfaces and Consent

A working surface is a surface where participants have knowingly consented to receive ambiguity, incompleteness, and possible breakage in exchange for tighter collaborative loops.

That consent matters.

A change that is acceptable on a working surface may be unacceptable on a broader shared surface. The difference is not the artifact itself. The difference is what the audience on that surface has agreed to receive.

This is why the same underlying process appears across documents, code, and experiences. The coordination question is not only what the artifact is. The coordination question is where it is exposed, to whom, and under what understood conditions.

## The Acceptance Gate

Before a change enters a broader shared carrier, it passes through an acceptance gate.

The acceptance gate is not supervision. It is a legibility and consent checkpoint:

- is this change understandable by agents other than its author?
- are the conditions of exposure appropriate for the next audience?
- is the transition explicit enough that downstream agents remain coherent?

Today the most visible acceptance gate is often a pull request reviewed before merge. That is one gate form, not the model itself.

A feature flag rollout, a documented promotion from working branch to shared reference, or publication to a downstream context consumer can also be acceptance gates.

## When System Agents Emerge

A system agent is a crystallized learned pattern.

The right time to introduce a system agent is after a pattern has been performed manually enough times — by human agents or AI agents — that:

1. the pattern is well understood
2. it is still the simplest answer
3. scripting it reduces friction without hiding meaning

System agents should not be written in anticipation of a need. They should emerge from demonstrated patterns.

An update script, a continuous integration check, a build rule, or a context synchronization tool are all examples of system agents when they encode a pattern that has already proved useful.

This is not a rule against automation. It is a rule against premature crystallization. A Rube Goldberg machine of automated steps that no agent fully understands is worse than a manual step that is visible and correctable.

## What This Model Does Not Encode

This model does not encode:

- which agent type performs which task
- a fixed sequence that must be followed
- a supervision hierarchy
- a permanent carrier
- a requirement that Git be the long-term coordination substrate

## Consequences

This model suggests that Milieu should evaluate its agent ecosystem not by asking whether the right specialist performed the right task, but by asking:

- can any agent entering this surface understand what came before?
- can any agent observing this change understand what was accepted and why?
- are the conditions of exposure explicit enough for the next audience?
- are system agents emerging from learned patterns, or being constructed in anticipation?
- are the loops tight enough that refinement is continuous rather than episodic?

## Open Questions

- Which surfaces are currently most fragile under this model?
- What minimum trace should be preserved when loops run too fast to record every intermediate step?
- How should consent and exposure be signaled when the carrier is not Git?
- How does this model interact with the context publishing question raised in REFERENCE-AGENTS-004?

## Related

- REFERENCE-AGENTS-000 — Agents Foundational View
- REFERENCE-AGENTS-001 — Multi-Dimensional Agent Systems
- REFERENCE-AGENTS-002 — Carried Context Working Concept
- AGENTS.md
- RECORD-001 — Record Types and Semantics
