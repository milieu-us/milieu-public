# DECISION-MILIEU-CORE-000 - Foundational Constraints

- **ID:** DECISION-MILIEU-CORE-000
- **Status:** Working Draft
- **Created:** 2026-03-29
- **Updated:** 2026-03-29

## Intent

To ensure that all work remains understandable, governable, and shareable across human agents, AI agents, and system agents.

## Decision

All systems and activities within Milieu adhere to the following constraints:

- Nothing unbounded  
- Nothing implicit  
- Nothing unobservable  

## Interpretation

- Nothing unbounded  
  All systems define clear limits (scope, time, resources, authority).

- Nothing implicit  
  All assumptions are made explicit in shared artifacts (records, code, schemas, contracts).

- Nothing unobservable  
  All meaningful state, decisions, and effects are inspectable. Where something is not observable, that limitation is made explicit.

## Notes

This decision establishes constraints on how systems are designed, how decisions are recorded, and how work is coordinated.

It does not require that all systems be fully reconstructable, but it does require that any limits to observability are explicit and understood.

## Implications

- Records avoid hidden structure or meaning.
- Systems emit observable signals for state and decisions.
- Governance avoids unwritten rules or hidden authority.
- Architectures favor bounded contexts and explicit interfaces.

## Related

- RECORD-000 — Milieu Record System  
- CCR-000 — Constitutional Core (proposed)
