# REFERENCE-PRISMAL-003 - Unified Lattice Substrate and Selection Model

- **ID:** REFERENCE-PRISMAL-003
- **Status:** Working Draft
- **Created:** 2026-04-09
- **Updated:** 2026-04-09

## Intent

Capture a unifying model for lattice structures in 3D space, exploring whether commonly referenced lattices such as Simple Cubic, Body-Centered Cubic, Face-Centered Cubic, and related structures may be interpreted as views arising from a shared underlying substrate through different primitive selections and selection rules.

This reference supports Prismal Space as a coherent simulation and representation framework in which multiple lattice interpretations can emerge from one underlying structure without requiring separate foundational models for each named lattice.

## Use and Status

This reference captures a conceptual model that may be relevant to Prismal Space, especially where multiple lattice views, primitive selections, or substrate interpretations are involved.

It does not decide Prismal's canonical data structure.

In particular, this record does not yet determine:

- whether Prismal should use FCC, `Z^3`, a combinatorial complex, or another substrate as its canonical representation
- whether named lattice views should be stored directly or derived from a lower-level substrate
- how selection rules should be represented in runtime systems
- how this model connects to structural constraints, joinery, material behavior, or play

Those questions remain open and should be resolved through later decisions and implementation evidence.

## Summary

In this model, a lattice can be described by:

- a shared underlying substrate
- a primitive selection
- a selection rule

Many common lattice systems may then be expressed as specific instances of those three components.

## Relationship to Prior Prismal References

This reference extends rather than replaces prior Prismal references.

It is intended to sit alongside:

- REFERENCE-PRISMAL-001, which frames Prismal Space as a discrete realization of an underlying continuum and treats FCC adjacency as the current working model
- REFERENCE-PRISMAL-002, which focuses on structural constraints, joinery, and playable assembly

This document generalizes how multiple lattice interpretations may be derived from a shared substrate. It does not by itself overturn the current working preference for FCC-oriented reasoning where that remains the most useful local model.

The model may have uses beyond Prismal. It is preserved here because Prismal currently provides the clearest local reason to examine substrate/view separation, primitive selection, and selection-rule-based representation.

## Underlying Substrate

The substrate is a discrete spatial structure capable of expressing adjacency, containment, and neighborhood relationships.

Examples include:

- an integer grid (`Z^3`)
- FCC adjacency
- a more general combinatorial complex, such as a Prismal complex

The key property is that the substrate may not need to be tied to a single lattice interpretation. It can instead be treated as a shared structure from which multiple lattice views may be derived.

## Primitive Selections

A lattice can be viewed by selecting which dimensional primitives are foregrounded.

### Vertex Lattice (0D)

Points and their adjacency.

Represents:

- position
- minimal topology

### Edge Lattice (1D)

Connections between vertices.

Represents:

- interaction
- flow
- constraint propagation

### Face Lattice (2D)

Surfaces bounded by edges.

Represents:

- boundaries
- interfaces
- contact regions

### Cell Lattice (3D)

Volumes and their adjacency.

Represents:

- occupancy
- state
- region-based simulation

Example:

- rhombic dodecahedron as the Voronoi cell of FCC

### Interstitial Lattice (Derived)

Void or constraint-derived positions within the structure.

Represents:

- potential states
- emergent positions
- transition sites such as diffusion positions in materials

Examples:

- tetrahedral sites
- octahedral sites

## Selection Rules

A lattice is further defined by selecting a subset of the substrate according to a rule.

These rules operate over coordinates, parity relationships, offsets, or adjacency structure.

### Simple Cubic (SC)

All points in the substrate:

`(x, y, z) in Z^3`

### Body-Centered Cubic (BCC)

Points satisfying parity or offset rules, for example:

- integer points plus `(1/2, 1/2, 1/2)`
- parity-constrained coordinate subsets

### Face-Centered Cubic (FCC)

Points where coordinate parity aligns under an appropriate scaling or embedding.

### Derived Structures

Additional structures arise from alternative selection rules, including:

- interstitial lattices
- multi-basis lattices such as diamond cubic

## Duality and Equivalence

Many named lattices are dual or equivalent representations under different primitive selections.

Examples:

- FCC as a vertex view and rhombic dodecahedral tiling as a cell view
- FCC and BCC as duals through Voronoi and Delaunay relationships

These may often be understood not as wholly separate systems, but as different projections or selections over related structure.

## Unified Model

In this framing:

`Lattice = Substrate + Primitive Selection + Selection Rule`

Implications:

- there is less need to treat named lattices as separate foundational systems
- multiple lattice views may be composed over one substrate
- transitions between representations may be modeled explicitly where the substrate and selection rules preserve enough information

## Architectural Implications

### Single Data Structure

A unified adjacency structure may support:

- simulation through edges and cells
- rendering through faces
- reasoning through vertices

### Constraint-Driven Selection

Selection rules may be expressible as constraints, aligning this model with Prismal constraint-oriented reasoning.

### Multi-Domain Support

Different domains may emphasize different views:

- physics may emphasize edges and vertices
- materials may emphasize cells and interstitials
- rendering may emphasize faces
- gameplay may emphasize cells and edges

### Continuity Across Scales

If these views share a substrate:

- transitions across scales can remain more coherent
- representation changes need not imply a change in foundational identity

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
