---
record_type: pattern
status: validated
name: Facet Selection Refines a Visible Result Set
definition: After a result set is visible, selecting a category or attribute facet updates the matching items and records the active constraint in the interface or URL while preserving the listing context.
problem:
- A broad listing may need narrowing after the visitor sees its contents.
mechanism: Apply a category, attribute, or result-type facet and reflect the selected constraint in the URL or selected filter state.
trigger:
- A result set is visible.
action:
- Select a category, result-type, or attribute filter; apply it if the interface stages the choice.
response:
- The selected facet is reflected in the URL or the filter control state.
- The visible result set updates to match the selected values; multiple values within one group may broaden the set.
- The visitor remains in the current listing context.
use_when:
- Results can be meaningfully narrowed by stable categories or attributes.
avoid_when:
- The result set has no useful facets or a filter would hide necessary context.
variants:
- 'Direct query-facet selection updates the URL immediately: GitHub, Amazon.'
- 'Modal facet selection is staged and applied with a results action: Airbnb.'
- 'Result-type selection navigates to query-specific image or category results: DuckDuckGo / Duck.ai, Spotify.'
- 'Editorial category selection updates a content-list URL and count: Mistral AI.'
- 'Removing an active query facet restores broader results: Amazon.'
- 'Multiple values in one facet group can broaden the set; a separate facet can narrow it: Amazon.'
examples:
- GitHub
- Amazon
- Nike
- Airbnb
- IKEA
- Spotify
- DuckDuckGo / Duck.ai
- Mistral AI
- AMD
evidence:
- ../observations/github/search-language-filter.md
- ../observations/amazon/search-results-noise-cancellation-filter.md
- ../observations/amazon/search-results-remove-noise-cancellation-filter.md
- ../observations/airbnb/search-results-wifi-filter.md
- ../observations/spotify/search-results-track-type-tab.md
- ../observations/duckduckgo/search-results-image-type-navigation.md
- ../observations/mistral/news-category-filter-updates-article-list.md
- ../observations/amd/processor-specifications-family-filter.md
- ../observations/amazon/high-price-active-noise-cancellation-filter.md
- ../observations/amazon/high-price-add-sound-isolation-alternative.md
- ../observations/amazon/high-price-add-bluetooth-with-noise-control-selected.md
- ../observations/nike/running-shoes-price-facets-same-group-expand-results.md
- ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
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
# Candidate: Facet Selection Refines a Visible Result Set

**Status:** promoted to [Facet Selection Refines a Visible Result Set](../patterns/facet-selection-refines-visible-results.md) after the same result-update mechanism was observed across seven independent sites; Nike later added a same-group price-range variant.

## Hypothesis

After a result set is visible, selecting a category or attribute facet updates the selected filter state and narrows the set while keeping the visitor in the listing context. A search query is one way to create the result set, but is not required.

Possible invariant:

```text
visible result set → select facet → selected constraint is reflected in the URL or control state → matching results remain
```

## Supporting observations

- [GitHub: JavaScript repository filter](../observations/github/search-language-filter.md) — selecting JavaScript updated the query URL and reduced the displayed repository count from about 7.3M to 4.5M.
- [Amazon: Active Noise Cancellation filter](../observations/amazon/search-results-noise-cancellation-filter.md) — selecting the feature added a refinement to the search URL and showed an active filter; the result count remained rounded to “over 6,000”.
- [Amazon: removing the filter](../observations/amazon/search-results-remove-noise-cancellation-filter.md) — removing the facet restored a broader results count from over 6,000 to over 50,000 while preserving the query.
- [Airbnb: Wi-Fi amenity filter](../observations/airbnb/search-results-wifi-filter.md) — selecting Wi-Fi in a filter dialog and applying it updated the search URL and checked state while retaining results context.
- [Spotify: Songs result type](../observations/spotify/search-results-track-type-tab.md) — selecting Songs navigated to a query-specific path and showed matching tracks.
- [DuckDuckGo: Images result type](../observations/duckduckgo/search-results-image-type-navigation.md) — selecting Images changed the result type in the URL, preserved the query, and exposed image cards with matching source titles and descriptions.
- [Mistral AI: Research category filter](../observations/mistral/news-category-filter-updates-article-list.md) — selecting Research changed the URL, checked the category, narrowed the displayed total from 89 to 40, and left only Research cards visible on the first page.
- [AMD: processor Family filter](../observations/amd/processor-specifications-family-filter.md) — selecting Ryzen narrowed the visible technical catalog from 745 to 302 entries, updated the selected filter, and left the URL unchanged.
- [Nike: adjacent price ranges selected together](../observations/nike/running-shoes-price-facets-same-group-expand-results.md) — selecting $25–$50 while retaining $0–$25 changed the Black Running Shoes count from 2 to 28. The initial cards were gift cards without visible prices.
- [Nike: Men's path with low-price gift cards](../observations/nike/running-shoes-men-price-under-25-gift-cards-remain.md) — the category path changed to Men's, but the same two unpriced gift-card cards remained; exact facet membership is unknown.
- [IKEA: zero-count facet options disabled](../observations/ikea/sofas-price-filter-disables-zero-count-options.md) — applying a price range changed the listing and disabled Color and Best seller options that fell to zero.
- [Airbnb: zero-result price filter and recovery](../observations/airbnb/price-filter-zero-results-offers-removal.md) — a narrow price filter reached a no-match state and offered a remove-filter action; see the [recovery observation](../observations/airbnb/price-filter-removal-restores-results.md).

## Validation questions

- **Resolved for initial validation:** GitHub, Amazon, Airbnb, Spotify, and DuckDuckGo support query-result refinements; Mistral AI shows the same selection-and-narrowing behavior in an editorial listing without a search query.
- Same-group multi-select alternatives are now observed on Amazon and Nike; how do other facet groups behave? Airbnb provides one filter-generated zero-result and recovery example.
- When a filter is applied, does the result count always change visibly or may rounded counts remain the same?
- Does removing one facet preserve other active filters?

## Validation outcome

The result-set update invariant is supported by nine sites. Spotify and DuckDuckGo use result-type navigation; Airbnb stages a facet in a dialog; Mistral AI filters an editorial listing; AMD filters a technical specification table without URL navigation; IKEA updates downstream facet counts after price filtering. Amazon and Nike confirm that alternatives in one facet group can broaden the visible set, while Amazon's separate Bluetooth facet narrows it. Airbnb adds one observed filter-generated empty state with a recovery action. Rounded result counts still limit exact delta claims on Amazon and Airbnb. Airbnb provides one filter-generated zero-result and recovery example; cross-site comparison remains open.

## Post-promotion refinement

The initial hypothesis described facet selection as narrowing results. Amazon showed that adding Sound Isolation while Active Noise Cancellation remained selected increased the count from one to six; Bluetooth under Connectivity then reduced it to two. Nike independently showed the same-group pattern: selecting $25–$50 while retaining $0–$25 increased the count from two to 28. The initial Nike cards were gift cards with no visible prices, so membership is uncertain. The record now describes result-set updates according to selected values rather than assuming every added value narrows the set.
