# FCC Lattice Planet — Reference Document

## 1. Core Concept

**Objective:**  
Build a procedurally generated planet using a **distance-preserving FCC lattice**, where all geometry, features, and procedural biomes emerge from **constraints + lattice rules**, without storing the full planet data.

**Key Principles:**

- Use spheres as building blocks; the **distance between sphere centers is exact and constant**.
- Expand spheres to **spherical caps**, then overlap symmetrically to define the surface.
- Two distinct overlap types naturally arise from the FCC lattice:
  - **Tetrahedral intersections** → smaller gaps
  - **Octahedral intersections** → larger gaps
- Constraints + rules at each node control emergent features (biomes, terrain, micro-scale elements).
- Scaling is simple: precompute the lattice once in 3D, then apply uniform scaling for any planet size.

**Extensions:**

- The same lattice-based approach scales to higher dimensions: 4D (D4 lattice), 8D (E8 lattice), 24D (Leech lattice).
- The duality between node types (3-connection vs 4-connection) mirrors energy dispersing vs conserving behaviors and storage vs flow interpretations in the system.

---

## 2. Geometry & Lattice

**FCC Lattice Properties:**

- All sphere centers are equidistant.
- Neighbor relationships define **constraints** for procedural generation.
- Dual lattice: BCC (useful for Cartesian conversions or interpolation).

**Implementation Notes:**

- Lattice basis vectors define the canonical structure.
- Neighbor tables should be precomputed for all lattice points.
- Barycentric coordinates can be used for **interpolation within tetrahedral cells**.
- Surface emerges from intersection of FCC spheres with the planetary radius boundary.
- Boundary cells may have incomplete symmetry but can follow the same rules.

---

## 3. Procedural System

**Node Types:**

| Node Type | Connections | Behavior |
|-----------|------------|----------|
| Type A (3 connections) | tetrahedral-like | storage, sticky, constrained, dense biomes |
| Type B (4 connections) | octahedral-like | dispersal, flow, open features |

**Macro-scale (orbit / distant view):**

- Render spherical caps representing lattice nodes.
- Use LOD to reduce computation for distant observation.
- Merge overlapping caps to produce smooth surface.

**Micro-scale (surface / interior):**

- Subdivide lattice cells dynamically.
- Use procedural meshes/metaballs for small features (biomes, terrain, microbes).
- Feature placement is deterministic and tied to parent lattice rules.

**Constraint-based design:**

- All behavior emerges from **local lattice constraints**, not stored global data.
- Two pipeline integration:
  - Macro: instanced spherical caps.
  - Micro: on-demand procedural expansion.

---

## 4. Rendering Pipeline

**Two Levels:**

1. **Macro Pipeline:**
   - Lattice points → spherical caps
   - Efficient instanced rendering
   - Determines planetary shape and biome regions

2. **Micro Pipeline:**
   - Subdivide lattice cells → procedural meshes
   - Apply node constraints and rules
   - Integrate local detail dynamically

**Optimization:**

- GPU instancing
- Compute shaders for procedural geometry
- Octree/BVH for spatial partitioning
- Deterministic generation ensures reproducibility

---

## 5. Implementation Notes

- Precompute FCC lattice + neighbor relationships once.
- Scaling factor applies to all derived structures.
- Intersections define **exact gap sizes**; only two types exist per lattice configuration.
- Surface tiling is **emergent**, not pre-defined; no pentagon/hexagon compromise is needed.
- Supports extension to higher dimensions by swapping in canonical dense lattices.

---

## 6. Key Advantages

- **Exact distances between centers** → predictable overlaps
- **Two exact gap types** → controllable feature placement
- **Constraint-based rules** → no global data storage required
- **Scalable across planets and dimensions**
- **Emergent surface features** → real-time rendering possible

---

## 7. Future Work / Next Steps

1. Derive **exact ratios** for sphere radius vs center spacing to control overlaps precisely.
2. Define lattice basis + neighbor tables in Unreal Engine.
3. Implement macro pipeline for spherical caps.
4. Implement micro pipeline for surface and subsurface procedural features.
5. Optional: explore barycentric coordinates for interpolation inside lattice cells.
6. Extend to higher-dimensional lattices if needed for research or procedural algorithms.

---

## 8. Notes for Next Agent

- This document serves as a **complete context handoff**.
- All subsequent work assumes:
  - FCC lattice as canonical 3D structure
  - Two node types with exact constraints
  - Dual rendering pipelines
  - Scaling is linear, no area or shape compromises
- No assumptions about previous trial-and-error with hex/pent tiling, wrapping, or warped surfaces.
- Focus on **constraint + lattice-first approach**, procedural emergence second.