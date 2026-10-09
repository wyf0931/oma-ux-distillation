---
record_type: pattern
status: validated
name: Upstream Selection Constrains Downstream Options
definition: "Selecting a parent choice scopes the next available choices to compatible descendants, either by updating dependent controls or revealing a child choice set."
problem:
  - "Visitors may face irrelevant or incompatible choices when related facets are presented independently."
mechanism: "Use a parent choice to update, select defaults for, or reveal the next compatible choice set."
trigger:
  - "A flow presents a hierarchy of choices where later options depend on an earlier choice."
action:
  - "Select a parent category or value."
response:
  - "The next available choices belong to the selected parent branch."
  - "A result set or later configuration state may also update in place."
use_when:
  - "Product families, series, models, or other choices form a real hierarchy."
avoid_when:
  - "Choice dimensions are independent and should remain available for cross-category exploration."
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
  - ../observations/nvidia/driver-search-category-updates-series-and-product-options.md
  - ../observations/nvidia/driver-search-category-change-resets-manual-series.md
  - ../observations/intel/product-specifications-processors-opens-families.md
  - ../observations/intel/core-ultra-family-opens-series-choices.md
  - ../observations/amd/processor-specifications-widen-family-retains-series.md
boundaries:
  - ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
  - ../observations/porsche/country-selector-expand-region.md
  - ../observations/tesla/model-y-selects-complete-long-wheelbase-variant.md
counterexamples: []
confidence: high
---

# Candidate: Upstream Selection Constrains Downstream Options

**Status:** promoted to [Upstream Selection Constrains Downstream Options](../patterns/upstream-selection-constrains-downstream-options.md) after the parent-child choice invariant was observed on AMD, NVIDIA, and Intel. This file preserves the original hypothesis and cross-site comparison.

## Hypothesis

Selecting a parent choice can scope the next available choices to compatible descendants. Implementations may update dependent controls, narrow a result set, or reveal child choices in an in-page taxonomy.

## Evidence comparison

- [AMD: Family filter on Processor Specifications](../observations/amd/processor-specifications-family-filter.md) — choosing Ryzen reduced the Series options from 101 across families to 18 Ryzen series and narrowed the table from 745 to 302 entries. The URL stayed unchanged.
- [AMD: clearing Family restores Series choices](../observations/amd/processor-specifications-clear-family-restores-series.md) — setting Family back to All restored all 101 Series values and the 745-row table without changing the URL.
- [AMD: widening Family retains Ryzen 9000 Series](../observations/amd/processor-specifications-widen-family-retains-series.md) — widening the parent to All leaves the selected child and its 15 matching rows in place.
- [NVIDIA: Product Category in Manual Driver Search](../observations/nvidia/driver-search-category-updates-series-and-product-options.md) — choosing NVIDIA RTX PRO / RTX / Quadro changed the available Series and Product choices and automatically selected defaults without navigating or submitting the form.
- [NVIDIA: changing Product Category](../observations/nvidia/driver-search-category-change-resets-downstream-defaults.md) — changing from RTX PRO / RTX / Quadro to GeForce reset Series and Product to compatible GeForce defaults while preserving the page URL.
- [NVIDIA: changing category after manually selecting a series](../observations/nvidia/driver-search-category-change-resets-manual-series.md) — switching from GeForce RTX 40 Series to RTX PRO / Quadro reset the series and product to compatible defaults.
- [Intel: Processors category opens family choices](../observations/intel/product-specifications-processors-opens-families.md) — selecting Processors replaced the top-level product categories with processor-family choices in the same Product Specifications view.
- [Intel: Core Ultra family opens series choices](../observations/intel/core-ultra-family-opens-series-choices.md) — selecting Intel Core Ultra replaced the family choices with Series 1, 2, and 3 links.
- [Intel: Back restores processor-family choices](../observations/intel/core-ultra-drilldown-back-restores-families.md) — Back returned from the series list to processor families and restored the `#@Processors` hash.

Amazon's Sony brand filter left other brands and separate facets available for combination ([boundary observation](../observations/amazon/search-results-sony-filter-keeps-facets-available.md)). That listing does not establish that one facet controls another facet's valid values. Porsche's Europe region disclosure exposed country links, but the region was not selected as an upstream constraint and no result set or child options were recomputed ([boundary observation](../observations/porsche/country-selector-expand-region.md)). Tesla's Model Y L choice selects a complete Long Wheelbase All-Wheel Drive variant without a separate child drivetrain control ([boundary observation](../observations/tesla/model-y-selects-complete-long-wheelbase-variant.md)). These are adjacent cases, not support or direct counterexamples.

## Validation questions

- **Partly resolved on AMD:** when Family widens to All, the selected Ryzen 9000 Series remains active and the same 15 rows remain. Retention across sibling parent branches or on other sites remains open. NVIDIA's observed child was incompatible with the new category.
- AMD restores child choices and results when the Family filter is cleared; do comparable table and form implementations behave the same way?
- Are option counts and result counts updated together or in separate steps?

## Validation outcome

The shared invariant is supported by three independent websites. AMD keeps a processor listing in place and filters it; NVIDIA updates driver selectors and resets defaults; Intel drills down through product categories, processor families, and series in place. Boundaries distinguish this mechanism from independent facets, region disclosures, and complete model-variant selection.
