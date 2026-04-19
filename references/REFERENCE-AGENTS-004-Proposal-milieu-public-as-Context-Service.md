# REFERENCE-AGENTS-004 — Proposal: milieu-public as a Context Distribution Service

- **ID:** REFERENCE-AGENTS-004
- **Status:** Proposal — Needs Review
- **Created:** 2026-04-19
- **Updated:** 2026-04-19

## Intent

Surface a reframing of milieu-public's role that emerged during early subtree testing, and propose a DECISION be opened to settle it before the subtree pattern is adopted at scale.

This document is a proposal, not a decision. It is written for Boss and any other agent with standing over milieu-public's architecture.

## What Surfaced

During the first subtree test (PrismalExperimental PR #1), a question emerged about where the vendor update script belongs.

The script (`update-milieu-public.sh`) currently lives in PrismalExperimental — the downstream consumer. If milieu-public acquires more downstream consumers (other repos, RAG pipelines, model training corpora), each would need to independently know how to pull from milieu-public correctly. That is a coupling problem: every consumer encodes the carrier mechanics, not just the subscription intent.

The reframing: if milieu-public is a **context distribution service**, the update mechanics belong to the service, not to the consumers.

## The Distinction

### milieu-public as a shared record archive

- holds documents
- consumers figure out their own access patterns
- no defined subscriber interface
- update mechanics are the consumer's problem

### milieu-public as a context distribution service

- holds documents
- defines a subscriber interface: how a downstream consumer declares a dependency and stays current
- owns the update mechanics (or at least the canonical form of them)
- consumers declare intent, not implementation

The difference matters most when carriers change. Git subtree is today's carrier. The same semantic pattern will be needed when the carrier is a RAG corpus, a vector store, or a model training dataset. If consumers own the mechanics, each carrier transition requires updating every consumer. If the service owns the interface, the transition is localized.

## The Provenance Angle

The subtree pattern gives each downstream consumer a versioned snapshot with a known commit hash. That commit hash is the current provenance primitive — it lets any agent (or any test run) say "I was operating against this specific version of shared context."

This is especially important for multi-variant testing: if two model variants behave differently, the first question is whether they were trained or prompted against the same context version. Without provenance, that question cannot be answered.

The service framing extends this naturally: the service owns the version identifier, and every consumer's snapshot is traceable to it. Consumers do not need to invent their own versioning.

## What This Does Not Settle

This proposal does not know:

- whether milieu-public should become a formal service with a defined interface, or whether a lighter convention (a canonical script location, a documented subscription pattern) is sufficient
- whether the subtree mechanism is the right carrier long-term, or whether it is a good-enough starting point that a DECISION should ratify before replacing
- how the service interface interacts with non-Git consumers (RAG, vector, model training)
- whether a separate repo or a subdirectory within milieu-public is the right home for the subscriber interface

These are the questions that need Boss's input and likely a DECISION to settle.

## What the Test Already Showed

PrismalExperimental PR #1 is a working test of the subtree pattern. It showed:

- the vendored snapshot is legible to agents (the AGENTS.md update script guidance worked)
- the commit hash is present and attributable
- the update script runs correctly
- the PR gate on the downstream side controls when context updates are accepted

The test did not show whether this pattern scales cleanly to multiple consumers, or whether the script ownership question matters in practice yet.

The recommendation is to treat PR #1 as evidence, not throwaway. The learning is real. The implementation may be revised by a DECISION, but the observations stand.

## What We Are Asking

1. Is the service reframing the right mental model for milieu-public, or is there a better framing?
2. Should a DECISION be opened to settle this before the subtree pattern spreads to more consumers?
3. Where should the subscriber interface (update mechanics, canonical script or equivalent) live?
4. Does the provenance requirement change how milieu-public should version its own snapshots?

## Related

- REFERENCE-AGENTS-002 — Carried Context (context propagation and provenance open questions)
- REFERENCE-AGENTS-003 — Agent Coordination Model
- PrismalExperimental PR #1 — first subtree test (vendored snapshot + update script)
- DECISION-OPERATIONS-CHANGE-000 — Change Proposals and Acceptance
- DECISION-OPERATIONS-CHANGE-001 — Git-Based Change Proposal Workflow
