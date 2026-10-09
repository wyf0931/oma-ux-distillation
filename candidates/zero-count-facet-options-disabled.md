---
record_type: pattern
status: candidate
name: Zero-Count Facet Options Are Disabled
definition: After an applied facet changes the visible result set, options with zero matching products are disabled in other facet groups.
problem:
  - Visitors may waste an action selecting an option that cannot return any products.
mechanism: Recalculate option counts under the active result constraints and disable zero-count options.
trigger:
  - A result set has an applied constraint and remaining facet options display matching counts.
action:
  - Apply a facet and inspect another facet group for newly unavailable options.
response:
  - Counts in another facet group update to reflect the constrained result set.
  - Options with a zero count are disabled rather than selectable.
use_when:
  - Facet counts can be updated accurately as result constraints change.
avoid_when:
  - Counts are stale, incomplete, or too costly to compute reliably.
variants:
  - "Applying a price range updates Color and Best seller counts; Orange and Best seller show 0 and are disabled: IKEA."
examples:
  - IKEA
evidence:
  - ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
boundaries:
  - ../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md
  - ../observations/ebay/headphone-brand-filter-updates-color-counts.md
  - ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
  - ../observations/airbnb/price-range-zero-availability-estimate.md
  - ../observations/airbnb/price-filter-zero-results-offers-removal.md
counterexamples: []
confidence: low
---

# Candidate notes

## Hypothesis

The observed price selection appears to prune zero-count options in other facet groups before the visitor can apply them. It is one IKEA catalog session, so the candidate is not yet a general pattern. The broader count-recalculation mechanism is already captured by the validated [Cross-Facet Availability Counts Update](../patterns/cross-facet-availability-counts-update.md) pattern; this candidate tests the narrower question of whether zero-count values are specifically disabled.

## Evidence comparison

IKEA's Price filter reduced the sofa listing from 225 to 33 items. Orange fell from one matching product to zero and its checkbox was disabled; Best seller also fell from 12 to zero and became disabled. No disabled option was activated and no zero-result state was produced. eBay's Under $18 price filter recalculated displayed positive Color counts. In a $1 maximum-price state, applying Bose reduced the visible results from 60 to 8 and updated the Color choices and counts; all values in the captured list remained positive, so this does not establish how eBay handles zero-count values. A second attempt reached the generic Error Page and was not counted as a reproduction. Amazon's Sony filter left other brand and Connectivity options available, but their counts were not exposed. Airbnb showed a 0% estimate for the selected price range but still allowed that same price facet to be applied; it then produced an empty state with a remove-filter recovery. This is adjacent same-facet behavior, distinct from IKEA's zero-count options in other facet groups. These cases do not validate or directly contradict the candidate.

## Validation questions

- Do independent commerce and travel sites disable unavailable facet values after a filter is applied?
- Do other sites keep zero-count values selectable and show a recoverable empty state instead?
- Are counts updated synchronously with the result list or after an explicit apply action?
