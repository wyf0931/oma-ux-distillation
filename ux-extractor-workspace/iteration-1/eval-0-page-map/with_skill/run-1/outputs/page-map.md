---
record_type: page_map
site: IKEA US
page: Sofas & sectionals category listing with a price-buckets filter parameter in the URL
visible_structure:
  - "Global header with IKEA Home, Products, Rooms, Deals, Design & ideas, Services, product search, ZIP code and store controls, sign-in, Favorites, and Shopping bag links."
  - "Category shortcuts for Sofas & armchairs, Loveseats, Three-seat sofas, Sofas with chaise lounge, Sectionals, and Modular sofas; followed by the Sofas & sectionals heading and breadcrumbs."
  - "Introductory category copy with popular-series links and a Read more button."
  - "An IKEA Family sofa-savings section with Terms & conditions and two offer links."
  - "A Sort and Filter region with a Sort button, a 224 items status, a Results list heading, a Showing 24 of 224 results status, and a Show more products link."
  - "A sofa feature section for GULLVALLA with descriptive copy and two image buttons labeled Hide price tags on image 1 and Hide price tags on image 2."
  - "A sofa navigator promotion with an Explore the sofa navigator link."
  - "Service and reassurance content for warranty, returns, planning, delivery, financing, assembly, and store visits."
  - "A Recommended for you heading, long-form sofa guidance with category links, related category links, and the site footer."
interaction_candidates:
  - "What options appear when the Sort button is activated, and does choosing an option change the displayed result order? Not tested."
  - "Where are the price and other facet controls for the Sort and Filter region, and how does changing one affect the result count and product list? The initial accessibility snapshot did not expose facet controls; not tested."
  - "Does Show more products append the next group or navigate to another results page? The link destination includes page=2 and an anchor; behavior not tested."
  - "Does Read more reveal additional introductory text, and how is its expanded state communicated? Not tested."
  - "What changes when either GULLVALLA image button labeled Hide price tags is activated? Not tested."
  - "Does selecting a category shortcut or popular-series link navigate to its linked category page? Not tested."
  - "What journey does Explore the sofa navigator open, and how does that flow respond to a first choice? Not tested."
  - "Do product cards or their controls appear in the results list after the initial snapshot? Product cards were not represented in the captured accessibility tree; not tested."
limits:
  - "Only the initial accessibility snapshot after loading the supplied URL was used. No controls were clicked, typed into, expanded, scrolled, or submitted."
  - "The URL contains an encoded price-buckets filter parameter, but the snapshot does not expose selected-filter state or facet controls; whether the filter is applied cannot be established from this capture."
  - "The accessibility tree reports 224 items and Showing 24 of 224 results, but contains no product-card entries in the captured listing region. Product details and card-level actions are therefore unverified."
  - "A page snapshot does not establish visual placement, whether below-fold regions were visible in the viewport, or any interaction response."
  - "Viewport dimensions and exact Chrome version were unavailable from the capture."
related_observations: []
evidence:
  - evidence_class: page-evidence
    url: "https://www.ikea.com/us/en/cat/sofas-sectionals-fu003/?filters=f-price-buckets%3APRICE_0_50000"
    page_title: "Sofas & Couches - Modern & Affordable - IKEA"
    viewport: unknown
    browser: "Google Chrome; exact version unknown"
    captured_at: "2026-10-09"
    tool: "Playwright CLI accessibility snapshot (isolated session ux-eval-page-map-with-skill)"
    capture_method: "Loaded the supplied URL and read the initial accessibility snapshot; no page controls were operated."
---

# Page map notes

This is static page evidence for choosing safe follow-up tests. The accessibility snapshot identifies a category hierarchy, sorting/results region, navigation links, promotions, and the available result-count status. It did not expose filter facets or product cards in the captured listing region. The page map does not claim that any candidate action was performed or that the URL's price filter changed the results.
