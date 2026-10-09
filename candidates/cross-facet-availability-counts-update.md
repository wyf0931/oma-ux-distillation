---
record_type: pattern
status: validated
name: Cross-Facet Availability Counts Update
definition: After a selected facet changes a result set, visible counts in other facet groups recalculate against the constrained set.
problem:
  - Visitors may need to know which values in other facet groups still match the active constraints.
mechanism: Recompute the displayed count for values in other facet groups after a result constraint changes.
trigger:
  - A populated result set and at least one other facet group display per-value counts.
action:
  - Apply a facet that changes the result set.
response:
  - Counts in other facet groups update to reflect the constrained result set.
use_when:
  - Visitors can use updated counts to compare remaining values before applying another filter.
avoid_when:
  - Facet counts are unavailable, unreliable, or cannot be updated from the current result set.
variants:
  - "Positive color counts update after a price filter; zero-count values are not exposed: eBay."
  - "Color and Best seller counts update after a price filter; zero-count choices become disabled: IKEA."
examples:
  - eBay
  - IKEA
evidence:
  - ../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md
  - ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
boundaries:
  - ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
  - ../observations/amd/processor-specifications-family-filter.md
  - ../observations/nvidia/driver-search-category-updates-series-and-product-options.md
counterexamples: []
confidence: medium
---

# Validation record: Cross-Facet Availability Counts Update

**Status:** promoted to [Cross-Facet Availability Counts Update](../patterns/cross-facet-availability-counts-update.md) after direct count recalculation was observed on eBay and IKEA.

## Hypothesis

Applying one facet may recalculate the counts shown in other facet groups, letting visitors inspect availability under the active constraints. Whether zero-count values are disabled, omitted, or shown as selectable may be a separate implementation detail.

## Evidence comparison

- [eBay: price filter updates Color counts](../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md) — the Under $18.00 price filter changed visible Black, Blue, Gold, and Gray counts.
- [IKEA: price filter disables zero-count options](../observations/ikea/sofas-price-filter-disables-zero-count-options.md) — applying the price range changed Orange and Best seller counts to zero and disabled both choices.

Amazon's Sony filter left other facets available but displayed no option counts, so it is a boundary rather than support or a direct contradiction.

AMD's Family filter reduced the Series options from 101 to 18, but did not show a matching count for each series. This is dependent-choice behavior described by `Upstream Selection Constrains Downstream Options`, not per-value count recalculation.

NVIDIA's parent category also changed the available Series and Product option sets without showing a matching count for each value; this is another dependent-choice case, not count recalculation.

## Validation outcome

The evidence supports count recalculation on two independent sites. The smallest shared invariant is that visible counts in another facet group update after a price filter changes the result set. The IKEA disabled state is a variant of this behavior and is not generalized to all sites.

This is narrower than `Facet Selection Refines a Visible Result Set`: the broader pattern covers changes to the displayed result set, while this pattern isolates the updated counts in other facet groups.

## Follow-up questions

- Does cross-facet count recalculation appear outside retail product listings?
- When a recalculated value reaches zero, do other sites hide it, disable it, or leave it selectable?
- Do displayed counts remain consistent with the result set under sorting and changing inventory?
