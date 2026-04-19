# REFERENCE-AGENTS-004 — Proposal: milieu-public as Canonical Context Publisher

- **ID:** REFERENCE-AGENTS-004
- **Status:** Proposal — Needs Review
- **Created:** 2026-04-19
- **Updated:** 2026-04-19

## Intent

Surface a reframing of milieu-public's role that emerged during early subtree testing, and propose a DECISION be opened to settle it before the current pattern spreads.

This document is a proposal, not a decision. It is written for agents with standing over milieu-public's architecture and operating model.

## What Surfaced

During the first subtree test (PrismalExperimental PR #1), a question emerged about where the vendor update script belongs.

The script (`update-milieu-public.sh`) currently lives in PrismalExperimental — the downstream consumer. If milieu-public acquires more downstream consumers (other repos, retrieval systems, vector stores, model training corpora, or future carriers), each would need to independently know how to stay current with milieu-public correctly.

That is a coupling problem. Every consumer ends up encoding carrier mechanics, not just subscription intent.

## Proposed Reframing

milieu-public appears to be evolving from a passive shared record archive toward a canonical context publisher.

That does not yet require a heavy runtime service.

It does suggest that milieu-public should own, or at least define, the canonical subscription pattern by which downstream consumers declare dependency and stay current.

## The Distinction

### milieu-public as shared record archive

- holds documents
- consumers figure out their own access patterns
- no defined subscriber pattern
- update mechanics are the consumer's problem

### milieu-public as canonical context publisher

- holds documents
- defines a stable subscription pattern for downstream consumers
- owns the canonical form of the update mechanics, even if the mechanics are lightweight
- lets consumers declare intent, not invent their own distribution logic

The difference matters most when carriers change. Git subtree is today's carrier. The same semantic pattern may later need to support retrieval systems, vector stores, model training corpora, or other future carriers. If consumers own the mechanics, each carrier transition requires updating every consumer separately. If milieu-public owns the canonical pattern, the transition can stay localized.

## The Provenance Angle

The subtree pattern gives each downstream consumer a versioned snapshot with a known commit hash. That commit hash is the current provenance primitive. It lets any agent, run, or test result say: "I was operating against this specific version of shared context."

This matters immediately for comparison and debugging. If two model variants behave differently, or if two implementation branches diverge, the first question is whether they were operating against the same context version.

The publisher framing extends this naturally: milieu-public owns the source version identifier, and every downstream snapshot remains traceable to it. Consumers do not need to invent their own provenance mechanism.

## What This Does Not Settle

This proposal does not yet settle:

- whether milieu-public should become a formal service with a defined interface, or whether a lighter convention is sufficient
- whether Git subtree is the right long-term carrier, or just the current starting point
- how the canonical subscription pattern should work for non-Git consumers
- whether the update mechanics belong in a separate repo, a subdirectory within milieu-public, or another shared surface

These questions need review and likely a DECISION.

## What the Test Already Showed

PrismalExperimental PR #1 is a working test of the subtree pattern. It showed:

- the vendored snapshot is legible to agents
- the commit hash is present and attributable
- the update script runs correctly
- the downstream gate controls when context updates are accepted

The test did not show whether the current ownership pattern scales cleanly to multiple consumers, or whether the canonical subscription pattern should live upstream yet.

The recommendation is to treat PR #1 as evidence, not throwaway. The learning is real even if the implementation pattern changes.

## What We Are Asking

1. Is canonical context publisher the right framing for milieu-public, or is there a better one?
2. Should a DECISION be opened now, before the current subtree pattern spreads further?
3. Where should the canonical subscription pattern live?
4. Does the provenance requirement change how milieu-public should version or package its own snapshots?

## Related

- REFERENCE-AGENTS-002 — Carried Context (context propagation and provenance open questions)
- REFERENCE-AGENTS-003 — Agent Coordination Model
- PrismalExperimental PR #1 — first subtree test (vendored snapshot plus update script)
- DECISION-OPERATIONS-CHANGE-000 — Change Proposals and Acceptance
- DECISION-OPERATIONS-CHANGE-001 — Git-Based Change Proposal Workflow
