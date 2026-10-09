---
record_type: pattern
status: validated
name: Upstream Selection Constrains Downstream Options
definition: Selecting a parent choice scopes the next available choices to compatible descendants, either by updating dependent controls or revealing a child choice set.
problem:
  - Visitors may face irrelevant or incompatible choices when related controls are presented independently.
mechanism: Use a parent choice to update, select defaults for, or reveal the next compatible choice set.
trigger:
  - A flow presents a hierarchy of choices where later options depend on an earlier choice.
action:
  - Select a parent category or value.
response:
  - The upstream control shows the selected value.
  - The next available choices belong to the selected parent branch.
  - A result set or later configuration state may also update in place.
use_when:
  - Product families, series, models, or other choices form a real hierarchy.
avoid_when:
  - Choice dimensions are independent and should remain available for cross-category exploration.
variants:
  - "A table filter narrows both a result set and another filter's options: AMD."
  - "A product category updates downstream series and product selectors, with defaults selected automatically: NVIDIA."
  - "An in-page product taxonomy replaces parent choices with child family or series links: Intel."
  - "Widening the parent to All retains a compatible selected Series value: AMD."
examples:
  - AMD
  - NVIDIA
  - Intel
evidence:
  - ../observations/amd/processor-specifications-family-filter.md
  - ../observations/amd/processor-specifications-clear-family-restores-series.md
  - ../observations/nvidia/driver-search-category-updates-series-and-product-options.md
  - ../observations/nvidia/driver-search-category-change-resets-manual-series.md
  - ../observations/intel/product-specifications-processors-opens-families.md
  - ../observations/intel/core-ultra-family-opens-series-choices.md
  - ../observations/amd/processor-specifications-widen-family-retains-series.md
confidence: high
boundaries:
  - ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
  - ../observations/porsche/country-selector-expand-region.md
  - ../observations/tesla/model-y-selects-complete-long-wheelbase-variant.md
counterexamples: []
---

## Cross-site invariant

On AMD, NVIDIA, and Intel, choosing an upstream product value scoped the next choices to that product branch. AMD's Family = Ryzen selection reduced the Series choices from 101 across families to 18 Ryzen series and narrowed the table from 745 entries to 302; clearing Family restored the 101 series choices and 745 results. NVIDIA's category choice changed the available driver series and model options and selected defaults; changing categories reset a manually selected, incompatible series and model. Intel's in-page Product Specifications flow replaced product-category choices with processor families, then replaced families with Intel Core Ultra series links. In a follow-up, Intel's Back control restored the parent family list and hash ([observation](../observations/intel/core-ultra-drilldown-back-restores-families.md)).

## Boundaries and counterexamples

Amazon's Sony brand filter left other brands and separate facets available for combination, so that result page does not establish a parent-child dependency. Porsche's Europe disclosure exposed country and language links, but it was a region expansion rather than a selected constraint that recomputed downstream choices. Neither is a direct counterexample to the stated invariant.

## Validation limits

The invariant has three independent site examples and high confidence for hierarchical product choices. AMD's table filter restores child options and results when Family is cleared; Intel's Back control restores the ancestor choice list. AMD also retained Ryzen 9000 Series when Family widened from Ryzen to All, with the matching 15-row result set unchanged. This does not establish retention across sibling parent branches or on other sites. NVIDIA resets a manually selected series and product when the parent changes to an incompatible category. Empty downstream option sets and keyboard operation also remain untested. Use guidance is inferred from the observed table, form, and drilldown variants.
