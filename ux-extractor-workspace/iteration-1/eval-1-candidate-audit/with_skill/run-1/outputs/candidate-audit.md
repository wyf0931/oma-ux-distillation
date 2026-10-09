# Candidate audit: Zero-Count Facet Options Are Disabled

## Decision

**Keep as `candidate`; it does not meet the promotion threshold.** Only IKEA directly demonstrates the proposed invariant. The Spec requires directly observed instances from at least two independent sites, with evidence showing the same trigger, action, and response. Boundary cases do not count toward that threshold.

## Site-by-site evidence

| Site | Classification | Evidence and comparison |
|---|---|---|
| IKEA | Direct support (1 independent site) | [Sofas price filter disables zero-count options](../../../../../../observations/ikea/sofas-price-filter-disables-zero-count-options.md): applying the $0–$499.99 price facet changed the result count from 225 to 33; Orange and Best seller each changed to zero and their checkboxes were disabled. The observation explicitly says neither disabled choice was activated. |
| eBay | Boundary; not support or counterexample | [Price filter updates Color counts](../../../../../../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md) and [Brand filter updates Color counts](../../../../../../observations/ebay/headphone-brand-filter-updates-color-counts.md): cross-facet counts/options update, but every exposed Color value remained positive. The records do not reveal how eBay handles a zero-count value. |
| Amazon | Boundary; not support or counterexample | [Sony filter keeps other facets available](../../../../../../observations/amazon/search-results-sony-filter-keeps-facets-available.md): other brand and Connectivity options remained available, but no per-option counts were shown. This does not establish that a zero-count option remained selectable. |
| Airbnb | Adjacent boundary; not support or direct counterexample | [Price range shows 0% availability before apply](../../../../../../observations/airbnb/price-range-zero-availability-estimate.md), [applying it produces an empty state](../../../../../../observations/airbnb/price-filter-zero-results-offers-removal.md), and [removal restores results](../../../../../../observations/airbnb/price-filter-removal-restores-results.md). This is a same-facet price estimate followed by an applied empty-result state and recovery, not a zero-count option in another facet group. |

## Cross-site context

The validated [Cross-Facet Availability Counts Update](../../../../../../patterns/cross-facet-availability-counts-update.md) pattern supports the broader mechanism on eBay and IKEA: counts in other facet groups recalculate after constraints change. Its invariant does not include disabling zero-count values; the pattern record explicitly says that behavior remains a one-site candidate. [Facet Selection Refines a Visible Result Set](../../../../../../patterns/facet-selection-refines-visible-results.md) establishes broader result-set refinement across sites, but does not supply additional zero-count disabling instances.

## Classification summary

- **Directly supporting sites:** IKEA (1).
- **Boundary / adjacent sites:** eBay, Amazon, Airbnb (3).
- **Direct counterexamples:** none observed in the cited evidence.
- **Promotion:** not eligible; obtain at least one independent, directly observed site where a post-filter option in another facet group has count zero and is disabled. Do not count positive-only counts, available alternatives without counts, or same-facet empty-result behavior as support.
