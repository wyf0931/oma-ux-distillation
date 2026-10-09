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
- 'Enter activates the selected Blog shortcut after Tab moved focus to CI/CD; selection and focus differ: GitHub.'
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
- ../observations/github/search-query-clear-restores-default-shortcuts.md
- ../observations/nvidia/search-empty-popular-links.md
- ../observations/airbnb/home-search-empty-location-shows-destinations.md
confidence: high
boundaries:
  - ../observations/amazon/search-empty-focus.md
counterexamples:
  - ../observations/spotify/search-empty-input-focus.md
---
# Candidate: Pre-query Search Shortcuts

**Status:** promoted to [Pre-query Search Shortcuts](../patterns/pre-query-search-shortcuts.md) after matching behavior was observed on four independent sites; retain this file as the hypothesis and validation record.

## Hypothesis

Opening an empty search surface can expose common destinations before the visitor enters a query.

Possible invariant:

```text
open empty search → default shortcuts appear → visitor may choose a destination or start typing
```

## Supporting observations

- [Apple: global search Quick Links](../observations/apple/global-search-quick-links.md) — opening Search apple.com exposed five default destinations.
- [GitHub: empty Quick search](../observations/github/search-empty-quick-suggestions.md) — opening Search or jump to exposed four generic Explore destinations.
- [GitHub: clearing a typed query](../observations/github/search-query-clear-restores-default-shortcuts.md) — after `react` produced an empty suggestion list, Clear search restored the four default shortcuts in their original order; this does not establish query-specific help for `react`.
- GitHub's empty combobox used ArrowDown to select GitHub Actions and then Blog ([first option](../observations/github/search-empty-arrow-down-activates-first-option.md), [next option](../observations/github/search-empty-arrow-down-advances-option.md)). After Tab moved focus to CI/CD while Blog remained selected, Enter opened GitHub Blog in two fresh isolated contexts ([Enter observation](../observations/github/search-empty-enter-opens-selected-option.md)); whether the focus/selection mismatch is intended remains unclear.
- From Blog, Tab focused the CI/CD option while Blog remained selected ([Tab focus observation](../observations/github/search-empty-tab-focus-next-option.md)); Enter then opened Blog in two contexts, so the active-selection and focus-order relationship remains unclear.
- From the initial no-selection state, Tab focused GitHub Actions without selecting it; Enter opened the focused action in two Playwright reproductions ([Tab focus](../observations/github/search-empty-tab-focuses-first-unselected-option.md), [Enter activation](../observations/github/search-empty-enter-activates-focused-unselected-option.md)).
- With Blog selected and CI/CD focused, ArrowDown moved focus to Code review while Blog stayed selected; this state was reproduced in two Playwright runs ([observation](../observations/github/search-empty-arrowdown-advances-focus-keeps-blog-selected.md)). The focus/selection relationship remains unresolved.
- After typing `react` without submitting, Clear search emptied the field and restored GitHub Actions, Blog, CI/CD, and Code review in their original order. The reset reproduced twice; it does not establish that query-specific suggestions appear for `react`.
- [NVIDIA: empty Search NVIDIA](../observations/nvidia/search-empty-popular-links.md) — opening Search NVIDIA exposed an empty AI-powered search field and Popular Links.
- [Airbnb: empty Location search](../observations/airbnb/home-search-empty-location-shows-destinations.md) — focusing the empty Location searchbox opened query-independent recommendations for Tokyo, Busan, and Perth.

## Counterexample evidence

- [Spotify: empty Search tab](../observations/spotify/search-empty-input-focus.md) — opening Search showed an empty combobox without query-independent shortcuts while homepage Popular Albums and Popular Radio remained visible. This is a direct counterexample to the shortcut response for an opened search surface in this logged-out session.

## Boundary evidence

- [Amazon: empty search focus](../observations/amazon/search-empty-focus.md) — the always-visible header field received focus without opening a separate search surface or shortcut list; this differs from the pattern's trigger.

## Validation questions

- Do other products expose query-independent shortcuts on an empty search surface?
- Are shortcuts most useful when chosen by popularity, recency, or task category?
- Do the default destinations remain accessible after query entry or transition to query-specific suggestions?
- How do keyboard users move between default shortcuts and the search field across implementations? GitHub Tab focused and Enter activated the first suggestion while it remained unselected; clearing `react` restored the empty-query shortcuts, but correcting to another nonempty query was not tested; Apple Tab focused the first Quick Link, whereas Airbnb Tab moved to Dates; ArrowDown did not select a shortcut in the latter two observed sessions.
- Does this pattern apply consistently within a product, or vary by logged-out page and search surface?

Apple's keyboard behavior was checked in one desktop session: ArrowDown left focus in the empty search field; Tab focused Find a Store, and a second Tab focused Apple Vision Pro ([ArrowDown observation](../observations/apple/global-search-arrow-down-no-highlight.md), [first Tab observation](../observations/apple/global-search-tab-focuses-first-quick-link.md), [second Tab observation](../observations/apple/global-search-tab-advances-quick-link.md)). Airbnb's behavior differed: ArrowDown left focus in the empty Location field without highlighting a recommendation; Tab moved focus to Dates while the list remained open ([ArrowDown observation](../observations/airbnb/home-empty-location-arrow-down-no-highlight.md), [Tab observation](../observations/airbnb/home-empty-location-tab-skips-recommendations.md)). On GitHub, Enter opened the focused, unselected GitHub Actions option; when Blog remained selected while CI/CD was focused, Enter instead opened Blog. The behavior differs by selection state, but intended semantics remain unknown. Other keyboard commands and screen-reader behavior remain untested.

## Validation outcome

Apple, GitHub, NVIDIA, and Airbnb expose default destinations when their search surfaces open empty. GitHub’s Playwright keyboard follow-up verified both focus-only activation and a separate selected/focused mismatch. Spotify provides a direct non-instance for its logged-out Search tab; Amazon's always-visible header input is an adjacent case. The pattern is a specific implementation, not a universal search behavior. Authenticated/personalized states remain untested.
