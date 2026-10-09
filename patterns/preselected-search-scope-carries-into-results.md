---
record_type: pattern
status: validated
name: Preselected Search Scope Carries into Results
definition: A category or search mode chosen before query submission is carried into the request or route and scopes the resulting listings, whether or not the selector keeps its displayed value.
problem:
  - Broad marketplace searches may return items from product areas the visitor did not intend to search.
mechanism: Include the preselected category or mode in the search request or route and expose the scope in the resulting URL or result context.
trigger:
  - A search form or search flow offers a category or mode before query submission.
action:
  - Choose a category or mode, enter a query, and submit the search.
response:
  - The search URL, route, or result context reflects the selected scope.
  - Matching listings appear within that scope while the query remains available.
  - The header selector may preserve or reset its displayed value after navigation.
use_when:
  - A marketplace, catalog, or travel product has distinct result scopes that visitors can choose before searching.
avoid_when:
  - The categories overlap so broadly that the scope would mislead, or the selector affects only pre-query suggestions.
variants:
  - Selected department remains visible in the Amazon search header and scoped results.
  - Selected Consumer Electronics scope appears in eBay's URL, title, and category filter while the header resets to All Categories.
  - The Experiences search mode establishes an experiences route before location entry and remains in the submitted Tokyo results path (Airbnb).
  - Switching from Tokyo Experiences results to Homes in the open search form retains Tokyo and submits a `/homes` route with home listings (Airbnb).
examples:
  - Amazon
  - eBay
  - Airbnb
evidence:
  - ../observations/amazon/search-department-scope.md
  - ../observations/amazon/search-department-scope-applies-to-submitted-results.md
  - ../observations/ebay/search-category-selection-before-query.md
  - ../observations/ebay/search-category-applies-to-submitted-results.md
  - ../observations/airbnb/experiences-search-category-applies-to-results.md
  - ../observations/airbnb/search-mode-switch-preserves-destination.md
boundaries:
  - ../observations/amazon/search-department-autocomplete-independence.md
counterexamples: []
confidence: high
---

## Cross-site invariant

Amazon, eBay, and Airbnb all let visitors choose a search scope before submitting a query and carry that scope into the result state. Amazon's Electronics choice appears in the result URL and header; submitting the same query under All Departments removed the category parameter and produced a broader result context. eBay's Consumer Electronics choice appears as `_sacat=293` in the result URL, in the page title, and in the Category filter; its header resets to All Categories after submission. Airbnb's Experiences tab routes to `/experiences` before location entry, and Tokyo results remain scoped to Experiences. In a follow-up, switching from those results to Homes retained Tokyo, changed the route to `/homes`, and showed home listings.

## Boundaries and counterexamples

Amazon's autocomplete suggestions remained the same when the category changed before submission; this is a pre-submit suggestion state and does not establish result scoping. Best Buy and IKEA's visible search controls did not expose a pre-submit category selector in the screened sessions, so they are not support or counterexamples. No direct counterexample has been observed.

## Validation limits

The invariant is directly supported by three independent products spanning marketplace search and travel experiences. Amazon supplies a paired scoped-versus-All comparison. eBay's scoped query succeeded on retry; its unscoped comparison showed an error page, so no direct eBay count comparison is claimed. Airbnb's Experiences and Homes modes were compared in one search session: switching to Homes retained Tokyo and displayed home results. Searches with user-selected dates were not tested.
