# REFERENCE-AGENTS-005 - Shared World Operating Environment

- ID: REFERENCE-AGENTS-005
- Status: Draft
- Created: 2026-07-21
- Updated: 2026-07-21

## Intent

Capture a working frame for an environment where human agents, AI agents, and system agents can understand and change a shared creative world together.

This is not a final architecture, a platform proposal, or a decision to replace existing operating systems, development environments, game engines, or coordination tools.

It records an emerging direction and, just as importantly, how we reached it.

The aim is to preserve enough context for later agents to continue the exploration without reducing it too early to a list of products or implementation components.

## Starting Point

This exploration began with a practical problem:

How do we debug complex scenes and behaviors from inside the scene itself?

Text logs, source files, and flat debugging tools remain useful, but they often separate a failure from the world in which the failure becomes meaningful.

A character may be in the wrong place because of:

- a behavior rule
- a navigation state
- a scene relationship
- a timing condition
- an outdated asset
- a configuration change
- a misunderstood design decision
- an interaction between several systems

The log may show an error without showing the situation.

The source file may show an implementation without showing the behavior that emerged.

The scene may show the problem without showing which records, revisions, constraints, or agent actions produced it.

Game development already works around this by placing debug information back into the world:

- collision shapes
- navigation paths
- state labels
- behavior trees
- animation state
- performance overlays
- spatial bounds
- trajectories
- event histories

This raised a broader question:

> What if the shared world were not only the thing being created, but also the primary place from which agents understand, coordinate, debug, and change it?

## Moving Away from a Tool List

An early version of the discussion produced a familiar list:

- operating system
- desktop
- editor
- integrated development environment
- scene editor
- source control
- build system
- observability stack
- coordination tools
- AI agent orchestration
- automation

These are real parts of current work, but they are mostly inherited descriptions of how work is divided today.

They do not necessarily tell us which capabilities must survive if the form of the working environment changes.

Instead of asking which tools should be combined or replaced, this exploration began asking why those tools exist.

For example:

- Source control, patching, provenance, and rollback all help agents understand and recover change.
- Logs, traces, profiling, and in-scene overlays all help agents observe behavior.
- Permissions, sandboxes, review gates, and policy boundaries all help keep action safe and bounded.
- Editors, graphs, timelines, terminals, and scene views are different ways of encountering the same underlying work.
- Issues, pull requests, briefings, and conversations help agents coordinate around intentions and changes.
- Records and references preserve meaning that must survive individual sessions and tools.

This produced a provisional capability map.

The categories overlap. They should not yet be treated as fixed system boundaries.

## Working Capability Map

### Revision Awareness

Agents need to understand change across the whole working environment, not only across source code.

Relevant changes may include:

- code
- configuration
- scene state
- assets
- behaviors
- operating environment
- tools
- records
- references
- agent instructions
- coordination artifacts

Revision awareness means being able to ask:

- What changed?
- When did it change?
- Which agent or process changed it?
- Why was it changed?
- Which sources informed the change?
- Which other parts of the world depend on it?
- Can the prior state be inspected or restored?

This is broader than version control alone.

Version control may be one carrier for revision awareness, but the capability must also reach state and behavior that are not naturally represented as mergeable text files.

### Observability

Agents need to understand the world from the state and signals it exposes.

This may include:

- spatial structure
- relationships
- timelines
- state transitions
- events
- logs
- metrics
- traces
- trajectories
- overlays
- provenance
- current and historical world state

Observability should work at several levels.

A human agent may need an in-scene visual explanation.

An AI agent may need structured relationships, events, and source references.

A system agent may need machine-readable state and explicit thresholds.

These should be different views of related evidence rather than unrelated monitoring systems reconstructing separate versions of reality.

### Safety

Agents must be able to explore and create without giving every action an unbounded blast radius.

Safety may include:

- bounded environments
- disposable sandboxes
- reversible changes
- explicit authority
- review gates
- protected foundational concepts
- constrained automation
- visible side effects
- recovery paths
- resistance to malicious or misaligned action

The desired environment should make the safe path easier than the unsafe path.

An agent should be able to try an idea, observe what happens, and discard the result without risking the primary world or build.

Safety also includes protection against meaning drift.

A convenient implementation choice should not silently become a foundational claim merely because it was encoded into a tool, schema, or scene.

### Shared World Model

Human agents, AI agents, and system agents need some coherent way to refer to the same world.

That does not necessarily mean every agent receives the same representation.

It means their views should refer back to compatible entities, relationships, behaviors, intentions, constraints, and changes.

A shared world model may need to represent:

- entities
- components
- places
- relationships
- behaviors
- rules
- events
- intentions
- constraints
- sources
- revisions
- agent actions
- unresolved questions

Without a shared model, each tool constructs a partial private truth.

The scene editor knows one set of relationships.

