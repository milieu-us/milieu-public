# RECORD-000 — Milieu Record System

ID: RECORD-000 \
Status: Working Draft \
Created: 2026-03-12 \
Updated: 2026-03-31

## Intent

Records preserve shared understanding over time for human, AI, system, and future agents.

The record system should remain usable without requiring a dedicated curator.

## Context

Milieu requires a durable, lightweight record system for constitutional, policy, decision, architecture, and related records. The system should remain clear to human readers, easy for agents to parse, and flexible enough to evolve without unnecessary structural overhead.

This record defines the minimal initial structure of the Milieu record system.

## Decision

Milieu records and artifacts use a minimal shared structure with metadata or optional formal schema.

### Record

A record captures a principle, policy, decision, architecture element,  or other structural artifact so it remains visible and referenceable over time.

### Record Type

Records are grouped by purpose.

Initial record types include:

- `RECORD-` for artifacts and records about the record system itself
- `CONSTITUTION-` for foundational principles
- `POLICY-` for operational rules
- `DECISION-` for strategic direction
- `ARCHITECTURE-` for implementation structure
= `REFERENCE-` for reference documentation

Record types use capital-case. Additional record types may be introduced later if needed.

### Record Identifier

Record identifiers follow the pattern `TYPE[-SUBTYPE]-NUMBER`.

Each record has a stable identifier. The stable identifier may optionally include a unique record subtype such as domain or project for a given set of records. Record subtypes also use capital-case when included. If a record subtype is used, we suggest reviewing if the resulting artifacts will benefit from formal metadata or schema.

The canonical identifier ends at the numeric component.

Examples:

- `RECORD-000`
- `CONSTITUTION-000`
- `DECISION-DOMAIN-000`
- `ARCHITECTURE-PROJECT-000`

A descriptive filename suffix may be added for readability.

Example:

- `RECORD-000-milieu-record-system.md`

The descriptive suffix is not part of the canonical identifier and may change without changing record identity.

### Representation

A record may be represented in one or more formats.

Some record types or subtypes may require a specific representation, a set of allowed representations, or a defined schema.

### Required Metadata

All records must include the following metadata using key-value format.

- `ID:`
- `Status:`
- `Created:`
- `Updated:`

Example:

```text
ID: RECORD-000
Status: Working Draft
Created: 2026-03-12
Updated: 2026-03-12
```

### Intent

Records should include an `Intent` section near the beginning.

The Intent section briefly states why the record exists.

Intent should remain short and clear.

### Optional and Conditional Elements

Optional sections do not affect record validity unless explicitly required by a later record for a defined record type, status, or condition.

Records may include optional sections when helpful.

Examples include:

- `Related`
- `Participants`
- `References`
- `Change Log`

Optional elements are optional unless a later record explicitly makes them required for a defined record type, status, or condition.

New format requirements should avoid invalidating existing records unless explicitly intended.

### Status

Initial record statuses include:

- `Working Draft`
- `Accepted`
- `Superseded`

Additional statuses may be introduced later if needed.

### Relationships

Records may reference other records.

Examples include:

- `Related`
- `Supersedes`
- `Superseded By`

These relationships may be used when helpful and may be formalized further later.

### Change History

The full revision history of records is preserved by the change control system, and records may include a `Change Log` section to summarize meaningful updates.

If used, the Change Log should appear near the end of the record.

## Consequences

This record establishes a minimal shared record structure for Milieu. Benefits include clearer records, lower cognitive load, easier parsing by agents, and stable identifiers with flexible filenames. Trade-offs include leaving some conventions undefined and requiring future records to clarify details. These trade-offs keep the system small and legible.

Benefits include:

- clearer and more consistent records
- lower cognitive load for human readers
- easier parsing by AI agents and system agents
- stable identifiers with flexible filenames
- room to evolve without unnecessary early formalism

Trade-offs include:

- some future conventions remain undefined
- later records may be needed to clarify metadata, lifecycle, or relationships

These trade-offs are acceptable in order to keep the initial system small, legible, and easy to use.

## Notes

This record defines the minimal initial structure only.

Milieu should prefer the least structure that preserves clarity, continuity, and shared understanding over time.
