---
record_type: principle
name: Preserve the Active Task Context
statement: During an ongoing task, let visitors change one dimension of the current state without losing the context they need to continue that task.
rationale: >
  Five validated patterns show this continuity across different local changes. Result sorting and facet selection retain the
  current query or listing; language selection retains the content destination; billing cadence updates prices in the
  current pricing context; and product configuration updates the live preview in the current build. Together, these
  patterns suggest that a local choice should update its affected state while keeping the active task anchor available.
  This is an interpretation of interface behavior, not evidence that users complete tasks faster or prefer this behavior.
supported_by_patterns:
  - patterns/context-preserving-result-sorting.md
  - patterns/facet-selection-refines-visible-results.md
  - patterns/language-selection-preserves-content-path.md
  - patterns/billing-cadence-selection-updates-plan-prices.md
  - patterns/selection-synchronized-product-preview.md
evidence:
  - patterns/context-preserving-result-sorting.md
  - patterns/facet-selection-refines-visible-results.md
  - patterns/language-selection-preserves-content-path.md
  - patterns/billing-cadence-selection-updates-plan-prices.md
  - patterns/selection-synchronized-product-preview.md
counterexamples:
  - patterns/request-type-driven-contact-routing.md
  - patterns/pre-query-search-shortcuts.md
confidence: medium
---

## Scope and boundaries

This principle applies when a visitor changes one dimension within an active task, such as result order, result membership,
language, billing cadence, or a product option. It does not mean that every interaction should stay on the same page. The
validated `Request-Type-Driven Contact Routing` pattern intentionally routes a declared contact need to another form or
team; `Pre-query Search Shortcuts` lets a visitor choose a new destination before a search task is established. These
patterns challenge an unqualified “always preserve context” rule, so the principle is limited to local changes within an
ongoing task.