The issue tracker knows another.

The source repository knows the implementation.

The records repository knows the intent and rationale.

The runtime knows what actually happened.

Agents then spend much of their effort trying to reconstruct the relationships between these partial truths.

The shared world model is the possibility that those relationships become explicit.

### Coordination

Multiple agents need to work together without reducing all activity to assigned tasks.

Coordination may include:

- expressing an intention
- exploring possibilities
- proposing a change
- requesting context
- negotiating scope
- delegating bounded action
- working in parallel
- detecting conflict
- reviewing evidence
- accepting or rejecting change
- escalating decisions
- propagating changed context

GitHub issues, branches, pull requests, records, references, conversations, and test harnesses can continue to serve as coordination surfaces.

The important point is that they are surfaces around the work, not necessarily the complete model of the work.

Coordination should preserve the relationships between:

- the request
- the context supplied
- the actions taken
- the world state affected
- the evidence produced
- the review performed
- the meaning changed or preserved

### Memory

The environment needs to retain more than its current state.

It should help preserve:

- what was attempted
- what was observed
- what worked
- what failed
- what was rejected
- what was decided
- why something matters
- which assumptions were in force
- which context was available at the time

Revision awareness preserves states and changes.

Memory preserves lessons, meaning, and continuity.

Records and references remain important memory carriers, but memory may also live in:

- scene histories
- experiment results
- builds
- measurements
- traces
- recordings
- test evidence
- rejected variants
- agent context traces

The goal is not to capture everything.

The goal is to preserve enough continuity that another agent can continue the work well.

### Agency Shaping

Different agents need different scopes of possible action.

An agent may be permitted to:

- observe
- ask questions
- propose
- simulate
- edit inside a sandbox
- implement
- test
- review
- approve
- merge
- deploy
- recover a prior state

These scopes may depend on the agent, the environment, the risk of the action, and the evidence available.

Agency shaping is not only an identity problem.

Identity helps with accountability and governance, but knowing who an agent is does not by itself determine what that agent should be able to do.

The more immediate questions are:

- What can this agent affect?
- Under which constraints?
- In which environment?
- For how long?
- With what review?
- With what provenance?
- With what recovery path?

### Multi-View Access

The same underlying world should be approachable through different views.

Possible views include:

- scene
- graph
- timeline
- text
- code
- diff
- map
- procedure
- telemetry
- conversation
- record
- simulation state

No single view is likely to serve every activity or every agent.

A scene view may make spatial failure obvious.

A graph may expose dependencies.

A timeline may reveal causality.

A diff may show what changed.

A record may preserve why a constraint exists.

A machine-readable event stream may let a system agent act without reconstructing meaning from screenshots.

The world becomes the center of gravity, while these views become lenses through which agents encounter it.

This does not require every tool to become three-dimensional.

It suggests that the desktop, terminal, editor, and dashboard may eventually be understood as views into shared work rather than independent centers of truth.

## A Possible Experience of Work

A small example may make the direction clearer.

A human agent notices that an embodied character is repeatedly choosing an unexpected path through a scene.

From inside the scene, they enable a diagnostic view.

The environment exposes:

- the path selected
- nearby constraints
- the current behavior state
- recent state transitions
- the relevant scene entities
- the revision that last changed the behavior
- the source implementation
- the test or record associated with that change

An AI agent is invited to inspect the bounded problem.

The AI agent receives:

- the visible scene state
- the related graph and timeline
- the applicable records
- the relevant source revision
- the permitted scope of action
- the expected evidence
- the explicit instruction not to modify the primary build

A system agent creates a disposable environment.

The AI agent proposes or implements a change within that environment.

The human agent reviews the changed behavior in the scene rather than only reading a code diff.

The environment still provides the code diff, source trace, measurements, and affected relationships.

The result can then be:

- accepted
- revised
- rejected
- preserved as an experiment
- discarded with the sandbox

The useful unit of work is not only the changed file.

It is the relationship between intention, context, action, world behavior, evidence, and review.

## Identity in This Frame

This exploration questioned whether identity belongs among the most fundamental capabilities.

Identity remains important for:

- accountability
- attribution
- governance
- trust
- audit
- access
- standing

However, identity alone does not create safety.

A fully identified agent may still have excessive authority.

An unidentified process may still be safe if it has narrowly bounded, observable, reversible capabilities.

The current working view is therefore:

- identity is important supporting infrastructure
- provenance and attribution must remain available
- capability boundaries and environmental safety are more immediate design concerns
- governance may impose stronger identity requirements for particular actions

This is not a rejection of Milieu's identity work.

It is a distinction between identifying an actor and shaping the actor's possible effects.

## Relationship to Existing Milieu Agent Work

This frame builds on the current Carried Context work.

Carried Context asks what minimum portable continuity another agent needs to continue work well.

