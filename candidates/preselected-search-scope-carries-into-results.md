---
record_type: pattern
status: validated
name: Preselected Search Scope Carries into Results
definition: A category or search mode chosen before query submission is carried into the request or route and scopes the resulting listings, whether or not the selector keeps its displayed value.
problem:
  - A broad query may produce results outside the visitor's chosen product domain.
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
  - Amazon keeps Electronics in the search header and scoped results.
  - eBay carries Consumer Electronics into the results URL and page context while the header resets to All Categories.
  - Airbnb's Experiences tab establishes a route that remains active after searching Tokyo.
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
boundaries:
  - ../observations/amazon/search-department-autocomplete-independence.md
counterexamples: []
confidence: high
---

# Validation Record: Preselected Search Scope Carries into Results

## Hypothesis

The category or search mode selected before query submission appears in the resulting search scope and result context. Amazon keeps Electronics in its header and URL; eBay keeps Consumer Electronics in the URL and result page even though the header resets to All Categories; Airbnb carries Experiences into the route and results page. Amazon's autocomplete observation shows that query-time suggestions persisted while the department changed before submission; that adjacent state does not contradict the submitted-results invariant.

## Evidence comparison

Amazon, eBay, and Airbnb provide three independent examples across retail marketplaces and travel experiences. Amazon's submitted-search observation pairs an Electronics-scoped query (1–24 of over 40,000 results) with the same query submitted under All Departments (1–16 of over 50,000 results) in one session. eBay's successful scoped result URL contains `_sacat=293`, its title names Consumer Electronics, and the Category filter retains that scope even though the header selector resets to All Categories. Airbnb's Experiences tab routes to `/experiences` before location entry; after Tokyo is submitted, the route and result header remain scoped to Experiences. In a follow-up from those Tokyo Experiences results, switching the open search form to Homes and submitting retained Tokyo, changed the route to `/homes`, and displayed home listings. The first eBay submission and a later All Categories comparison attempt produced an error page, so no direct eBay count comparison is claimed. Airbnb user-selected dates were not tested. Result totals vary by session.

## Validation questions

- **Resolved at the cross-site threshold:** Amazon, eBay, and Airbnb carry a preselected search category or mode into the resulting scope.
- How often does the visible search control itself retain the selected value after submission?
- How does the scoped search behave when optional criteria such as dates are added?
- How should pre-submit scope selection relate to post-result facet filtering?

## Validation outcome

The shared scope-carrying invariant is directly observed on Amazon, eBay, and Airbnb, including marketplace category selection and Airbnb's Experiences/Homes mode switch. Confidence is high for the selected scope appearing in the resulting route or context. The selected header control may reset, eBay's unscoped comparison could not be observed, and Airbnb searches with user-selected dates remain untested. This candidate is promoted with those limits retained.
