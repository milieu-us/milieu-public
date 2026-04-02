# REFERENCE-DOMAIN-000 — Milieu Domain Orientation Model

**Status:** Working Draft\
**Owner:** Milieu Stewards\
**Scope:** Milieu-wide

## Intent

Provide a simple map of the major domains of activity within Milieu so that human agents, AI agents, and system agents can orient their interaction and work.

The domain model exists to support navigation and coordination across projects. It is not intended to impose rigid structure or hierarchy.

## Context

Milieu is developing multiple interdependent efforts, including governance, participation models, operational infrastructure, simulation research, and interactive experiences.

These efforts influence one another but do not form a strict hierarchy. Without a shared orientation model, context becomes difficult to maintain across projects.

A small set of domains provides a stable frame for organizing discussion and work-streams while allowing the architecture to evolve.

## Decision

Milieu adopts a domain orientation model.

Domains describe areas of activity, not authority or ownership.

Domains may overlap and evolve as the project grows.

Each domain may have a short Domain Decision Record describing its intent, scope, and relationships.

## Initial Domain Map

Current domains include:

| Domain        | Purpose                                   |
| ------------- | ----------------------------------------- |
| Institution   | governance and stewardship                |
| Participation | agents contributing and coordinating      |
| Operations    | building and running systems              |
| Simulation    | modeling reality (Prismal Space)          |
| Experience    | agent interaction, perception, and action |

These domains represent the current working understanding and may evolve over time.

## Principles

### 1. Domains describe activity, not hierarchy

Domains are not organizational units or chains of authority.

### 2. Domains support orientation

They exist to help agents understand where work is happening and how efforts relate.

### 3. Domains may overlap

Work may legitimately touch multiple domains.

### 4. Domains may change

The model may evolve as Milieu learns.

## Relationship to Projects

Minimum Viable projects often explore one domain primarily, while interacting with others.

| Project                   | Primary Domain |
| ------------------------- | -------------- |
| Minimum Viable Milieu     | Institution    |
| Agentic Workflow          | Participation  |
| Operations                | Operations     |
| Prismal Space             | Simulation     |
| Minimum Viable Experience | Experience     |

Projects are not restricted to a single domain.

## Consequences

The domain model provides:

- a shared orientation structure
- a common vocabulary across projects
- improved context tracking for human agents, AI agents, and system agents

The model intentionally avoids premature architectural commitment.

## Open Questions

- Will additional domains emerge?
- Will some domains merge or split?
- Should the model later be visualized formally?

These questions will be answered through experience.

