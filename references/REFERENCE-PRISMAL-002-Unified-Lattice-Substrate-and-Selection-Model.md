# REFERENCE-PRISMAL-002 - Unified Lattice Substrate and Selection Model

- **Status:** Working Draft
- **Created:** 2026-04-09
- **Updated:** 2026-04-09

---

## Intent

Capture a unifying model for lattice structures in 3D space, establishing that commonly referenced lattices (Simple Cubic, Body-Centered Cubic, Face-Centered Cubic, and related structures) are not fundamentally distinct systems, but arise from a shared underlying substrate through different primitive selections and selection rules.

This reference supports Prismal Space as a coherent simulation and representation framework, where multiple lattice interpretations emerge from a single data structure.

---

## Summary

A Prismal lattice is defined by:

- A shared underlying substrate (adjacency structure)
- A primitive selection (vertex, edge, face, cell, interstitial)
- A selection rule (subset definition over the substrate)

All commonly used lattice systems can be expressed as combinations of these three components.

---

## 1. Underlying Substrate

The substrate is a discrete spatial structure capable of expressing adjacency, containment, and neighborhood relationships.

Examples include:

- Integer grid (ℤ³)
- Face-Centered Cubic (FCC) adjacency
- More generally: a combinatorial complex (Prismal Complex)

Key property:

The substrate is not tied to a specific lattice interpretation. It is a shared structure from which multiple lattices can be derived.

---

## 2. Primitive Selections

A lattice can be viewed by selecting which dimensional primitives are foregrounded.

### 2.1 Vertex Lattice (0D)

Points and their adjacency.

Represents:
- Position
- Minimal topology

---

### 2.2 Edge Lattice (1D)

Connections between vertices.

Represents:
- Interaction
- Flow
- Constraint propagation

---

### 2.3 Face Lattice (2D)

Surfaces bounded by edges.

Represents:
- Boundaries
- Interfaces
- Contact regions

---

### 2.4 Cell Lattice (3D)

Volumes and their adjacency.

Represents:
- Occupancy
- State
- Region-based simulation

Example:
- Rhombic dodecahedron (Voronoi cell of FCC)

---

### 2.5 Interstitial Lattice (Derived)

Void or constraint-derived positions within the structure.

Represents:
- Potential states
- Emergent positions
- Transition sites (e.g., diffusion in materials)

Examples:
- Tetrahedral sites
- Octahedral sites

---

## 3. Selection Rules

A lattice is further defined by selecting a subset of the substrate according to a rule.

These rules operate over coordinates or adjacency relationships.

### Examples

#### Simple Cubic (SC)

All points in the substrate:

(x, y, z) ∈ ℤ³

---

#### Body-Centered Cubic (BCC)

Points satisfying parity or offset rules, such as:

- integer points plus (1/2, 1/2, 1/2)
- or parity constraint on coordinates

---

#### Face-Centered Cubic (FCC)

Points where coordinate parity aligns (e.g., all even or all odd under scaling).

---

#### Derived Structures

Additional structures arise from alternative selection rules, including:

- Interstitial lattices
- Multi-basis lattices (e.g., diamond cubic)

---

## 4. Duality and Equivalence

Many named lattices are dual or equivalent representations under different primitive selections.

Examples:

- FCC (vertex view) ↔ Rhombic Dodecahedral tiling (cell view)
- FCC ↔ BCC duality via Voronoi/Delaunay relationships

These are not distinct systems, but different projections of the same structure.

---

## 5. Unified Model

A lattice in Prismal Space is defined as:

Lattice = (Substrate) + (Primitive Selection) + (Selection Rule)

Implications:

- No need to switch between lattice systems
- All lattices are composable
- Transitions between representations are lossless

---

## 6. Architectural Implications

### 6.1 Single Data Structure

A unified adjacency structure can support:

- simulation (edges, cells)
- rendering (faces)
- reasoning (vertices)

---

### 6.2 Constraint-Driven Selection

Selection rules can be expressed as constraints, aligning with the Prismal constraint fabric.

---

### 6.3 Multi-Domain Support

Different domains emphasize different views:

- Physics → edges and vertices
- Materials → cells and interstitials
- Rendering → faces
- Gameplay → cells and edges

---

### 6.4 Continuity Across Scales

Because all views share a substrate:

- transitions across scales remain coherent
- no conversion between representations is required

---

## 7. Relationship to Existing Theory

This model aligns with established concepts, including:

- Bravais lattices (SC, BCC, FCC)
- Voronoi and Delaunay duality
- Cell complexes and combinatorial topology

However, it reframes them as:

- selections over a shared structure
- rather than fundamentally distinct systems

---

## 8. Minimal Statement

A Prismal lattice is not a distinct structure, but a view over a shared substrate defined by primitive selection and selection rules. Common lattices such as SC, BCC, and FCC are specific instances of this general model.

---

## Open Questions

- What is the minimal substrate required to express all useful lattice views?
- Should FCC be preferred as the canonical substrate over ℤ³ for uniformity?
- How should selection rules be encoded for efficient runtime evaluation?
- What is the minimal representation that preserves continuity across scales?

---

## Notes

This reference builds on prior Prismal Space work and external research demonstrating equivalence between cubic lattices through subset selection.

