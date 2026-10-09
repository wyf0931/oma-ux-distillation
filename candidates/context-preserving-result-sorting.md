---
record_type: pattern
status: validated
name: Context-Preserving Result Sorting
definition: On a search or catalog results page, selecting a sort criterion changes the displayed item order while retaining the current query or category context.
problem:
  - Visitors may need to prioritize a particular attribute when scanning a large result set.
mechanism: Apply the selected ordering to visible results while preserving the search or category context.
trigger:
  - Search or catalog results are visible and a sort control is available.
action:
  - Choose a sort criterion such as price ascending or star count descending.
response:
  - The sort control reflects the selected criterion.
  - Comparable displayed items follow that ordering.
  - The current query or category remains in the results context.
use_when:
  - A result set has a stable attribute visitors may want to prioritize, such as price or popularity.
avoid_when:
  - A relevance-based order is important and an alternate sort would hide useful matches.
variants:
  - "Price: Low to High on search results (Amazon)."
  - Most stars on repository search results (GitHub).
  - "Price: Low-High on a category listing, with unpriced gift cards before priced shoes (Nike)."
  - "Price: Low-High with the Black filter retained (Nike)."
  - Most stars with a JavaScript language facet retained (GitHub).
  - "Price: Low to High with a minimum-price facet retained (Amazon)."
  - "Price + Shipping: lowest first with the wireless-headphones query and Under $18.00 filter retained; displayed result count changed (eBay)."
examples:
  - Amazon
  - GitHub
  - Nike
  - eBay
evidence:
  - ../observations/amazon/search-results-sort-price-ascending.md
  - ../observations/github/search-results-sort-most-stars.md
  - ../observations/nike/running-shoes-sort-price-low-high.md
  - ../observations/amazon/search-results-sort-retains-price-facet.md
  - ../observations/github/search-results-sort-retains-language-filter.md
  - ../observations/nike/running-shoes-sort-retains-black-filter.md
  - ../observations/ebay/headphones-sort-price-low-high-retains-price-filter.md
boundaries:
  - ../observations/github/search-language-filter.md
counterexamples: []
confidence: high
---

# Validation Record: Context-Preserving Result Sorting

**Status:** initially promoted to [Context-Preserving Result Sorting](../patterns/context-preserving-result-sorting.md) after direct sort behavior was observed on Amazon, GitHub, and Nike; eBay later supplied a fourth independent example with a price filter active.

## Cross-site invariant

Selecting a sort criterion reorders comparable visible results while the query or category context remains active. Amazon, Nike, and eBay sort by price; GitHub sorts repositories by star count. Sorting changes order, while facet refinement changes result membership.

## Supporting observations

- "[Amazon: price ascending](../observations/amazon/search-results-sort-price-ascending.md) — changing Sort by from Featured to Price: Low to High retained the query and ordered visible price-bearing products upward; the rounded result count changed and its cause is unknown."
- "[GitHub: Most stars](../observations/github/search-results-sort-most-stars.md) — choosing Most stars added `s=stars&o=desc`, retained `q=react`, and reordered the first repositories by displayed star count."
- "[Nike: category price ascending](../observations/nike/running-shoes-sort-price-low-high.md) — choosing Price: Low-High added `sortBy=priceAsc`, retained the Running Shoes category, and ordered priced shoes ascending after two gift-card products without visible prices."
- "[Amazon: sort retains minimum price](../observations/amazon/search-results-sort-retains-price-facet.md) — choosing Price: Low to High retained the query and `low-price=5800` while the visible result prices rose in order; the displayed count and maximum slider endpoint changed, so identical result membership is not claimed."
- "[GitHub: sort retains JavaScript language filter](../observations/github/search-results-sort-retains-language-filter.md) — Most stars added sort parameters while retaining the `react` query and JavaScript filter; visible results remained JavaScript and reordered by star count."
- "[Nike: sort retains the Black filter](../observations/nike/running-shoes-sort-retains-black-filter.md) — Price: Low-High added the sort parameter while the Black category, selected color, and 140-product count remained."
- "[eBay: sort retains the price filter](../observations/ebay/headphones-sort-price-low-high-retains-price-filter.md) — Price + Shipping ascending kept the wireless-headphones query and Under $18.00 chip; the first visible listed prices were $6.99, $9.19, and $10.00 in increasing order; exact combined shipping costs were not compared."

## Boundary

- "[GitHub: JavaScript language filter](../observations/github/search-language-filter.md) changes the query constraints and result membership; it is a facet interaction, not sorting."

## Validation limits

The sort behavior is directly supported on four independent sites. Amazon's query and minimum-price constraint remained in the URL during an ascending sort, while the count changed from 13 to 19 and the maximum slider endpoint changed; the cause and exact eligible set are unknown. GitHub's Most stars sort retained the JavaScript language filter and 4.5M displayed count. Nike's Black filter, category path, and 140-product count remained while price-bearing shoes sorted ascending; two gift-card cards without visible prices appeared first. eBay retained the query and Under $18.00 filter, but its count changed from 26,000+ to 19,000+ and `rt=nc` disappeared from the URL; the cause and exact eligible set are unknown. Other active-facet combinations and personalized rankings remain untested.
