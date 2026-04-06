# RESOURCE-SYSTEMS-000 — Systems: Minimal Ontology for Intent, Behavior, and Observation

**Status:** Working Draft \
**Created:** 2026-04-05 \
**Updated:** 2026-04-05 \

---

## Intent

Establish a minimal, shared ontology for describing and reasoning about systems across domains (people, processes, software, hardware, physical environments, and their interactions).

The ontology supports:

* capturing what we believe systems should do
* capturing what we believe systems are doing
* capturing what systems are actually doing
* reconciling differences through iteration

The goal is not perfect modeling, but **continuous alignment between intent, belief, and reality**.

---

## Core Concepts

### System

A bounded set of interacting elements.

A boundary defines the scope of analysis for participants, events, relations, and constraints.

Systems may contain subsystems, participate in larger systems, and be treated as participants within those systems.

---

### Participant

An entity that can act or be acted upon.

Participants include:

* human agents
* AI agents
* system agents (code, services)
* physical components

---

### Event

A discrete occurrence within a system.

Examples include:

* an action
* a message
* a state change
* an observation

Events are the primary representation of behavior.

---

### EventRelation

A relation between events describing how they are connected.

EventRelation captures:

* ordering
* causality
* interaction
* enablement

EventRelations are typed.

Examples include:

* precedes
* causes
* enables
* responds_to
* synchronizes_with

Behavior is represented as a **partially ordered set of events connected by EventRelations**.

---

### Constraint

A rule that defines what is valid within the system.

Constraints express:

* what is allowed
* what must happen
* what must not happen

Constraints operate over:

* events
* participants
* EventRelations

---

## System Aspects

### Structure (Possibility)

Participants and their relationships define what interactions are possible.

---

### Behavior (Realization)

Events and EventRelations define what occurs.

---

### Constraints (Validity)

Constraints define which behaviors are valid.

---

### Principle

Structure defines possibilities.
Behavior realizes those possibilities.
Constraints define validity.

---

## Views

Systems are understood through multiple views.

### Intent View

What we believe the system should do.

Includes:

* expected flows
* goals
* constraints

---

### Model View

What we believe the system is doing.

Includes:

* inferred structure
* assumed flows
* mental or documented models

This view may be incomplete or incorrect.

---

### Runtime View

What the system is actually doing.

Includes:

* observed events
* observed EventRelations
* metrics and traces when available

This view is evidence-based and may be partial.

---

### Revision

Changes made based on differences between views.

Revision updates:

* intent
* constraints
* structure
* understanding

---

## System Loop

Systems are continuously understood and evolved through a loop:

Intent → (Structure ↔ Behavior) → Observation → Revision → Intent

This loop is not strictly sequential.

Structure and behavior co-evolve, and observation may occur at any point.

---

## Key Properties

### Partial Order

System behavior is not strictly sequential.

Events are related through EventRelations forming a partial order.

Sequential representations are projections for comprehension.

---

### Incompleteness

No view is required to be complete.

Partial representations are expected and acceptable.

---

### Runtime Primacy

Observed behavior is first-class evidence.

Differences between intent, model, and runtime are expected and informative.

---

### Minimality

The ontology is intentionally minimal.

Additional structure should only be introduced when required by use.

---

## Formal Alignment (Non-Normative)

This ontology is compatible with, but not dependent on:

* process algebras (behavioral interpretation)
* Petri nets (concurrency and enablement)
* temporal logic (safety and liveness)
* provenance systems (causal tracking)

The ontology serves as a source representation that can be mapped into formal systems when needed.

---

## Guidance

* Do not require full specification before use
* Do not collapse intent, model, and runtime into a single view
* Do not assume sequential execution
* Prefer simple, explicit language over formal notation unless required

---

## Open Questions

* What is the minimal stable set of EventRelation types?
* How should uncertainty or confidence be represented in Model View?
* What is the minimal structure required for constraints to support formal verification?
* How should resources and value flows be represented within this ontology?

---
