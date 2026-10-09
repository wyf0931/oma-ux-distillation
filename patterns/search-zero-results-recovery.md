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
## Cross-site invariant

Across Amazon, GitHub, Apple Support, and Airbnb, a no-match search state explained the missing results and offered a way to continue. Amazon suggested checking spelling or broadening terms; GitHub offered query/search guidance; Apple showed suggested support topics; Airbnb showed a price-filter empty state with a remove-filter action. Selecting an Apple topic replaced the synthetic no-match query and opened a populated Support result page while keeping the Support scope selected. Removing Airbnb's price filter restored the Tokyo Homes results.

## Boundaries and counterexamples

This pattern concerns a submitted or filtered search state that yields no matches. Mistral AI's article search filters as text is entered and shows a zero-results adjustment hint without a separate submit action; it remains adjacent to this pattern and belongs to query-guided assistance. Empty-query shortcuts also happen before a submitted-results state. In one logged-out Spotify session, a synthetic query led to broad results that did not match the query, without an explicit no-results message or recovery options ([observation](../observations/spotify/search-synthetic-query-broad-results.md)). Nike's under-$25 men's Black Running Shoes path still displayed two gift cards and no empty state; their membership in the filtered shoe catalog is unclear. IKEA disabled zero-count facet values before an empty result page could occur. These are boundaries, not zero-result recovery instances, and do not claim behavior for authenticated states.

## Validation limits

Apple's topic-based recovery was exercised: the selected topic became the new query, Support remained selected, and the page reported 100 results. Airbnb is the only observed post-filter zero-result example; it showed removal of the price filter restoring more than 1,000 Tokyo homes. The applied URL normalized the entered maximum from 70 SGD to `price_max=75`, and an order-only `selected_filter_order` entry remained after removal. Cross-site filtered-empty-state variants, Amazon's spelling guidance, GitHub's saved-search guidance in a fresh recovery action, suggestion ranking, and authenticated states remain untested.
