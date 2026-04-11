# RECORD-001 - Record Types and Semantics

- **ID:** RECORD-001
- **Title:** Record Types and Semantics
- **Status:** Working Draft
- **Created:** 2026-04-06
- **Updated:** 2026-04-11

## Intent

Define the current set of record types and their semantic roles, and establish how new types may emerge over time.

This enables human agents, AI agents, and system agents to consistently interpret records while preserving flexibility for the system to evolve through use.

## Types

### RECORD

A RECORD captures enduring structure, agreements, or definitions.

- Normative in nature
- Represents current, accepted state
- Changes slowly and deliberately

A RECORD answers:

What is currently held as true or agreed upon?

### DECISION

A DECISION captures reasoning, tradeoffs, and outcomes that lead to change or commitment.

- Contextual and explanatory
- May be revisited or superseded
- Captures intent and rationale

A DECISION answers:

Why was this chosen?

### REFERENCE

A REFERENCE captures supporting knowledge used for understanding.

- Descriptive, not normative
- May summarize or point to external material
- Freely updated

A REFERENCE answers:

What information helps us understand this?

## Distinguishing Properties

- RECORD: normative, defines current state, high stability
- DECISION: contextual, explains change and reasoning, medium stability
- REFERENCE: descriptive, supports understanding, flexible stability

## Metadata Expectations

Each type may carry different supporting information.

- RECORDS prioritize clarity of current state
- DECISIONS prioritize rationale and consequences
- REFERENCES prioritize context and sources

Metadata should remain minimal and evolve through use.

## Type Evolution

The set of record types is intentionally minimal and not fixed.

New types may be introduced when:

- a pattern appears repeatedly in practice
- existing types cannot express the pattern clearly
- the distinction materially improves coordination between agents

Until then:

- use existing types
- allow new forms to emerge informally within them

## Formalization of New Types

When a new type is needed:

- it should be justified through use and/or a DECISION
- it is incorporated into this record once established

Types are introduced through use, not anticipation.

## Notes

- Avoid proliferation of types unless clearly necessary
- Prefer extending patterns within existing types before introducing new ones
- Types define semantic roles and should remain few and legible
