# Candidate Audit: Zero-Count Facet Options Are Disabled

## Decision

**Keep as `candidate`; do not promote to `validated`.** The Spec requires directly observed support from at least two independent sites. Only IKEA directly demonstrates zero-count values in other facet groups becoming disabled.

## Site-by-site evidence

| Site | Classification | Evidence and comparison |
|---|---|---|
| IKEA | Direct support (1 unique site) | [Sofas price filter disables zero-count options](../../../../../../observations/ikea/sofas-price-filter-disables-zero-count-options.md): after selecting a price range, results fell from 225 to 33; Color → Orange and Best seller each changed to 0 and their checkboxes were disabled. Neither disabled option was activated. |
| eBay | Boundary / untested for this invariant | [Price filter updates Color counts](../../../../../../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md) and [Brand filter updates Color counts](../../../../../../observations/ebay/headphone-brand-filter-updates-color-counts.md): other-facet counts and options recalculated, but every exposed value had a positive count. The observations do not reveal whether zero-count options would be disabled, selectable, or hidden. |
| Amazon | Boundary / untested for this invariant | [Sony filter keeps facets available](../../../../../../observations/amazon/search-results-sony-filter-keeps-facets-available.md): other brand and Connectivity facets remained available, but counts were not exposed. No zero-count value was observed, so this neither supports nor contradicts disabling such values. |
| Airbnb | Adjacent boundary, not a direct counterexample | [Zero-availability price estimate](../../../../../../observations/airbnb/price-range-zero-availability-estimate.md) shows a same-facet price range estimated at 0% while still applicable; [applied zero-results price filter](../../../../../../observations/airbnb/price-filter-zero-results-offers-removal.md) then produced an empty state with a removal path. This concerns applying the price facet itself, not zero-count values in another facet group, so it does not contradict the candidate's stated mechanism. |

**Direct counterexamples:** none identified in the cited evidence. A direct counterexample would need to show a zero-count option in another facet group remaining selectable or otherwise not disabled under the same relevant filtered context.

## Related validated pattern

[Cross-Facet Availability Counts Update](../../../../../../patterns/cross-facet-availability-counts-update.md) is supported by eBay and IKEA for the broader invariant that counts in other facet groups recalculate after a constraint changes the result set. It explicitly treats zero-count disabling as a one-site IKEA variant; that broader pattern must not be counted as a second support site for this narrower candidate.

The broader [Facet Selection Refines a Visible Result Set](../../../../../../patterns/facet-selection-refines-visible-results.md) pattern concerns result-set refinement and does not add independent evidence for zero-count option disabling.

## Promotion check

- Independent direct-support sites: **1 (IKEA)**.
- Minimum required by the Spec: **2**.
- Boundaries and adjacent cases: **eBay, Amazon, Airbnb**; none count as support.
- Direct counterexamples: **none observed**.
- Result: **promotion threshold not met**. Preserve the candidate as unvalidated and seek a direct observation on another independent site that exposes a zero-count option and its enabled/disabled state.
