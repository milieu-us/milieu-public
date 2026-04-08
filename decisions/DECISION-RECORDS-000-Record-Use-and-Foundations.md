# DECISION-RECORDS-000 - Record Use and Foundations

- **ID:** DECISION-RECORDS-000
- **Status:** Working Draft
- **Created:** 2026-04-07
- **Updated:** 2026-04-07

## Intent

Make use of the Milieu record system explicit for human agents, AI agents, and system agents when working with record artifacts.

This decision also establishes how record families should express their foundations so the system becomes more self-documenting over time.

## Context

Milieu now has an explicit record system defined by `RECORD-000`, `RECORD-001`, and `RECORD-002`.

At the same time, the repository contains mixed-era documents created before the current record conventions were fully explicit or consistently applied.

This makes it easy for agents to infer structure from whichever document they encounter first, even when that document is not the intended foundation for the family.

For this decision, a record family is a set of related record artifacts that share a stable identifier prefix before the numeric component.

Examples include:

- `RECORD-000`, `RECORD-001`, `RECORD-002`
- `DECISION-RECORDS-000`, `DECISION-RECORDS-001`

`AGENTS.md` and `README.md` help agents orient into the repository, but they exist outside the formal record system proper.

They are useful bridges, not normative examples of record-system form.

## Decision

Milieu uses the record system explicitly for record artifacts such as `RECORD`, `DECISION`, and `REFERENCE` documents.

This use is not optional or merely conventional. It is the expected way shared record artifacts are created, interpreted, and maintained in this repository.

Within a record family, the relevant `-000` record is the default foundational anchor when one exists.

When creating, editing, or interpreting a record artifact within a family, agents should read the relevant `-000` first when one exists.

Later records may extend, interpret, or apply a family, but they should not silently replace the family's `-000` as the practical foundation.

If foundational guidance has drifted into later records, agents should treat that as a maintenance signal and update or propose updating the corresponding `-000`.

If no relevant `-000` exists, agents should surface that absence explicitly rather than inventing hidden foundation.

If classification, family boundaries, or structure are unclear, agents should surface the uncertainty rather than guess.

`AGENTS.md` and `README.md` should continue to point accurately into the record system, but they do not define or override record-system form.

## Consequences

This decision makes use of the record system explicit rather than optional or inferred.

It strengthens self-documentation inside the record families by giving agents a clear starting point for orientation and change.

It also keeps the role of meta-orientation documents narrow: they help agents find the system, but the system should explain itself through its own canonical artifacts.

Older records may remain partially out of alignment until a later renormalize or cleanup pass addresses them directly.

That follow-on normalization work is separate from this decision.

## Related

- `RECORD-000`
- `RECORD-001`
- `RECORD-002`
