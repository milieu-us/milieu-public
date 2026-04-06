# RECORD-002 - Current Markdown Representation for Records

- **ID:** RECORD-002
- **Status:** Working Draft
- **Created:** 2026-04-06
- **Updated:** 2026-04-06

## Intent

Define the current Markdown representation used to preserve records so that human agents, AI agents, and system agents can read, validate, render, and process them consistently.

This record establishes practical conventions for clarity and stability while preserving the ability to adopt other representations in the future.

## Representation Principle

Records are format-independent in principle.

Markdown is the current preservation and working format.

Any representation of a record must preserve:

- identity
- required metadata
- semantic content

Markdown is one such representation, chosen for current practicality.

## Why Markdown (Current Use)

Markdown is used because it:

- is legible to humans
- is legible to LLM-based agents
- works well with version control and diffs
- renders cleanly to HTML
- can be parsed with simple scripts

These benefits are practical, not foundational.

## Required Structure

Each record must follow this structure:

1. First H1 (heading)
2. Metadata block (bullet list)
3. Body sections

## Heading (H1)

The first H1 is required.

It must begin with the record ID.

### Valid forms

`# RECORD-001 - Record Types and Semantics`
`# RECORD-033`

### Rules

- ID must appear first
- additional text is optional
- additional text is for human readability
- the H1 is the canonical rendered heading

## Title Delimiter

When including additional heading text after the ID in the H1, use a hyphen.

Example:

`# RECORD-001 - Record Types and Semantics`

Rules:

- use `-` (space hyphen space)
- do not use em-dash (`—`)
- do not use colon (`:`)
- keep delimiter consistent across all records

## Metadata Block

The metadata block appears immediately after the first H1.

It is a flat bullet list using `-`.

### Required fields

- **ID:** RECORD-001
- **Status:** Working Draft
- **Created:** 2026-04-06
- **Updated:** 2026-04-06

### Rules

- one field per line
- use `-` for bullets (not `*`)
- key is bold and includes colon (`**Key:**`)
- single space after colon
- no nested structures
- no additional formatting in values

## Identity Consistency

The ID in metadata must match the ID in the first H1 exactly.

A mismatch indicates a malformed record and must be corrected.

Agents are expected to verify this when creating or editing records.

## Sections

Sections use `##` headings.

The first section should be:

`## Intent`

Additional sections follow as needed.

### Rules

- use `##` for primary sections
- use `###` and so on for subsections if needed
- avoid skipping heading levels

## Section Numbering

Numbered sections are optional and should be used only when stable referencing or deep structure is beneficial (e.g. the 'Required Structure' section above).

Prefer unnumbered headings (`##`, `###`) by default.

### When to Use Numbered Sections

Use numbered sections when:

- the document is normative and relatively stable
- sections must be referenced externally (e.g., policy, agreements)
- the document contains multiple levels of nested structure
- hierarchical relationships need to be made explicit (e.g., `1`, `1.2`, `1.2.3`)

### When to Avoid Numbered Sections

Avoid numbered sections when:

- the document is evolving or frequently refactored
- there are few sections or minimal nesting
- numbering does not add clarity
- section order is likely to change

### Guidance

- prefer numbering only when necessary
- simple documents are usually clearer without numbering
- deeply nested or highly structured documents benefit most from numbering

If numbering is used:

- numbering is part of the content and must be maintained explicitly
- do not rely on automatic numbering behavior
- ensure numbering remains consistent after edits

## Lists

Lists must use -.

### Example

- item one
- item two

### List Rules

- do not mix - and *
- include a space after -
- use blank lines before and after lists

## Spacing

Use blank lines to separate:

- H1 and metadata
- metadata and first section
- sections
- lists and surrounding content

Avoid relying on Markdown edge cases for rendering.

## Code Blocks

Use fenced code blocks with triple backticks when needed for multi-line or structured examples.

Do not rely on indentation-based code blocks.

## Formatting Constraints

Prefer consistency over stylistic variation.

Avoid:

- decorative formatting
- unnecessary emphasis
- complex nesting

Records should be:

- easy to scan
- easy to diff
- easy to parse

## Optional Fields

Additional metadata fields may be introduced as needed.

They must:

- follow the same formatting rules
- provide clear value
- not conflict with existing fields

No field should be added without demonstrated use.

## Future Representation Compatibility

Records are not bound exclusively to Markdown.

Alternate representations may be introduced if they:

- preserve identity
- preserve required metadata
- preserve semantic meaning

Multiple representations may coexist.

Markdown remains the current working format unless replaced or supplemented by future records.

## Notes

- Markdown is a vessel, not the source of truth
- conventions are intentionally minimal
- structure should evolve through use, not anticipation
