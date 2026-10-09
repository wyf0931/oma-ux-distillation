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
# Candidate: query-guided search assistance

**Status:** first promoted to [Query-Guided Search Assistance](../patterns/query-guided-search-assistance.md) after five independent sites; later Apple, Mistral AI, and Best Buy evidence extended it to eight sites; GitHub supplies a query-specific positive case for `issues`, while its `react` session remains a separate counterexample, bringing support to nine sites.

Best Buy provided an eighth independent example at the initial promotion: entering “wireless headphones” showed related query refinements, a category-related suggestion, and product previews before submission. GitHub later supplied a positive `issues` query alongside its `react` counterexample, extending support to nine sites. The Best Buy category suggestion was not selected.

## Hypothesis

Typing a query can update a discovery region before the user submits a search, offering suggestions, results, or alternate query actions.

## Supporting observations

- [Amazon autocomplete](../observations/amazon/search-autocomplete.md) — typing opened ten query-completion buttons.
- [Spotify search](../observations/spotify/search-results-as-you-type.md) — typing showed artist, track, and collection results.
- [DuckDuckGo query action list](../observations/duckduckgo/search-query-action-list.md) — typing opens Search and Ask Duck.ai actions.
- [DuckDuckGo search-to-AI handoff](../observations/duckduckgo/search-to-ai-chat-handoff.md) — choosing Ask Duck.ai carries the query into chat.
- [Airbnb location autocomplete](../observations/airbnb/location-autocomplete.md) — a typed place name exposes matching destinations before search submission.
- [Airbnb keyboard navigation in Location autocomplete](../observations/airbnb/location-autocomplete-arrowdown-advances-suggestion.md) — ArrowDown advances from an already highlighted Tokyo-area suggestion to Shinjuku.
- [Airbnb Enter commits a place suggestion](../observations/airbnb/location-autocomplete-enter-advances-to-dates.md) — Enter commits the selected destination and opens the Dates picker without submitting the full search.
- [IKEA store search](../observations/ikea/store-search-filtering.md) — a typed country name filters a short regional store/language list.
- [Apple global search](../observations/apple/global-search-suggestions.md) — a typed product name shows suggested destinations and related searches.
- [Mistral AI Latest news search](../observations/mistral/news-query-filters-article-list.md) — typing a title filters the existing editorial list and updates the URL and count before submission.
- [Mistral AI Latest news no-match state](../observations/mistral/news-zero-results-query-guidance.md) — an unmatched synthetic query updates the URL, reports zero articles, and advises adjusting the search or filters before any separate submission.
- [Best Buy search autocomplete](../observations/bestbuy/search-query-suggestions-and-product-previews.md) — entering a query shows refinements and product previews before submission.
- [GitHub query-matched destination](../observations/github/search-query-issues-shows-destination-suggestion.md) — typing `issues` showed Explore Issues before submission in two captures; typing `react` still produced an empty list, so GitHub behavior varies by query.

## Follow-up questions

- How does the interface distinguish a suggested query from a playable or navigable result?
- What feedback appears for no matches, slow results, or broad queries?
- How does query correction to a different nonempty term change the suggestion set?

## Counterexample record

- [GitHub: Quick search after typing](../observations/github/search-query-no-suggestions.md) — in a logged-out homepage session, keyboard entry of “react” left the query suggestions list empty for about 3.5 seconds while Search syntax tips remained. This directly contradicts the query-dependent assistance response for that search surface; it does not generalize to GitHub's authenticated or other search modes.

## Boundaries

- [Airbnb: date range picker](../observations/airbnb/search-date-range-picker.md) collects structured dates rather than offering text-query assistance.
- [Netflix: FAQ disclosure](../observations/netflix/faq-pricing-disclosure.md) reveals a static answer after activation and is not search-query assistance.
