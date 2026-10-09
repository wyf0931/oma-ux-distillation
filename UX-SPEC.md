---
name: UX Distillation Spec
version: 0.1.0
status: stable
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
    optional:
      - boundaries
      - counterexamples
  page_map:
    required:
      - record_type
      - site
      - page
      - visible_structure
      - interaction_candidates
      - limits
      - evidence
    optional:
      - related_observations
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
      - boundaries
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
  observation:
    low: The immediate user intent is unknown or several materially different intents are equally plausible.
    medium: The action and context suggest an immediate intent, but plausible alternatives remain.
    high: The action and context make the immediate user intent clear. The purpose field remains a hypothesis regardless of this rating.
  pattern:
    low: The proposed invariant has plausible alternatives or fits the observed interactions weakly.
    medium: Direct observations support the invariant, but cross-site comparison or boundary checks are limited.
    high: The invariant is directly supported across independent sites and a meaningful boundary has been checked.
  principle:
    low: The rationale is tentative or weakly connected to the supporting patterns.
    medium: Multiple validated patterns support the rationale, but alternatives or boundaries remain plausible.
    high: Multiple validated patterns support the rationale and explicit boundaries or counterexamples have been considered.
---

# UX Distillation Spec

## Overview

The UX Distillation Spec defines how an agent turns website research into evidence that can be compared across products. It is the contract for the companion UX Extraction Skill and for the observation dataset in this repository.

