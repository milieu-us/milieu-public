# REFERENCE-PRISMAL-000 - Prismal Space - Current View and Open Questions

- **ID:** REFERENCE-PRISMAL-000
- **Status:** Working / Provisional Reference
- **Created:** 2026-04-03
- **Updated:** 2026-04-27
- **Scope:** Minimum constraint foundation and long-range simulation representation context for Prismal Space
- **Related:** Prismal Starter exploration, multi-scale simulation research, REFERENCE-PRISMAL-GEOMETRY-000

---

## Intent

This Reference Record captures the **current provisional view of Prismal™ and Prismal Space™** as it is presently understood.

The purpose of this record is to preserve a shared orientation toward the long-range simulation representation that multiple exploration efforts are investigating. It describes the **apparent structure, durable pressures, and open questions** surrounding Prismal Space.

This record **is not a directive for implementation teams**. It does not prescribe architecture for current projects such as Prismal Starter.

Instead, it provides a **big-picture reference** that teams may use when evaluating local decisions and experiments.

Exploration work - including Prismal Starter - will generate evidence that may refine or replace the views expressed here.

---

## Scope

This record addresses the **conceptual representation of simulation space across scales**.

It is concerned with:

- minimum constraint foundations
- spatial reference structures as derived views
- multi-scale composition and decomposition
- neighborhood and other relation families
- representation layering
- alignment and authoring reasoning
- simulation state representation
- observation, measure, and quantity domains

It does **not** define:

- project-specific architecture
- engine implementation details
- rendering pipelines
- project governance policies
- runtime simulation rules

Those decisions belong in project-level Decision Records and Architectural Decision Records.

---

## Minimum Constraint Foundation

Current exploration suggests that Prismal Space should not begin from coordinates, geometry, lattices, cells, or rendering. Those are derived representations or views.

At the minimum foundation layer, Prismal Space is better understood as a **bounded, observable constraint system**.

Minimum concepts:

- **Boundary:** declared scope.
- **Distinction:** observable difference.
- **State:** arrangement of distinctions inside a boundary.
- **Delta:** before-and-after difference between states; a candidate transition before constraints are applied.
- **Constraint:** checkable limit on states or deltas.
- **Transition:** a delta that is allowed under constraints.
- **Observation:** recorded distinction about state, constraint, delta, or transition.
- **Measure:** rule that assigns a quantity to something.
- **Quantity:** measurable value with declared meaning.

Derived concepts:

- **Structure:** persistent constraint.
- **Information:** observable distinction.
- **Energy:** bounded capacity for transition.

Consequences:

- Coordinates are representations, not structure.
- Geometry is interpretation under declared measures.
- Rendering is observation or presentation, not canonical state.
- Lattices are constraint families or derived views, not first principles.
- No measure is implicit: distance, time, angle, scale, and coordinate basis must be declared where used.

This foundation is provisional. It exists to reduce premature commitment to any single representation layer while preserving enough formal structure for implementation, testing, and review.

---

## Current Provisional View

Current exploration suggests that **Prismal Space may function as a bounded, observable constraint framework for organizing simulation state, transitions, observations, measures, and derived representations across multiple scales**.

Spatial, lattice, geometric, rendering, energy, information, and computational views should be treated as derived lenses over that foundation unless a later record explicitly decides otherwise.

Early work indicates several potential characteristics.

### Multi-scale structure

Prismal Space appears suited to representing environments across multiple scale bands, ranging from human-scale interaction outward toward planetary or cosmic contexts and inward toward finer molecular, atomic, and quantum structures. We leave open the possibility the space may wrap around with yet unknown structures between Cosmic and Quantum.

### Candidate reference structures

Early investigation suggests that some lattice and cell relationships may provide useful neighborhood, packing, alignment, and multi-scale organization properties.

Face-centered cubic relationships and rhombic dodecahedron cells remain important candidates for exploration, but they should not be treated as the starting assumption for Prismal Space.

Any candidate reference structure should be evaluated as a constraint family, measure space, embedding, authoring aid, or derived view rather than as the root ontology.

### Reference structure rather than ultimate reality

A lattice representation should be treated as **one possible reference structure for organizing simulation**, not as the root definition of Prismal Space and not as a claim that physical reality must conform exactly to the lattice.

Fields, flows, objects, and social constructs may cross, span, or ignore lattice boundaries.

### Multiple representations may coexist

Simulation environments will likely involve several overlapping representations, including:

- constraint systems
- spatial reference structures
- lattice-oriented views
- volumetric or material fields
- discrete objects and agents
- energy and information views
- computational representations
- rendering geometry
- authoring grids or alignment guides
- streaming or storage partitions

These representations may share anchors or identities without necessarily sharing the same data model.

Prismal Space should not be reduced to any single representation layer. Lattice-oriented spatial views, energy views, information views, computational views, rendering views, storage views, and authoring views may each expose different aspects of the same underlying constraint system.

---

## Durable Constraints We Suspect Matter

Early exploration suggests several pressures that appear likely to remain relevant across projects. These should be treated as **guiding concerns**, not rigid rules.

### Representation is not the world

Spatial reference structures help organize simulation and computation but should not be mistaken for the complete ontology of the simulated world.

Different phenomena may cross and/or span reference boundaries freely.

### Multi-scale coherence

The representation should support both:

- **decomposition toward finer resolution**
- **composition toward larger aggregates**

Ideally these operations preserve meaningful relationships across scale bands.

### Relations and neighborhoods are fundamental

Stable relation families appear central to many simulation tasks. Neighborhood relations are especially useful derived relations, but they should not be assumed to be purely geometric or spatial.

Relevant relation families may support:

