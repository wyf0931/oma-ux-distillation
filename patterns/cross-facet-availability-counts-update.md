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
  - "A second Brand constraint further updates visible Color options and counts: eBay."
  - "Color and Best seller counts update after a price filter; zero-count choices become disabled: IKEA."
examples:
  - eBay
  - IKEA
evidence:
  - ../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md
  - ../observations/ebay/headphone-brand-filter-updates-color-counts.md
  - ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
boundaries:
  - ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
  - ../observations/amd/processor-specifications-family-filter.md
  - ../observations/nvidia/driver-search-category-updates-series-and-product-options.md
counterexamples: []
confidence: medium
---

## Cross-site invariant

After a price facet narrowed a result set, both eBay and IKEA recalculated counts in other facet groups. eBay updated visible Color counts for Black, Blue, Gold, and Gray; in a separate capture, adding the Bose Brand facet further changed the Color options and counts while retaining the $1 price limit. IKEA updated Orange and Best seller counts to zero and disabled those choices. The shared behavior is count recalculation; whether zero-count values are disabled or exposed is an implementation variant and remains supported directly only by IKEA.

This pattern isolates the secondary response in other facet groups. `Facet Selection Refines a Visible Result Set` captures the broader change to result membership and active-filter context; this pattern does not require any particular result-list presentation or zero-count disabling behavior.

## Boundaries and counterexamples

Amazon's Sony facet left other brands and the Connectivity group available, but those options did not display counts. AMD's Family filter reduced the Series list from 101 options to 18 compatible Ryzen series, and NVIDIA's category choice changed Series and Product options, but neither displayed a matching count for each value; these are dependent-choice behaviors covered by `Upstream Selection Constrains Downstream Options`. These adjacent cases do not test per-value count recalculation. No direct counterexample to recalculation has been observed.

## Validation limits

Two independent retail listings show cross-facet count changes, one in a broad marketplace search and one in a furniture category. Counts are dynamic and can change with inventory or delivery context; displayed count accuracy was not independently audited. No user outcome data were collected. Zero-count disabling is a separate, one-site candidate.
