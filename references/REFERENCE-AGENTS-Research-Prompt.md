# REFERENCE-AGENTS-000 - Research Prompt for Milieu.Us

- ID: REFERENCE-AGENTS-Research-Prompt
- Status: Draft
- Created: 2026-04-29
- Updated: 2026-04-29

```text
You are performing a Deep Research pass for Milieu.Us on agentic workflows for bounded context, agent briefing, carried context, and practical validation through an Unreal Engine test harness.

Primary repository to review:

https://github.com/milieu-us/milieu-public

Begin with:

https://github.com/milieu-us/milieu-public/tree/main/references

Required reference documents to review at minimum:

- REFERENCE-AGENTS-000 - Agents Foundational View
- REFERENCE-AGENTS-001 - Multi-Dimensional Agent Systems
- REFERENCE-AGENTS-002 - Carried Context Working Concept
- REFERENCE-AGENTS-003 - Agent Coordination Model
- REFERENCE-AGENTS-004 - Proposal: milieu-public as Context Service
- REFERENCE-AGENTS-Change-Proposals-Merge-Strategy
- REFERENCE-AGENTS-VALUEFLOWS-001 - Measurement Types

Also review any directly related records or references needed to understand:

- Milieu record conventions
- decision/architecture/reference document expectations
- Prismal Space
- Unreal Engine experiment/test harness work
- agent coordination
- carried context
- context publishing
- value-flow measurement
- change proposals and pull request workflow

Do not assume the existing documents are correct or final. Treat them as working guesses that may need revision.

Research goal:

Validate and improve a practical agentic workflow that allows human agents, AI agents, and system agents to receive bounded, source-traceable context before acting, without requiring every agent to reread the entire repository or reconstruct specialized domain knowledge from scattered conversations.

The workflow should be tested against a real scenario involving an Unreal Engine test harness. The specific Unreal test may be small; the important thing is to prove the agent workflow with real work, real context boundaries, real artifacts, and observable results.

Important Milieu framing:

- “Agents” includes human agents, AI agents, and system agents.
- Avoid insider slang where possible.
- Prefer clear, explicit names.
- Spell out terms before using acronyms.
- Do not treat task lists as the primary model of work.
- Treat carried context as the portable continuity another agent needs to continue the work well.
- Treat GitHub issues, branches, pull requests, records, and references as coordination surfaces, not merely storage.
- Prefer observable, source-traceable workflows.
- Avoid workflows that produce endless documentation without working validation.
- The purpose is not to create more bureaucracy. The purpose is to help agents work with enough context, at the right time, with bounded scope and visible assumptions.

Specific problem to investigate:

Milieu now has many complex overlapping domains:

- mathematics
- physics and chemistry
- philosophy
- multi-stakeholder governance
- value flows and business model
- Unreal Engine
- Prismal Space
- roleplay entertainment experience
- agent coordination
- records and repository governance
- operations and future system automation

Agents cannot reasonably ingest all of this context every time. The repository alone is too much context, and many important assumptions currently live across records, references, pull requests, issues, and conversations.

We need an agentic workflow where an agent can receive only the relevant context needed for a specific work session, while preserving traceability and preventing meaning drift.

Candidate workflow to validate:

Work request
→ context intake
→ bounded context bundle / briefing
→ agent action
→ context trace
→ context diff
→ review gate
→ context propagation

Evaluate whether this is a good model. Improve it if needed.

Core concepts to investigate:

1. Context intake

What questions should be answered before an agent begins work?

Candidate questions:

- What is the requested work?
- Which surface is this work happening on?
- Which artifact is being changed or reviewed?
- Which domain or domains are involved?
- Which records or references are required?
- Which records or references are relevant but not required?
- Which assumptions must not be made?
- Which decisions are open?
- Which authority or standing does the acting agent have?
- What output is allowed?
- What output is explicitly out of scope?
- What would count as observable evidence of success?

2. Context bundle / briefing

Define the minimum viable structure for a context bundle.

A context bundle should not be a dump of repository files. It should be a bounded continuity object.

Candidate contents:

- work request
- relevant domain lenses
- required sources
- optional sources
- excluded sources
- current working frame
- loaded terms
- known risks
- open decisions
- permitted actions
- expected outputs
- review gates
- measurement expectations

3. Context trace

Define what an agent must report after acting.

Candidate trace:

- sources used
- sources not inspected
- assumptions made
- constraints followed
- terms interpreted
- context changed
- context preserved
- confidence
- evidence quality
- recommended follow-up

4. Context diff

Define a pull request or change proposal section that captures meaning changes, not just file changes.

Candidate structure:

- Context Added
- Context Changed
- Context Preserved
- Context Excluded
- Downstream Consumers Affected
- Required Follow-Up
- Meaning Drift Risk
- Review Requested

5. Review gates

Define the minimum review gates needed before merging or accepting work.

Possible gates:

- Records compliance
- Domain meaning preservation
- Implementation feasibility
- test evidence
- context trace completeness
- safety or governance review where needed

6. Context propagation

Define when a completed change should update:

- a record
- a reference
- a current working frame
- a context packet
- a GitHub issue
- a pull request template
- a test harness scenario
- a system automation

Real-world validation scenario:

Use an Unreal Engine test harness scenario to evaluate the proposed workflow.

The actual Unreal test can be simple, but it must be concrete. The goal is to prove that the workflow enables agents to do bounded, meaningful work and produce observable results.

Possible test scenario:

“Add or review a minimal Prismal Unreal Engine test harness scene that demonstrates a lattice or cell cluster view, while explicitly preventing the implementation substrate from being mistaken for Prismal’s foundation ontology.”

The test should require context from more than one domain, for example:

- Prismal foundations
- Unreal Engine implementation
- Records or architecture conventions
- Agent carried context
- test evidence
- context diff

The research should propose a minimal validation plan using this scenario.

The validation plan should answer:

- What work request should start the test?
- What context bundle should the acting agent receive?
- What should the agent be forbidden from assuming?
- What artifact should the agent produce or modify?
- What observable result should prove progress?
- What review gates should apply?
- What context trace should the agent return?
- What context diff should appear in the pull request or change proposal?
- What measurement types should be used?
- What would count as success?
- What would count as workflow failure?

Preferred output:

Produce a practical research report, not a generic essay.

Use this structure:

# Deep Research Report: Agent Briefing and Context Intake Workflow for Milieu

## 1. Executive Summary

Summarize whether the proposed workflow is viable, what should change, and what should be tested first.

## 2. Repository Findings

Summarize the relevant claims from the reviewed Milieu references and records. Cite specific files and sections where possible.

## 3. Problem Diagnosis

Explain why “read the whole repository” fails as an agent workflow.

Distinguish between:

- missing context
- too much context
- stale context
- hidden assumptions
- meaning drift
- domain collision
- implementation choices becoming ontology
- documentation without observable work

## 4. Proposed Workflow

Define the recommended workflow.

Include:

- workflow steps
- agent roles
- inputs
- outputs
- required traceability
- minimum required artifacts

## 5. Context Bundle Template

Provide a reusable template for an agent briefing/context bundle.

The template should be usable by human agents, AI agents, and system agents.

## 6. Context Trace Template

Provide a reusable template for what an agent reports after acting.

## 7. Context Diff Template

Provide a reusable pull request or change proposal section.

## 8. Unreal Engine Test Harness Validation

Design a concrete validation scenario.

The validation should involve a small Unreal Engine test harness task, but the test should prove the workflow rather than merely prove Unreal code works.

Include:

- scenario
- work request
- required context bundle
- expected action
- expected artifact
- observable result
- review gates
- success criteria
- failure criteria

## 9. Measurement Plan

Use the Milieu measurement vocabulary where applicable:

- Boolean
- Unit Scale
- Quantity with Units

Suggest specific measurements, for example:

- context_bundle_complete: Boolean
- required_sources_inspected: Boolean
- records_compliance_passed: Boolean
- implementation_test_passed: Boolean
- meaning_drift_risk: Unit Scale
- evidence_quality: Unit Scale
- reviewer_confidence: Unit Scale
- time_spent_minutes: Quantity with Units
- rework_minutes: Quantity with Units

## 10. Recommended Repository Changes

Recommend specific next changes.

For example:

- create REFERENCE-AGENTS-005 - Agent Briefing and Context Intake Workflow
- update pull request template with Context Diff
- create one or more context bundle examples
- create one canonical Unreal test harness validation issue
- update REFERENCE-AGENTS-004 if context publishing is now urgent
- identify whether any decision record is needed

## 11. Risks and Failure Modes

Include likely failures, such as:

- context bundles becoming too large
- agents treating briefing summaries as authoritative when they are not
- too many gates
- hidden human assumptions not recorded
- overfitting to one Unreal scenario
- creating more documents without working evidence
- letting implementation convenience define foundation concepts
- system automation hiding meaning too early

## 12. Final Recommendation

Provide a concrete recommended next move.

This should be practical and action-oriented.

Avoid recommending a large platform build as the first step. Prefer a minimal manual workflow that can later be automated after repeated use.

Expected style:

- Clear and direct.
- No hype.
- No generic “AI agents are the future” framing.
- Use Milieu’s language carefully.
- Do not overfit to current documents.
- Surface uncertainty.
- Prefer practical validation over more theory.
- Distinguish reference, decision, architecture, and implementation work.
- Avoid proposing rigid task-based workflows as the primary model.
- Make sure the output can lead to a real GitHub issue, pull request, or Unreal Engine test harness run.

Key research question:

What is the minimum viable agent briefing and context intake workflow that lets Milieu agents act with enough specialized context to produce real, observable work, without requiring every agent to ingest the whole repository every time?
```
