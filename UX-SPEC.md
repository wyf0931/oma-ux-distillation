---
name: UX Distillation Spec
version: 0.1.0
status: draft
record_formats:
  observation:
    required:
      - record_type
      - site
      - page
      - context
      - trigger
      - action
      - response
      - state
      - intent
      - purpose
      - evidence
      - confidence
  pattern:
    required:
      - record_type
      - status
      - name
      - definition
      - problem
      - mechanism
      - trigger
      - action
      - response
      - use_when
      - avoid_when
      - variants
      - examples
      - evidence
      - confidence
    optional:
      - counterexamples
  principle:
    required:
      - record_type
      - name
      - statement
      - rationale
      - supported_by_patterns
      - evidence
      - counterexamples
      - confidence
interaction_schema:
  required:
    - trigger
    - action
    - response
    - state
pattern_statuses:
  - candidate
  - validated
  - rejected
confidence_levels:
  low: The claim has plausible alternatives or is only weakly connected to the observed state.
  medium: The claim fits direct evidence, but reproduction or cross-site comparison is limited.
  high: The claim is supported by reproducible evidence, independent examples, and an explicit boundary check.
---

# UX Distillation Spec

## Overview

The UX Distillation Spec defines how an agent turns website research into evidence that can be compared across products. It is the contract for the companion UX Extraction Skill and for the observation dataset in this repository.

The format follows a useful separation from `DESIGN.md`: structured YAML carries fields that tools can read, while Markdown prose explains context, meaning, and limits. In UX records, the YAML is the normative evidence structure; prose must not claim more than the captured evidence supports.

The Spec does not prescribe what a product should look or behave like. It defines how to observe what a product does, how to distinguish observation from interpretation, and when a repeated mechanism can be called a pattern.

## The five evidence layers

Every claim must remain traceable through this sequence:

```text
L1 Observation → L2 Interaction → L3 Intent → L4 Pattern → L5 Principle
```

### L1 — Observation

Record directly visible facts: site, page, context, the action taken, the response seen, and supporting evidence. A screenshot or page snapshot without an action is page evidence, not proof of an interaction response.

### L2 — Interaction

Normalize a single interaction as:

```text
Trigger → Action → Response → State
```

Use the smallest concrete description that preserves what changed. Include unchanged state when relevant.

These four fields form the reusable `interaction` schema fragment. An observation embeds the fragment with site/page context and intent; the Skill may validate the fragment separately from the full observation record.

### L3 — Intent

Record the likely immediate user intent and the hypothesized purpose separately from observation. Use `unknown` when intent cannot be inferred. Mark confidence on the interpretation, not on whether the page snapshot exists.

### L4 — Pattern

Describe the smallest reusable mechanism that explains independent examples from multiple products. A product or brand name belongs under examples, not in the pattern definition.

### L5 — Principle

State a broader reason or design principle only when multiple validated patterns support it. Keep the supporting patterns and counterexamples linked.

An agent must not jump from one observation to a principle.

## Observation record

One observation file records one interaction. Its YAML front matter contains the required fields listed in the Spec metadata. The evidence field is a list so a record can retain multiple independently inspectable items. The Markdown body explains nuance and limitations without contradicting the structured fields.

```markdown
---
record_type: observation
site: Apple
page: iPhone overview
context: The hero gallery has the iPhone Duo tab selected.
trigger: explicit selection
action: select the iPhone 18 Pro tab
response:
  - the iPhone 18 Pro tab becomes selected
  - the heading, copy, image, and links in the active panel change
state: the active hero product changes from iPhone Duo to iPhone 18 Pro
intent: view another iPhone model
purpose: hypothesis — allow product exploration without leaving the overview page
evidence:
  - evidence_class: observed
    url: https://www.apple.com/iphone/
    captured_at: 2026-10-08
    tool: Chrome DevTools MCP
    reproduction: Open the page and select the iPhone 18 Pro tab.
    before: iPhone Duo tab and panel are active.
    after: iPhone 18 Pro tab and matching panel are active.
    screenshot: null
confidence: medium
---

## Notes

The purpose is an inference from the page behavior; the before/after state is the direct evidence.
```

Field meanings:

- `site`, `page`, `context`: identify the product, location, and initial state.
- `trigger`: the condition that makes the action available or starts it.
- `action`: the user's concrete action; do not write an inferred goal here.
- `response`: observable system output, including feedback or no change.
- `state`: the before/after state transition in concise form.
- `intent`: the likely immediate user goal; may be `unknown`.
- `purpose`: a design-purpose hypothesis, never direct evidence.
- `evidence`: source URL, reproduction, before/after facts, capture tool/date, and optional screenshot.
- `confidence`: `low`, `medium`, or `high` using the rubric in the front matter. State uncertainty in prose as well when needed.

Field types:

