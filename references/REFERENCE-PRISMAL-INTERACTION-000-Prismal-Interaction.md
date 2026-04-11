# REFERENCE-PRISMAL-INTERACTION-000 - Prismal Interaction

- **ID:** REFERENCE-PRISMAL-INTERACTION-000
- **Status:** Working Paper (Exploratory)
- **Created:** 2026-03-26
- **Updated:** 2026-04-11

## Intent

Define the minimum viable interaction model that lets sentients present posture to an oracle, resolve consequence against Prismal state, and update shared experience state without blocking early implementation.

## Note

This is v0 and exploratory. It is long because we do not yet know enough to constrain it. It introduces concepts that may change or be replaced. Terms such as Oracle and Guide are provisional.

## Why

We need a thin, buildable interaction model for early Milieu experiments.

We have enough shared direction to define a minimum viable slice, but not enough certainty to lock a full theory of energy space, information space, or Prismal Space as a complete simulation framework.

This record exists to provide a stable core that:

- gives builders something concrete to implement now
- preserves room for multiple oracle media and interpretation styles
- keeps LLMs, guides, players, and other sentients within the same interaction model
- avoids collapsing improvisation into hidden system judgment
- allows experimental posture inputs without requiring them for the first roleplay session
- introduces potential use cases for Energy Based Reasoning Models (EBRMs)

## Decision

Milieu will use a minimum viable Prismal interaction model built from five parts:

1. **Prismals** as localized state-bearing interaction objects
2. **Posture** as the way a sentient presents agency into an interaction
3. **Oracles** as the means by which interacting postures are resolved
4. **Visibility** as a first-class rule for who can know oracle results
5. **Expression** as the in-world rendering of consequence by a player, guide, non-player sentient, or system

This record defines the v0 interaction contract only. It does not attempt to fully define Prismal Space, physical simulation, lattice fidelity, or formal energy and information mathematics.

## Core view

### Energy

For this interaction model, energy is treated as **capacity to change state**.

In v0, this is represented operationally through posture and the resulting change applied to Prismals and their relationships.

### Information

For this interaction model, information is treated as **structure of possible states**.

In v0, this is represented operationally through what is known, visible, hidden, revealed, persistent, or ambiguous within Prismal state and oracle output.

### Interaction

A Prismal interaction is the resolution of one or more sentients presenting posture into shared state.

A single actor is a valid case. Multi-actor interaction is not a special system layered on later. It is a natural extension of the same model.

## Definitions

### Prismal

A Prismal is a localized state-bearing interaction object.

In v0, a Prismal may represent any of the following:

- an entity
- a place
- a relationship
- an emotional tension
- a social condition
- an unresolved thread
- another meaningful state-bearing object needed by the experience

A Prismal is not restricted to physical objects.

### Posture

Posture is the way a sentient presents agency into an interaction.

Posture is the replacement for many roles often split across declared approach, modifiers, hidden intent, stance, and dice-driven advantage.

A posture may be declared, inferred, or mixed.

In v0, posture is treated as an interface rather than a fixed input medium.

### Oracle

An oracle resolves the interaction between posture and current state.

The oracle is not a speaking character. It does not replace a guide, player, or non-player sentient performance layer. It determines consequence and updates state.

The oracle may be expressed through different media, including but not limited to:

- symbolic media such as cards, sticks, stones, or similar methods
- numeric or randomizing methods such as dice
- guide-mediated interpretive methods
- structured system logic
- model-assisted methods

The oracle is defined by its outcome space and resolution logic, not by the signal medium used to surface it.

### Visibility

Visibility defines who is allowed to know oracle output.

This replaces the simple distinction between public and hidden rolls.

### Expression

Expression is how oracle consequence becomes visible in the experience.

Expression may be performed through:

- player action or response
- guide interpretation
- non-player sentient dialogue or behavior
- environmental change
- memory or future reincorporation
- visual, audio, or other system-mediated signals

## v0 interaction flow

The minimum viable interaction loop is:

**sentient input -> posture -> oracle resolution -> Prismal update -> expression**

Where relevant, visibility rules determine who receives which parts of the oracle result before expression.

## Posture interface v0

Posture must reduce to a canonical form before oracle resolution.

For v0, posture should remain minimal and legible. A starting structure may include:

- **approach**: open, guarded, forceful, deceptive, exploratory, or equivalent
- **commitment**: low, medium, high
- **exposure**: low, medium, high

This structure is provisional. The important decision is not the exact fields, but that posture has a stable shared form before resolution.

### Input flexibility

Posture may be generated from many input sources, including but not limited to:

- direct player declaration
- guide interpretation
- LLM interpretation of language and context
- voice characteristics
- controller input
- phone-based sensors and interfaces
- mouse and keyboard input
- system-generated or inferred signals

These are valid posture generators, not separate interaction systems.

Experimental posture inputs are encouraged, but none are required for the first roleplay session.

## Oracle output v0

Oracle outputs must map into a consistent consequence structure even when the signal medium differs.

A minimal v0 output may include:

- **yield**: low, partial, strong
- **cost**: low, rising, high
- **memory**: none, weak, strong
- **information shift**: none, reveal, obscure, distort

Additional axes may be added later, such as status, trust, tension, attention, or obligation.

The oracle should favor gradients and consequence patterns over binary pass-fail resolution.

## Visibility modes v0

The interaction model recognizes visibility as a first-class concern.

