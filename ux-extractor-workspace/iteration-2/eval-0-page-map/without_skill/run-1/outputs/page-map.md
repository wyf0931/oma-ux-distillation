---
record_type: page_map
site: IKEA
page: US sofas and sectionals category listing
visible_structure:
  - "Global header with language/region, ZIP code and store controls, IKEA Home, Products/Rooms/Deals/Design & ideas/Services navigation buttons, product search, login, Favorites, and Shopping bag links."
  - "Main content begins with a skip-to-product-list link, a sofa category link group, the page heading 'Sofas & sectionals', and breadcrumbs."
  - "Introductory sofa copy includes popular-series links and a 'Read more' button."
  - "An IKEA Family savings section contains a terms link and two promotion links."
  - "A 'Sort and Filter' area includes a 'Sort' button, a 'Results list' heading, status text 'Showing 24 of 224 results', a progress bar, and a 'Show more products' link. The supplied URL includes a price-bucket query parameter."
  - "Additional content includes a GULLVALLA editorial section with two image buttons, a sofa navigator link, a set of warranty/returns/planning/delivery promotional links, delivery/financing/assembly/planning service links, sofa buying-guide copy, and related category links."
  - "Footer includes IKEA Family and Business Network sections, Help/Shop & Learn/About IKEA/Legal link groups, social links, payment-method images, cookie settings, and language/region control."
interaction_candidates:
  - "Could the Products, Rooms, Deals, Design & ideas, or Services navigation buttons reveal a menu? Not tested."
  - "Could the product search field show suggestions or navigate to results after text entry? Not tested."
  - "Could the category links and breadcrumbs navigate to the corresponding category pages? Not tested."
  - "Could 'Read more' reveal additional introductory copy? Not tested."
  - "Could the 'Sort' button expose sorting options? Not tested."
  - "What filter controls, if any, are available in the 'Sort and Filter' area, and does the URL's price-bucket parameter correspond to a visibly selected filter? The snapshot did not expose filter controls or a selected-filter label."
  - "Could 'Show more products' append another product group or navigate to a paginated state? Not tested."
  - "Could the GULLVALLA image buttons reveal or hide product price tags? Their accessible names mention hiding price tags; no button was activated."
  - "Could the sofa navigator link open an interactive product-finding flow? Not tested."
limits:
  - "Only the page's initial accessibility snapshot was inspected; no control was clicked, focused, expanded, typed into, scrolled, or submitted."
  - "The accessibility snapshot exposed result counts and a 'Show more products' link but did not expose product cards or filter controls; their contents and availability could not be established from this capture."
  - "The URL contains a price-bucket query parameter, but the snapshot did not establish whether the page rendered that filter as selected."
  - "Viewport dimensions and exact browser version were unavailable from the permitted snapshot-only capture."
related_observations: []
evidence:
  - evidence_class: page-evidence
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    page_title: "Sofas & Couches - Modern & Affordable - IKEA"
    viewport: unknown
    browser: unknown
    captured_at: "2026-10-09"
    tool: "Playwright CLI (isolated in-memory browser session); initial accessibility snapshot only"
---

# Page map notes

This is a static map of the requested US IKEA sofas listing page, captured immediately after navigation. It records page regions and candidate questions only. The result summary is present in the snapshot, but product cards and filter controls are absent from the accessibility tree at capture time; this does not establish whether they were visually present or how they behave. No interaction response has been observed.
