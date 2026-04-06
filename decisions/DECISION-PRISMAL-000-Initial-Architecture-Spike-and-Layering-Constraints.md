# DECISION-PRISMAL-000

## Prismal Space — Initial Architecture Spike and Layering Constraints

ID: DECISION-PRISMAL-000
Status: Working Draft
Created: 2026-04-05
Updated: 2026-04-05

## Intent

Establish the initial direction for Prismal Space development by defining:

- the purpose of the first deep architecture spike,
- the separation of concerns between core, engine, and exploration layers,
- the constraints required to support partial-context human agents, AI agents, and system agents,
- and the conditions necessary to support future persistence, networking, multi-engine realization, and compositional integrity across scales.

This decision guides early work without prematurely fixing architecture or interfaces.

## Decision

We will conduct an initial deep architecture spike using a constrained scenario:

> Represent a planetary-scale structure and support traversal from planetary view to surface detail.

This scenario is a stress case to reveal required structure, boundaries, and constraints within Prismal Space, not a final product goal.

To support this, we will:

1. **Separate Prismal Space into distinct layers**
   - Core (authoritative structure and constraints)
   - Engine adapters (e.g., Unreal, future engines)
   - Exploration / demo implementations (e.g., Prismal Starter, experimental demos)

2. **Prioritize authoritative state above engine realization**
   - Prismal Core defines what is true
   - Engine layers derive realizations from that truth
   - Engine representations must not become the sole source of truth

3. **Support partial-context orchestration**
   - Work must be decomposable into units understandable with limited context
   - Contracts and validation must be locally legible

4. **Prefer numeric and structural validation before visual trust**
   - Correctness is established through math and structure
   - Rendering is a secondary confirmation

5. **Allow multiple exploration paths**
   - The same underlying Prismal state may support multiple interpretations
   - No single demo approach defines the core model

6. **Allow exploration without contaminating core truth**
   - Exploration may experiment freely
   - Core contracts must not be implicitly redefined

7. **Defer detailed architecture and interfaces**
   - Exact boundaries and formats emerge through implementation and validation
   - All must remain consistent with constraints defined here

## Rationale

The planet → surface traversal scenario is simple in description but broad in implications. It pressures:

- scale transitions
- boundary consistency
- coarse vs fine representation
- engine adaptation
- future persistence and synchronization

Development will occur across multiple human agents, AI agents, and system agents with limited context. Without clear constraints and separation, work risks becoming inconsistent or overly dependent on engine assumptions.

This approach enables multiple exploration strategies to test the same underlying structure.

## Exploration Context (Non-Binding)

The planetary scenario should aim to be Earth-like in character, where helpful for evaluation.

This may include:

- recognizable land/ocean distribution
- large-scale regional variation
- plausible transitions between regions (e.g., arid, temperate, cold)
- surface features legible to human observers

**Purpose:**

- Provide a familiar reference frame for evaluating composition across scales
- Improve interpretability for human agents and AI agents
- Make boundary and regional behavior easier to assess

**Constraint:**

- Earth-like characteristics are guidance for interpretation, not requirements
- The system must not depend on Earth-specific assumptions or models

## Exploration Options (Non-Binding)

The spike may be explored through multiple derived strategies. These must not constrain core design.

### Option A — Elevation-First Composition

- Focus on planetary shape and elevation
- Minimal regional classification
- Emphasis on boundary continuity and scale transitions

### Option B — Derived Biome Classification (simplified Holdridge-style)

- Use a small set of continuous input fields (e.g., temperature proxy, moisture proxy, elevation influence)
- Map to discrete regional classifications
- Treat biomes as a derived interpretive layer, not authoritative state
- No simulation or temporal evolution required

**Purpose:**

- Provide mid-scale composition between planetary and local detail
- Test stability and legibility of regions across scales
- Evaluate boundary coherence and inheritance

### Option C — Alternative Regionalization Strategies

- Noise-based grouping
- Rule-based systems
- Lattice-driven partitioning
- Other experimental approaches

**Purpose:**

- Compare different approaches to mid-scale structure
- Ensure Prismal is not coupled to a single model

## Constraints

### Layer Separation

- Authoritative Prismal state must remain separate from engine realization
- Engine layers should be thin and derived

### Authority and Derivation

- Stored or synchronized state should be minimized and, where possible, deterministic
- Derived detail must not redefine authoritative state
- Regional or biome-like representations must remain derived layers unless explicitly elevated

### Boundary and Scale Awareness

- The system must support reasoning about:
  - region boundaries
  - authority handoff
  - scale transitions

- Coarse state remains authoritative unless explicitly delegated

### Agent Legibility

- Components should be understandable in isolation
- Contracts must be small, explicit, and testable

### Validation First

- Structural validation must not require engine context
- Rendering is not required for correctness

### Exploration Safety

- Exploration must consume core contracts
- Experiments must not corrupt shared understanding

### Future Compatibility (Deferred but Required)

The design must not preclude:

- persistence and replay
- networking and synchronization
- multi-engine support
- region and scale handoffs

## Considered

### Single Unified Project

Rejected due to:

- context overload
- poor isolation
- reduced effectiveness for agent workflows

### Engine-First Development

Rejected due to:

- risk of engine becoming source of truth
- poor adaptability for persistence and networking

### Fully Defined Architecture Upfront

Rejected due to:

- lack of validation
- premature constraint
- reduced adaptability

## Deferred

- Repository structure and boundaries
- Interface definitions and data formats
- Persistence and networking models
- Authority ownership models
- Engine-specific details

Additionally:

- Discrete construction and joinery-based assembly will be explored in a subsequent spike to validate constraint-based composition at small scales

## References

- RECORD-000 — Milieu Record System
- REFERENCE-PRISMAL-001 — Field, Lattice, and Projection — Working Model
- REFERENCE-PRISMAL-002 — Structural Constraints, Joinery as Tests, and Playable Assembly
- REFERENCE-PRISMAL-DEMO-000 — Planet Biome Demo Proposal

## Notes

This decision establishes direction and constraints, not final form.

Architecture will emerge through:

- small validated experiments
- iterative refinement
- coordination across human agents, AI agents, and system agents

The same underlying Prismal state is expected to support multiple valid interpretations and realizations.
