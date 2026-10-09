---
record_type: pattern
status: validated
name: Search Zero-Results Recovery
definition: When a search query or applied filters produce no matches, the interface explains the empty result state and
  offers one or more ways to continue while retaining useful search context.
problem:
- A visitor with no matches needs a clear next step.
mechanism: Pair an explicit no-match state with recovery actions that preserve useful query, location, or filter context.
trigger:
  - The current search state, including its query, scope, and applied filters, produces no matching items.
action:
- Review the no-result state and choose a recovery path.
response:
  - The interface explains that no matches were found.
  - One or more recovery paths are offered without discarding useful search context.
use_when:
- A search can return no matches and visitors need help continuing.
avoid_when:
- The current search always returns broad, non-empty results and a no-result explanation would be misleading.
variants:
  - 'Spelling and query-broadening guidance: Amazon.'
  - 'Advanced search, organization search, and saved-search guidance: GitHub.'
  - 'Suggested support topics within a selected search scope: Apple.'
  - 'Selecting a suggested topic replaces the no-match query and opens populated results in the same scope: Apple.'
  - 'A zero-result price filter offers a link to remove that filter while retaining the Tokyo Homes search: Airbnb.'
examples:
- Amazon
- GitHub
- Apple
- Airbnb
evidence:
- ../observations/amazon/search-zero-results-spelling-guidance.md
- ../observations/github/search-zero-results-recovery.md
- ../observations/github/search-zero-results-advanced-search.md
- ../observations/github/search-zero-results-saved-search-tip.md
- ../observations/apple/support-search-zero-results-recovery.md
- ../observations/apple/support-zero-results-topic-opens-scoped-results.md
- ../observations/airbnb/price-filter-zero-results-offers-removal.md
- ../observations/airbnb/price-filter-removal-restores-results.md
boundaries:
  - ../observations/spotify/search-synthetic-query-broad-results.md
  - ../observations/mistral/news-zero-results-query-guidance.md
  - ../observations/nike/running-shoes-men-price-under-25-gift-cards-remain.md
  - ../observations/ikea/sofas-price-filter-disables-zero-count-options.md
confidence: high
counterexamples: []
---
# Candidate: Search Zero-Results Recovery

**Status:** promoted to [Search Zero-Results Recovery](../patterns/search-zero-results-recovery.md) after no-match recovery behavior was observed on Amazon, GitHub, and Apple Support.

## Hypothesis

When a submitted query returns no results, the interface can offer next steps that preserve the original query or explain how to refine it.

Possible invariant:

```text
zero results → show recovery guidance → allow query refinement without starting over
```

## Supporting observations

- [GitHub: zero-results recovery](../observations/github/search-zero-results-recovery.md) — a no-match message offered organization search, saved-search guidance, and Advanced search.
- [GitHub: Advanced search handoff](../observations/github/search-zero-results-advanced-search.md) — the Advanced search form opened with the original query prefilled.
- [Amazon: zero-results spelling guidance](../observations/amazon/search-zero-results-spelling-guidance.md) — a no-result product search advises checking spelling or broadening the query.
- [Apple: Support no-results recovery](../observations/apple/support-search-zero-results-recovery.md) — a no-match support search suggests relevant support topics.
- [Apple: suggested topic opens populated Support results](../observations/apple/support-zero-results-topic-opens-scoped-results.md) — selecting a suggestion replaces the synthetic query with a topic search and shows 100 Support results; the matching article itself was not opened.
- [Airbnb: filter-generated zero results](../observations/airbnb/price-filter-zero-results-offers-removal.md) — a price constraint produced a no-match state with a Remove price filter action.
- [Airbnb: removing the price filter](../observations/airbnb/price-filter-removal-restores-results.md) — the recovery action restored more than 1,000 Tokyo Homes results.

## Boundaries

- [Spotify: synthetic query returns broad results](../observations/spotify/search-synthetic-query-broad-results.md) — the query had no textual match, but the logged-out page returned unrelated content instead of a no-results state.
- [Mistral AI: live article search no-match state](../observations/mistral/news-zero-results-query-guidance.md) — the list showed zero articles and query-adjustment guidance while text was being edited, without a separate submission; it is adjacent to this submitted-query pattern and belongs to Query-Guided Search Assistance.
- [Nike: low-price men's category retains gift cards](../observations/nike/running-shoes-men-price-under-25-gift-cards-remain.md) — two gift cards remained under the selected filters and no empty state appeared; the cards' price-range membership is unknown.
- [IKEA: zero-count facet options disabled](../observations/ikea/sofas-price-filter-disables-zero-count-options.md) — after a price filter, Color and Best seller options with zero matching products were disabled, so this did not produce a no-results state.

## Validation questions

- **Resolved for submitted-query states:** Amazon, GitHub, and Apple Support provide distinct no-result recovery paths.
- Does the recovery option preserve the query, suggest alternatives, or help broaden the search?
- Which no-results states intentionally offer no recovery action?
- Can the user return to results without losing filters or other search context?

## Validation outcome

The initial no-result message plus recovery path was promoted from Amazon, GitHub, and Apple Support. Apple’s topic recovery was exercised and replaced the unmatched query with a selected topic while retaining the Support scope; the matching article remained a result and was not opened.

## Post-promotion scope extension

Airbnb adds a filtered-empty-state variant. Applying a narrow Tokyo price constraint produced no matching homes and offered Remove price filter; activating it restored more than 1,000 Tokyo results. The shared invariant now covers no-match states caused by a submitted query or applied filters. Airbnb is the only filter-generated example so far; the query-generated recovery variants remain as originally validated.
