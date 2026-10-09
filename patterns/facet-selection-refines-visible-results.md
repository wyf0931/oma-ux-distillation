---
record_type: pattern
status: validated
name: Facet Selection Refines a Visible Result Set
definition: After a result set is visible, selecting a category or attribute facet updates the matching items and records
  the active constraint in the interface or URL while preserving the listing context. Multiple values in one facet group
  may act as alternatives and broaden the set; a separate facet may narrow it further.
problem:
- A broad listing may need narrowing after the visitor sees its contents.
mechanism: Apply a category, attribute, or result-type facet and reflect the selected constraint in the URL or selected
  filter state.
trigger:
- A result set is visible.
action:
- Select a category, result-type, or attribute filter; apply it if the interface stages the choice.
response:
  - The selected facet is reflected in the URL or the filter control state.
  - The visible result set updates to match the selected category or attribute values. Multiple values in one group may broaden the set, while a separate facet may narrow it.
  - The visitor remains in the current listing context, including when the selected facet changes a query-specific path.
use_when:
- Results can be meaningfully narrowed by stable content attributes or types.
avoid_when:
- The result set has no useful facets or a filter would hide necessary context.
variants:
  - 'Direct query-facet selection updates the URL immediately: GitHub, Amazon.'
  - 'Modal facet selection is staged and applied with a results action: Airbnb.'
  - 'Result-type selection navigates to query-specific image or category results: DuckDuckGo / Duck.ai, Spotify.'
  - 'Editorial category selection updates a content-list URL and count: Mistral AI.'
  - 'In-place table attribute filter narrows a technical catalog without changing the URL: AMD.'
  - 'Removing an active query facet restores broader results: Amazon.'
  - 'Visible quick filters combine and can be removed independently while retaining the remaining facet: Airbnb.'
  - 'Removing the selected brand retains the active noise-control facet and query: Amazon.'
  - 'A price-range slider updates the visible result set: Amazon.'
  - 'Selecting a second Noise Control value broadened the result set from one to six; adding Bluetooth under Connectivity narrowed it to two while retaining both Noise Control alternatives: Amazon.'
  - 'Selecting a second Shop by Price range while retaining the first broadened Black Running Shoes results from two to 28: Nike.'
  - 'A zero-result price facet can offer a remove-filter path that restores the broader listing: Airbnb.'
  - 'A price facet updates other option counts and disables zero-count Color and Best seller choices: IKEA.'
  - 'A price range narrows marketplace search results and updates visible Color counts: eBay.'
examples:
- GitHub
- Amazon
- Nike
- Airbnb
- IKEA
- eBay
- Spotify
- DuckDuckGo / Duck.ai
- Mistral AI
- AMD
evidence:
- ../observations/github/search-language-filter.md
- ../observations/amazon/search-results-noise-cancellation-filter.md
- ../observations/amazon/search-results-sony-filter-keeps-facets-available.md
- ../observations/amazon/search-results-remove-noise-cancellation-filter.md
- ../observations/airbnb/search-results-wifi-filter.md
- ../observations/spotify/search-results-track-type-tab.md
- ../observations/duckduckgo/search-results-image-type-navigation.md
- ../observations/mistral/news-category-filter-updates-article-list.md
- ../observations/amd/processor-specifications-family-filter.md
- ../observations/airbnb/search-results-add-washer-to-wifi-filter.md
- ../observations/airbnb/search-results-remove-wifi-retains-washer-filter.md
- ../observations/amazon/search-results-remove-sony-retains-noise-cancellation.md
- ../observations/amazon/search-results-minimum-price-slider.md
- ../observations/amazon/high-price-active-noise-cancellation-filter.md
- ../observations/amazon/high-price-add-sound-isolation-alternative.md
- ../observations/amazon/high-price-add-bluetooth-with-noise-control-selected.md
- ../observations/nike/running-shoes-price-facets-same-group-expand-results.md
- ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
- ../observations/ebay/headphones-price-filter-updates-result-and-color-counts.md
- ../observations/airbnb/price-filter-zero-results-offers-removal.md
- ../observations/airbnb/price-filter-removal-restores-results.md
confidence: high
boundaries:
  - ../observations/amazon/search-department-scope.md
  - ../observations/github/search-empty-quick-suggestions.md
  - ../observations/apple/global-search-suggestions.md
  - ../observations/spotify/search-result-artist-opens-artist-page.md
  - ../observations/mistral/news-query-filters-article-list.md
  - ../observations/nike/running-shoes-men-price-under-25-gift-cards-remain.md
counterexamples: []
---
## Cross-site invariant

Across GitHub, Amazon, Nike, Airbnb, IKEA, eBay, Spotify, DuckDuckGo, Mistral AI, and AMD, selecting a facet after a result set was visible changed the matching items or the next available filter options while preserving the listing context. The direction depends on how facet values combine: adding same-group alternatives within Amazon's Noise Control and Nike's Shop by Price groups expanded counts from one to six and from two to 28; adding Bluetooth under Amazon's Connectivity narrowed results from six to two. GitHub and Amazon applied query attribute facets immediately; Amazon's price range also narrowed headphone results from over 50,000 to 13. IKEA's price choice narrowed sofas from 225 to 33 and disabled Color and Best seller options that then had zero matches; eBay's Under $18 filter narrowed wireless-headphone results from 150,000+ to 26,000+ and recalculated visible color counts. Airbnb staged a Wi-Fi selection in a dialog and applied it with a show-results action, then combined Wi-Fi and Washer as quick filters and removed Wi-Fi while retaining Washer. Amazon combined Sony and Active Noise Cancellation, then removed Sony while retaining the noise-control facet and query. Spotify and DuckDuckGo switched to query-specific result types while preserving the query; Mistral AI filtered an editorial listing by category; AMD narrowed a processor table by family and updated its count without changing the URL. Amazon also removed an active filter and returned to broader results while preserving the query.

## Boundaries and counterexamples

The pattern begins after a result set is visible. GitHub's [empty Quick search suggestions](../observations/github/search-empty-quick-suggestions.md), Apple's [query-time suggestions](../observations/apple/global-search-suggestions.md), and Amazon's [pre-query department selection](../observations/amazon/search-department-scope.md) occur before a result set appears and are boundaries. Nike's Gender path changed under a $0–$25 price selection, but the same unpriced gift cards remained; whether they are filtered catalog items is unknown, so this is not counted as support or a direct counterexample. Direct navigation links that leave the listing are not instances.

## Validation limits

Mistral AI's displayed article count fell from 89 to 40, AMD's processor table narrowed from 745 entries to 302, and GitHub's displayed count fell from about 7.3M to 4.5M. Amazon and Airbnb displayed rounded counts that did not visibly change in other sessions, so exact result-set deltas are not required by the invariant. Airbnb directly showed two quick amenity filters active together and removal of one while retaining the other; the URL's `selected_filter_order[]` retained both order entries after removal, while active parameters, checkbox states, and applied-filter count showed only Washer active. Amazon directly showed two active facets, then removal of Sony while retaining Active Noise Cancellation and the query. Amazon and Nike both show same-group alternative values increasing the listed result count; the initial Nike cards were gift cards with no displayed prices, so their facet membership is unclear. Amazon also showed a separate Bluetooth facet narrowing results. IKEA disables facet choices that reach zero matches, while Airbnb allows an applied price filter to produce an empty state with a removal path; the disabled-option behavior is a single-site example. DuckDuckGo's Images view loaded image results, but result counts and keyboard traversal were not assessed. Independent facet removal is directly observed on both Amazon and Airbnb.