### Open visibility

Used when participants should directly know the outcome they would normally roll for themselves.

### Veiled visibility

Used when some result should remain hidden from one or more sentients, similar to hidden game master resolution.

In these cases, a guide or another authorized interpreting layer may receive the oracle output and reveal consequence indirectly or later.

### Partitioned visibility

Used when different sentients receive different slices or interpretations of the same underlying result.

This mode is important for asymmetry, secrecy, uncertainty, and layered experience design.

## Composition

Multiple sentients may combine posture into a shared interaction.

The system should allow at least the following modes:

- **reinforcement**: aligned posture strengthens a common direction
- **complementarity**: different postures combine into a more capable whole
- **interference**: misaligned posture produces friction, ambiguity, or added cost

This should emerge from posture composition rather than from bolt-on teamwork bonuses.

## Role of LLMs

LLMs are not the oracle.

LLMs may support:

- language interpretation
- context gathering
- posture inference
- non-player sentient expression
- guide support
- rendering consequence in-world

LLMs should not collapse performance, fairness, and consequence determination into one opaque layer.

## EBRMs and Oracle Modeling (v0 guidance)

This record introduces potential use of **Energy-Based Reasoning Models (EBRMs)** for oracle behavior, and clarifies why LLMs alone are not suitable for the energy potential space.

### Why not LLMs for energy potential space

LLMs are optimized for:

- generating plausible language and narratives
- compressing and recalling patterns from training data
- producing coherent continuations given context

LLMs are not optimized for:

- maintaining stable, repeatable state evaluation across interactions
- representing multi-modal outcome distributions explicitly
- providing consistent, auditable consequence logic over time
- separating performance (what is said) from adjudication (what changes)

Using LLMs directly as the oracle risks:

- opaque and inconsistent outcomes
- collapse of fairness into narrative convenience
- loss of trust due to non-legible decision processes

### Why EBRM-like approaches fit the oracle

EBRM-style models (or structured equivalents) are better aligned with the oracle role because they:

- evaluate **relative fit of possible outcomes** rather than generate a single narrative answer
- can represent **multiple competing outcomes** and sample or select among them
- support **stable axes of consequence** (yield, cost, memory, etc.)
- separate **evaluation** from **expression**

In this framing, the oracle is estimating:

> which resulting state configurations best fit the current posture interaction within the constraints of the system

This aligns with:

- Energy: capacity to change state
- Information: structure of possible states

### Practical v0 stance

For v0, EBRMs do not need to be implemented as full machine learning systems.

Acceptable oracle implementations include:

- rule-based scoring systems
- weighted random systems with context inputs
- small structured evaluators
- hybrid systems combining rules and model assistance

The key requirement is:

> **oracle evaluation remains structured, repeatable, and separable from language generation**

LLMs may assist with interpretation and expression, but should not be the sole source of oracle judgment.

## Role of the guide

The guide may interpret oracle signals and manage veiled or partitioned visibility.

The guide does not replace the oracle's consequence function.

For v0, the operating principle is:

**The oracle determines what changes. The guide determines how it is revealed.**

## What this record does not define

This record does not define:

- full Prismal Space ontology
- final posture schema
- final oracle media
- lattice implementation details
- full memory architecture
- formal energy and information mathematics
- all future interaction axes
- final user interface or embodiment methods

These remain open and may evolve through implementation and play.

## Consequences

### Positive

- we have a stable interaction core to build against
- multiple oracle media can coexist without fragmenting the underlying model
- posture-based interaction supports solo and cooperative play under one system
- experimental embodiment inputs remain possible without blocking the first session
- guides, players, and LLM-based sentients can all participate under the same model

### Trade-offs

- v0 remains intentionally underspecified in several areas
- posture categories may prove too coarse or too narrow
- guide interpretation could drift if outcome mapping is not kept consistent
- some teams may want harder rules sooner than this record provides

### Risk

The main risk is premature expansion into full theory or implementation detail before the interaction loop has been tested in play.

## Implementation guidance

For the first implementation pass, prefer:

- a small canonical posture schema
- a small canonical oracle output schema
- simple visibility rules
- Prismals represented as lightweight state-bearing nodes with relationships
- clear boundaries between resolution and expression

Experimental inputs and presentation layers should plug into the posture or expression layers without changing the shared interaction contract.

## Open questions

- What is the minimum useful canonical posture schema for the first live session?
- Which oracle media feel most legible and embodied for different groups?
- How much of posture should be declared versus inferred?
- How should memory and reincorporation connect to Prismal updates?
- What is the minimum Prismal representation needed for early scenes?
- Which outcome axes best support roleplay without becoming overly mechanical?
- When should visibility be delayed, partitioned, or revealed?
- How should group posture composition be surfaced, if at all, to participants?

## Related

- RECORD-000 - Milieu Record System
- DECISION-PRISMAL-SPACE-000 - Prismal Space: Current View and Open Questions
- DECISION-EXP-000 - Minimum Viable Experience
- REFERENCE-EXP-000 - Impro Embodied Play and Improvisation
- DECISION-GOV-000 - Minimum Viable Governance

## Addendum A - Practical framing for builders

If implementation pressure rises, prefer this simplified frame:

- **Prismals** hold state
- **Posture** applies agency
- **Oracles** resolve consequence
- **Visibility** controls who knows
- **Expression** renders the result

That is enough for v0.
