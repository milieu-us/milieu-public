# ARCHITECTURE-PRISMAL-001 - Prismal Core — First Implementation Context

- **ID:** ARCHITECTURE-PRISMAL-001
- **Status:** Working Draft
- **Created:** 2026-04-13
- **Updated:** 2026-04-13

## Intent

Carry the implementation context needed by any agent to begin building Prismal™ Core — the substrate geometry and lattice view machinery — as the first working library.

This document does not provide a task list. It carries the constraints, relationships, and reasoning that must survive handoff so that implementation decisions are made well rather than made again from scratch.

## Current Home

Prismal Core currently lives inside the PrismalExperimental project as namespaced classes under `Prismal::Core`. The project currently uses Unreal Engine 5, but the Core namespace must have no dependency on it.

This is a pragmatic starting point, not a permanent home. The target state is a standalone library with no host dependencies, usable from any engine or environment. The boundary is enforced by discipline now — Core must not include host engine headers or use host engine types, even while physically residing in a host project.

When Core moves to its own library, nothing in Core should need to change. If something does need to change at that point, the boundary was not being respected during the experimental phase.

## The Substrate

The substrate is `Z^3` — an integer coordinate space. A site is a position in that space:

```
{ x, y, z } where x, y, z are integers
```

The substrate itself has no geometry, no scale, and no preferred lattice. It is the space over which selections are made.

This directly expresses REFERENCE-PRISMAL-003's model: the substrate is the structure over which adjacency and neighborhood relationships can be evaluated, prior to any named lattice interpretation.

## The LatticeView

A `LatticeView` is the carried context for all lattice operations. It binds a selection rule to a unit scale and passes explicitly through every call that needs it.

It carries:

- **SelectionRule** — which lattice view is active (FCC, SC, BCC, or future rules)
- **unitScale** — the value of `a`, the nearest-neighbor distance, in whatever units the caller cares about

`LatticeView` is never implicit state. It is never global. Every lattice operation that depends on it receives it as a parameter.

This constraint exists because REFERENCE-PRISMAL-001 establishes that coordinate systems are projections, not foundations. Making the view implicit would silently encode a foundational assumption that the system explicitly rejects. An agent reading Core code must be able to determine the active lattice view from the call site alone.

The runtime parameterization of `SelectionRule` is a deliberate decision, not a default. It exists because data passing and data storage patterns for views need to be worked through with real usage, and locking to a compile-time selection before that evidence exists would foreclose options that the substrate model explicitly keeps open.

## Selection Rules

A selection rule determines two things for a given substrate site: whether that site participates in the view, and who its neighbors are.

The three rules needed now, and their expressions over `Z^3`:

### FCC

A site `(x, y, z)` participates when `x + y + z ≡ 0 mod 2`.

Its 12 nearest neighbors are all permutations of `(±1, ±1, 0)`:

```
(+1,+1, 0)  (+1,-1, 0)  (-1,+1, 0)  (-1,-1, 0)
(+1, 0,+1)  (+1, 0,-1)  (-1, 0,+1)  (-1, 0,-1)
( 0,+1,+1)  ( 0,+1,-1)  ( 0,-1,+1)  ( 0,-1,-1)
```

All 12 offsets have `|offset|² = 2` and all preserve the parity constraint — an FCC site's neighbors are always valid FCC sites.

### SC

All sites in `Z^3` participate — no constraint.

6 nearest neighbors: `(±1, 0, 0)`, `(0, ±1, 0)`, `(0, 0, ±1)`.

### BCC

All sites in `Z^3` participate.

8 nearest neighbors: all `(±1, ±1, ±1)`.

BCC can also be understood as two interleaved SC sublattices — `Z^3` and `Z^3 + (1,1,1)` — which is the same structure expressed differently.

### Why three rules, not three structures

SC, BCC, and FCC are not three different data structures. They are three different selections over the same `Z^3` substrate. The substrate does not change. The neighbor function changes. This is the direct expression of REFERENCE-PRISMAL-003's core model, and it is the reason `SelectionRule` is a parameter rather than a type.

