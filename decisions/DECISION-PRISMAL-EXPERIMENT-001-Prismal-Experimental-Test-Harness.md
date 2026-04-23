# DECISION-PRISMAL-EXPERIMENT-001 - Prismal Space Experiment - Experimental Test Harness

- **ID:** DECISION-PRISMAL-EXPERIMENT-001
- **Status:** Working Draft
- **Created:** 2026-04-06
- **Updated:** 2026-04-06

## Intent

Establish a minimal, repeatable test harness approach within the Prismal Unreal Engine Experimental project to support comparison across rendering regimes, while preserving fast iteration and clear interpretation.

---

## Context

Prismal experimentation requires evaluating:

- spatial continuity
- structural legibility
- perceptual coherence

Unreal Engine rendering systems (e.g., Lumen, Nanite) materially affect these observations.

Without structured comparison:

- results may be implicitly tied to rendering features
- dependencies may remain hidden
- decisions may not be reproducible across agents or time

A minimal harness is required to:

- compare identical scenes under different rendering conditions
- surface dependencies on rendering systems
- support lightweight, parseable decision capture

This approach emerges from Prismal experimentation and is not a generalized experimentation framework for Operations.

---

## Decision

### Test Harness Location

The test harness will be implemented within the **PrismalExperimental project**.

A separate host/test project is out of scope at this stage.

---

### Test Harness Structure (Minimal)

The harness consists of:

- one or more dedicated test maps, beginning with:

  * `Prismal_TestHarness_Main`

- a minimal harness actor or controller responsible for:

  * applying rendering/scalability profiles
  * executing deterministic camera paths

- fixed camera positions or sequences to ensure identical observation conditions

No additional testing framework is required at this stage.

---

### Profile-Based Comparison (Required)

The harness must explicitly apply named profiles.

It must not rely on editor defaults or implicit state.

At minimum:

**Reference Profile**

- Lumen enabled
- Nanite enabled
- high scalability

**Structural Profile**

- reduced or disabled Lumen contribution
- reduced or non-Nanite geometry where relevant
- lower scalability

Optional:

**Degraded Profile**

- aggressively reduced rendering support for stress testing

---

### Core Testing Principle

> Compare identical scene state under different projection regimes.

This requires:

- identical scene setup
- identical camera path
- only rendering/scalability differences between runs

---

### Observation Discipline (Minimal)

Observations may be captured as:

- screenshots
- short notes
- sketches or images
- lightweight markdown

Each observation must be parseable by another agent.

Minimum expectation:

- scene or context
- observed difference between profiles
- interpretation or implication

Formal records are only required when meaning changes materially.

---

### Dependency Posture

Unreal Engine features (e.g., Lumen, Nanite) are treated as:

> instrumental capabilities, not foundational assumptions

Prismal representations must remain interpretable under reduced rendering conditions.

Dependencies must be surfaced through comparison, not assumed.

---

## Consequences

**Positive**

- surfaces hidden rendering dependencies early
- supports repeatable comparison across agents
- preserves fast iteration with minimal structure

**Tradeoffs**

- requires explicit profile management
- introduces lightweight discipline in running comparisons
- observations remain partially manual at this stage

---

## References

RECORD-000 — Milieu Record System
REFERENCE-PRISMAL-000 — Current View and Open Questions
REFERENCE-PRISMAL-001 — Field, Lattice, and Projection — Working Model
REFERENCE-PRISMAL-002 — Structural Constraints, Joinery as Tests, and Playable Assembly
REFERENCE-PRISMAL-003 — Unified Lattice, Substrate, and Selection Model

---

## Follow-on

- introduce Functional Test integration when repetition increases
- add screenshot comparison for regression tracking
- introduce automated runs (e.g., Gauntlet) when required
- consider separate host project for plugin validation

---

## Addendum

> Capture fast. Parse clearly. Formalize when needed.