| Field | Type | Rule |
|:--|:--|:--|
| `record_type` | string | `observation`, `pattern`, or `principle` |
| `site`, `page`, `context` | string | Use a stable site name and concise page/context labels |
| `trigger`, `action`, `state`, `intent`, `purpose` | string | Use `unknown` when not known; mark purpose as a hypothesis |
| `response` | string or string list | List separate visible responses when useful |
| `evidence` | evidence object list | Each item should identify evidence class, URL/reference, and reproduction or source details |
| `confidence` | enum | `low`, `medium`, or `high` |

Pattern and principle fields use strings for definitions and statements, lists for variants/examples/references, and the same confidence enum. A dedicated interaction schema is a reusable fragment of an observation record, not a separate evidence record.

Use `evidence_class: observed` only when an action and response were inspected. Use `page-evidence` for static page maps and `secondary` for official documentation that describes behavior not reproduced in the browser.

## Pattern record

Pattern records use this YAML front matter and a Markdown body for cross-site reasoning, boundaries, counterexamples, and validation limits:

```markdown
---
record_type: pattern
status: validated
name: Expanded Primary Navigation
definition: A top-level control opens related destinations without leaving the current page.
problem: Visitors need to choose among several destinations under one broad topic.
mechanism: Activate the top-level control to reveal its destination group.
trigger:
  - click
action:
  - activate an expandable navigation control
response:
  - the control enters an expanded state
  - related destination links become available
use_when:
  - several related destinations need to be exposed from one top-level entry
avoid_when:
  - one direct destination is already clear
variants:
  - grouped menu with descriptions
  - topic menu with direct links
examples:
  - Linear
  - Stripe
  - Notion
  - Anthropic
  - Vercel
evidence:
  - ../observations/linear/product-navigation-menu.md
  - ../observations/stripe/product-navigation-menu.md
  - ../observations/notion/product-navigation-menu.md
  - ../observations/anthropic/research-navigation-menu.md
  - ../observations/vercel/products-menu.md
confidence: high
---

## Cross-site invariant

Activating an expandable top-level control reveals related destinations while preserving the current page context.

## Boundaries and counterexamples

Direct links navigate to one destination and do not instantiate this pattern.
```

Use `status: candidate` for a hypothesis that still needs independent examples or counterexample search; use `status: validated` only after it meets the promotion criteria below. Keep rejected hypotheses with `status: rejected` only when their history is useful.

The Markdown body should state:

- The cross-site invariant.
- The sites and observations that support it.
- Boundaries and meaningful counterexamples.
- Limits in the evidence or behavior that remains untested.

## Principle record

Principles summarize why multiple patterns may work together. They require multiple validated pattern references and evidence, for example:

```markdown
---
record_type: principle
name: Preserve agency in content progression
statement: Visitors should retain a way to control the progression of featured content.
rationale: Manual selection and pause controls both let people set the pace of content exploration.
supported_by_patterns:
  - selectable-featured-content
  - user-controlled-automatic-motion
evidence:
  - ../patterns/selectable-featured-content.md
  - ../patterns/user-controlled-automatic-motion.md
counterexamples: []
confidence: medium
---

## Rationale

This claim is a hypothesis supported by the referenced pattern; it is not an observation about an individual site.
```

Do not create principle records just to fill a layer. A principle remains a hypothesis until examples and counterexamples have been compared.

## Promotion and falsifiability

- A candidate needs evidence from at least two independent sites before promotion; three or more is preferred.
- Similar-looking controls do not establish the same pattern. Compare trigger, action, response, and state.
- Record at least one boundary condition or counterexample search in every pattern file.
- Keep website-specific behavior in variants when the shared mechanism still holds.
- If the evidence does not fit one minimal invariant, split or reject the candidate.
- Confidence describes the strength of the interpretation or cross-site fit, not the amount of prose.

## UX tokens and future grammar

This version standardizes observations, interactions, patterns, and principles. It does not predefine a taxonomy or a final UX token vocabulary. A token layer may be derived later as a compact reference to validated patterns and principles, with links back to evidence. Visual design tokens remain out of scope.

## Compatibility with the current dataset

The first research batches used an earlier Markdown template with metadata front matter, fenced YAML interaction blocks, and separate Evidence sections. Existing observations and pattern records remain valid historical evidence in that format. New records and future migrations should conform to this Spec after review; do not rewrite observations in a way that loses original wording, URLs, or capture limits.

## Companion Skill package

The UX Extraction Skill is derived from this Spec and includes focused schema files:

```text
ux-extractor/
├── SKILL.md
└── schemas/
    ├── observation.yaml
    ├── interaction.yaml
    ├── pattern.yaml
    └── principle.yaml
```

The Skill teaches the observation workflow. It may not redefine the schemas or promote a pattern contrary to this Spec.
