# REFERENCE-PRISMAL-GEOMETRY-000-Sphere-Geometry-Derivation

## Prismal Space – Sphere Geometry: FCC, D4, E8, and Leech Lattices

- ID: REFERENCE-PRISMAL-GEOMETRY-000
- Status: Working Draft
- Created: 2026-04-09
- Updated: 2026-04-09

---

## Intent

Establish exact sphere geometry for the lattice families underlying Prismal Space: FCC in 3D, D4 in 4D, E8 in 8D, and the Leech lattice Λ₂₄ in 24D.

All definitions start from spheres. This record derives the canonical ratios — packing radius, void distances, void sphere radii, and overlap cap depth — that govern how spheres tile space and interact in each lattice.

These ratios are foundational for:

- procedural surface generation (cap overlap control)
- feature placement in voids (gap geometry)
- constraint-based assembly (snap distances)
- cross-scale structural reasoning
- rendering pipeline parameters (macro and micro)

---

## Normalization Convention

Throughout this record, all quantities are expressed in units of the **nearest-neighbor distance** `a`:

> `a` = the distance between the centers of any two adjacent (touching) spheres

This normalization is lattice-independent and makes ratios directly comparable across dimensions.

The **packing radius** (radius at which adjacent spheres just touch) is therefore:

```
r = a / 2
```

All other distances are expressed as multiples of `a`.

---

## 3D — FCC (Face-Centered Cubic)

### Structure

FCC lattice vectors (one standard basis, with conventional cubic side `c = a√2`):

```
(0, c/2, c/2),   (c/2, 0, c/2),   (c/2, c/2, 0)
```

| Property | Value |
|---|---|
| Nearest-neighbor distance | `a` (normalized) |
| Conventional cubic side | `c = a√2 ≈ 1.4142·a` |
| Kissing number | 12 |
| Packing radius | `r = a/2` |
| Self-dual | No |

### Void Geometry

FCC is the **only lattice in this family with two geometrically distinct void types** at different distances from lattice points.

#### Tetrahedral Void

The tetrahedral void center lies at `(c/4, c/4, c/4)` from a lattice point.

```
dist(lattice → tet void) = a√6 / 4  ≈  0.6124·a

inscribed sphere radius   = (√6/4 − 1/2)·a  ≈  0.1124·a

ratio r_tet / r           = (√6/2 − 1)       ≈  0.2247
```

- 2 tetrahedral voids per lattice point
- Surrounded by 4 lattice points at equal distance

#### Octahedral Void

The octahedral void center lies at the midpoint of a cube edge, e.g. `(c/2, 0, 0)`.

```
dist(lattice → oct void) = a / √2  ≈  0.7071·a

inscribed sphere radius   = (1/√2 − 1/2)·a  ≈  0.2071·a

ratio r_oct / r           = (√2 − 1)         ≈  0.4142
```

- 1 octahedral void per lattice point
- Surrounded by 6 lattice points at equal distance

> **Note:** The octahedral void is the *larger* of the two distances from a lattice point, but it admits a *larger* inscribed sphere. The tetrahedral void center is closer but tighter.

### Rhombic Dodecahedron (Voronoi Cell of FCC)

The Voronoi cell of FCC is the rhombic dodecahedron (RD). It has two types of vertices:

| Vertex type | Valence | Distance from center | Coincides with |
|---|---|---|---|
| 4-valent (square-face) | 4 faces meet | `a/√2 ≈ 0.7071·a` | octahedral void center |
| 3-valent (triangular-face) | 3 faces meet | `a√6/4 ≈ 0.6124·a` | tetrahedral void center |

| RD metric | Value |
|---|---|
| Inradius (face center distance) | `a/2 = r` |
| Midradius (4-valent vertex) | `a/√2 ≈ 0.7071·a` |
| Circumradius (3-valent vertex) | `a√6/4 ≈ 0.6124·a` |
| Circumradius / Inradius | `√6/2 ≈ 1.2247` |

The inradius equals the packing radius `r`. This means the inscribed sphere of the RD cell is exactly the packing sphere — a clean geometric identity.

---

## 4D — D4 Lattice

### Structure

```
D4 = { (x₁, x₂, x₃, x₄) ∈ ℤ⁴ : x₁ + x₂ + x₃ + x₄ ≡ 0 mod 2 }
```

Shortest vectors: all permutations of `(±1, ±1, 0, 0)` → length `√2` in ℤ⁴ embedding. Normalized so `a = 1`.

| Property | Value |
|---|---|
| Nearest-neighbor distance | `a` (normalized) |
| Kissing number | 24 |
| Packing radius | `r = a/2` |
| Self-dual | **Yes** (D4 = D4*) |

