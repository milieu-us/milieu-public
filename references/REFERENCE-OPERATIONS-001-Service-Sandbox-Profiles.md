# REFERENCE-OPERATIONS-001 - Service Sandbox Profiles

- **ID:** REFERENCE-OPERATIONS-001
- **Status:** Working Draft
- **Created:** 2026-04-14
- **Updated:** 2026-04-14

## Intent

Establish a minimal, shared understanding of how Milieu defines and uses sandboxed service environments across local and cloud systems.

This note explores:
- how isolation is applied across work types
- how development tooling interacts with sandboxed environments
- how to balance security, reproducibility, and developer experience

This is not a final decision.

It is a working model to guide early implementation and experimentation.

## Context

Milieu requires:

- reproducible environments across local and cloud systems
- isolation for services and agent execution
- support for multiple runtimes:
  - V8-based runtimes (likely Deno / TypeScript)
  - Rust
  - Python (LLM / EBRM data work)
  - C++ (Prismal and Unreal Engine)
- compatibility with full-featured IDEs (for example, JetBrains Rider)

Constraints:

- host security posture should remain strong (no broad exclusions)
- agent execution may involve untrusted or partially trusted code
- Unreal Engine workflows impose additional constraints (GPU, editor interactivity)

## Problem

Define a system that:

- allows developers to work efficiently using modern IDEs
- ensures services run in controlled, reproducible environments
- supports multiple levels of isolation depending on risk
- avoids over-centralizing all work into a single heavy platform

## Work Types

Milieu work spans multiple domains with different runtime, latency, and isolation requirements.

These work types inform which sandbox profile and execution lane should be used.

This classification is intentionally minimal and may evolve.

### 1. Interactive Simulation and Tooling (Unreal Engine)

Examples:
- Unreal Editor usage
- C++ gameplay and system development
- real-time visualization and testing

Characteristics:
- highly interactive
- latency-sensitive
- GPU-bound
- tightly coupled to editor and runtime state

Implications:
- not well suited to heavy sandboxing for primary workflows
- best supported via local or remote workstation environments
- supporting tasks such as builds, packaging, and validation may run in controlled environments

### 2. Service Development (Deno / Rust / TypeScript)

Examples:
- backend services
- orchestration layers
- APIs
- internal tooling

Characteristics:
- well-defined inputs and outputs
- reproducible builds
- minimal GPU dependency

Implications:
- strong fit for container-based sandboxing
- suitable for both local and cloud execution

### 3. Data and Model Work (Python, LLM / EBRM)

Examples:
- dataset construction
- model evaluation and analysis
- fine-tuning

Characteristics:
- batch-oriented or semi-interactive
- high I/O and storage usage
- dependency variability

Implications:
- requires controlled environments with explicit dependency isolation
- containerization is a strong default, with attention to data and cache management

### 4. Agent Execution and Automation

Examples:
- agent-driven code generation or modification
- automated evaluation runs
- external data ingestion

Characteristics:
- partially trusted or untrusted execution
- non-deterministic behavior

Implications:
- requires the strongest isolation
- suited for microVM-based execution and ephemeral environments

### 5. Documentation and Governance Work

Examples:
- DR / ADR authoring
- record maintenance
- proposal and specification work

Characteristics:
- text-centric
- low resource requirements

Implications:
- can run in lightweight environments
- strong candidate for AI-assisted workflows

### 6. Core Library and Constraint Work (C++ / Prismal)

Examples:
- Prismal lattice and constraint systems
- geometric and mathematical primitives
- simulation-independent core libraries

Characteristics:
- can be interactive or headless
- deterministic and testable
- often CPU-bound

Modes of operation:

#### Interactive

- IDE-assisted development
- debugging and integration work

#### Headless

- CLI-driven builds and tests
- agent-assisted workflows
- batch validation

Implications:
- should support both modes cleanly
- suitable for controlled build and test environments
- should avoid unnecessary coupling to:
  - engine runtime
  - editor-specific assumptions
  - a single output or integration target

## Interaction Modes

Work may be executed in different interaction modes:

- Interactive: human-driven, IDE-based
- Headless: agent-driven or scripted

Implication:

Sandbox selection depends on both work type and interaction mode.

## Current Working Model

Milieu separates concerns into execution lanes.

### Human Development Lane

- IDE connects to a local or remote development environment

Characteristics:
- interactive
- optimized for developer experience

### Service and Build Lane

- services and builds run in controlled environments

Characteristics:
- reproducible
- suitable for local and cloud execution

### High-Isolation Agent Execution Lane

- uses microVM-based isolation

Characteristics:
- strong isolation
- ephemeral execution

## Service Sandbox Profiles

Each service type defines a profile with:

- runtime
- permissions
- mount policy
- cache policy
- network policy

Profiles are intentionally minimal and may evolve.

## IDE Integration

- IDEs are treated as clients, not environment authorities
- environments are defined by repository configuration

Implication:

This preserves developer experience without weakening system boundaries.

## Security Posture

- host-level protections remain enabled by default
- broad directory exclusions are discouraged
- higher-risk work should move into more isolated environments

Isolation increases with risk:

Human Development < Service Environments < MicroVM Execution

## Observations

- different work types require different isolation strategies
- Unreal workflows require a hybrid model
- core library work spans both interactive and headless modes
- service and data workflows align well with controlled environments
- agent execution introduces distinct trust requirements
- separating source, build artifacts, and caches is critical
- sandboxing overhead is acceptable when aligned with workload

## Open Questions

- What is the minimal required sandbox definition schema?
- How are secrets managed across lanes?
- How are artifacts promoted between lanes?
- When should execution escalate from container to microVM?
- How should Unreal workflows integrate with this model?

## Next Steps

- implement an initial development environment for one service
- define one executable sandbox profile
- test local and controlled execution workflows
- evaluate microVM integration for agent execution

## Notes

This model emphasizes:

- reproducibility
- explicit constraints
- flexibility across work types and targets