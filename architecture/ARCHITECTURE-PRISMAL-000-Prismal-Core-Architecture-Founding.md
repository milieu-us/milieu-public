# ARCHITECTURE-PRISMAL-000 - Prismal Core — Architecture Founding

- **ID:** ARCHITECTURE-PRISMAL-000
- **Status:** Working Draft
- **Created:** 2026-04-13
- **Updated:** 2026-04-13

## Intent

Establish the founding architecture context for all Prismal™ Core library work.

This document is the first anchor in the ARCHITECTURE-PRISMAL family. Agents working on any Prismal Core implementation — regardless of language, engine, or host environment — should read this first.

## Context

The DECISION-PRISMAL family establishes why Prismal Core exists and what it is committed to. This document carries the implementation context that must survive handoff so that work on Core can continue well.

REFERENCE-PRISMAL-001 establishes that Prismal Space is a discrete realization of an underlying continuum. REFERENCE-PRISMAL-003 establishes that named lattice structures are views over a shared substrate, not independent foundational systems. REFERENCE-PRISMAL-GEOMETRY-000 establishes the exact sphere geometry ratios that govern those views. These three references are the primary sources for any agent working on Core.

## What Core Is

Prismal Core is the engine-agnostic library that holds the substrate geometry and lattice view machinery for Prismal Space.

It is not a game engine module. It is not a rendering system. It is not a simulation framework. Those things are adapters and explorations built on top of Core.

Core exists because the substrate geometry and selection logic must be expressible, testable, and reasoned about independently of any engine or platform. If Core cannot be understood and verified without an engine, it is not Core — it has leaked into the adapter layer.

## Foundational Constraints

These constraints apply to all Prismal Core work. They derive from the REFERENCE-PRISMAL family and must not be silently violated by implementations or later documents.

### No engine dependencies

Core must not include engine headers, depend on engine types, or rely on engine lifecycle. This constraint holds even when Core physically lives inside an engine project during early development. Discipline enforces the boundary now; the build system enforces it later when Core moves to a standalone library.

### Nothing implicit

Lattice views, selection rules, and unit scale are explicit parameters passed through the call chain. No global lattice state. No ambient configuration. An agent reading Core code must be able to determine the active lattice view from the call site alone.

This derives directly from REFERENCE-PRISMAL-001's treatment of coordinate systems as projections, not foundations. Making the view implicit would silently encode a foundational assumption that the system explicitly rejects.

### Scale agnosticism

Core operates in units of the nearest-neighbor distance `a`. Physical or simulation scale is injected by the caller. Core contains no hard-coded units. This derives from REFERENCE-PRISMAL-GEOMETRY-000's normalization convention.

### Views are not the substrate

Named lattices — FCC, SC, BCC — are selections over the shared substrate, not independent structures. An implementation that treats them as separate systems has misread the model. REFERENCE-PRISMAL-003 is the authoritative source on this constraint.

### Computation before storage

Core's first responsibility is to answer questions about the substrate correctly. Storage of site state is a separate concern and must not pollute the substrate geometry layer.

## The Adapter Contract

Any engine or platform that consumes Core must provide:

- a unit scale `a` — the distance in host-space units corresponding to one nearest-neighbor step
- a coordinate mapping — how Core's current first-implementation integer carrier coordinates map to positions in the host environment

Core does not provide these. They are injected by the adapter.

Core must not make assumptions about the host coordinate system. REFERENCE-PRISMAL-001 establishes that coordinate systems are projections, not foundations.

The first adapter is currently being built for Unreal Engine 5 within the PrismalExperimental project. The adapter contract is not yet expressed as a formal interface. It will be formalized when a second host environment is added and the pattern is confirmed by evidence.

## What This Family Does Not Cover

- Host-specific adapter implementations (see ARCHITECTURE-PRISMAL-EXPERIMENT family and future host-specific families)
- Day-to-day operations for building and running Core (see OPERATIONS domain records when established)
- Decisions about which lattice view Prismal uses canonically (see DECISION-PRISMAL family)
- Play, interaction, and exploration systems built on top of Core (see REFERENCE-PRISMAL-INTERACTION family)

## Open Questions

- When Core moves to a standalone library, what is the minimal build system requirement that remains host-agnostic?
- Should the adapter contract be expressed as a formal interface in Core itself, or left to convention until a second host environment requires it?

## Related

- REFERENCE-PRISMAL-001 — Field, Lattice, and Projection
- REFERENCE-PRISMAL-003 — Unified Lattice Substrate and Selection Model
- REFERENCE-PRISMAL-GEOMETRY-000 — Sphere Geometry Derivation
- ARCHITECTURE-PRISMAL-001 — First Implementation Context
- ARCHITECTURE-PRISMAL-EXPERIMENT-000 — Test Harness Architecture Founding
