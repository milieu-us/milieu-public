# REFERENCE-AGENTS-002 — Carried Context (Working Concept)

ID: REFERENCE-AGENTS-002
Status: Working Draft
Created: 2026-04-11
Updated: 2026-04-19

## Intent

Provide a shared working concept for the minimum portable continuity another agent needs to continue an initiative or slice of work well.

This reference exists to help human agents, AI agents, and system agents preserve continuity across fragmented tools, activities, and artifacts without assuming any single platform, interface, or representation is the permanent home of meaning.

## Summary

Carried Context is the minimum portable continuity another agent needs to continue the work well.

Context is what must survive.  
Carriers are how it travels.  
Activities are what change it.

## Context

Milieu work already spans multiple agents, tools, and representations. Important continuity is frequently fragmented across chat systems, repositories, development environments, build outputs, screenshots, videos, observations, and human memory.

When context is trapped inside one tool, one agent, or one representation, coordination degrades. Work slows, misunderstandings increase, and later agents must reconstruct intent, constraints, and relationships that were already known.

Carried Context is a working concept for reducing that fragmentation without prematurely standardizing a single platform, interface, or storage model.

## Why This Belongs in Agents

This concept is currently scoped to the Agents domain because it is framed around what another agent needs in order to continue work well.

The immediate concern is cross-agent continuity:

- handoff between human agents
- handoff between AI agents
- handoff between system agents
- continuity across mixed-agent collaboration

This reference does not yet claim that Carried Context is a Milieu-wide foundational concern, though later evidence may support a broader Milieu-level reference.

## Core Distinctions

### Context

The relevant understanding needed to continue work well.

Context may include intent, constraints, observations, relationships, artifacts, unresolved questions, and current activity.

### Carrier

Any artifact, system, medium, or view that holds or expresses some of that context.

A carrier may be textual, visual, structured, executable, or otherwise embodied in a system.

Examples may include a record, pull request, chat thread, test harness, map, build artifact, screenshot, session log, or repository.

### Activity

What agents are actually doing.

Examples include exploring, deciding, designing, building, running, playtesting, observing, and learning.

Activities change context over time. Carriers help preserve enough of that changing context for later continuation.

## Working Definition

Carried Context is the minimum portable continuity required for another agent to continue an initiative or slice of work well.

This definition is intentionally minimal.

It does not require that all context be captured.

It does require that enough context be carried forward to avoid avoidable confusion, repeated effort, and loss of intent.

## Design Principles

### Portability

Carried Context should remain portable across platforms, tools, and agent types.

No single platform should be assumed to be the permanent or complete home of meaning.

### Minimum Sufficient Continuity

Carried Context should preserve what another agent needs to continue well, not attempt to restate everything known.

### Multi-Representation

Text is only one carrier.

Relevant context may also be carried by code, configuration, measurements, screenshots, video, runtime state, maps, harnesses, or other artifacts.

### Relationship Awareness

Carried Context should preserve not only artifacts, but important relationships between them.

Examples include:

- this observation came from this build
- this build used this configuration
- this map was created to test this idea
- this decision constrained this implementation

### Agent Equality

Carried Context should be legible and useful to human agents, AI agents, and system agents alike.

## Context Access and Source References

A task is not ready for agent execution unless the agent can inspect the sources required to reason about that task.

Agents should be given explicit, permissioned access to the repositories, archives, issues, pull requests, branches, commits, files, records, or other carriers that the task depends on.

When an output depends on carried context, the agent must record the sources and refs used, including repository names and branch, commit, issue, pull request, file, or record identifiers where applicable.

Do not vendor upstream archives into downstream repositories as the default context-delivery mechanism. Prefer explicit repository access, links, refs, and source manifests. Vendored snapshots are appropriate only when the snapshot itself is the artifact under review, test, or preservation.

## Minimum Useful Contents

The exact form may vary by carrier, but Carried Context usually needs to preserve at least:

- what we are trying to do
- why this work exists
- what currently constrains it
- what artifacts matter
- what has been tried
- what has been observed
- what remains unresolved
- what should likely happen next

## What Carried Context Is Not

Carried Context is not:

- just a chat thread
- just a record
- just a repository
- just a task tracker
- just text
- just a summary

A given carrier may hold some of the context, but the concept is broader than any single carrier.

## Early Implications

This concept suggests that agent coordination should avoid coupling continuity too tightly to one tool or interface.

Git may be a useful early carrier, but Git is not itself the context.

Likewise, a chat interface, development environment, or agent runtime may carry important context without being its permanent home.

## Open Questions

- When is context sufficiently carried?
- What relationships matter most to preserve across agent handoff?
- Which carriers are best suited for which kinds of context?
- How should carried context be expressed when the primary artifact is not text?
- When should a carrier be considered authoritative versus partial?
- Does later evidence justify a broader Milieu-level reference?
- What is the operational mechanism for delivering Carried Context to an agent at session start? The current approach — expecting the agent to fetch context from an upstream repository — fails when the agent lacks network access or cannot discover the relevant documents. A generated orientation bundle committed to the working repository is one candidate, but the right pattern has not yet been established through use.
- How should upstream architecture records be made observable to agents working in downstream repositories that may not have direct access to the source? This surfaced concretely when a Rider agent working in PrismalExperimental could not fetch ARCHITECTURE documents from milieu-public, correctly refused to proceed without them, and had to be given the content manually.
- How does Carried Context propagate when it changes? When a source record is updated, every downstream consumer — other repositories, RAG pipelines, vector stores, model training corpora — needs to receive the change. Git-based snapshot sync with a PR gate is the current mechanism. Future carrier technologies will need equivalent propagation mechanisms with the same gate semantics: the consumer controls when it accepts an upstream context change, not the producer. The right general pattern is not yet established.
- How is context provenance tracked across carrier transitions? When context moves from a Git record into a model training corpus, a vector store, or a tensor-based representation, the original source version must remain traceable. A model training run, agent session, or test variant that depends on a specific version of shared context must be able to record which version it used. The Git commit hash of a vendored snapshot is the current provenance primitive. Future carriers will need equivalent versioning. This is especially important for multi-variant testing, where different variants must be attributable to specific context states to produce meaningful comparisons.

## Related

- RECORD-000 — Milieu Record System
- REFERENCE-AGENTS-001 — Multi-Dimensional Agent Systems

## Consequences

Potential benefits include improved continuity across agents, lower coordination friction, and reduced dependence on any single platform.

Trade-offs include ambiguity during early use, the need for judgment about what is sufficient, and the risk of over-capturing context if the concept is applied too mechanically.

These trade-offs are acceptable during exploration because this record is intended as a working reference, not yet a binding decision.
