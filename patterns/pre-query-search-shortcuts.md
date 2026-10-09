---
record_type: pattern
status: validated
name: Pre-query Search Shortcuts
definition: Opening an empty search surface reveals a small set of query-independent destinations before the visitor enters
  a query.
problem:
- Visitors may want to reach a common destination without composing a search query.
mechanism: Opening search presents default links or task shortcuts while leaving the query field empty.
trigger:
- The visitor opens the search surface with no query entered.
action:
- Open the search control.
response:
- The empty search field appears.
- Query-independent destination shortcuts are shown.
use_when:
- A small set of common destinations can help visitors begin exploration.
avoid_when:
- The current page already provides relevant discovery content and search-specific shortcuts would duplicate it.
variants:
- 'Curated Quick Links: Apple.'
- 'Explore categories: GitHub.'
- 'Keyboard-active suggestions in an empty combobox: GitHub.'
- 'Tab focuses GitHub Actions without selecting it; Enter activates the focused option: GitHub.'
- 'ArrowDown moves focus from CI/CD to Code review while Blog remains selected: GitHub.'
- 'Clearing a query restores the default Explore shortcuts in their original order: GitHub.'
- 'Enter activated the selected Blog shortcut after Tab moved focus to CI/CD; selected state and focus differed: GitHub.'
- 'Popular Links: NVIDIA.'
- 'Recommended destinations from an empty Location field: Airbnb.'
- 'Clearing a query restores the default Explore shortcuts in their original order: GitHub.'
examples:
- Apple
- GitHub
- NVIDIA
- Airbnb
evidence:
- ../observations/apple/global-search-quick-links.md
- ../observations/github/search-empty-quick-suggestions.md
- ../observations/github/search-empty-arrow-down-activates-first-option.md
- ../observations/github/search-empty-arrow-down-advances-option.md
- ../observations/github/search-empty-enter-opens-selected-option.md
- ../observations/github/search-empty-tab-focuses-first-unselected-option.md
- ../observations/github/search-empty-enter-activates-focused-unselected-option.md
- ../observations/github/search-empty-arrowdown-advances-focus-keeps-blog-selected.md
- ../observations/github/search-query-clear-restores-default-shortcuts.md
- ../observations/nvidia/search-empty-popular-links.md
- ../observations/airbnb/home-search-empty-location-shows-destinations.md
confidence: high
boundaries:
  - ../observations/amazon/search-empty-focus.md
counterexamples:
  - ../observations/spotify/search-empty-input-focus.md
---
## Cross-site invariant

Across Apple, GitHub, NVIDIA, and Airbnb, opening an empty search surface exposed query-independent destinations that could be chosen without typing. The labels and organization differed: Quick Links, Explore suggestions, Popular Links, and recommended travel destinations in Airbnb's Location picker.

## Boundaries and counterexamples

Spotify's logged-out Search tab opens an empty search view but shows no query-independent shortcuts; its Popular Albums and Popular Radio content remains visible. This directly contradicts the shortcut response for that empty-search surface in the observed session.

Amazon's search field is always visible in the homepage header; focusing it does not open a separate search surface. No shortcut list appeared, but that interaction is adjacent to the pattern's open-search trigger and remains a boundary rather than a direct counterexample. Neither record generalizes to authenticated or personalized states.

Query-specific suggestions after typing belong to Query-Guided Search Assistance, a separate interaction phase.

## Validation limits

Shortcut ranking and whether shortcuts remain available as text is entered were not tested consistently. In two fresh GitHub desktop contexts, ArrowDown selected GitHub Actions and then Blog; Tab focused CI/CD while Blog remained selected; Enter opened GitHub Blog. In two Playwright reproductions from a no-selection state, Tab focused GitHub Actions without setting `aria-selected`; Enter opened the focused GitHub Actions destination. With Blog still selected and CI/CD focused, ArrowDown moved focus to Code review while leaving Blog selected in two Playwright reproductions. Thus focus can move independently from selection; Enter opened the focused option when none was selected, but activated the selected Blog when focus differed. Clearing the `react` query restored the four default shortcuts in order in two Playwright captures; query-specific suggestions were still absent before clearing. The intended keyboard model remains unknown. In one Apple desktop session, ArrowDown left focus in the empty search field, while Tab moved focus to the first and then the second Quick Link. In one Airbnb desktop session, ArrowDown left focus in the empty Location field without highlighting a recommendation, and Tab moved focus to Dates while the list remained visible. Other keyboard commands and screen-reader behavior remain untested.
