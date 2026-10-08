# Candidate: selectable featured content

**Status:** promoted to [Selectable Featured Content](../patterns/selectable-featured-content.md) after replication across eight sites; retain this file as the hypothesis and validation record.

## Hypothesis

Within a bounded featured-content sequence, a user can select an item or advance the sequence, and the interface updates which item is active while keeping the user in the same page context.

Possible invariant to test:

```text
select / next / previous → active item changes → associated content becomes the current item
```

This remains a candidate. The examples may differ in whether they replace a complete content panel, move a carousel, or only expose a selected state. Further sites and counterexamples are needed before deciding whether these are one reusable pattern or separate variants.

## Supporting observations

- [Apple: hero product tab replacement](../observations/apple/hero-product-tab-replacement.md) — direct tab selection replaced the active product panel.
- [AMD: AI Portfolio carousel](../observations/amd/ai-portfolio-next-carousel.md) — Next advanced the active solution card.
- [NVIDIA: homepage feature carousel](../observations/nvidia/homepage-feature-carousel-next.md) — Next advanced the active story panel.
- [Nike: hero next slide](../observations/nike/homepage-hero-next-slide.md) — Next changed the current slide.
- [Tesla: vehicle slide selection](../observations/tesla/homepage-vehicle-slide-selection.md) — direct tab selection changed the selected slide state.
- [Figma: community carousel](../observations/figma/community-carousel-next.md) — Next changed the current resource and associated image/link.
- [GitHub: Plan feature tab](../observations/github/features-tab-plan.md) — selecting a feature tab changed the selected state and its summary.
- [IKEA: Designer stories carousel](../observations/ikea/designer-stories-next.md) — Next enabled Previous, showing the carousel left its initial position.

## Validation questions

- Does the active item always update its own content, image, and action links, or can selection change only position/state?
- Are direct tabs and sequential Next/Previous controls instances of one pattern or different patterns?
- How does automatic progression affect a user's ability to inspect content? Nike's pause control is one observed response; search for sites that hide it or provide another way to stop motion.
- Check touch, keyboard, reduced-motion, loading, and boundary behavior before making a broader pattern definition.
