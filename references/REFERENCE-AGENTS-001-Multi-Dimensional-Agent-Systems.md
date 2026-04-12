# REFERENCE-AGENTS-001 - Agentic Ecosystems - Working Synthesis

- **ID:** REFERENCE-AGENTS-001
- **Status:** Working Draft
- **Created:** 2026-04-03
- **Updated:** 2026-04-11

## Intent

Capture the current working synthesis that agent systems are multi-dimensional, and that agentic ecosystems are not defined only by agent capability or count, but by how human agents, AI agents, and system agents coordinate across governance, operations, change, carried context, validation, authority, and memory over time.

This reference exists to preserve the broader working theory emerging in Milieu without prematurely splitting that theory into too many narrower records.

## Context

Milieu is not designing isolated agent tasks.

It is developing ecosystems in which human agents, AI agents, and system agents contribute across shared artifacts, repositories, branches, pull requests, runtime systems, and future public experiences.

Current Milieu work already assumes that:

- stakeholders act through agents
- agent action must be bounded and observable
- shared artifacts evolve through explicit proposal and acceptance
- later agents must be able to continue work without pretending to share the same original context
- continuity cannot be tied permanently to one tool, one interface, or one representation

These patterns suggest that agent capability alone is not enough to explain system behavior.

## Working Synthesis

Agent systems are multi-dimensional.

Increasing autonomy, count, or orchestration may increase capability, but does not by itself produce a stable, legible, or trustworthy ecosystem.

The present synthesis expands that view by focusing not only on dimensions in the abstract, but on the practical coordination requirements of an agentic ecosystem.

A workable agentic ecosystem must coordinate:

- what can act
- how authority is bounded
- how work moves
- how context moves
- how outputs become trustworthy
- how continuity is preserved

These dimensions are interdependent.

Weakness in one dimension often appears as overload, confusion, or hidden assumptions in another.

## Dimensions

### Agency

What can act.

This includes:

- human agents
- AI agents
- system agents
- degrees of autonomy
- orchestration complexity

Agency describes the presence and capability of actors, but not yet the quality of their coordination.

### Governance and Authority

How action is bounded, interpreted, and held accountable.

This includes:

- who may request change
- who may implement change
- who may review change
- who may accept change
- who acts as steward or boundary-holder when shared risk is involved

Governance is not separate from agent systems.

It shapes what kinds of action are legitimate, reviewable, and acceptable.

### Operations and Working Surfaces

How the ecosystem runs in practice.

This includes environments and surfaces such as:

- repositories
- branches
- pull requests
- records
- local working copies
- build systems
- runtime systems
- logs and related operational outputs

Operations provide the practical surfaces through which agents act, inspect, and coordinate.

### Change, Collaboration, Review, and Learning

How work moves through the ecosystem.

This includes:

- collaborative development of candidate changes
- review of outputs against intent and constraints
- learning from outcomes to improve future prompts, tools, records, and workflows
- nested and recursive loops within larger changes

A single change may contain multiple smaller loops.

Different loops may have different requesters, implementers, reviewers, and acceptance boundaries.

### Carried Context and Handoffs

How understanding moves between agents and working surfaces.

This includes continuity across:

- conversations
- records
- repository files
- branches
- pull requests
- logs
- build outputs
- screenshots, video, and other non-text artifacts

Not all context should be carried forward.

The ecosystem must preserve enough context for another agent to continue well without requiring every later agent to load everything.

This dimension is explored further in `REFERENCE-AGENTS-002`.

### Validation, Evidence, and Trust Surfaces

How outputs become trustworthy enough to review or accept.

This includes:

- diffs
- tests
- logs
- screenshots
- file presence checks
- direct inspection of artifacts
- explicit reporting of uncertainty or authority limits

Trust should rely on observable evidence appropriate to the scope of change.

Confidence without evidence is not enough.

### Memory and Continuity

What persists over time.

This includes:

- records
- decision lineage
- accepted changes
- validation artifacts
- preserved assumptions
- retained open questions
- reusable patterns for future agents

Memory allows later agents to continue work without reconstructing everything from scratch.

## Coupling Between Dimensions

These dimensions should not be treated as independent checklists.

Examples:

- weak carried context increases review burden
- weak validation increases pressure to trust identity alone
- weak authority boundaries create confusion about who may accept change
- weak memory forces repeated rediscovery
- high agency without supporting dimensions increases instability

The ecosystem should therefore be designed for balance rather than maximum autonomy.

## Working Patterns Observed So Far

Current Milieu work suggests several early patterns:

- requester review is often the best review for intent satisfaction
- implementation review and boundary review may require different agents
- shared artifacts reduce hidden assumptions during handoff
- branch isolation and explicit diffs help bound change surfaces
- evidence should match the scope of the change
- missing context should be surfaced rather than invented
- collaboration loops matter alongside review loops
- feedback from physical human work must be able to re-enter the shared system

These are working findings, not final doctrine.

## Consequences

This synthesis suggests that Milieu should not evaluate agentic progress only by asking whether agents can do more work.

It should also ask:

- can the ecosystem carry context cleanly
- can changes be reviewed at the right scope
- can acceptance rely on visible evidence
- can authority boundaries be understood
- can later agents continue work without unnecessary reconstruction

This shifts attention from isolated capability toward ecosystem quality.

## Open Questions

- What is the minimum viable ecosystem structure required before public-facing experiences are exposed?
- Which dimensions are most fragile in practice?
- What context should be carried forward directly, and what should remain as pointers?
- Which evidence surfaces are sufficient for different classes of change?
- When should requester, reviewer, and accepter be separated?
- How should physical human work be reflected back into shared records and agent workflows?
- Which parts of this synthesis should later be split into their own references?

## Related

- `REFERENCE-AGENTS-000`
- `REFERENCE-AGENTS-002`
- `REFERENCE-DOMAIN-000`
- `DECISION-MILIEU-CORE-000`
- `DECISION-MILIEU-MVM-000`
- `DECISION-OPERATIONS-CHANGE-000`
- `DECISION-OPERATIONS-CHANGE-001`