A shared world operating environment asks whether that continuity can become directly connected to the world, activity, and evidence it describes.

For example:

- a context bundle could identify the exact scene entities and revisions in scope
- a context trace could be connected to the actions and observations made during a session
- a context diff could describe changes in meaning alongside code and asset changes
- a review gate could include direct inspection of resulting world behavior
- context propagation could update downstream agents and carriers when accepted meaning changes

The current workflow surfaces remain useful:

- repositories
- issues
- branches
- pull requests
- records
- references
- builds
- test harnesses
- conversations

This frame does not require replacing them.

It asks how they might become coherent views and carriers around shared activity instead of isolated silos.

## Why Unreal Engine and Prismal Space Matter Here

Unreal Engine and Prismal Space provide a useful test environment because the problems are already multi-dimensional.

Relevant state may be:

- spatial
- temporal
- behavioral
- relational
- visual
- physical
- computational
- conceptual

An Unreal Engine test harness can reveal whether an agent workflow actually connects context, action, and observable world behavior.

Prismal Space adds an important constraint: an implementation representation must not silently become the foundation ontology.

This makes the test more valuable.

A successful environment must help agents see both:

- what the current implementation does
- what the current records claim or leave unresolved

It must preserve the difference.

## What This Reference Does Not Decide

This reference does not decide:

- that Milieu should build a new operating system
- that the desktop should be abandoned
- that Rider, Unreal Editor, GitHub, or current tools should be replaced
- which engine or interface should host the shared environment
- whether the primary experience should be two-dimensional, three-dimensional, spatial, textual, or mixed
- what the canonical shared world data model should be
- how identity, trust, and governance should be implemented
- which capabilities belong in one product or several interoperating systems
- how much state should be centralized or distributed
- which concepts should become formal Architecture or Decision records

Those questions remain open.

## Questions to Carry Forward

- What is the smallest experiment that would test this frame through real work?
- Which parts of a scene or runtime can already be connected to source, records, and revisions?
- What is the minimum useful shared world model?
- Which relationships must be canonical, and which may remain view-specific?
- How should non-text state participate in revision awareness?
- How does an agent ask for missing context from inside the working environment?
- What evidence should be returned after an agent acts?
- How should meaning changes appear alongside code, asset, and configuration diffs?
- Which actions require identity, and which require only bounded capability and provenance?
- How should human agents, AI agents, and system agents receive views suited to them without creating separate truths?
- How do we prevent the shared model from becoming another enormous context dump?
- What remains useful when the current desktop and tool stack are treated as compatibility layers rather than permanent foundations?

## Suggested First Validation

Do not begin by building a general shared-world platform.

Begin with one bounded Unreal Engine test harness scenario.

A useful test might include:

- one visible scene behavior that is difficult to understand from logs alone
- one in-scene diagnostic view
- one graph or timeline view
- explicit links to relevant source and context records
- one disposable agent environment
- one bounded proposed change
- one observable before-and-after result
- one context trace
- one human review gate

The test should ask:

> Can another agent understand the problem, act safely, and return evidence without ingesting the entire repository or losing the relationship between the implementation and its meaning?

The result should be allowed to disprove or substantially change this frame.

## Working Summary

A concise expression of the current direction is:

> Build a safe, observable, revision-aware shared world where human agents, AI agents, and system agents can understand and change creative work through multiple coherent views.

This should be treated as a question-bearing frame, not a blueprint.

A tool, workflow, or experiment may be evaluated by asking:

- Which capability does it strengthen?
- Which relationship does it make visible?
- Which action does it make safer?
- Which context does it help carry?
- Does it improve coherence between agents and views?
- Does it accidentally create another isolated source of truth?

## Sources and Carried Context

Repository:

- `milieu-us/milieu-public`
- Branch reviewed: `main`

Repository files reviewed:

- `AGENTS.md`
- `references/REFERENCE-AGENTS-002-Carried-Context-Working-Concept.md`
- `references/REFERENCE-AGENTS-Research-Prompt.md`
- `records/RECORD-000-Milieu-Record-System.md`
- `records/RECORD-001-Record-Types-and-Semantics.md`
- `records/RECORD-002-Current-Markdown-Representation-for-Records.md`
- `decisions/DECISION-MILIEU-CORE-Foundational-Constraints.md`
- `decisions/DECISION-MILIEU-MVM-000-Minimum-Viable-Milieu-(MVM).md`
- `decisions/DECISION-MVE-STAKEHOLDERS-000-Minimum-Viable-Experience-Stakeholders.md`

Additional carried context:

- The current conversation about debugging from inside scenes, questioning inherited desktop and tool boundaries, and identifying the underlying capabilities the environment should preserve.
- The attached initial draft produced through the earlier Perplexity research attempt.

This reference should be updated when later experiments produce better evidence or a clearer capability model.