## Geometry Ratios

Core carries the exact geometry ratios from REFERENCE-PRISMAL-GEOMETRY-000 as dimensionless constants. These are multiplied by `unitScale` at the call site to produce values in host units.

All quantities are exact closed forms normalized to nearest-neighbor distance `a = 1`. These have been verified computationally.

### Packing radius

```
r = a / 2
```

### RD cell metrics (Voronoi cell of FCC)

```
RD_inradius      = a / 2          // equals packing radius — exact algebraic identity
RD_midradius     = a / sqrt(2)    // distance to 4-valent vertex; coincides with octahedral void center
RD_circumradius  = a * sqrt(6)/4  // distance to 3-valent vertex; coincides with tetrahedral void center
```

The coincidence of RD vertex distances with void centers is not approximate — it is an exact geometric identity. REFERENCE-PRISMAL-GEOMETRY-000 derives this fully.

### Void geometry

```
// Tetrahedral void (closer, smaller)
tet_void_distance = a * sqrt(6)/4          // == RD_circumradius exactly
tet_void_radius   = a * (sqrt(6) - 2) / 4

// Octahedral void (farther, larger)
oct_void_distance = a / sqrt(2)            // == RD_midradius exactly
oct_void_radius   = a * (sqrt(2) - 1) / 2
```

### Critical overlap thresholds

When spheres of radius `R` are placed at each lattice site, the qualitative topology of their union changes at two thresholds:

```
R = a * sqrt(6)/4  ≈ 0.6124·a   // sphere surface reaches tetrahedral void centers
R = a / sqrt(2)    ≈ 0.7071·a   // sphere surface reaches octahedral void centers
```

These thresholds matter for the test harness rendering profiles. REFERENCE-PRISMAL-GEOMETRY-000 covers the full derivation and implications.

## What Core Answers

In this first implementation, Core is asked to answer three categories of questions:

**Membership** — is a given site a valid member of the active view?

**Neighborhood** — who are the neighbors of a given site under the active selection rule?

**Geometry** — what are the metric properties of a given site and its relationships, scaled to the caller's unit system via `unitScale`?

Core does not answer questions about state, occupancy, material, or history. Those concerns belong to layers built on top of Core.

## What Is Not Specified Here

These are intentionally deferred. They will be addressed through later documents or through evidence gathered from the experimental harness.

- Spatial indexing and storage of site state — a separate concern that must not couple to the substrate geometry layer
- The formal interface for the adapter contract — deferred until a second host environment is needed
- Higher-dimensional extensions (D4, E8, Leech) — the math is understood and documented in REFERENCE-PRISMAL-GEOMETRY-000; implementation waits until needed
- The `Selection → View` machinery as a general runtime system — the first implementation handles FCC, SC, BCC as an enumeration; generalization follows from evidence

## Open Questions

- What is the right representation for `SelectionRule` at this stage — an enum, a struct carrying a neighbor-offset table, or a callable? The enum is simplest; the offset table makes neighbor sets data rather than code and is trivially extensible; the callable is most general. The choice affects how easily new rules are added without modifying Core.
- Should geometry ratio constants live in a dedicated `Prismal::Geometry` namespace or alongside the lattice view machinery?
- How should the test harness first consume Core — directly, or through the adapter layer from the start? The answer shapes how the adapter boundary is first exercised and whether any violations are caught early.

## Related

- ARCHITECTURE-PRISMAL-000 — Founding document for this family
- REFERENCE-PRISMAL-001 — Field, Lattice, and Projection
- REFERENCE-PRISMAL-003 — Unified Lattice Substrate and Selection Model
- REFERENCE-PRISMAL-GEOMETRY-000 — Sphere Geometry Derivation
- ARCHITECTURE-PRISMAL-EXPERIMENT-001 — Test Harness First Implementation Context