### Void Geometry

D4 has **one type of deep hole** — all voids are equivalent under the lattice symmetry group.

```
dist(lattice → hole center) = a / √2  ≈  0.7071·a

inscribed sphere radius      = (1/√2 − 1/2)·a  ≈  0.2071·a

ratio r_hole / r             = (√2 − 1)          ≈  0.4142
```

### Key Property: Self-Duality

D4 is self-dual: the dual lattice D4* is identical to D4 (up to scaling). This means:

> The void geometry and the lattice geometry are the **same object**.

The Voronoi cell of D4 is the **24-cell** — a regular 4D polytope with 24 vertices, 96 edges, 96 triangular faces, and 24 octahedral cells. Its 24 vertices coincide with the 24 kissing neighbors of the origin.

This is an exceptional property not shared by FCC. In D4, there is no geometric distinction between "lattice structure" and "gap structure."

---

## 8D — E8 Lattice

### Structure

E8 is the unique even self-dual lattice in 8 dimensions. It is most compactly defined as:

```
E8 = D8 ∪ (D8 + (1/2, 1/2, ..., 1/2))
```

where D8 is the 8D checkerboard lattice. Shortest vectors have length `√2` in the standard embedding. Normalized so `a = 1`.

| Property | Value |
|---|---|
| Nearest-neighbor distance | `a` (normalized) |
| Kissing number | 240 |
| Packing radius | `r = a/2` |
| Self-dual | **Yes** (E8 = E8*) |
| Packing density | `π⁴/384 ≈ 0.2537` |

The packing density is proven optimal for 8D (Viazovska, 2016).

### Void Geometry

E8 has **one type of deep hole**.

```
dist(lattice → hole center) = a / √2  ≈  0.7071·a

inscribed sphere radius      = (1/√2 − 1/2)·a  ≈  0.2071·a

ratio r_hole / r             = (√2 − 1)          ≈  0.4142
```

### Key Property: Self-Duality and Voronoi Cell

E8 is self-dual. Its Voronoi cell is the **Gosset polytope 4₂₁**, whose 240 vertices are exactly the 240 kissing neighbors — the same self-dual coincidence as D4, now in 8D.

---

## 24D — Leech Lattice Λ₂₄

### Structure

The Leech lattice is the unique even self-dual lattice in 24 dimensions with no vectors of length `√2` (in the standard integer embedding; shortest vectors have length 2). Normalized so `a = 1`.

| Property | Value |
|---|---|
| Nearest-neighbor distance | `a` (normalized) |
| Kissing number | 196,560 |
| Packing radius | `r = a/2` |
| Self-dual | **Yes** (Λ₂₄ = Λ₂₄*) |
| Packing density | `π¹²/12! ≈ 0.001930` |

The packing density is proven optimal for 24D (Cohn, Kumar, Miller, Radchenko, Viazovska, 2017).

### Void Geometry

The Leech lattice has **two types of deep holes**, but unlike FCC they are at the **same distance** from lattice points. They differ in the number and arrangement of nearest lattice points surrounding each hole.

```
dist(lattice → hole center) = a / √2  ≈  0.7071·a   (both types)

inscribed sphere radius      = (1/√2 − 1/2)·a  ≈  0.2071·a  (both types)

ratio r_hole / r             = (√2 − 1)          ≈  0.4142   (both types)
```

| Hole type | Nearest lattice points |
|---|---|
| Type 1 | 552 |
| Type 2 | 4,600 |

The two types are distinguished by the combinatorial structure of their neighborhood shells, not by distance.

---

## Unified Summary

All quantities normalized to nearest-neighbor distance `a = 1`.

| Lattice | Dim | Kissing # | Packing r | Void types | Void dist | Void r | Self-dual |
|---|---|---|---|---|---|---|---|
| FCC | 3 | 12 | `a/2` | 2 (distinct) | `a√6/4`, `a/√2` | `≈0.1124a`, `≈0.2071a` | No |
| D4 | 4 | 24 | `a/2` | 1 | `a/√2` | `≈0.2071a` | **Yes** |
| E8 | 8 | 240 | `a/2` | 1 | `a/√2` | `≈0.2071a` | **Yes** |
| Leech Λ₂₄ | 24 | 196,560 | `a/2` | 2 (same dist) | `a/√2` | `≈0.2071a` | **Yes** |

### Structural Observations

**FCC is the unique exception.** It is the only lattice in this family that:
- is not self-dual
- has two void types at *geometrically distinct distances*
- has a Voronoi cell (the RD) whose two vertex types map to those two void types

