# Query-Guided Search Assistance

```yaml
name: Query-Guided Search Assistance
definition: >
  As a user types a search query, the interface surfaces query-related suggestions,
  results, or alternate actions before the user submits a search.
user_problem:
  - The user may need help refining an incomplete query.
  - A query can lead to different useful actions or result types.
trigger:
  - Text entry in a search field.
interaction:
  - The user edits the query and can choose a suggestion, result, or search action.
system_response:
  - A query-related assistance region appears or updates before submission.
  - The region may show suggested queries, matched results, or alternate destinations.
purpose:
  - Help users move from a query to a useful result or next action.
when_to_use:
  - Queries have common refinements or results can be meaningfully identified while typing.
  - More than one result type or destination can satisfy the query.
when_not_to_use:
  - A query must be submitted before results can be calculated or explained accurately.
  - The result set is too large to usefully summarize in the input context.
variants:
  - Query completions: Amazon.
  - Live result groups: Spotify.
  - Explicit Search / AI chat choice: DuckDuckGo / Duck.ai.
  - Destination autocomplete: Airbnb.
examples:
  - Amazon
  - Spotify
  - DuckDuckGo / Duck.ai
  - Airbnb
evidence:
  - ../observations/amazon/search-autocomplete.md
  - ../observations/spotify/search-results-as-you-type.md
  - ../observations/duckduckgo/search-query-action-list.md
  - ../observations/duckduckgo/search-to-ai-chat-handoff.md
  - ../observations/airbnb/location-autocomplete.md
```

## Cross-site invariant

Across four sites, entering a query exposed relevant next steps before a conventional search submission. The responses differ: Amazon showed query completions, Spotify showed artist and track results, DuckDuckGo offered Search or a handoff to Duck.ai, and Airbnb returned matching destinations.

## Boundary cases

This pattern concerns text-query assistance. Airbnb's date-range picker collects a structured date range, and Netflix's FAQ discloses static answers; those controls are not instances even though Airbnb's Location field is.

## Validation limits

Keyboard navigation through suggestions, empty results, latency, query correction, and reduced-network behavior were not tested consistently. Duck.ai showed a Terms / Privacy notice before its chat could be used; no agreement was accepted and no response was generated.
