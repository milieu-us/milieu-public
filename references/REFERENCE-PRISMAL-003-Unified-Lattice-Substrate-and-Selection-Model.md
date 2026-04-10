# REFERENCE-PRISMAL-003 - Unified Lattice Substrate and Selection Model

- **ID:** REFERENCE-PRISMAL-003
- **Status:** Working Draft
- **Created:** 2026-04-09
- **Updated:** 2026-04-10

## Intent

Capture a conceptual model for reasoning about lattice structures as derived views over an underlying substrate.

This reference explores whether commonly referenced lattices such as Simple Cubic, Body-Centered Cubic, Face-Centered Cubic, and related structures may be understood through primitive selection and selection rules rather than as separate foundational systems.

## Use and Status

This reference may inform Prismal Space where multiple lattice views, primitive selections, or substrate interpretations are involved.

It does not decide Prismal's canonical data structure.

In particular, this record does not yet determine:

- whether Prismal should use FCC, `Z^3`, a combinatorial complex, or another substrate as its canonical representation
- whether named lattice views should be stored directly or derived from a lower-level substrate
- how selection rules should be represented in runtime systems
- how this model connects to structural constraints, joinery, material behavior, or play

Those questions remain open and should be resolved through later decisions and implementation evidence.

## Core Model

In this model, a lattice view is described by:

- a substrate
- a primitive selection
- a selection rule

The substrate describes what relationships are available before interpretation.

Primitive selection determines which kind of element is foregrounded.

The selection rule determines which subset or arrangement of those elements is being read as the view.

A view is derived from the substrate for a purpose. It is not automatically the canonical substrate itself.

Many common lattice systems may then be understood as specific views produced from those components.

## Relationship to Prior Prismal References

This reference extends rather than replaces prior Prismal references.

It is intended to sit alongside:

- REFERENCE-PRISMAL-001, which frames Prismal Space as a discrete realization of an underlying continuum and treats FCC adjacency as the current working model
- REFERENCE-PRISMAL-002, which focuses on structural constraints, joinery, and playable assembly

This document generalizes how multiple lattice interpretations may be derived from a shared substrate. It does not by itself overturn the current working preference for FCC-oriented reasoning where that remains the most useful local model.

The model may have uses beyond Prismal. It is preserved here because Prismal currently provides the clearest local reason to examine substrate/view separation, primitive selection, and selection-rule-based representation.

## Substrate Hypothesis

The substrate is a connectivity structure independent of any one named lattice interpretation.

It is the structure over which adjacency, containment, neighborhood, and incidence relationships can be evaluated.

This record does not yet decide whether the substrate should be represented as:

- a graph
- a fixed lattice with known neighbor relationships
- a cell complex
- another discrete or combinatorial structure

For this reference, the important property is not the final storage form. The important property is that a substrate preserves relationships from which multiple views may be derived.

The following examples sit at different modeling layers and should not yet be treated as interchangeable peers:

- index space, such as an integer grid (`Z^3`)
- adjacency model, such as FCC neighborhood relationships
- structural formalism, such as a graph, cell complex, or Prismal complex

## Substrate Invariants

If this model is useful for Prismal, the substrate likely needs to preserve:

- stable identity for addressable elements
- adjacency or neighborhood relationships
- incidence relationships between primitives
- enough structure to derive more than one lattice view

These are candidate invariants, not final data-structure requirements.

A related Prismal research goal is to preserve enough continuity across scale to avoid treating each view as a disconnected system.

## Primitive Selections

A primitive selection chooses which dimensional elements of the substrate are foregrounded for a particular view or operation.

Examples include:

- vertices
- edges
- faces
- cells
- interstitial positions

Primitive selections are not necessarily separate stored systems. They may be different readings of the same underlying substrate.

### Vertex View (0D)

Foregrounds points and their adjacency.

This may be useful for:

- position
- minimal topology

### Edge View (1D)

Foregrounds connections between vertices or sites.

This may be useful for:

- interaction
- flow
- constraint propagation

### Face View (2D)

Foregrounds surfaces bounded by edges.

This may be useful for:

- boundaries
- interfaces
- contact regions
- rendering surfaces

### Cell View (3D)

Foregrounds volumes and their adjacency.

This may be useful for:

- occupancy
- state
- region-based simulation

Example:

