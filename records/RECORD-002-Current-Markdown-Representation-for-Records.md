# RECORD-002 - Current Markdown Representation for Records

- **ID:** RECORD-002
- **Status:** Working Draft
- **Created:** 2026-04-06
- **Updated:** 2026-04-22

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

## Unicode Character Usage

Use ASCII for content that might be searched or implemented.

Use Unicode only where the symbol itself carries established semantic weight or serves a decorative purpose.

### Allowed Unicode

| Character | Example | Rationale |
|-----------|---------|-----------|
| **λ** (lambda) | **λ_0** through **λ_3** | Established math convention (150+ years) |
| **™** (trademark) | Prismal Space™ | Decorative/aesthetic, not searchable |

### Normalize to ASCII

| Instead of | Use | Rationale |
|------------|-----|-----------|
| **Z³** | **Z^3** | Searchable, matches code conventions |
| **α**, **β**, **γ** for arbitrary variables | **a**, **b**, **c** or descriptive names | Avoidable, adds friction |

### Rule

> Prefer ASCII for semantic content. Reserve Unicode for symbols with established meaning or decorative marks.

## Mathematical Expressions

Use ASCII-first notation for narrative text. Reserve fenced code blocks with `math` language tag for precise formulas.

### Approach

1. **Narrative first**: Define concepts with plain text and bold symbols
2. **Precision second**: Provide exact formulas in ` ```math ` blocks when needed

### Example

````markdown
A point **x** in a tetrahedron with vertices **v_0** through **v_3** is defined as a weighted combination of those vertices, where the barycentric weights **λ_0** through **λ_3** sum to 1:

```math
x = \sum_{i=0}^{3} \lambda_i v_i, \quad \sum_{i=0}^{3} \lambda_i = 1
```
````

### Rationale

- **Human readability**: Plain text is scannable without parsing LaTeX
- **LLM efficiency**: Reduces token overhead for narrative sections
- **Precision preservation**: Exact formulas remain available for rendering
- **Searchability**: ASCII terms are grep-friendly

### When to Use Math Blocks

Use ` ```math ` when:

- The exact notation carries semantic weight
- Summation, integration, or complex operators are required
- The formula may be rendered to MathML or displayed

Use ASCII in narrative when:

- Simple variable references suffice
- The concept is explained in prose
- Search and scan efficiency matters more than notational precision
- Inline code backticks may be used for short coordinate tuples and simple expressions that do not require full math rendering (e.g., `(1/2, 1/2, 0, 0)`, `x + y + z`)

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
