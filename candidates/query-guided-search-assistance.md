# Candidate: query-guided search assistance

**Status:** promoted to [Query-Guided Search Assistance](../patterns/query-guided-search-assistance.md) after five independent examples; retain this file as the hypothesis and validation record.

## Hypothesis

Typing a query can update a discovery region before the user submits a search, offering suggestions, results, or alternate query actions.

## Supporting observations

- [Amazon autocomplete](../observations/amazon/search-autocomplete.md) — typing opened ten query-completion buttons.
- [Spotify search](../observations/spotify/search-results-as-you-type.md) — typing showed artist, track, and collection results.
- [DuckDuckGo query action list](../observations/duckduckgo/search-query-action-list.md) — typing opens Search and Ask Duck.ai actions.
- [DuckDuckGo search-to-AI handoff](../observations/duckduckgo/search-to-ai-chat-handoff.md) — choosing Ask Duck.ai carries the query into chat.
- [Airbnb location autocomplete](../observations/airbnb/location-autocomplete.md) — a typed place name exposes matching destinations before search submission.
- [IKEA store search](../observations/ikea/store-search-filtering.md) — a typed country name filters a short regional store/language list.

## Validation questions

- Which services show suggestions versus full results while typing?
- How does the interface distinguish a suggested query from a playable or navigable result?
- What feedback appears for no matches, slow results, or broad queries?
- Test keyboard selection and correction after choosing a suggestion before deciding whether these behaviors share one pattern.
