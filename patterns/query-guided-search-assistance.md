---
record_type: pattern
status: validated
name: Query-Guided Search Assistance
definition: Entering text in a search field or searchable selector surfaces query-related suggestions, results, or alternate
  actions before the visitor selects a result, navigates, or submits the full search.
problem:
- The user may need help refining an incomplete query.
- A query can lead to different useful actions or result types.
mechanism: Use the current text to update query-dependent choices before navigation or final submission.
trigger:
- Text entry in a search field or searchable selector.
action:
- Type or edit a query, then choose a completion, matching result, destination, or alternate action.
response:
- A query-related assistance region appears or updates before the choice is committed.
- The region may show suggested queries, matched results, or alternate destinations.
use_when:
- Queries have common refinements or results can be meaningfully identified while typing.
- More than one result type or destination can satisfy the query.
avoid_when:
- A query must be submitted before results can be calculated or explained accurately.
- The result set is too large to usefully summarize in the input context.
variants:
  - 'Query completions: Amazon.'
  - 'Live result groups: Spotify.'
  - 'Explicit Search / AI chat choice: DuckDuckGo / Duck.ai.'
  - 'Destination autocomplete: Airbnb.'
  - 'ArrowDown advances the highlighted destination; Enter commits it and opens the next trip-search control: Airbnb.'
  - 'Searchable regional option filtering: IKEA.'
  - 'Suggested destinations and query refinements: Apple.'
  - 'Live editorial search filters an existing list as text is entered: Mistral AI.'
  - 'Live editorial search shows an adjustment hint when query typing returns no matches: Mistral AI.'
  - 'Related query refinements and product previews appear together before search submission: Best Buy.'
  - 'Typing `issues` surfaces Explore Issues, while another query may show no suggestions: GitHub.'
examples:
- Amazon
- Spotify
- DuckDuckGo / Duck.ai
- Airbnb
- IKEA
- Apple
- Mistral AI
- Best Buy
- GitHub
evidence:
- ../observations/amazon/search-autocomplete.md
- ../observations/spotify/search-results-as-you-type.md
- ../observations/duckduckgo/search-query-action-list.md
- ../observations/duckduckgo/search-to-ai-chat-handoff.md
- ../observations/airbnb/location-autocomplete.md
- ../observations/airbnb/location-autocomplete-arrowdown-advances-suggestion.md
- ../observations/airbnb/location-autocomplete-enter-advances-to-dates.md
- ../observations/ikea/store-search-filtering.md
- ../observations/apple/global-search-suggestions.md
- ../observations/mistral/news-query-filters-article-list.md
- ../observations/mistral/news-zero-results-query-guidance.md
- ../observations/bestbuy/search-query-suggestions-and-product-previews.md
- ../observations/github/search-query-issues-shows-destination-suggestion.md
confidence: medium
boundaries:
  - ../observations/airbnb/search-date-range-picker.md
  - ../observations/netflix/faq-pricing-disclosure.md
counterexamples:
  - ../observations/github/search-query-no-suggestions.md
---
## Cross-site invariant

Across nine sites, entering text into a search field or searchable selector exposed query-dependent choices before the visitor navigated or submitted the full search. The responses differ: Amazon showed query completions, Spotify showed artist and track results, DuckDuckGo offered Search or a handoff to Duck.ai, Airbnb returned matching destinations, IKEA filtered the store/language options, Apple showed suggested destination links and related searches, Mistral AI filtered an editorial list to a matching article or an empty-state adjustment hint, Best Buy showed related query refinements with product previews, and GitHub showed Explore Issues for the `issues` query. GitHub's `react` query left the list empty, so its query guidance varies by term. Best Buy's category-related suggestion was not selected, so its effect on submitted results remains unknown.

## Boundaries and counterexamples

This pattern concerns query-dependent assistance after text entry. Airbnb's date-range picker collects structured dates, and Netflix's FAQ discloses static answers; neither is query assistance.

GitHub's logged-out homepage Quick search is a direct counterexample for that surface: typing “react” left the suggestions listbox empty while Search syntax tips remained. The empty state persisted for about 3.5 seconds after real keyboard input with no loading state visible. This does not characterize GitHub's authenticated or other search surfaces.

## Validation limits

Keyboard navigation through suggestions is now directly observed on Airbnb: ArrowDown advanced from an already highlighted place to Shinjuku, and Enter committed that place and opened the Dates picker without submitting results. The initial highlight varied from the first suggestion in this session; other services, correction to a different nonempty query, latency, and reduced-network behavior remain untested. GitHub's Clear search control restored the four default Explore shortcuts after the `react` query was cleared. Mistral AI's matching article list and zero-result guidance both updated before any separate submission; clear-query and filter-based recovery behavior were not tested. Duck.ai showed a Terms / Privacy notice before its chat could be used; no agreement was accepted and no response was generated.
