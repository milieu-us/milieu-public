# REFERENCE-AGENTS-000 - Agents - Foundational View

- **ID:** REFERENCE-AGENTS-000
- **Status:** Working Draft
- **Created:** 2026-04-11
- **Updated:** 2026-04-11

## Intent

Provide a foundational working view of agents in Milieu so that human agents, AI agents, and system agents can be treated as explicit actors in coordination, change, execution, validation, and continuity, without confusing agents with stakeholders, expressions, or governance authority.

## Context

Milieu already assumes that important work is carried out through agents.

Governance states that stakeholders act through human agents, AI agents, and system agents.

Experience assumes that agents may appear through runtime expressions such as performers, guides, storytellers, moderation systems, and memory systems.

Operations and repository workflows already rely on agents acting across multiple tools and working surfaces.

Current Milieu work is therefore not only about isolated agent tasks. It is increasingly about bounded ecosystems in which multiple agent types coordinate, validate, hand off, and learn together over time.

Without a shared founding view, these assumptions remain scattered across documents and are likely to be repeated inconsistently.

## Working View

An agent is a bounded actor that can receive context, interpret or transform it, take action within a scoped surface, and leave effects that may need to be observed, reviewed, or remembered.

Milieu currently recognizes at least three agent types:

- human agents
- AI agents
- system agents

These are not stakeholder classes.

They are ways action enters the system.

## Why Agents Need Explicit Treatment

Agents need explicit treatment because Milieu is not working with a single operator in a single tool.

Work is carried across conversations, records, repositories, local tools, runtime systems, and future operational surfaces.

Agents therefore matter not only for execution, but also for:

- coordination
- carried context
- authority and accountability
- observability
- validation
- memory and continuity

If agents are left implicit, Milieu will accumulate hidden assumptions about who acted, what context they had, what authority they were operating under, and how later agents should interpret the result.

## Initial Distinctions

### Stakeholder

A stakeholder is an entity with standing, interest, exposure, or accountability in relation to Milieu.

### Agent

An agent is the actor through which work is performed.

A stakeholder may act through one or more agents.

An agent may serve one or more bounded functions.

### Expression

An expression is how an agent appears within a specific domain or situation.

Examples include guide, performer, archivist, moderator, builder, or reviewer.

Expressions are contextual. They are not the same as stakeholder standing or agent type.

### System

A system is a bounded set of interacting elements.

A system may contain agents.

A system may also be treated as acting through a system agent when that helps clarify responsibility and observability.

## Relationships to Other Domains

### Institution

Institution defines authority, accountability, stewardship, and limits on agent action.

### Operations

Operations provides the surfaces, tools, environments, and controls through which agents act.

### Experience

Experience is where agents may appear in embodied, social, performative, or support expressions.

### Simulation

Simulation may define the world or model within which agents perceive, decide, or act.

### Records and Memory

Records preserve the context, lineage, and outcomes needed by later agents.

## Initial Principles

### Agents are explicit

Milieu should prefer naming the acting agent type when it matters.

### Agents are bounded

Agent scope, authority, and working surface should be bounded.

### Agents are observable

Meaningful actions and effects should leave inspectable traces where practical.

### Agents are accountable

Agent action should remain attributable to a responsible stakeholder, stewarded system, or defined authority surface.

### Agents carry context imperfectly

Agents should not be assumed to share the same context window, memory, or visibility.

Important context should be made explicit in shared artifacts.

### Agents participate in loops, not just tasks

Milieu needs collaboration loops, review loops, validation loops, and learning loops that include human agents, AI agents, and system agents.

## Working Findings

Current Milieu work suggests the following:

- agents are acting surfaces, not stakeholder classes
- agents do not share identical context, memory, or visibility
- durable shared artifacts are required for handoff and continuity
- multi-agent systems require explicit proposal, review, and acceptance paths
- agent systems must be understood across multiple dimensions, including governance, operations, change, validation, and memory
- collaboration loops and learning loops matter alongside review loops
- feedback from physical human work must be able to re-enter the shared system
- a minimal measurement vocabulary for agent work and value flows is already emerging

## What This Note Does Not Yet Define

This note does not yet define:

- identity and trust architecture
- authentication methods
- full permissioning model
- detailed workflow mechanics
- value accounting rules
- a final domain rename from Participation to Agents

## Consequences

Making agents explicit should help Milieu:

- reduce hidden context
- separate stakeholder standing from acting surfaces
- make change and review easier to reason about
- support mixed human, AI, and system workflows
- improve continuity across time and tools

It also creates pressure to define clearer identity, audit, and handoff patterns later.

## Open Questions

- Should AGENTS remain a foundational reference under Participation, or become the clearer domain name?
- What is the minimum identity and audit trail required for agent action?
- How should Milieu distinguish human agents, AI agents, and system agents in shared workflows without creating unnecessary overhead?
- Which agent actions require proposal and review, and which may be automatic?
- How should carried context be represented across conversations, repositories, and runtime systems?
- How should collaboration loops be represented distinctly from review loops?
- When does a system become clearer to describe as acting through a system agent rather than only as infrastructure?

## Related

- AGENTS.md
- REFERENCE-DOMAIN-000 - Milieu Domain Orientation Model
- DECISION-MILIEU-MVM-000 - Minimum Viable Milieu (MVM)
- DECISION-MVE-000 - Minimum Viable Experience (MVE) Stakeholder Expressions
- DECISION-OPERATIONS-CHANGE-000 - Change Proposals and Acceptance
- DECISION-OPERATIONS-CHANGE-001 - Git-Based Change Proposal Workflow
- REFERENCE-AGENTS-001 - Multi-Dimensional Agent Systems
- REF - Measurement Types for Agent Work and Value Flows
