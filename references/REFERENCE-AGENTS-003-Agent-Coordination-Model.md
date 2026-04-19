# REFERENCE-AGENTS-003 — Agent Coordination Model

- **ID:** REFERENCE-AGENTS-003
- **Status:** Working Draft
- **Created:** 2026-04-19
- **Updated:** 2026-04-19

## Intent

Capture the working coordination model for how human agents, AI agents, and system agents move through the Milieu artifact states together.

This reference sits alongside REFERENCE-AGENTS-001 (which describes the dimensions of an agentic ecosystem) and adds the practical coordination layer: how agents actually refine shared understanding across artifact states, what the acceptance gate means, and when system agents emerge.

## Core Framing

Milieu artifacts — RESOURCE, DECISION, ARCHITECTURE, code — are not pipeline deliverables passed between specialists.

They are **states of shared understanding**.

Any agent type can contribute to any artifact state. What changes across states is what kind of understanding is being refined, not which agent class is permitted to act.

The actual distribution of work at any moment reflects current capability, not fixed role assignment. Today an AI agent may draft the bulk of an ARCHITECTURE document because that is where it can contribute most. A human agent may catch a constraint the AI missed. A system agent may enforce a boundary the build system understands and no one thought to specify explicitly. Tomorrow those distributions may shift.

## Artifact States

These are the current states of understanding in the Milieu record system. They are named after the record types that carry them.

### Proposal (RESOURCE, Issue, or informal artifact)

A need, observation, or idea that has not yet been refined into a shared commitment.

The proposal state exists to surface something worth refining. It does not require a specific record type. A GitHub Issue, a REFERENCE document, a conversation thread, or a quick note may all carry a proposal.

What must survive this state:
- what is being observed or proposed
- who has standing over it
- known constraints arriving with it
- pointers to related existing records

### DECISION

The state in which impacted stakeholders have refined a proposal into a shared commitment: what will be done and why, including what was explicitly left out.

A DECISION is not authored by the agent that implements it. It is accepted by the agents with standing over the problem. The authoring agent (human, AI, or system) may produce the draft; acceptance is the act that matters.

What must survive this state:
- the reasoning, not just the conclusion
- the constraints that propagate forward
- what was weighed and set aside
- which version was accepted and when

### ARCHITECTURE

The state in which the accepted commitment is translated into technical constraints and background sufficient for any agent to begin building without reconstructing intent.

ARCHITECTURE documents are the primary context carrier for agents beginning implementation work. If an agent cannot observe the relevant ARCHITECTURE document, it should ask for it rather than invent its own constraints.

What must survive this state:
- the DECISION it implements (explicit relationship)
- module or structural boundaries
- what is host-specific versus genuinely general
- open questions that remain unresolved

### Code

The state in which something actually exists and runs.

Code is not the end of the loop. Observations from code — build results, test outcomes, unexpected behaviors — feed back into ARCHITECTURE and DECISION. The loop is continuous.

What must survive this state:
- which context versions (DECISION, ARCHITECTURE) the code was built against
- what was tried and why
- build and test results as evidence
- open questions the code revealed

## The Loops Are Tight

These states are not phases with handoffs between them. They are positions an artifact can occupy, and agents move artifacts between positions continuously.

The loop may run in seconds. An observation during a build may immediately refine an ARCHITECTURE constraint. A constraint in an ARCHITECTURE document may immediately prompt a revision to a DECISION. An agent may skip states in either direction.

All agents are expected to refine as they go. The record system provides structure; it does not impose process latency.

## The Acceptance Gate

Before a change enters the shared carrier (currently: merge to main in a public repo), it passes through an acceptance gate.

The acceptance gate is not supervision. It is a legibility checkpoint: is this change reviewable and understandable by any agent in the ecosystem, not just the agent that made it?

The current mechanism is a pull request reviewed by at least one other agent before merge. The reviewer may be human, AI, or system. What matters is that the change is legible to someone other than its author.

The gate exists because the shared carrier is a context distribution surface. A change that enters it propagates to every downstream consumer. Legibility before merge is how downstream agents stay coherent.

## When System Agents Emerge

A system agent is a crystallized learned pattern.

The right time to introduce a system agent is after the pattern has been performed manually enough times — by human or AI agents — that:

1. the task is well understood
2. the task is still the simplest answer
3. scripting it reduces friction without hiding meaning

System agents should not be written in anticipation of a need. They should emerge from demonstrated patterns. An update script, a CI check, a build rule — these are system agents. They exist because the pattern they encode has been validated through use.

This is not a rule against automation. It is a rule against premature crystallization. A Rube Goldberg machine of automated steps that no agent fully understands is worse than a manual step that is visible and correctable.

## What This Model Does Not Encode

This model does not encode:

- which agent type performs which task (that is capability-dependent and will shift)
- a fixed sequence that must be followed (artifacts move between states in any direction)
- a supervision hierarchy (all agents think, do, and teach to the best of their current capability)
- a permanent carrier (Git is today's carrier; the coordination model applies regardless of carrier)

## Consequences

This model suggests that Milieu should evaluate its agent ecosystem not by asking whether the right specialist performed the right task, but by asking:

- can any agent entering this state understand what came before?
- can any agent observing this change understand what was accepted and why?
- are system agents emerging from learned patterns, or being constructed in anticipation?
- are the loops tight enough that refinement is continuous rather than episodic?

## Open Questions

- Which artifact states are currently most fragile under this model?
- How should the coordination model be expressed when the carrier is not Git?
- When a loop runs fast enough that intermediate artifact states are not explicitly recorded, what is the minimum trace that should be preserved?
- How does this model interact with the context distribution question raised in REFERENCE-AGENTS-004 (milieu-public as a context distribution service)?

## Related

- REFERENCE-AGENTS-000 — Agents Foundational View
- REFERENCE-AGENTS-001 — Multi-Dimensional Agent Systems
- REFERENCE-AGENTS-002 — Carried Context Working Concept
- AGENTS.md
- RECORD-001 — Record Types and Semantics