**D4, E8, and Leech share a single dominant pattern:**
```
void center distance  = a / √2  =  r · √2
void sphere radius    = (1/√2 − 1/2) · a  ≈  0.2071 · a
```

This arises directly from self-duality: in a self-dual lattice, the covering radius equals `r√2`.

**The Leech lattice is an intermediate case.** Like FCC it has two hole types; like D4 and E8 they are at the same distance. The distinction is combinatorial, not geometric.

---

## Exact Closed Forms

These are the exact algebraic expressions — no approximations.

### Packing radius (all lattices)
```
r = a / 2
```

### FCC tetrahedral void
```
dist   = a√6 / 4
r_tet  = a(√6 − 2) / 4   =  a(√6/4 − 1/2)
```

### FCC octahedral void / D4 / E8 / Leech (dominant void)
```
dist   = a / √2   =  a√2 / 2
r_void = a(√2 − 1) / 2   =  a(1/√2 − 1/2)
```

### FCC RD cell metrics
```
inradius      = a / 2
midradius     = a / √2   =  a√2 / 2
circumradius  = a√6 / 4
```

---

## Overlap Cap Geometry

When a sphere of radius `R > a/2` is placed at each lattice point, adjacent spheres overlap. The **cap depth** (how far each sphere extends past the midplane between two centers) is:

```
h = R − a/2
```

This is dimension-independent — it depends only on `R` and `a`, not on the ambient dimension.

### Critical overlap thresholds

| R/a | Geometric meaning |
|---|---|
| `1/2` | Spheres just touch — no overlap |
| `√6/4 ≈ 0.6124` | Sphere surface reaches FCC tetrahedral void center; also RD circumradius |
| `1/√2 ≈ 0.7071` | Sphere surface reaches octahedral void center (FCC) and dominant void (D4/E8/Leech) |
| `1` | Sphere surface reaches opposite nearest neighbor |

### Cap depth at the two critical radii

```
R = a√6/4   →   h = a(√6/4 − 1/2)  ≈  0.1124·a
R = a/√2    →   h = a(1/√2 − 1/2)  ≈  0.2071·a
```

Note: at `R = a/√2`, the cap depth `h` equals the void sphere radius. This is not a coincidence — it is another expression of the same algebraic identity `(1/√2 − 1/2)`.

### Implications for rendering

For procedural surface generation via overlapping spheres (as described in REFERENCE-PRISMAL-DEMO-000):

- Setting `R = a√6/4` causes sphere surfaces to pass through tetrahedral void centers — the tighter gap type in FCC.
- Setting `R = a/√2` causes sphere surfaces to pass through octahedral void centers — the dominant gap in FCC and the *only* void type in D4, E8, and Leech.
- The surface defined by the intersection of inflated spheres is therefore **controlled by a single ratio R/a**, with the two critical thresholds above marking qualitative transitions in surface topology.

---

## Dimensional Scaling

If a physical or simulation scale requires lattice spacing `a = s` (for some unit `s`), all derived quantities scale linearly:

| Quantity | Value |
|---|---|
| Packing radius | `s/2` |
| FCC tet void dist | `s√6/4` |
| Dominant void dist (all) | `s/√2` |
| RD inradius | `s/2` |
| RD midradius | `s/√2` |
| RD circumradius | `s√6/4` |

No quadratic or higher-order corrections arise — all geometry is Euclidean and scales exactly with `s`.

---

## Open Questions for This Record

- How should the two Leech hole types (same distance, different neighborhood) be treated in a simulation context — as effectively one type, or as a meaningful distinction?
- Does the self-duality of D4/E8/Leech suggest a natural way to represent the "void lattice" and the "sphere lattice" as the same data structure?
- For the FCC case: which void type (tet or oct) is the more natural "primary" for constraint placement? The oct void is larger and has higher symmetry (6 neighbors vs 4), but the tet void is closer.
- How does cap overlap topology change as R increases through the two critical thresholds? Does the surface remain simply connected?

---

## References

- Conway, J. H. & Sloane, N. J. A. *Sphere Packings, Lattices and Groups*. 3rd ed. Springer, 1999. (Primary source for all lattice properties.)
- Viazovska, M. "The sphere packing problem in dimension 8." *Annals of Mathematics* 185 (2017): 991–1015.
- Cohn, H., Kumar, A., Miller, S. D., Radchenko, D., & Viazovska, M. "The sphere packing problem in dimension 24." *Annals of Mathematics* 185 (2017): 1017–1033.

---

© 2011–present Milieu.Us © All rights reserved.
Milieu®, Prisml®, and Prisml Space® are trademarks of Milieu.Us.
