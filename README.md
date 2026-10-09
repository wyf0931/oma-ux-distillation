# UX Distillation

This repository builds an evidence dataset from real product interactions. The two core reusable outputs are the **UX Distillation Spec** and the **UX Extraction Skill**; the corpus and pattern library ground them in observed behavior.

## Research sequence

```text
site / page / initial state
  → user action + observed response + provenance
  → L1 observation
  → L2 interaction
  → L3 intent hypothesis
  → cross-site L4 pattern candidate
  → validated pattern
  → L5 principle
```

Keep evidence linked at every step. Observations describe visible behavior; intent and purpose remain hypotheses. A single site can support an observation or a candidate, but a reusable L4 pattern requires directly observed examples from multiple independent sites.

## Repository map

- `corpus/` — target sites, metadata, and static page maps. New site records use [`corpus/_site-template.v1.md`](corpus/_site-template.v1.md), validated by [`ux-extractor/schemas/site.yaml`](ux-extractor/schemas/site.yaml); new page maps use [`corpus/_page-map-template.v1.md`](corpus/_page-map-template.v1.md).
- `observations/` — one concrete interaction per file, using the current Spec template.
- `candidates/` — hypotheses and promotion records using [`candidates/_template.v1.md`](candidates/_template.v1.md) for new candidates.
- `patterns/` — validated, evidence-linked patterns with a flat [pattern index](patterns/README.md).
- `taxonomy/principles/` — evidence-derived principles supported by multiple validated patterns. Start from [`taxonomy/_principle-template.v1.md`](taxonomy/_principle-template.v1.md); higher-level groupings wait until principles reveal useful clusters.
- `research/` — batch log and repeatable capture protocol.
- [`UX-SPEC.md`](UX-SPEC.md) — stable version 0.1.0 record and promotion contract, informed by Google's DESIGN.md format while keeping UX evidence distinct from visual design tokens.
- `ux-extractor/SKILL.md` — companion extraction workflow, paired with machine-readable schemas in `ux-extractor/schemas/`.

## Current progress

See [the corpus catalog](corpus/README.md) and [research log](research/README.md). The active corpus contains 23 sites (the initial 20 plus Intel, eBay, and Best Buy as targeted follow-ups), with 195 interaction observations (163 using UX-SPEC 0.1.0 and 32 historical records), eleven page maps (two using the current schema and nine historical maps), nineteen cross-site patterns, one candidate awaiting cross-site validation, and one evidence-derived principle. OpenAI and Perplexity are deferred after human-verification challenges; Mistral AI and DuckDuckGo / Duck.ai are the documented substitutes. UX-SPEC 0.1.0 is stable and passes Draft 2020-12 validation; the Skill is aligned and evaluated, with browser-baseline limits documented in the research log. The zero-count facet candidate remains unvalidated.

## Add an observation

New observations should use [`observations/_template.v1.md`](observations/_template.v1.md), which follows stable UX-SPEC 0.1.0. The original [`observations/_template.md`](observations/_template.md) remains as the legacy format for existing records; historical records are not silently migrated. Preserve source URLs, action/response, reproduction steps, capture date, and tool, and mark uncertainty explicitly.

## Promotion rule

A candidate can move into `patterns/` only after independent examples from at least two sites show the same interaction invariant. Keep supporting cases separate from boundary evidence and true counterexamples; retain meaningful implementation differences as variants only when the invariant still holds. Keep the abstraction falsifiable and small.

Confirmed patterns: [Expanded Primary Navigation](patterns/expanded-primary-navigation.md), [Escape Dismissal for Navigation Menus](patterns/escape-dismissal-for-navigation-menus.md), [Inline Answer Disclosure](patterns/inline-answer-disclosure.md), [Inline Email Format Validation Feedback](patterns/inline-email-format-validation-feedback.md), [Email Validation Feedback Updates After Correction](patterns/email-validation-feedback-updates-after-correction.md), [Language Selection Preserves Content Path](patterns/language-selection-preserves-content-path.md), [Facet Selection Refines a Visible Result Set](patterns/facet-selection-refines-visible-results.md), [Pre-query Search Shortcuts](patterns/pre-query-search-shortcuts.md), [Request-Type-Driven Contact Routing](patterns/request-type-driven-contact-routing.md), [Search Zero-Results Recovery](patterns/search-zero-results-recovery.md), [Selectable Featured Content](patterns/selectable-featured-content.md), [Query-Guided Search Assistance](patterns/query-guided-search-assistance.md), [Selection-Synchronized Product Preview](patterns/selection-synchronized-product-preview.md), [Context-Preserving Result Sorting](patterns/context-preserving-result-sorting.md), [Cross-Facet Availability Counts Update](patterns/cross-facet-availability-counts-update.md), [Billing Cadence Selection Updates Plan Prices](patterns/billing-cadence-selection-updates-plan-prices.md), [User-Controlled Automatic Motion](patterns/user-controlled-automatic-motion.md), [Upstream Selection Constrains Downstream Options](patterns/upstream-selection-constrains-downstream-options.md), and [Preselected Search Scope Carries into Results](patterns/preselected-search-scope-carries-into-results.md). Promoted candidate records remain in `candidates/` for traceability.

First derived principle: [Preserve the Active Task Context](taxonomy/principles/preserve-active-task-context.md). It is a medium-confidence interpretation supported by five validated patterns; user outcome data has not been collected.

The eventual UX token / grammar format will be derived from the validated library rather than decided in advance.