- rhombic dodecahedron as the Voronoi cell of FCC

### Interstitial View (Derived)

Foregrounds void or constraint-derived positions within the structure.

This may be useful for:

- potential states
- emergent positions
- transition sites such as diffusion positions in materials

Examples:

- tetrahedral sites
- octahedral sites

## Selection Model

Selection is the operation that maps a substrate into a view.

In minimal form:

`Selection(Substrate, Primitive, Rule) -> View`

Selection takes a substrate together with a choice of primitive and rule set, then produces a view that interprets the same underlying structure.

The substrate supplies available relationships.

The primitive identifies the kind of element to foreground.

The rule identifies which elements or relationships participate in the resulting view.

Selection rules may operate over:

- coordinates
- parity relationships
- offsets
- adjacency
- incidence
- constraints
- context

This framing is intended to make selection first-class without yet deciding how selection is represented in runtime systems.

## Lattice Views (Derived)

Named lattice structures can be treated as derived views when they can be produced by selecting primitives and applying rules over a substrate.

This does not mean every lattice view is always lossless, interchangeable, or equally useful. It means the relationship between views can be made explicit instead of hidden behind separate names.

### Simple Cubic (SC)

A simple cubic view may be produced by selecting all points in an integer-grid substrate:

`(x, y, z) in Z^3`

### Body-Centered Cubic (BCC)

A body-centered cubic view may be produced by applying parity or offset rules, for example:

- integer points plus `(1/2, 1/2, 1/2)`
- parity-constrained coordinate subsets

### Face-Centered Cubic (FCC)

A face-centered cubic view may be produced by selecting points whose coordinate parity aligns under an appropriate scaling or embedding.

### Derived Structures

Additional structures may arise from alternative selection rules.

Examples include:

- interstitial lattices
- multi-basis lattices such as diamond cubic

## Duality and Equivalence

Many named lattices are dual or equivalent representations under different primitive selections.

Examples:

- FCC as a vertex view and rhombic dodecahedral tiling as a cell view
- FCC and BCC as duals through Voronoi and Delaunay relationships

These may often be understood not as wholly separate systems, but as different projections or selections over related structure.

## Implications

### Simulation

Simulation systems may be able to operate over the primitive view best suited to the phenomenon being modeled.

Examples:

- physics may emphasize edges and vertices
- materials may emphasize cells and interstitials
- region simulation may emphasize cell adjacency

### Rendering

Rendering may emphasize faces or derived surfaces without making those surfaces the canonical simulation state.

### Coordinate Systems

Coordinate systems may be treated as projections or selection aids rather than as the foundation of the model.

### Runtime Systems

Selection may become a runtime concern if different agents, scales, domains, or systems need different views over the same substrate.

This possibility is not yet an implementation requirement.

## Relationship to Existing Theory

This model aligns with established concepts including:

- Bravais lattices such as SC, BCC, and FCC
- Voronoi and Delaunay duality
- cell complexes and combinatorial topology

The main shift here is interpretive: these may be treated as selections over a shared structure rather than as fundamentally isolated systems.

## Minimal Statement

A Prismal lattice may not need to be treated as a distinct foundational structure in itself. It can be understood as a view over a shared substrate defined by primitive selection and selection rules. Common lattices such as SC, BCC, and FCC may be specific instances of this broader model.

## Unresolved Bridge to Prismal Structure

This model is not yet fully connected to Prismal's structural and playable work.

Important bridge questions remain:

- how primitive selection over a lattice relates to authoring primitives such as squares, triangles, cells, panels, or edges
- whether structural constraints operate as selection rules, operate on already-selected structures, or require a separate layer
- how static lattice views become assembly processes over time
- where material behavior enters if the substrate model is primarily topological or geometric
- what play reveals that the lattice model alone cannot validate

## Open Questions

- What is the minimal substrate required to express the lattice views that Prismal actually needs?
- When should FCC remain the preferred working substrate over `Z^3` or other alternatives?
- How should selection rules be encoded for efficient runtime evaluation?
- What is the minimal representation that preserves continuity across scales?
- How much, if at all, should this model shape near-term Prismal data structures?

## Notes

This reference builds on prior Prismal Space work and related external theory regarding equivalence, duality, and subset selection across lattice families.

It should be treated as a research reference and conceptual aid, not as an implementation decision.
