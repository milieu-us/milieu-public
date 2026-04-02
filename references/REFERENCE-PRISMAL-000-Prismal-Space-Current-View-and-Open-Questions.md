# REFERENCE-PRISMAL-000

## Prismal Space — Current View and Open Questions

**Status:** Working / Provisional Reference\
**Date:** 2026-03-06\
**Scope:** Long-range simulation representation context for Prismal Space\
**Related:** Prismal Starter exploration, multi-scale simulation research

---

# Intent

This Reference Record captures the **current provisional view of Prismal™ and Prismal Space™** as it is presently understood.

The purpose of this record is to preserve a shared orientation toward the long-range simulation representation that multiple exploration efforts are investigating. It describes the **apparent structure, durable pressures, and open questions** surrounding Prismal Space.

This record **is not a directive for implementation teams**. It does not prescribe architecture for current projects such as Prismal Starter.

Instead, it provides a **big-picture reference** that teams may use when evaluating local decisions and experiments.

Exploration work —- including Prismal Starter —- will generate evidence that may refine or replace the views expressed here.

---

# Scope

This record addresses the **conceptual representation of simulation space across scales**.

It is concerned with:

- spatial reference structures
- multi-scale composition and decomposition
- neighborhood relationships
- representation layering
- alignment and authoring reasoning
- simulation state representation

It does **not** define:

- project-specific architecture
- engine implementation details
- rendering pipelines
- project governance policies
- runtime simulation rules

Those decisions belong in project-level Decision Records and Architectural Decision Records.

---

# Current Provisional View

Current exploration suggests that **Prismal Space may function as a reference framework for organizing simulation across multiple scales**.

Early work indicates several potential characteristics.

## Multi-scale structure

Prismal Space appears suited to representing environments across multiple scale bands, ranging from human-scale interaction outward toward planetary or cosmic contexts and inward toward finer molecular, atomic, and quantum structures. We leave open the possibility the space may wrap around with yet unknown structures between Cosmic and Quantum.

## Reference geometry advantages

Early investigation suggests that **face-centered cubic (FCC) lattice relationships and rhombic dodecahedron cells** provide useful neighborhood and packing properties that may support coherent multi-scale organization.

These geometries remain candidates for further exploration rather than settled conclusions.

## Reference structure rather than ultimate reality

The lattice representation should be treated as **a reference structure for organizing simulation**, not as a claim that physical reality must conform exactly to the lattice.

Fields, flows, objects, and social constructs may cross, span, or ignore lattice boundaries.

## Multiple representations may coexist

Simulation environments will likely involve several overlapping representations, including:

- spatial reference structures
- volumetric or material fields
- discrete objects and agents
- rendering geometry
- authoring grids or alignment guides
- streaming or storage partitions

These representations may share spatial anchors without necessarily sharing the same data model.\
\
Prismal Space represents the lattice-oriented spatial view of the simulation. Other views—such as energy, information, or computational representations—may coexist and be navigated between for different purposes.

---

# Durable Constraints We Suspect Matter

Early exploration suggests several pressures that appear likely to remain relevant across projects. These should be treated as **guiding concerns**, not rigid rules.

## Representation is not the world

Spatial reference structures help organize simulation and computation but should not be mistaken for the complete ontology of the simulated world.

Different phenomena may cross and/or span reference boundaries freely.

## Multi-scale coherence

The representation should support both:

- **decomposition toward finer resolution**
- **composition toward larger aggregates**

Ideally these operations preserve meaningful relationships across scale bands.

## Neighborhood relations are fundamental

Stable adjacency relationships appear central to many simulation tasks, including:

- propagation
- interaction
- aggregation
- partitioning
- streaming
- navigation

Structures that preserve consistent neighborhood logic across scales may offer strong advantages.

## Alignment legibility for authors

Builders, designers, and tool users must be able to **reason about alignment and placement**.

Representations that are mathematically elegant but difficult to interpret may create long-term usability challenges.

## Discrete composition may be preferable to ad-hoc correction

Where possible, lawful composition from discrete units may reduce the need for compensating geometry or alignment hacks.

## Multiple authorities for different truths

Different aspects of the world may require different authoritative sources, including:

- structural placement
- terrain or substrate
- material state
- agent state
- governance or ownership
- narrative or social state

These truths may overlap spatially but need not share the same storage model or update cadence.

## Stable identity with local reference frames

Any candidate spatial indexing scheme should support **stable canonical spatial identity together with derived local reference frames used for computation**.

