# REFERENCE-PRISMAL-SCALE-ADDRESSABILITY-000 - Scale Addressability Proof Need

- **ID:** REFERENCE-PRISMAL-SCALE-ADDRESSABILITY-000
- **Status:** Working Draft
- **Created:** 2026-06-03
- **Updated:** 2026-06-03

## Intent

Capture the proof need for scale addressability in Prismal Space.

The purpose of this record is to preserve the question we need to prove, not to decide the final subdivision scheme.

## Context

Prismal Space needs a way to address structure across scale without losing track of where something is.

The current proving ground is 2D because it is computable, visualizable, and easier to falsify. The first candidate model is a circle-address plane with integer-native coordinates, scale levels, and exact relationships between adjacent scale levels.

This record does not claim that physical space is ordered by a lattice, grid, circle packing, sphere packing, or Voronoi structure. Those structures may be useful as models, views, or implementation aids.

The narrower claim is that Milieu needs a proof that an addressable subdivision scheme can scale up and down while preserving recoverable location.

## Proof Need

We need to prove that a subdivision scheme can support both:

- scaling down to progressively smaller addressable regions
- scaling up to progressively larger addressable regions

without losing the ability to answer:

> Where is this?

The answer may require a local frame, a regional origin, a scale level, and a durable ancestry or absolute reference. It does not require every object, sample, or simulation value to carry a full absolute coordinate at all times.

## Starting Scope

The proof starts in 2D.

The current 2D proving object is an infinitely scalable circle-address plane. Triangles, hexagons, Voronoi cells, and Cartesian embeddings may appear as derived views, but they are not the primary object of the proof.

The primary object is scale addressability.

A provisional 2D address may have this shape:

```text id="ehykmw"
CircleAddress2D:
    level: integer
    i: integer
    j: integer
```

A provisional membership rule may be:

```text id="2ea0d2"
i + j is even
```

A provisional embedding may be:

```text id="caw0hh"
x = scale(level) * i
y = scale(level) * sqrt(3) * j
```

The value `sqrt(3)` belongs to the embedding or view layer. It should not be required for native address membership, neighbor lookup, or ancestry tracking.

## Scaling Model

For an integer subdivision factor `k`, scale may be represented as:

```text id="3z68gu"
scale(level) = base_scale / k^level
```

Increasing `level` addresses smaller regions.

Decreasing `level` addresses larger regions.

A location at one level should have an exact relationship to the same location at another level. For one level of downward refinement, the relationship may be:

```text id="qji2ya"
(level, i, j)
```

corresponding to:

```text id="wqlpww"
(level + 1, k * i, k * j)
```

The proof must show which choices of `k` preserve the needed address relationships.

## Rebase Requirement

Rebasing is allowed and expected.

Local computation may need compact relative coordinates for precision and performance. Rendering, physics, simulation, and field evaluation should not require every hot-path value to carry a large absolute address.

Rebasing is valid only if the system preserves enough information to recover or relate:

```text id="gmxy11"
local address
regional origin
scale level
ancestral reference
absolute reference when required
```

The proof must distinguish between two paths:

```text id="61fyrs"
absolute reference path:
    sparse
    durable
    high precision
    used for anchors, indexes, persistence, audit, and cross-scale identity

local computation path:
    compact
    fast
    relative
    used for simulation, rendering, and neighborhood work
```

## Absolute Index Requirement

Some index types may require very large integer coordinates.

This is expected for sparse durable references, such as:

- scale anchors
- region origins
- persistent world features
- cross-scale identity records
- audit or debug references
- ancestry links between local patches and larger contexts

This should not imply that large integer coordinates are appropriate for all local simulation data.

The proof should allow large absolute indexes where needed and compact local coordinates where possible.

## Non-Claims

This record does not claim that:

- physical space is ordered by a triangular lattice
- physical space is ordered by the lattice currently called FCC
- physical space is made of circles or spheres
- Voronoi cells are the fundamental object
- hexagons are the fundamental object
- Cartesian coordinates are false
- one coordinate view must replace all others

The proof target is narrower:

```text id="bhcqtd"
A chosen subdivision and addressing scheme must preserve recoverable location across scale changes and rebasing.
```

## Later Generalization

The proof starts in 2D.

Later work may extend or generalize from 0 through N dimensions, or at minimum through the dimensions needed for modeling and simulating reality.

Possible stages include:

```text id="t9l1r3"
0D:
    identity, point, anchor

1D:
    order, interval, scale relation

2D:
    circle-address plane

3D:
    sphere-address space and close-packing-derived subdivision candidates

higher dimensions:
    only where needed for projection, state, phase space, constraint systems, or other modeling requirements
```

No later dimensional result should be assumed from the 2D case without proof or explicit limitation.

## Open Questions

- Which subdivision factor should be preferred for the 2D circle-address plane?
- Is factor 3 geometrically preferable for circle-first scaling?
- Are factors 2 or 4 preferable for implementation or binary compatibility?
- Can multiple subdivision factors coexist?
- What exact data structure represents ancestry across scale?
- Which indexes require absolute-scale coordinates?
- Which indexes should remain local only?
- What rebasing rules are required for rendering, simulation, persistence, and audit?
- What is the minimum proof needed before extending the model to 3D?
- Which parts of the 2D proof remain true from 0 through N dimensions?

## Success Criteria

The proof succeeds if it shows that:

- addresses exist at every supported scale level
- scaling up preserves recoverable location
- scaling down preserves recoverable location
- rebasing does not destroy the ability to recover where something belongs
- local computation can remain compact
- sparse absolute indexing is sufficient for durable cross-scale references
- the 2D case can be tested before broader dimensional generalization

## Working Summary

Prismal Space needs a scale-addressability proof.

The immediate task is not to prove that reality has a particular lattice structure. The task is to prove that a subdivision and addressing scheme can preserve recoverable location while expanding and contracting across scale.

The proof begins in 2D with addressable circles because this case is computable and visualizable. Other structures may help explain or implement the model, but the central requirement is to keep track of where something is as scale changes.
