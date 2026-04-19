# ARCHITECTURE-PRISMAL-EXPERIMENT-000 - Prismal Experimental Test Harness - Architecture Founding

- **ID:** ARCHITECTURE-PRISMAL-EXPERIMENT-000
- **Status:** Working Draft
- **Created:** 2026-04-13
- **Updated:** 2026-04-18

> **Terminology note:** "profile" in this document always means a harness rendering profile — a named set of rendering and scalability conditions applied during a test run. This is distinct from the service sandbox profiles defined in REFERENCE-OPERATIONS-001, which use the same word for a different concept.

## Intent

Establish the founding architecture context for all experimental test harness work under the Prismal™ project.

This document is the first anchor in the ARCHITECTURE-PRISMAL-EXPERIMENT family. Agents should read this first when working on any test harness implementation, regardless of which engine or platform is currently in use.

## Context

DECISION-PRISMAL-EXPERIMENT-000 established that Prismal development proceeds through constrained experiments organized into three layers: Core, Engine Adapters, and Exploration. DECISION-PRISMAL-EXPERIMENT-001 established that experimental work requires a structured test harness to support comparison across rendering regimes using named harness rendering profiles.

This architecture family carries the implementation context needed to work within those decisions. It does not restate the decisions or their rationale. It exists because the gap between a decision and working code is where shared understanding most often gets lost.

## Scope of This Family

The ARCHITECTURE-PRISMAL-EXPERIMENT family covers:

- the structure of the test harness and its components
- the constraints that apply to harness implementations
- the carried context needed by agents implementing or extending the harness

This family is engine-agnostic in principle. The current implementation uses Unreal Engine 5. Future implementations may use other engines. Architecture documents in this family should distinguish clearly between constraints that are universal and constraints that are engine-specific.

## Foundational Constraints

The following constraints apply to all experimental test harness work. They derive from DECISION-PRISMAL-EXPERIMENT-000 and DECISION-PRISMAL-EXPERIMENT-001 and must not be silently violated by later documents or implementations.

### Harness Isolation

The test harness exists to compare Prismal behavior across different conditions. It must not itself become a source of uncontrolled variation.

Harness components must be simple, explicit, and inspectable.

### Harness Rendering Profile Explicitness

Rendering and scalability conditions must be applied through named, explicitly defined harness rendering profiles.

Implicit reliance on editor defaults or ambient state is not permitted.

### Scene Invariance

The scene under test must be identical across harness rendering profile runs. Only the applied harness rendering profile may vary between comparison runs.

### Observation Parsability

Observations produced by or during a harness run must be parseable by another agent — human, AI, or system — without requiring access to the originating agent's context.

### Engine as Adapter

The engine is an adapter for Prismal Core, not the source of truth. Harness implementations must not treat engine state or engine defaults as authoritative Prismal state.

## What This Family Does Not Cover

- Prismal Core architecture (see ARCHITECTURE-PRISMAL family)
- Day-to-day operations for running experiments (see OPERATIONS domain records when established)
- Engine-specific setup and tooling beyond what is needed to understand implementation constraints

## Open Questions

- Should engine-specific architecture documents live under this family (e.g., ARCHITECTURE-PRISMAL-EXPERIMENT-UE5-000) or should engine specifics be carried within numbered documents like ARCHITECTURE-PRISMAL-EXPERIMENT-001?
- When does an experimental harness finding warrant promotion to a constraint in this founding document?

## Related

- DECISION-PRISMAL-EXPERIMENT-000 - Initial Architecture Spike and Layering Constraints
- DECISION-PRISMAL-EXPERIMENT-001 - Prismal Experimental Test Harness
- ARCHITECTURE-PRISMAL-EXPERIMENT-001 - Test Harness - First Implementation Context
- REFERENCE-PRISMAL-000 - Prismal Space Current View and Open Questions
- REFERENCE-PRISMAL-003 - Unified Lattice Substrate and Selection Model