The supplied [`design.md` format specification](https://github.com/google-labs-code/design.md/blob/9bf8eae67128b6cc55ad9bf86665767deb4c11cd/docs/spec.md) defines DESIGN.md as plain text with optional YAML front matter and a Markdown body. UX-SPEC borrows the split between machine-readable fields and human-readable guidance, while keeping the evidence source of truth explicit: browser-reproduced action/response and provenance fields are facts; `intent`, `purpose`, `problem`, usage guidance, and principles are interpretations. An item marked `secondary` records what official documentation says, not a browser-verified interaction. Markdown prose explains interpretations and limits. YAML structure does not turn a hypothesis into a fact, and prose cannot strengthen a claim beyond the linked observations. UX-SPEC does not adopt DESIGN.md's visual-token vocabulary or section order; its record types and evidence layers determine the UX structure. Keep shared UX fields small, retaining site-specific details in notes or extensions until repeated research shows they improve comparison.

The Spec does not prescribe what a product should look or behave like. It defines how to observe what a product does, how to distinguish observation from interpretation, and when a repeated mechanism can be called a pattern.

## Scope

Observe interactions that affect how visitors navigate, make choices, understand a state, recover, or continue a task. Relevant evidence includes:

- Navigation and information architecture; page and state transitions.
- Scrolling, hover, click, drag, swipe, and keyboard actions.
- Search, filtering, sorting, comparison, product discovery, and content exploration.
- Forms, progressive disclosure, onboarding, and calls to action.
- Feedback, loading, empty states, errors, recovery, and confirmation.
- Storytelling and motion when they affect navigation, comprehension, feedback, or user decisions.

Do not treat color, typography, spacing, radius, shadow, CSS, framework, or pixel-level appearance as UX evidence. Visual design tokens remain separate; motion is in scope only when its effect on interaction or comprehension can be observed.

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
For an observation, `trigger`, `action`, and `state` are strings describing one concrete interaction; `response` may be a string or a list when several visible responses need recording. Pattern records may summarize shared triggers and actions as lists because they aggregate multiple observations.

For carousels, tabs, paginated groups, and other sequences, identify the active item or visible group before and after. A Previous / Next enabled-state change can corroborate progression, but does not by itself prove the displayed content changed.

These four fields form the reusable `interaction` schema fragment. An observation embeds the fragment with site/page context and intent; the Skill may validate the fragment separately from the full observation record.

### L3 — Intent

Record the likely immediate user intent and the hypothesized purpose separately from observation. Use `unknown` when intent cannot be inferred. Mark confidence on the interpretation, not on whether the page snapshot exists.

### L4 — Pattern

Describe the smallest reusable mechanism that explains independent examples from multiple products. A product or brand name belongs under examples, not in the pattern definition.

### L5 — Principle

State a broader reason or design principle only when multiple validated patterns support it. Keep the supporting patterns and counterexamples linked.

An agent must not jump from one observation to a principle.

## Observation record

One observation file records one interaction. Its required YAML keys are the union of `record_formats.observation.required` and `interaction_schema.required` in the Spec metadata; this keeps the trigger/action/response/state fragment reusable while requiring all four fields on every observation. The evidence field is a list so a record can retain multiple independently inspectable capture or reproduction items. Keep each verification pass in its own item with its own before/after state; do not replace the original capture with a later repetition. The Markdown body explains nuance and limitations without contradicting the structured fields.

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
    captured_at: "2026-10-08"
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
- `evidence`: one capture or reproduction item per list entry, with its source URL, reproduction steps, before/after facts, and capture tool/date; page title, viewport, browser, section, and screenshot are optional. Use a separate item for each safe repeat so the original and repeated states remain inspectable. Store a screenshot beside its observation and reference it with an observation-relative path when possible; a repository-root-relative path is also valid.
- `confidence`: `low`, `medium`, or `high` using the record-type-specific rubric in the front matter. For observations it applies only to inferred immediate intent, not to the certainty of captured facts or to the purpose hypothesis; use `low` when `intent` is `unknown`. For patterns and principles it describes cross-record fit and support.
- `boundaries` and `counterexamples`: optional record-level annotations for an observed adjacent case or a direct contradiction to an identified candidate/pattern. They do not count as pattern support; pattern records remain the canonical place to classify linked observations.

Observation field types:

| Field | Type | Rule |
|:--|:--|:--|
| `record_type` | string enum | `observation`, `page_map`, `pattern`, or `principle`; pattern records also use the `status` field |
| `site`, `page`, `context` | string | Use a stable site name and concise page/context labels |
| `trigger`, `action`, `state`, `intent`, `purpose` | string | Use `unknown` when not known; mark purpose as a hypothesis |
| `response` | string or string list | List separate visible responses when useful |
| `evidence` | record-specific list | Observation and page-map records use evidence objects; pattern and principle records use repository links |
| `confidence` | enum | `low`, `medium`, or `high` |
| `boundaries` | optional string list | Short notes about observed adjacent cases or non-instances; they do not count as pattern support |
| `counterexamples` | optional string list | Short notes about an observed contradiction under the same trigger/context as an identified candidate or pattern |

### YAML string quoting

Quote a YAML string that contains a colon followed by a space, particularly a list item under `response`. An unquoted value such as `- The page title changes to Amazon.com: Wireless Headphones.` may parse as a mapping rather than a string and fail the observation schema. Write it as `- "The page title changes to ‘Amazon.com: Wireless Headphones’."`.

Pattern and principle fields use strings for definitions and statements, lists for variants/examples/references, and the same confidence enum. A dedicated interaction schema is a reusable fragment of an observation record, not a separate evidence record.

### Shared fields and extensions

The schema files define the shared fields needed to compare evidence. Keep details that matter only to one site or one interaction in Markdown notes or an `extensions` object; do not turn every useful local detail into a required field. Preserve unknown YAML keys when reading records. Promote an extension into the shared schema only when multiple independent observations show that it improves comparison or extraction. This keeps the record format consistent without forcing unlike interactions into premature categories.

Use `evidence_class: observed` only when an action and response were inspected. Use `secondary` for official documentation that describes behavior not reproduced in the browser; mark reproduction and before/after as not reproduced or not observed, and phrase `response` as the documentation's claim rather than a reproduced outcome. A secondary item establishes that the source describes a behavior, not that the website currently exhibits it; it cannot count as a directly observed pattern instance. Static page maps are page evidence stored in `corpus/`, not interaction observations, and do not use the observation evidence schema.

## Page-map record

A page map captures static page evidence when a page or control is visible but no interaction response has been tested. It helps choose the next safe action; it cannot support a pattern or be described as an observed interaction. Save one page map per page under `corpus/<corpus-slug>/`, using `corpus/_page-map-template.v1.md` and `ux-extractor/schemas/page-map.yaml`. The path uses the corpus directory slug; the frontmatter `site` value must exactly match `corpus/<corpus-slug>/site.md`.

Its YAML front matter records:

- `site` and `page`: the product and page label.
- `visible_structure`: directly visible regions and controls.
- `interaction_candidates`: controls or paths worth testing later, stated as questions or possible actions rather than observed responses.
- `limits`: what was not tested or could not be established.
- `evidence`: URL, capture date, tool, and available title, viewport, and browser details. Each item uses `evidence_class: page-evidence`.
- `related_observations`: optional links to interaction observations from the same page.

Keep the page map factual. If an action is later tested, save a separate interaction observation and link it; do not rewrite the map as interaction evidence.

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
boundaries:
  - ../observations/vercel/pricing-direct-link.md
counterexamples: []
confidence: high
---

## Cross-site invariant

Activating an expandable top-level control reveals related destinations while preserving the current page context.

## Boundaries and counterexamples

Direct links navigate to one destination and do not instantiate this pattern.
```

Use `status: candidate` for a hypothesis that still needs independent examples or counterexample search; use `status: validated` only after it meets the promotion criteria below. Keep rejected hypotheses with `status: rejected` only when their history is useful.

Pattern front matter keeps three evidence roles separate:

- `evidence` contains only observations that instantiate the pattern and count toward the independent-site threshold.
- `boundaries` link non-instances or adjacent cases that clarify where the pattern does and does not apply. They do not count as support and do not by themselves disprove the pattern.
- `counterexamples` link cases that match the pattern's stated trigger and context but contradict its proposed invariant. Use this field only when the case could falsify the definition.

`problem`, `use_when`, and `avoid_when` are interpretation fields by schema definition: they express hypotheses inferred from the interaction examples, not direct observations or user-research findings. Keep the claims proportionate to the evidence and never present them as user-research results unless separate research is linked. Pattern `confidence` describes fit of the shared interaction invariant; it does not validate every usage recommendation.

Candidate files in `candidates/` use the same `pattern.yaml` schema with `status: candidate`. When a candidate is promoted, write the validated record in `patterns/` and keep the candidate file as a traceable decision record; update its structured status to `validated`. A rejected candidate may remain with `status: rejected` when its evidence is useful to future comparisons.

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
  - patterns/selectable-featured-content.md
  - patterns/user-controlled-automatic-motion.md
evidence:
  - patterns/selectable-featured-content.md
  - patterns/user-controlled-automatic-motion.md
counterexamples: []
confidence: medium
---

## Rationale

This claim is a hypothesis supported by the referenced pattern; it is not an observation about an individual site.
```

Do not create principle records just to fill a layer. A principle remains a hypothesis until examples and counterexamples have been compared.
Use repository-root-relative paths in principle records' `supported_by_patterns` and `evidence` fields so tools can resolve the validated pattern records regardless of where the principle document is stored.

Store principle records in `taxonomy/principles/<slug>.md` using `taxonomy/_principle-template.v1.md`. Require at least two validated supporting patterns, preferably three or more. State the shared rationale and alternative explanations, link patterns that challenge the scope, and keep confidence proportionate to the evidence. Interface observations alone do not establish user outcomes or causal benefit. Do not add higher-level taxonomy groups until multiple principles reveal a useful cluster.

## Pattern quality

A pattern proposed for promotion must meet these criteria:

- **Reusable:** the same interaction invariant is directly supported by multiple independent product sites.
- **Observable:** every supporting example records a concrete trigger, user action, system response, and resulting state.
- **Semantic:** the definition describes the interaction logic, not a brand-specific component or visual treatment.
- **Minimal:** the definition states the smallest behavior shared by the examples; real implementation differences stay in `variants`.
- **Falsifiable:** the definition makes clear what behavior would contradict it, and the record includes at least one boundary or counterexample search.

If a criterion cannot be checked from the available evidence, keep the record as a candidate or state the unresolved limit. Do not use opinions such as “smooth,” “modern,” or “user-friendly” as pattern definitions.

## Promotion and falsifiability

- A candidate needs evidence from at least two independent sites before promotion; three or more is preferred.
- Count independence by distinct product/site identities in `corpus/`, not by pages, paths, locales, or subdomains; those are one site when they belong to the same product. Separate products may count separately when they have distinct product experiences and separate corpus records. If independence is uncertain, count the examples as one site and record the reason for any exception.
- Similar-looking controls do not establish the same pattern. Compare trigger, action, response, and state.
- Only directly observed interaction records that instantiate the candidate count toward the independent-site threshold. In version 0.1.0 records, the supporting item in `evidence` must use `evidence_class: observed`. In historical records, the front matter may place `evidence_class: observed` at the top level and store interaction details in Markdown; count such a record only when its `Interaction` and `Evidence` sections identify the user action, observed result, source URL, and reproduction or capture method. This is an evidence review rule, not permission to rewrite the historical record. `secondary` documentation and page maps never count as observed instances.
- Non-instances belong in `boundaries`; blocked behavior and unverified states belong in `limits`. None count as support.
- Use `counterexamples` only for cases that match the trigger/context but contradict the proposed invariant; a different interaction or a missing state is not automatically a counterexample.
- Record at least one boundary condition or counterexample search in every pattern file.
- Keep website-specific behavior in variants when the shared mechanism still holds.
- If the evidence does not fit one minimal invariant, split or reject the candidate.
- Confidence describes the strength of the interpretation or cross-site fit, not the amount of prose.

## UX tokens and future grammar

This version standardizes observations, interactions, patterns, and principles. It does not predefine a taxonomy or a final UX token vocabulary. A token layer may be derived later as a compact reference to validated patterns and principles, with links back to evidence. Visual design tokens remain out of scope.

## Compatibility with the current dataset

The first research batches used an earlier Markdown template with metadata front matter, fenced YAML interaction blocks, and separate Evidence sections. Existing observations, page maps, and pattern records remain valid historical evidence in their original formats. Historical-format interaction records may support a pattern only when `evidence_class: observed` and the documented action, result, URL, and capture or reproduction method establish a directly observed interaction. Treat incomplete historical entries as unverified and do not count them. New observations and page maps use the version 0.1.0 templates and schemas. Keep historical records unchanged unless a migration is deliberately planned; do not lose original wording, URLs, or capture limits.

## Companion Skill package

The UX Extraction Skill is derived from this Spec and includes focused schema files:

```text
ux-extractor/
├── SKILL.md
└── schemas/
    ├── observation.yaml
    ├── page-map.yaml
    ├── interaction.yaml
    ├── pattern.yaml
    └── principle.yaml
```

The Skill teaches the observation workflow. It may not redefine the schemas or promote a pattern contrary to this Spec.

The companion Skill also uses `ux-extractor/schemas/site.yaml` to validate corpus target metadata. That schema is repository planning metadata, not one of the UX evidence record formats defined by this Spec.
