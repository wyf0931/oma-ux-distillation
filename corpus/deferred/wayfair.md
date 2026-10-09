# Deferred targeted follow-up: Wayfair

- Requested URL: https://www.wayfair.com/keyword.php?keyword=sofas
- Validation question: After a price facet narrows a furniture listing, are zero-count upholstery-color options disabled, selectable, or omitted?
- Outcome: The public sofa listing and filters loaded. Selecting Under $500 and Gray changed their checkboxes to checked, but no result-card change could be verified. The page's GraphQL requests returned HTTP 429 during the interaction.
- Evidence date: 2026-10-09
- Interaction research: inconclusive; no observation was created because the result state may have been affected by service rate limiting.
- Active corpus status: not added; this attempt supplies no interaction evidence for pattern validation.

The site was considered as a furniture marketplace follow-up to the IKEA zero-count facet observation. Resume only when the public listing updates without 429 responses and the resulting product/filter state can be inspected.
