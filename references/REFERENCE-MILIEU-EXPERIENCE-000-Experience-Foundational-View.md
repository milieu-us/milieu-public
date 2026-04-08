# REFERENCE-MILIEU-EXPERIENCE-000 - Experience Foundational View

- **ID:** REFERENCE-MILIEU-EXPERIENCE-000
- **Status:** Working Draft
- **Date:** 2026-03-12
- **Scope:** Foundational framing for Experience within Milieu
- **Related:** DR-PRISMAL-SPACE-000, Minimum Viable Experience, Impro design reference

## Intent

This Decision Record defines the current foundational view of **Experience** within Milieu.

The purpose of this record is to establish a shared orientation for how Experience should be understood across future design, simulation, operations, and participation work.

This record is intentionally foundational. It does **not** define a full implementation architecture, user interface system, content pipeline, or runtime feature set.

Instead, it clarifies what Experience appears to be **at the level of Milieu itself** so that later project records can build on a common frame.

---

## Decision

Milieu currently treats **Experience** as:

**the layer through which agents perceive, interpret, and act within Milieu.**

Experience is therefore **not limited to user interface** and should not be treated as a presentation layer added after simulation.

Experience is the **agent-facing encounter layer** between agents and the rest of Milieu.

This applies to:

- human agents
- AI agents
- system agents
- other agent types that may be discovered or introduced later

Milieu should assume that **agent** is an open category rather than a closed list.

---

## Why this matters

A simpler framing such as Ã¢â‚¬Å“the worlds people engage withÃ¢â‚¬Â is too narrow for Milieu.

It implies that Experience is primarily human-facing and downstream from more fundamental systems.

Current understanding suggests something broader and more useful:

- agents do not access the whole system directly
- agents encounter Milieu through bounded representations, interfaces, embodiments, and control surfaces
- those encounter forms shape what an agent can perceive, understand, and affect

Experience is therefore a **primary mediation layer**, not decorative output.

---

## Scope

This record is concerned with the foundational meaning of Experience as a Milieu domain.

It is concerned with:

- agent-facing encounter
- perception
- interpretation
- agency
- embodiment
- mediation between agents and modeled world state
- experience as a cross-domain concern

It does **not** define:

- a specific user interface framework
- rendering technology
- content authoring workflows
- multiplayer interaction rules
- agent protocol formats
- safety mechanics in detail
- project-specific feature lists

Those belong in later project-level Decision Records, Architectural Decision Records, and design references.

---

## Current Foundational View

## Experience is agent-facing, not human-only

Experience should be framed for **all agent types**, not only human participants.

This means Experience may take different forms for different agents, including but not limited to:

- embodied spatial and social encounter for human agents
- structured world views, summaries, and tool-mediated context for AI agents
- event streams, scoped state views, and control surfaces for system agents

These are not separate realities. They are different encounter forms with the same broader Milieu.

## Experience is not merely interface

Milieu does not treat Experience as equivalent to screen layout, controls, menus, or conventional user experience alone.

Experience includes the broader conditions through which an agent encounters a world, including:

- what can be sensed
- what can be interpreted
- what can be acted upon
- what consequences follow
- what embodiment or role perspective is present
- what social and temporal context gives meaning

## Experience mediates encounter with state and constraint

Current Milieu thinking suggests:

- simulation represents state
- simulation applies constraints to that state
- agents encounter that state and those constraints through Experience

This means Experience is one of the primary ways Milieu makes simulation meaningful to agents.

## Experience may involve multiple modalities and embodiments

Experience should support multiple modes of encounter rather than assume a single preferred interface model.

Possible forms include:

- visual
- auditory
- spatial
- symbolic
- textual
- operational
- social
- embodied
- machine-readable
- hybrid forms

Embodiment may be especially important where understanding depends on position, role, consequence, timing, and feedback.

---

## Candidate Experience Invariants

Current discussion suggests that Experience, for any agent type, likely involves a small set of recurring properties.

These are provisional and should be tested through project work.

## Situated encounter

Experience occurs from a bounded perspective.

Agents do not perceive the whole of Milieu. They encounter it from some position, role, scope, and context.

## Perception

Experience provides signals about the state of the world.

Those signals may differ by modality and agent type.

## Affordance

Experience communicates **what actions appear possible** within a given context.

Affordances help agents understand:

- what capabilities exist
- what actions are currently possible
- what may happen next
- how they are oriented within a possibility space
- what elements of the environment are interactive or meaningful

Affordances may be conveyed through:

- visual or spatial cues
- interaction patterns
- narrative framing
- role expectations
- system prompts
- structured signals for machine agents

Affordances help agents **perceive the space of possibility**.

## Agency

Experience must allow agents to **affect the world in meaningful ways**.

Agency is the capacity of an agent to act within Milieu and produce observable consequences.

