# milieu-public

This repository contains public Milieu records: governance materials, design references, decisions, and exploratory documents.

It is not a product repository or a game client. Think of it as a public map of how Milieu is currently being understood, shaped, and tested.

Contents here are limited to materials appropriate for public sharing and that are not required by law or established policy, including steward judgment, to remain private.

## Local Git Workflow

Use a fresh clone for each person or agent context that contributes to this repository.

- Do not copy an existing working tree or reuse someone else's `.git` directory.
- Set commit identity in each clone with `git config --local user.name "Your Name"` and `git config --local user.email "you@example.com"`.
- Verify the effective identity before the first commit with `git config user.name`, `git config user.email`, and `git remote -v`.
- Prefer `git pull --ff-only` unless you are intentionally creating a local merge.
- Keep hooks opt-in and visible. If hooks become part of the workflow, they should be documented in the repository rather than living only in machine-local Git config.

If you are creating or editing records, follow the record-system guidance in [AGENTS.md](AGENTS.md) and the core record docs in `records/`.

## What Is Milieu?

Milieu is exploring shared experiences where people, AI agents, and systems participate together in world-like spaces.

Current experience work is especially interested in:

- small-group play
- embodied improvisation
- worldbuilding and storytelling
- shared meaning that emerges through participation
- archives that support return, reinterpretation, and continuation

If you like roleplay, improv, tabletop play, fictional settings, or actual play, the Experience documents are usually the best place to start.

## Start Here

If you are new to the repo, start with these three documents:

1. [Milieu Experience Orientation](references/REFERENCE-EXPERIENCE-Milieu-Experience-Orientation.md) for the clearest plain-language introduction to how Milieu thinks about time, threads, places, archives, and participation.
2. [Minimum Viable Experience (MVE): Emergence First](decisions/DECISION-MVE-000-Minimum-Viable-Experience-(MVE)-Emergence-First.md) for the clearest picture of what an early Milieu session is supposed to feel like.
3. [Minimum Viable Experience (MVE) Stakeholder Expressions](decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md) for the best current map of who might show up around an experience and how people may move between those expressions.

## Quickstart By Stakeholder

Milieu's governance model treats stakeholders as modes, not fixed classes. At the Milieu-wide level, the main modes are Participant, Contributor, and Steward.

For onboarding, especially around Experience work, it is often easier to start from the more familiar experience-facing expressions described in the MVE stakeholder record. Use the path below that feels closest to you today.

### If you are an Audience Member, Guest, or Curious Visitor

Start here if you want to understand the vibe before you worry about structure.

1. [Milieu Experience Orientation](references/REFERENCE-EXPERIENCE-Milieu-Experience-Orientation.md)
2. [Minimum Viable Experience (MVE): Emergence First](decisions/DECISION-MVE-000-Minimum-Viable-Experience-(MVE)-Emergence-First.md)
3. [Impro: Embodied Play and Improvisation](references/REFERENCE-EXPERIENCE-Impro-Embodied-Play-and-Improvisation.md)

This path is best for:

- roleplayers
- theatre and improv people
- fiction fans
- actual play viewers
- anyone asking "what kind of thing is this?"

### If you are a Player, Actor, or Direct Participant

Start here if you care most about what it feels like to enter play and discover how interaction works.

1. [Minimum Viable Experience (MVE): Emergence First](decisions/DECISION-MVE-000-Minimum-Viable-Experience-(MVE)-Emergence-First.md)
2. [Milieu Experience Orientation](references/REFERENCE-EXPERIENCE-Milieu-Experience-Orientation.md)
3. [Impro: Embodied Play and Improvisation](references/REFERENCE-EXPERIENCE-Impro-Embodied-Play-and-Improvisation.md)
4. [Voice Fonts for Embodied Play and Production](proposals/PROPOSAL-EXPERIENCE-000-Voice-Fonts-for-Embodied-Play-and-Production.md)

This path is best for:

- players
- performers
- live roleplayers
- people interested in embodiment, voice, and character presence

### If you are a World Builder, Storyteller, or Producer

Start here if you want to understand how Milieu approaches setting, structure, interaction, and continuity.

1. [Milieu Experience Orientation](references/REFERENCE-EXPERIENCE-Milieu-Experience-Orientation.md)
2. [Minimum Viable Experience (MVE): Emergence First](decisions/DECISION-MVE-000-Minimum-Viable-Experience-(MVE)-Emergence-First.md)
3. [Prismal Interaction](references/REFERENCE-PRISMAL-INTERACTION-000-Prismal-Interaction.md)
4. [Prismal Space: Current View and Open Questions](references/REFERENCE-PRISMAL-000-Prismal-Space-Current-View-and-Open-Questions.md)

This path is best for:

- tabletop game masters
- setting designers
- narrative designers
- producers shaping live or asynchronous experiences

### If you are a Facilitator, Guide, Moderator, or Safety-Oriented Contributor

Start here if you care about invitation quality, flow, coherence, safety, and recovery.

1. [Minimum Viable Experience (MVE): Emergence First](decisions/DECISION-MVE-000-Minimum-Viable-Experience-(MVE)-Emergence-First.md)
2. [Minimum Viable Experience (MVE) Stakeholder Expressions](decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md)
3. [Impro: Embodied Play and Improvisation](references/REFERENCE-EXPERIENCE-Impro-Embodied-Play-and-Improvisation.md)
4. [Milieu Experience - Foundational View](references/REFERENCE-MILIEU-EXPERIENCE-000-Experience-Foundational-View.md)

This path is best for:

- facilitators
- guides
- moderators
- safety stewards
- people shaping how others enter and move through experience

### If you are Working on Memory, Archive, or Continuity

Start here if you care about how experiences are preserved, revisited, and carried forward.

1. [Milieu Experience Orientation](references/REFERENCE-EXPERIENCE-Milieu-Experience-Orientation.md)
2. [Milieu Record System](records/RECORD-000-Milieu-Record-System.md)
3. [Minimum Viable Experience (MVE) Stakeholder Expressions](decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md)

This path is best for:

- archivists
- memory and continuity functions
- documentation-minded contributors
- people interested in replay, recall, and reinterpretation

### If you are a Contributor or Steward Looking for Governance Context

Start here if you want the Milieu-wide participation and governance frame.

1. [Minimum Viable Milieu (MVM)](decisions/DECISION-MVM-000-Minimum-Viable-Milieu-(MVM).md)
2. [Milieu Constitutional Core - Green Paper](references/REFERENCE-MILIEU-CORE-Milieu-Constitutional-Core-Green-Paper-Consultation.md)
3. [Milieu Domain Orientation Model](references/REFERENCE-DOMAIN-000-Milieu-Domain-Orientation-Model.md)

This path is best for:

- contributors shaping policy or direction
- stewards
- people trying to understand authority, scope, continuity, and change

## How To Read This Repo

Most documents are one of these:

- `references/` for orientation, conceptual framing, and upstream inspirations
- `decisions/` for current working decisions and directional commitments
- `proposals/` for specific experiments or pilot ideas
- `records/` for record-keeping conventions and system-level documentation

If you are unsure where to begin, start in `references/`, then move to `decisions/`.
