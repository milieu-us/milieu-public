# REFERENCE-PRISMAL-002-Structural-Constraints-Joinery-and-Playable-Assembly

## Prismal Space — Structural Constraints, Joinery as Tests, and Playable Assembly

ID: REFERENCE-PRISMAL-002
Status: Working Draft
Created: 2026-04-04
Updated: 2026-04-04

---

## Intent

Establish a minimal, buildable framing for structural relationships in Prismal Space based on constraints rather than predefined parts or join types.

This reference captures:
- the shift from geometry-first to constraint-first modeling
- the use of real-world joinery as a validation suite rather than a taxonomy
- the extension of joinery into material behavior (including compliant systems)
- the requirement that all of this remains explorable through play

The goal is not to fully define a system, but to establish a coherent direction that can be implemented and tested.

---

## Context

Earlier references established:
- Prismal Space as arising from field, lattice, and projection
- FCC / rhombic dodecahedron adjacency as a candidate structural substrate
- minimal primitives and discrete representations (integer / fractional preference)

This reference moves from:
- *what space is*

to:
- *how things connect, assemble, and hold within that space*

---

## Core Direction

### 1. Minimal Primitives (No Semantic Parts)

Prismal Space begins with:
- square
- equilateral triangle

Everything else is derived through:
- thickness
- extrusion (length)
- rotation (fractional turns)
- adjacency-based snapping

Objects such as beams, panels, or columns are not distinct types, but configurations of primitives.

---

### 2. Curves as Fractional Composition

Curvature is expressed without continuous floats:

- arcs defined by:
  - radius
  - fractional segment of rotation (e.g. 1/12 turn)

Curved forms emerge through:
- composition of discrete segments
- alignment with lattice and rotation systems

---

### 3. Joinery as Constraints (Not Types)

Joinery is not defined as a catalog of named joints.

Instead, a connection is described by:

- allowed motion (degrees of freedom)
- constraint progression (how motion is restricted)
- locking conditions
- assembly sequence
- load transfer characteristics
- reversibility

A “joint” is understood as:
> a transformation of allowed states under constraints

---

### 4. Joinery as a Validation Suite

Known joinery (including Western, Japanese, and Korean traditions) is used as a **test set**, not a feature list.

The system is evaluated by asking:

- can these structural behaviors be reproduced?
- do they assemble correctly?
- do they lock as expected?
- do they transfer load in meaningful ways?

This shifts development from:
- implementation of types

to:
- validation of expressiveness

---

### 5. Material Behavior as First-Class

Connections are not purely geometric.

Material response must be considered, including:

- rigidity vs compliance
- elastic vs plastic deformation
- friction and compression
- anisotropy (e.g. grain-like behavior)

This enables:
- snap fits
- wedge locks
- compression-based joins
- deformation-assisted assembly

Locking may be understood as:
> a stable energy state under constraints, not only zero degrees of freedom

---

### 6. Cross-Scale Structural Reasoning

The same structural ontology should be testable across:

- rigid systems (e.g. masonry, metal)
- semi-compliant systems (e.g. wood)
- soft systems (e.g. polymers, biological structures)

The goal is not strict equivalence, but to identify:
- invariant structural patterns
- material-dependent behavior
- scale-dependent effects

---

### 7. Play as a System Requirement

Exploration must be possible through direct interaction.

The system should support:

- immediate feedback (visible constraint behavior)
- legible motion and snapping
- reversible experimentation
- progressive discovery of structure

Play is not optional; it is required for:
- usability
- learning
- evolution of the system

---

## Test Framing

Initial validation can be organized along four axes:

- Fit — can the form be represented?
- Assembly — can it be constructed through valid motion?
- Lock — does it become constrained as intended?
- Load — does it carry force meaningfully?

With an additional requirement:

- Play — is the system explorable and intuitive?

---

## What This Enables (Near-Term)

- constraint-driven structural prototyping
- exploration of joinery without predefined types
- generation and testing of new connection patterns
- early physical experimentation (mockups, prints, simple builds)

---

## Open Questions (Condensed)

- What is the minimal constraint schema required for useful expression?
- How are assembly sequences encoded and validated?
- How should tolerance and fit be represented?
- What is the smallest viable material model for early testing?
- How do curves interact with constraints and snapping at different resolutions?
- How much of this should be enforced vs emergent?

---

## Notes

This reference is intentionally incomplete.

It defines a direction that:
- is consistent with prior Prismal work
- is grounded enough to build
- remains open to refinement through testing and play