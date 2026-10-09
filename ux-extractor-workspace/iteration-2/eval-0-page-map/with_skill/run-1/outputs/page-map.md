---
record_type: page_map
site: IKEA
page: US sofas and sectionals listing with a price-bucket filter parameter
visible_structure:
  - "The header contains language/region and store controls, IKEA Home, Products/Rooms/Deals/Design & ideas/Services navigation buttons, Search by product, login or sign-up, Favorites, and Shopping bag."
  - "The main content begins with skip links, sofa category links, the Sofas & sectionals heading, and Products → Sofas & armchairs → Sofas & sectionals breadcrumbs."
  - "The introductory section has category copy, popular-series links, and a Read more button."
  - "An IKEA Family savings section contains a terms link and two promotional links."
  - "The Sort and Filter section reports 33 items and shows Color quick-filter buttons with counts, including Gray (26), Beige (22), Black (9), Blue (7), and additional colors."
  - "Additional facet controls include Sort, Type, Color, Price, Size, Number of seats, Material, Shape, Firmness, Features, Customer rating, Series, and Category."
  - "The listing shows Last chance (12 products), Best seller (0 products, disabled checkbox), and New products (8 products), followed by an Active filters section with Remove filter by $0.00–499.99."
  - "The Results list contains product-comparison checkboxes and product entries."
interaction_candidates:
  - "Does removing the active price filter change the result count and the availability of facet values? Not tested."
  - "Does selecting an enabled Color or category facet change the product list and other facet counts? Not tested."
  - "What sorting choices appear when Sort is activated, and how does a choice affect result order? Not tested."
  - "How does the disabled Best seller checkbox relate to the active price-filtered state? It was not activated."
  - "Can product comparison checkboxes be selected, and what state change follows? Not tested."
  - "Does Read more reveal additional category copy? Not tested."
  - "Do the sofa navigator link, category shortcuts, or navigation buttons open distinct destinations or menus? Not tested."
limits:
  - "Only the initial accessibility snapshot was inspected. No controls were clicked, expanded, typed into, scrolled, or submitted."
  - "The URL contains a price-bucket parameter and the page displays a matching active price-filter removal control, but no filter action was performed in this capture; no before/after response is claimed."
  - "Chrome DevTools MCP could not create a named isolated context. A fresh tab in its research browser was used as fallback; the header displayed 'Hej! Log in or sign up', and no account or personal data was inspected."
  - "The accessibility snapshot does not establish visual placement, viewport visibility, or motion behavior. Viewport dimensions and exact browser version were unavailable."
related_observations: []
evidence:
  - evidence_class: page-evidence
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    page_title: "Sofas & Couches - Modern & Affordable - IKEA"
    viewport: unknown
    browser: unknown
    captured_at: "2026-10-09"
    tool: "Chrome DevTools MCP take_snapshot"
    capture_method: "Loaded the supplied URL in a fresh research tab and inspected the initial accessibility snapshot only. No page controls were operated."
---

## Page map notes

The snapshot exposes an active price-filter removal control, result and facet counts, and one disabled zero-count facet. These are static page facts from a filtered initial state. This capture does not add an interaction observation or change the support count for any pattern.