Agency may include actions such as:

- movement
- speech
- manipulation of objects
- proposals or governance participation
- system operations
- observation or attention shifts
- modification of world state

Agency operates within constraints defined by simulation rules, permissions, roles, and safety structures.

Without agency, experience collapses into passive observation.

## Consequence

Actions must produce observable effects.

Without consequence, experience becomes thin and participation loses meaning.

## Feedback over time

Experience unfolds through change, response, and temporal relation.

Time introduces causality, anticipation, and learning.

## Constraint

Experience exists within rules, limits, permissions, and other structures that define meaningful action.

Constraints are not merely limitations. They define the space of meaningful action.

## Interpretation

Agents make meaning from what they encounter.

Meaning may be narrative, operational, social, symbolic, or computational.

---

## Relationship to Participation

Experience and Participation are related but not identical.

A useful current distinction is:

- **Participation** concerns contribution, coordination, proposal, and taking part
- **Experience** concerns the perceptual, interpretive, and interactive means through which an agent takes part

Participation addresses the social and procedural fact of involvement.

Experience addresses the lived, perceived, and enacted encounter through which involvement becomes possible.

---

## Relationship to Simulation

Experience is closely coupled to Simulation but should not be collapsed into it.

Simulation concerns:

- state
- rules
- constraints
- lawful transitions

Experience concerns:

- encounter with that state
- shaped perception of that state
- action within those constraints
- meaning-making arising from those encounters

Experience therefore mediates how agents interact with modeled state.

---

## Relationship to Embodiment

Current Milieu thinking suggests that embodiment should be treated as a serious concern rather than an optional presentation feature.

For human agents, embodiment may shape learning, meaning, role assumption, and social interaction.

For AI agents, embodiment may help ground perception, action, consequence, and situated understanding.

For system agents, embodiment may appear in more abstract forms such as bounded operational presence, scoped authority, or localized sensing and actuation.

This record does not prescribe one embodiment model, but it preserves the expectation that **how an agent is situated affects what that agent can understand and do**.

---

## Relationship to Design References

The Keith Johnstone reference is relevant because it reinforces that meaningful experience may arise through embodied relational play rather than abstract description alone.

It also suggests that invitation, role assumption, status, co-creation, safety, and recovery structures may need to be treated as core experience concerns rather than optional polish.

This record preserves those ideas as design pressure rather than formal doctrine.

---

## Consequences

Adopting this framing has several implications.

## Experience becomes a first-class domain

Experience should be treated as foundational to Milieu, not as a secondary layer applied after simulation or operations work is complete.

## Human-only assumptions should be avoided

Experience records and implementations should avoid assuming that the only meaningful participant is a human user.

## Multiple encounter forms are expected

Different agents may require different representations, modalities, and action surfaces while remaining meaningfully connected to the same broader world.

## Embodiment and perspective matter

Future work should consider what an agent can sense, do, and understand from its situated form of encounter.

## Safety may be architectural, not cosmetic

Where experiences involve deep role assumption, embodiment, or intense interaction, safety and recovery structures may need to be treated as core design architecture.

---

## Open Questions

Several important questions remain open.

## What makes an encounter meaningfully shared across agent types?

Different agents may encounter the same world differently. It remains unclear what must be common for that experience to count as genuinely shared.

## What minimum experience surface is required for each agent type?

Milieu will likely need to determine what minimal perception, action, and consequence loop is sufficient for meaningful participation by each agent type.

## Which forms of embodiment materially improve understanding?

It remains unresolved how strongly different forms of embodiment influence learning, coordination, and meaning-making.

## How should experience views relate to multiple simulation views?

If simulation may be navigated through spatial, informational, energetic, or computational views, future work must clarify how agents encounter and move across those views coherently.

## Which safety structures are foundational for embodied play?

This is especially important for experiences involving role assumption, trance-adjacent states, or strong social intensity.

---

## Expected Sources of Evidence

This record should be refined by evidence from:

- Minimum Viable Experience prototypes
- authoring and builder experience tests
- observer and participant studies
- AI agent interaction experiments
- system agent orchestration experiments
- embodied play tests
- safety and recovery design experiments
- cross-agent coordination scenarios

---

## Review Triggers

This record should be revisited when significant findings occur, including:

- evidence that Experience should be split into multiple domains
- evidence that Participation and Experience are insufficiently distinct
- evidence that embodiment is more or less central than currently assumed
- successful cross-agent encounter prototypes
- meaningful findings from MVE experiments
- adoption of a more formal agent model in Milieu

---

## Summary

Milieu currently treats **Experience** as the agent-facing layer through which agents perceive, interpret, and act within a constrained world over time.

This makes Experience more than interface and more than human-facing presentation.

It is a foundational mediation layer between agents and Milieu itself.

