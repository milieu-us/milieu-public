# REFERENCE-SYSTEMS-001 — Knowledge, State, and Representation Substrates

- ID: REFERENCE-SYSTEMS-001
- Status: Working Draft
- Created: 2026-04-12
- Updated: 2026-04-12

## Intent

Establish a shared reference for thinking about knowledge, state, and representation across Milieu.

This record exists to capture current findings and explicit unknowns about how Milieu may need to represent and preserve multiple kinds of truth across institutional knowledge, shared experiences, simulation, and other future work.

This is not a decision record and does not select an architecture.

## Context

Milieu is not only building a language-facing record system.

Milieu is also exploring shared experiences where people, AI agents, and systems participate together in world-like spaces, with an interest in archives that support return, reinterpretation, and continuation.

The current record system makes language first-class for shared reasoning across agents. That is necessary, but it is not sufficient for all state Milieu expects to handle.

The current Prismal work also already assumes that multiple representations may coexist, that different truths may have different authoritative sources, and that some important representations may be based on fields, flows, structures, vectors, or other non-language forms.

## Why This Work Exists

Milieu is trying to support continuity and shared understanding across changing agents, tools, systems, and conditions.

That requires more than preserving documents.

It requires a way to reason about:

- what is held to be true,
- what is observed,
- what is inferred,
- what changes over time,
- what differs by viewpoint,
- and what cannot be adequately represented as language alone.

This work therefore sits at the intersection of:

- institutional memory,
- agent coordination,
- simulation and world-state,
- experience and interpretation,
- and archives that support later return and reinterpretation.

## Current Findings

### 1. This is not a single representation problem

The systems reviewed so far do not suggest one universal substrate.

Instead, they cluster around different strengths:

- semantic and collaborative knowledge systems,
- preservation-oriented repository systems,
- real-time operational state systems,
- and multidimensional or vector-valued state systems.

### 2. Language-based knowledge is only one part of the larger picture

Language remains first-class for records, interpretation, coordination, and shared reasoning.

However, many Milieu concerns appear likely to involve important state or function that is not naturally language-shaped, including:

- simulation state,
- geometry and adjacency,
- fields and flows,
- embeddings or other vectors,
- material or runtime conditions,
- and experiential or embodied signals.

### 3. Different truth classes may require different authoritative representations

Current Milieu and Prismal work already suggests that material state, agent state, narrative state, governance state, and social state may not share the same storage model, update cadence, or projection rules.

### 4. Projection is a first-class concern

When one representation is derived from another, the hard problem is not merely storage.

The hard problem includes at least:

- what is the source representation for this class of truth,
- what version or basis of that source a projection reflects,
- whether that projection is lossless, lossy, or interpretive,
- how quickly it must converge,
- and what divergence is acceptable.

This concern appears repeatedly across institutional records, operational systems, and possible simulation substrates.

### 5. Candidate systems appear to specialize rather than converge

Current review suggests:

- RDF-adjacent and linked-data systems are strong for assertions, references, provenance, and viewpoint-aware knowledge.
- Preservation-oriented repository systems are strong for durability, versioning, auditability, and reconstruction.
- Real-time relational systems may be strong for hot operational state and live coordination.
- Array- and vector-oriented systems appear better aligned with dense, sparse, multidimensional, or non-language state.

These are findings about apparent strengths, not decisions.

## Non-Language State: Explicit Unknowns

This section exists to make visible what is currently not well understood.

### 1. Unknown state classes

It is not yet clear which non-language state classes Milieu must treat as first-class rather than derived.

Examples may include:

- energy-related state,
- information-related state,
- geometric state,
- field state,
- embodied interaction state,
- attention or salience state,
- and simulation-specific internal state.

### 2. Unknown source representations

It is not yet clear what the most natural source representation is for many of these classes.

Some may be better represented as text or assertions.
Some may be better represented as events.
Some may be better represented as vectors, tensors, arrays, fields, traces, or executable functions.

### 3. Unknown authority boundaries

It is not yet clear which truths should be treated as authoritative in which substrate.

Different possibilities may apply to:

- institutional records,
- runtime system state,
- world-state or simulation state,
- participant-specific belief or memory,
- and narrative or social truth.

### 4. Unknown identity and continuity rules across representations

If multiple representations describe the same phenomenon, it is not yet clear:

- how identity is preserved across them,
- what counts as the same thing,
- what counts as a new thing,
- and how continuity is maintained when representations change.

### 5. Unknown projection discipline

Milieu does not yet have a settled shared language for the meta-facet governing projection across representations.

What is currently visible is that any such discipline must account for:

- source,
- basis,
- loss profile,
- convergence expectation,
- and acceptable divergence.

The name and final shape of this facet remain open.

### 6. Unknown evidence needs

It is not yet clear what experiments, prototypes, or operational observations will be sufficient to reduce these unknowns.

## Notes on Candidate System Families

This section captures only present orientation, not commitment.

### Semantic and linked-data systems

These appear useful for:

- assertions,
- references,
- provenance,
- viewpoint separation,
- and portable knowledge packaging.

These do not yet appear sufficient by themselves for all vector-, field-, or simulation-heavy state.

### Preservation-oriented repository systems

These appear useful for:

- durable storage,
- reconstruction,
- versioning,
- fixity,
- and long-horizon institutional memory.

These do not yet appear to be the natural center of high-frequency live state.

### Real-time operational state systems

These appear useful for:

- live coordination,
- subscriptions,
- hot state,
- and interactive runtime behavior.

It remains open how well they fit state that is more naturally multidimensional, field-like, or non-relational.

### Array-, vector-, and multidimensional systems

These appear increasingly relevant where state is:

- dense or sparse,
- multidimensional,
- vector-valued,
- versioned over time,
- or more naturally treated as mathematical or computational structure than as language.

Their fit for institutional memory and viewpoint-rich human reasoning remains less clear.

## Working Implications

At present, the strongest shared implication is modest:

Milieu should not assume that a single language-based knowledge system will be sufficient for all important forms of state.

Milieu should also not assume that every non-language representation can be safely deferred until later.

The unknowns should remain visible as first-class research pressure.

## Open Questions

### 1. Truth Classes

What truth classes does Milieu need to distinguish explicitly?

### 2. Representation Classes

Which representation classes are likely to be first-class rather than derived?

### 3. Authority

Which classes of truth should be authoritative in which kinds of substrate?

### 4. Projection

What shared language should Milieu use for source, basis, loss, convergence, and divergence across representations?

### 5. Evidence

What experiments or prototypes would most quickly reduce the current unknowns?

## Related Records

- RECORD-000 — Milieu Record System
- REFERENCE-MILIEU-CORE — Milieu Constitutional Core
- REFERENCE-DOMAIN-000 — Milieu Domain Orientation Model
- REFERENCE-MILIEU-EXPERIENCE-000 — Experience Foundational View
- REFERENCE-PRISMAL-000 — Prismal Space: Current View and Open Questions
- REFERENCE-PRISMAL-001 — Field, Lattice, and Projection
- REFERENCE-SYSTEMS-000 — Systems: Minimal Ontology for Intent, Behavior, and Observation

## Status Note

This record is intentionally early.

Its purpose is to preserve orientation, findings, and explicit unknowns so later work can refine them without losing why this question matters.
