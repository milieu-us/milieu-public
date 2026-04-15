# ARCHITECTURE-PRISMAL-EXPERIMENT-001 - Test Harness - First Implementation Context

- **ID:** ARCHITECTURE-PRISMAL-EXPERIMENT-001
- **Status:** Working Draft
- **Created:** 2026-04-13
- **Updated:** 2026-04-13

## Intent

Carry the implementation context needed by any agent — human, AI, or system — to begin implementing the Prismal™ test harness as decided in DECISION-PRISMAL-EXPERIMENT-001.

This document does not repeat the decision rationale. It does not provide a task list. It provides the structural constraints, relationships, and context that must survive handoff so that implementation work can continue well without loss of shared understanding.

## Current Engine Context

The current implementation uses Unreal Engine 5.7, within the PrismalExperimental project.

This is a contingent fact, not a foundational constraint. Future harness implementations may use other engines. Constraints in this document that are universal are marked as such. Constraints that are Unreal-specific are marked accordingly.

## Component Structure

The harness consists of two collaborating components. They are separated because their concerns are distinct and because either may need to be replaced or extended independently.

### Harness Controller

The Harness Controller is responsible for applying a named profile to the current session and reporting that a profile has been applied.

Its concerns are:

- knowing which profiles exist
- applying the correct conditions for a named profile
- making the active profile observable (logged, visible, or otherwise inspectable)

It is not responsible for camera movement, scene setup, or observation capture.

**Universal constraint:** the Harness Controller must apply profiles explicitly. It must not read or rely on ambient engine state.

**UE5 constraint:** profile application is implemented through Scalability settings and Console Variable (CVar) overrides. These must be set programmatically at runtime, not relied upon from editor project settings.

### Camera Path Actor

The Camera Path Actor is responsible for moving through a defined sequence of positions and orientations so that identical viewpoints are observed under each profile.

Its concerns are:

- holding a defined sequence of transforms
- executing that sequence deterministically
- signaling when a sequence is complete

It is not responsible for profile application or observation capture.

**Universal constraint:** the camera path must be fully deterministic. Given the same sequence definition, the path must produce identical viewpoints on every run.

## Profile Schema

Each named profile defines a complete set of rendering and scalability conditions. A profile is not a delta from a default — it is a full specification.

Current profiles required by DECISION-PRISMAL-EXPERIMENT-001:

### Reference Profile

Represents the highest-fidelity rendering conditions available in the current environment.

- Lumen: enabled
- Nanite: enabled
- Scalability: high (engine quality group 3 or equivalent)

Purpose: establish the visual baseline against which reduced profiles are compared.

### Structural Profile

Represents a reduced rendering configuration that removes or minimizes dynamic global illumination contributions, to isolate Prismal structural legibility from lighting quality.

- Lumen: disabled or contribution minimized
- Nanite: disabled or non-Nanite geometry used where relevant
- Scalability: reduced (engine quality group 1 or equivalent)

Purpose: test whether Prismal representations remain legible and interpretable without high-fidelity rendering.

### Degraded Profile (optional)

Represents an aggressively reduced configuration for stress testing.

- Rendering support: minimal
- Scalability: lowest available

Purpose: surface any hard dependencies on rendering features that are not apparent at the Structural level.

## CVar Reference (UE5-specific)

The following console variables are the current implementation mechanism for Lumen and Nanite control. This list is a working reference, not a complete specification. Agents implementing the harness should verify current UE5 documentation for their engine version.

Lumen control:

- `r.Lumen.Reflections.Allow` — set to 0 to disable Lumen reflections
- `r.Lumen.DiffuseIndirect.Allow` — set to 0 to disable Lumen diffuse indirect
- `r.DynamicGlobalIlluminationMethod` — set to 0 for None, 1 for Lumen

Nanite control:

- `r.Nanite.ProjectEnabled` — set to 0 to disable Nanite globally for the session

Scalability groups (UE5 `Scalability::SetQualityLevels`):

- `sg.ShadowQuality`, `sg.TextureQuality`, `sg.PostProcessQuality`, `sg.EffectsQuality`, `sg.FoliageQuality`, `sg.ShadingQuality`
- Values: 0 (low), 1 (medium), 2 (high), 3 (epic/cinematic)

**Constraint:** CVar values must be applied after engine initialization and before the first rendered frame of the test sequence. Timing of application must be explicit and verifiable.

## Observation Output

Each harness run must produce output that is parseable by another agent without access to the originating agent's session context.

Minimum required per run:

- profile name applied
- engine and project version
- timestamp
- one or more viewpoint captures (screenshots or equivalent)
- a stub observation record ready for interpretation

The stub observation record format is not yet formalized. Until it is, the minimum is a markdown file containing the above fields with interpretation left blank.

This is intentionally minimal. Formalization is deferred until patterns emerge from actual use.

## Relationships Between Components

The Harness Controller and Camera Path Actor are independent actors. They coordinate through a simple sequencing contract:

1. Harness Controller applies profile
2. Harness Controller signals ready
3. Camera Path Actor executes sequence
4. Camera Path Actor signals complete
5. Observation output is captured

This sequencing must be explicit. Neither component should assume the other has acted without an observable signal.

**UE5 implementation note:** this coordination may be implemented through Blueprint event bindings, a simple C++ delegate, or a controlling Game Mode. The mechanism is not yet decided. What must be preserved is that the sequencing is observable and not implicit.

## What Is Not Specified Here

The following are intentionally deferred. They will be addressed in later documents, OPERATIONS records, or through the decisions that emerge from actual harness runs.

- Exact class names and file locations (these belong in code and code comments, not here)
- Automated comparison or regression tooling
- Integration with Gauntlet or other test frameworks
- Repository structure for storing observation outputs
- The formalized observation record format

## Open Questions

- Should the Camera Path Actor hold its transform sequence as a data asset, or as inline UPROPERTY values? The tradeoff is editor visibility versus simplicity.
- What is the right signal mechanism between Harness Controller and Camera Path Actor given that the project currently has no custom subsystems?
- Should observation stubs be committed to the PrismalExperimental repo or to milieu-public?

## Related

- ARCHITECTURE-PRISMAL-EXPERIMENT-000 - Founding document for this family
- DECISION-PRISMAL-EXPERIMENT-001 - Prismal Experimental Test Harness
- DECISION-PRISMAL-EXPERIMENT-000 - Initial Architecture Spike and Layering Constraints
- REFERENCE-DEVEX-UNREAL-000 - Developer Experience for Unreal Engine