- propagation
- interaction
- aggregation
- partitioning
- streaming
- navigation
- identity preservation
- view derivation

Structures that preserve consistent relation logic across scales may offer strong advantages.

### Alignment legibility for authors

Builders, designers, and tool users must be able to **reason about alignment and placement**.

Representations that are mathematically elegant but difficult to interpret may create long-term usability challenges.

### Discrete composition may be preferable to ad-hoc correction

Where possible, lawful composition from discrete units may reduce the need for compensating geometry or alignment hacks.

### Multiple authorities for different truths

Different aspects of the world may require different authoritative sources, including:

- structural placement
- terrain or substrate
- material state
- agent state
- governance or ownership
- narrative or social state

These truths may overlap spatially but need not share the same storage model or update cadence.

### Stable identity with derived local reference frames

Any candidate indexing scheme should distinguish stable canonical identity from derived local reference frames used for computation, rendering, storage, or authoring.

Large simulations cannot assume a single global computational coordinate frame with sufficient numerical precision for all purposes. Rendering, simulation, and interaction systems will often operate within **local reference frames** derived from canonical identity.

This implies:

- canonical identity should remain stable even when computational frames change
- systems should be able to operate within local frames suited to their precision needs
- candidate indexing approaches should be evaluated partly by how well they support **change of reference frame across scale bands**

This concern is independent of any specific runtime or engine implementation.

### Rendering representation should not become canonical identity

Meshes, textures, and shaders are presentation layers. They should not become the canonical definition of simulation state.

---

## Questions Active Explorations Should Help Answer

Several important questions remain unresolved.

Exploration projects, including Prismal Starter, are expected to provide evidence that helps answer them.

### What constitutes canonical identity?

Possible candidates include:

- constraint identifiers
- state identifiers
- transition identifiers
- observation identifiers
- lattice coordinate systems
- hierarchical cell identifiers
- region aggregates
- multi-scale spatial addresses

The system may ultimately require more than one identity layer. Spatial identity may be one such layer, but it should not be assumed to be the root identity layer.

### Which aspects of candidate reference structures are canonical, derived, or provisional?

It remains unclear which candidate structure properties should be treated as:

- canonical structure
- derived view
- measure convention
- computational convenience
- authoring guidance
- temporary exploration scaffold

### How should scale bands compose and decompose?

Questions include:

- how fine resolution aggregates into coarser representations
- whether boundaries align across bands
- how simulation meaning is preserved when transitioning between scales

### What relation rules remain stable across scales?

Certain adjacency or neighborhood rules may hold consistently across levels, while others may require translation. Other non-spatial relation families may also need stable cross-scale behavior.

### How many representation layers are required in practice?

Candidate layers include:

- canonical constraint system
- spatial reference views
- simulation fields
- object placement
- navigation abstraction
- rendering geometry
- streaming partitions
- authoring surfaces

Exploration will reveal which layers are necessary.

### What should be stored as authoritative state?

Some structures may exist only as derived views. Others must be persisted as canonical simulation state.

Understanding this boundary is important for distributed simulation and persistence.

### How should rotation freedom be exposed to authors?

Placement flexibility introduces complexity in alignment reasoning. The system may require explicit rotation sets or policies to keep builder expectations clear.

### Where do existing engine assumptions help or hinder?

Existing engines and tools may provide strong capabilities but may also embed assumptions (for example, surface-centric geometry or Cartesian partitioning) that interact with Prismal Space in complex ways.

---

## Expected Sources of Evidence

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

## Relationship to Project-Level Records

Projects such as Prismal Starter will produce their own Decision Records and Architectural Decision Records describing local implementation choices.

Those decisions may:

- adopt temporary simplifications
- constrain the problem space for experimentation
- diverge from the provisional view presented here

Such divergence is expected and useful.

Project records should reference this document where relevant, especially when a local decision may influence long-term representation assumptions.

---

## Consequences

Maintaining a provisional big-picture record allows:

- exploration work to remain grounded in a shared long-term context
- local decisions to be evaluated against broader representation goals
- contradictory findings to be surfaced earlier
- architectural assumptions to be revisited before they become entrenched

This record should evolve as new insights emerge.

---

## Review Triggers

This record should be revisited when significant findings occur, including:

- major discoveries from Prismal Starter
- successful multi-scale simulation prototypes
- evidence that canonical identity requires redefinition
- evidence that representation layering must change
- strong performance or usability findings affecting spatial representation

---

## Addendum A - Multiple Views of Simulation

Prismal Space is currently better understood as a **bounded, observable constraint system** that may support multiple derived views of simulation.

Spatial and lattice views, energy views, information views, computational views, rendering views, storage views, and authoring views may each be necessary for different purposes. A given phenomenon may be easier to simulate, reason about, optimize, or render from one view than another.

This does not imply separate realities. It suggests that the same underlying simulation may need to be understood through multiple lenses, with lawful ways to navigate between them while preserving identity, meaning, and relevant constraints.

This addendum is explanatory and provisional. It does not yet define a formal architecture for view transitions.

---

## Summary

Prismal Space currently appears to be a **multi-scale constraint framework** that may support coherent simulation across bands of scale through bounded states, checkable constraints, lawful transitions, explicit observations, declared measures, and derived representations.

Spatial and lattice representations remain important candidate views, but they are no longer treated as the minimum foundation.

The precise form of that framework, and how it interacts with fields, objects, rendering systems, and authoring tools, remains an open question.

Active exploration projects are expected to generate the evidence necessary to refine this understanding.

This record exists to **preserve shared orientation while that exploration proceeds**.

© 2011-present Milieu.Us - All rights reserved.
Milieu™, Prismal™, and Prismal Space™ are trademarks of Milieu.Us.
