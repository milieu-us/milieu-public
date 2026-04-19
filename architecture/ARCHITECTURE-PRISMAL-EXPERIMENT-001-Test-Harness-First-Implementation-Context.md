# ARCHITECTURE-PRISMAL-EXPERIMENT-001 - Test Harness - First Implementation Context

- **ID:** ARCHITECTURE-PRISMAL-EXPERIMENT-001
- **Status:** Working Draft
- **Created:** 2026-04-13
- **Updated:** 2026-04-18

> **Terminology note:** "profile" in this document always means a harness rendering profile — a named set of rendering and scalability conditions applied during a test run. This is distinct from the service sandbox profiles defined in REFERENCE-OPERATIONS-001, which use the same word for a different concept.

## Intent

Carry the implementation context needed by any agent — human, AI, or system — to begin implementing the Prismal™ test harness as decided in DECISION-PRISMAL-EXPERIMENT-001.

This document does not repeat the decision rationale. It does not provide a task list. It provides the structural constraints, relationships, and context that must survive handoff so that implementation work can continue well without loss of shared understanding.

## Current Engine Context

The current implementation uses Unreal Engine 5.7, within the PrismalExperimental project.

This is a contingent fact, not a foundational constraint. Future harness implementations may use other engines. Constraints in this document that are universal are marked as such. Constraints that are host-specific are marked accordingly.

## Module Structure

The PrismalExperimental project uses two modules. This structure is a prerequisite for all harness implementation work and must be established before any harness components are written.

**PrismalCore** — a pure C++ module with no host engine dependencies. This is where the substrate geometry and lattice view machinery lives, as specified in ARCHITECTURE-PRISMAL-001. It must not reference PrismalExperimental or any host engine type.

**PrismalExperimental** — the host engine module. This is where the harness components, adapter code, and all UE5-specific implementation lives. It depends on PrismalCore. PrismalCore does not depend on it.

The physical separation into two modules enforces the no-engine-dependencies constraint at build time rather than by convention. This is a deliberate choice: agents are better at respecting structural boundaries than social ones.

When PrismalCore eventually moves to a standalone library, it should require no changes to the Core code itself. If changes are needed at that point, the boundary was not being respected during the experimental phase.

**Universal constraint:** nothing in PrismalCore may include a host engine header or reference a host engine type, even while physically residing in the host project.

**UE5 constraint:** PrismalCore is registered as a separate module in the `.uproject` and has its own `Build.cs`. PrismalExperimental's `Build.cs` lists PrismalCore as a public dependency.

## Component Structure

The harness consists of two collaborating components. They are separated because their concerns are distinct and because either may need to be replaced or extended independently.

### Harness Controller

The Harness Controller is responsible for applying a named harness rendering profile to the current session and reporting that a profile has been applied.

Its concerns are:

- knowing which harness rendering profiles exist
- applying the correct conditions for a named harness rendering profile
- making the active harness rendering profile observable (logged, visible, or otherwise inspectable)

It is not responsible for camera movement, scene setup, or observation capture.

**Universal constraint:** the Harness Controller must apply harness rendering profiles explicitly. It must not read or rely on ambient engine state.

**UE5 constraint:** profile application is implemented through Scalability settings and Console Variable (CVar) overrides. These must be set programmatically at runtime, not relied upon from editor project settings.

### Camera Path Actor

The Camera Path Actor is responsible for moving through a defined sequence of positions and orientations so that identical viewpoints are observed under each profile.

Its concerns are:

- holding a defined sequence of transforms
- executing that sequence deterministically
- signaling when a sequence is complete

It is not responsible for profile application or observation capture.

**Universal constraint:** the camera path must be fully deterministic. Given the same sequence definition, the path must produce identical viewpoints on every run.

## Harness Rendering Profile Schema

Each harness rendering profile defines a complete set of rendering and scalability conditions. A harness rendering profile is not a delta from a default — it is a full specification.

Current harness rendering profiles required by DECISION-PRISMAL-EXPERIMENT-001:

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

- harness rendering profile name applied
- engine and project version
- timestamp
- one or more viewpoint captures (screenshots or equivalent)
- a stub observation record ready for interpretation

The stub observation record format is not yet formalized. Until it is, the minimum is a markdown file containing the above fields with interpretation left blank.

This is intentionally minimal. Formalization is deferred until patterns emerge from actual use.

Harness observation runs are also expected to produce early evidence toward the open question in REFERENCE-OPERATIONS-001 of how Unreal Engine workflows integrate with Milieu's service sandbox model. Agents working on that question should treat harness observations as a relevant data source.

## Relationships Between Components

The Harness Controller and Camera Path Actor are independent actors. They coordinate through a simple sequencing contract:

1. Harness Controller applies harness rendering profile
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
- ARCHITECTURE-PRISMAL-001 - Prismal Core First Implementation Context
- DECISION-PRISMAL-EXPERIMENT-001 - Prismal Experimental Test Harness
- DECISION-PRISMAL-EXPERIMENT-000 - Initial Architecture Spike and Layering Constraints
- REFERENCE-DEVEX-UNREAL-000 - Developer Experience for Unreal Engine
- REFERENCE-OPERATIONS-001 - Service Sandbox Profiles