Large simulations cannot assume a single global computational coordinate frame with sufficient numerical precision for all purposes. Rendering, simulation, and interaction systems will often operate within **local reference frames** derived from canonical spatial identity.

This implies:

- canonical spatial identity should remain stable even when computational frames change
- systems should be able to operate within local frames suited to their precision needs
- candidate indexing approaches should be evaluated partly by how well they support **change of reference frame across scale bands**

This concern is independent of any specific runtime or engine implementation.

## Rendering representation should not become canonical identity

Meshes, textures, and shaders are presentation layers. They should not become the canonical definition of simulation state.

---

# Questions Active Explorations Should Help Answer

Several important questions remain unresolved.

Exploration projects—including Prismal Starter—are expected to provide evidence that helps answer them.

## What constitutes canonical spatial identity?

Possible candidates include:

- lattice coordinate systems
- hierarchical cell identifiers
- region aggregates
- multi-scale spatial addresses

The system may ultimately require more than one identity layer.

## Which aspects of the lattice are reference only?

It remains unclear which lattice properties should be treated as:

- canonical spatial structure
- computational convenience
- authoring guidance

## How should scale bands compose and decompose?

Questions include:

- how fine resolution aggregates into coarser representations
- whether boundaries align across bands
- how simulation meaning is preserved when transitioning between scales

## What neighborhood rules remain stable across scales?

Certain adjacency rules may hold consistently across levels, while others may require translation.

## How many representation layers are required in practice?

Candidate layers include:

- canonical spatial reference
- simulation fields
- object placement
- navigation abstraction
- rendering geometry
- streaming partitions

Exploration will reveal which layers are necessary.

## What should be stored as authoritative state?

Some structures may exist only as derived views. Others must be persisted as canonical simulation state.

Understanding this boundary is important for distributed simulation and persistence.

## How should rotation freedom be exposed to authors?

Placement flexibility introduces complexity in alignment reasoning. The system may require explicit rotation sets or policies to keep builder expectations clear.

## Where do existing engine assumptions help or hinder?

Existing engines and tools may provide strong capabilities but may also embed assumptions (for example, surface-centric geometry or Cartesian partitioning) that interact with Prismal Space in complex ways.

---

# Expected Sources of Evidence

Evidence informing this record may emerge from multiple exploration efforts, including:

- Prismal Starter experiments
- alignment grid prototypes
- authoring and builder usability testing
- simulation instrumentation and profiling
- volumetric streaming experiments
- state-authority and persistence experiments
- rendering and shader experiments
- large-scale aggregation tests

Findings from these efforts should be referenced in project-level Decision Records and Architectural Decision Records.

---

# Relationship to Project-Level Records

Projects such as Prismal Starter will produce their own Decision Records and Architectural Decision Records describing local implementation choices.

Those decisions may:

- adopt temporary simplifications
- constrain the problem space for experimentation
- diverge from the provisional view presented here

Such divergence is expected and useful.

Project records should reference this document where relevant, especially when a local decision may influence long-term representation assumptions.

---

# Consequences

Maintaining a provisional big-picture record allows:

- exploration work to remain grounded in a shared long-term context
- local decisions to be evaluated against broader representation goals
- contradictory findings to be surfaced earlier
- architectural assumptions to be revisited before they become entrenched

This record should evolve as new insights emerge.

---

# Review Triggers

This record should be revisited when significant findings occur, including:

- major discoveries from Prismal Starter
- successful multi-scale simulation prototypes
- evidence that canonical spatial identity requires redefinition
- evidence that representation layering must change
- strong performance or usability findings affecting spatial representation

---

# Addendum A — Multiple Views of Simulation

Prismal Space currently represents the **lattice-oriented spatial view** of the simulation.

Other views—such as **energy**, **information**, or **computational** views—may also be necessary for different purposes. A given phenomenon may be easier to simulate, reason about, optimize, or render from one view than another.

This does not imply separate realities. It suggests that the same underlying simulation may need to be understood through multiple lenses, with lawful ways to navigate between them while preserving identity, meaning, and relevant constraints.

This addendum is explanatory and provisional. It does not yet define a formal architecture for view transitions.

---

# Summary

Prismal Space currently appears to be a **multi-scale spatial reference framework** that may support coherent simulation across bands of scale.

However, the precise form of that framework—and how it interacts with fields, objects, rendering systems, and authoring tools—remains an open question.

Active exploration projects are expected to generate the evidence necessary to refine this understanding.

This record exists to **preserve shared orientation while that exploration proceeds**.

© 2011–present Milieu.Us — All rights reserved.
Milieu™, Prismal™, and Prismal Space™ are trademarks of Milieu.Us.