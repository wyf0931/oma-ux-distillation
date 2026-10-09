---
record_type: pattern
status: validated
name: Selectable Featured Content
definition: A bounded set of featured items offers direct selection or sequential controls. The active item or visible group
  changes in place, and the interface identifies the current item or position; implementations may also replace associated
  copy, imagery, or actions.
problem:
- Visitors need to inspect several featured items without leaving the page.
- A sequence needs a visible current position.
mechanism: Keep a finite set of featured items in one page region and update the active item or visible group in place when
  the visitor selects an item or advances the sequence.
trigger:
- A featured sequence is visible and offers direct selection or Previous / Next controls.
action:
- Select an item or advance the sequence.
response:
- The active item changes.
- The interface marks the selected or current item.
- Where tested, the active item’s supporting content changes with it.
use_when:
- A small set of featured products, stories, capabilities, or resources should share one page region.
- Visitors benefit from one active item at a time and a way to inspect alternatives.
avoid_when:
- The user needs search, filters, or comparison across a large or unbounded set.
- All information needs to remain visible together for reference.
variants:
- 'Direct tab selection: Apple, Tesla, GitHub.'
- 'Sequential Previous / Next: AMD, NVIDIA, Nike, Figma, IKEA.'
- 'Mouse drag advances the active position: Figma.'
- 'Touch-emulated swipe advances the active position: Figma.'
- 'Next / Previous advances a page of cards with position dots: Netflix.'
- 'Timed progression with a pause control: Nike.'
examples:
- Apple
- AMD
- NVIDIA
- Nike
- Tesla
- Figma
- GitHub
- IKEA
- Netflix
evidence:
- ../observations/apple/hero-product-tab-replacement.md
- ../observations/amd/ai-portfolio-next-carousel.md
- ../observations/nvidia/homepage-feature-carousel-next.md
- ../observations/nike/homepage-hero-next-slide.md
- ../observations/nike/homepage-hero-autoplay.md
- ../observations/tesla/homepage-vehicle-slide-selection.md
- ../observations/figma/community-carousel-next.md
- ../observations/figma/community-carousel-drag.md
- ../observations/figma/community-carousel-touch-swipe.md
- ../observations/github/features-tab-plan.md
- ../observations/ikea/designer-stories-next.md
- ../observations/netflix/tudum-fan-favorites-next-items.md
boundaries:
- ../observations/amazon/search-autocomplete.md
- ../observations/spotify/search-results-as-you-type.md
- ../observations/airbnb/search-date-range-picker.md
- ../observations/netflix/faq-single-open.md
- ../observations/nike/homepage-hero-touch-swipe-no-advance.md
confidence: high
counterexamples: []
---
# Candidate: selectable featured content

**Status:** promoted to [Selectable Featured Content](../patterns/selectable-featured-content.md) after replication across nine independent sites; retain this file as the original hypothesis and validation record.

## Hypothesis

Within a bounded featured-content sequence, a user can select an item or advance the sequence, and the interface updates the active item or visible group while keeping the user in the same page context.

Possible invariant to test:

```text
select / next / previous → active item changes → associated content becomes the current item
```

The candidate was promoted with a deliberately narrow invariant: a user action changes the active item, visible group, or sequence position in a finite featured set, and the interface identifies the current item or position. Changes to the full content panel, carousel position, or selected state remain implementation variants. Supporting copy or media was only observed to change on a subset of examples and is not required by the pattern.

## Supporting observations

- [Apple: hero product tab replacement](../observations/apple/hero-product-tab-replacement.md) — direct tab selection replaced the active product panel.
- [AMD: AI Portfolio carousel](../observations/amd/ai-portfolio-next-carousel.md) — Next advanced the active solution card.
- [NVIDIA: homepage feature carousel](../observations/nvidia/homepage-feature-carousel-next.md) — Next advanced the active story panel.
- [Nike: hero next slide](../observations/nike/homepage-hero-next-slide.md) — Next changed the current slide.
- [Tesla: vehicle slide selection](../observations/tesla/homepage-vehicle-slide-selection.md) — direct tab selection changed the selected slide state.
- [Figma: community carousel](../observations/figma/community-carousel-next.md) — Next changed the current resource and associated image/link.
- [Figma: community carousel mouse drag](../observations/figma/community-carousel-drag.md) — dragging the carousel left advanced the current position from Slide 1 of 10 to Slide 2 of 10.
- [Figma: community carousel touch-emulated swipe](../observations/figma/community-carousel-touch-swipe.md) — a mobile-emulated touch swipe advanced the slide counter from 1 of 10 to 2 of 10; physical-device behavior remains untested.
- [GitHub: Plan feature tab](../observations/github/features-tab-plan.md) — selecting a feature tab changed the selected state and its summary.
- [IKEA: Designer stories carousel](../observations/ikea/designer-stories-next.md) — Next enabled Previous, showing the carousel left its initial position.
- [IKEA: Designer stories visible card window](../observations/ikea/designer-stories-next-advances-card-window.md) — Next shifted the visible cards from David Wahl / Friso Wiersma to Friso Wiersma / Wiebke Braasch and moved scrollLeft from 0 to 336; the URL stayed unchanged.
- [Netflix: Tudum Fan Favorites carousel](../observations/netflix/tudum-fan-favorites-next-items.md) — Next items advanced the visible card group, showed Previous items, and moved the position indicator to page 2 of 4 without changing the URL.

## Validation limits retained at promotion

- Does the active item always update its own content, image, and action links, or can selection change only position/state? Evidence showed both, so the content update is optional.
- Are direct tabs and sequential Next/Previous controls instances of one pattern or different patterns? They share the narrower active-item invariant and remain variants.
- How does automatic progression affect a user's ability to inspect content? Nike's pause control is one observed response; search for sites that hide it or provide another way to stop motion.
- Mouse drag and touch-emulated swipe are observed on Figma. A touch-emulated swipe did not advance Nike's hero carousel in one session ([boundary observation](../observations/nike/homepage-hero-touch-swipe-no-advance.md)); physical-device touch, keyboard, reduced-motion, loading, and boundary behavior remain open.
- Netflix's Next items control remained enabled at Page 4 of 4 but produced no observed change when clicked ([boundary observation](../observations/netflix/tudum-fan-favorites-next-at-final-position.md)). It did not wrap in that session; the reason the control remains enabled is unknown.
