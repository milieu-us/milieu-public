## REF-AGENTS — Merge Strategy for Change Proposals (Pull Requests)

### Intent
Provide a simple, consistent merge approach for human agents, AI agents, and system agents so that:
- `main` stays legible and auditable,
- pull requests remain the primary review + evidence surface,
- exceptions are explicit and rare.

### Defaults
- **Default merge method:** **Squash merge** into `main`.
- **Default branch hygiene:** delete the head branch after merge (the PR remains the audit surface).

### Cheat Sheet

#### Use **Squash merge** (default)
Use when:
- the PR represents one coherent change proposal,
- the branch contains “work in progress” commits,
- you want `main` to read like a sequence of decisions/changes.

Required habit:
- The PR description must include **intent**, **scope**, **commands/tests run**, **results/evidence links**, and **rollback notes**.

#### Use **Rebase and merge** (rare)
Use when:
- the commit series is intentionally structured as atomic steps (e.g., “refactor”, “add tests”, “enable feature”),
- you expect commit-level archaeology or bisection across those commits to matter.

Notes:
- Only choose this if commit messages are already clean and meaningful.
- Avoid if the branch contains WIP commits.

#### Use a **Merge commit** (rare integration boundary)
Use when:
- preserving the merge boundary itself has value (true “integration event”),
- you are merging a long-lived integration branch,
- you need the merge graph on `main` to reflect parallel integration.

### Rule of Minimality
If you’re unsure, **squash merge**. Exceptions should be justified in the PR description (one sentence is enough).

### Relationship to Agentic Work
Agents should optimize for producing a **reviewable PR with strong evidence**, not for crafting perfect commit history. The PR is the audit record; `main` is the clean ledger of accepted changes.
