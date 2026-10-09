---
record_type: pattern
status: validated
name: Context-Preserving Result Sorting
definition: On a search or catalog results page, selecting a sort criterion changes the displayed item order while retaining the current query or category context.
problem:
  - Visitors may need to prioritize a result attribute such as price or popularity.
mechanism: Apply a chosen ordering to comparable visible items while preserving the search or category context.
trigger:
  - Search or catalog results are visible and a sort control is available.
action:
  - Choose a sort criterion.
response:
  - The sort control reflects the selected criterion.
  - Comparable displayed items follow that ordering.
  - The current query or category remains in the results context.
use_when:
  - A result set has a stable attribute visitors may want to prioritize.
avoid_when:
  - A relevance-based order is important and alternate sorts could hide useful matches.
variants:
  - "Price: Low to High on search results (Amazon)."
  - Most stars on repository search results (GitHub).
  - "Price: Low-High on a catalog listing, with unpriced gift cards ahead of priced shoes (Nike)."
  - "Price: Low to High with a minimum-price facet retained (Amazon)."
  - "Price + Shipping: lowest first with the wireless-headphones query and Under $18.00 filter retained; displayed result count changed (eBay)."
  - Most stars with a JavaScript language facet retained (GitHub).
  - "Price: Low-High with the Black filter retained (Nike)."
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

## Cross-site invariant

Across Amazon, GitHub, Nike, and eBay, the visitor selected a criterion on an existing result page and the displayed ordering changed without losing the current query or category. Amazon and Nike applied price ascending; GitHub ordered repositories by star count. Amazon retained a minimum-price URL constraint, GitHub retained the JavaScript language facet, and Nike retained the Black category filter while changing sort order. eBay kept the wireless-headphones query and Under $18.00 filter after Price + Shipping ascending was selected; the sort label changed and the first visible listed prices were $6.99, $9.19, and $10.00 in increasing order; exact combined shipping costs were not compared. The sorted value was reflected in the URL or sort control.

## Boundaries and counterexamples

GitHub's JavaScript language filter refines the membership of the current repository result set, which is a facet action rather than a sort. No direct counterexample to the order-change invariant has been observed.

## Validation limits

In the active-price-filter follow-up on Amazon, the query and minimum price remained in the URL, but the reported count changed from 13 to 19 and the Maximum price slider endpoint changed from $6,600+ to $12,900+; the cause and exact eligible set are unknown, so only retention of the query and minimum-price constraint is claimed. GitHub's JavaScript filter and 4.5M displayed count remained after Most stars was selected; the first repositories sorted by star count and still displayed JavaScript. Nike's Black filter, category path, and 140-product count remained after sorting; price-bearing shoes were ordered ascending after two gift-card cards without visible prices. eBay’s displayed count changed from 26,000+ to 19,000+ and `rt=nc` disappeared from the URL while `_udhi=18` and the Under $18.00 chip remained; exact membership and the reason for the count change are unknown. Other active-facet combinations and personalized rankings remain untested.
