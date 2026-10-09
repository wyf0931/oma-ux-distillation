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
- The active item or visible group changes.
- The interface marks the selected item or current position.
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
- ../observations/ikea/designer-stories-next-advances-card-window.md
- ../observations/netflix/tudum-fan-favorites-next-items.md
boundaries:
  - ../observations/amazon/search-autocomplete.md
  - ../observations/spotify/search-results-as-you-type.md
  - ../observations/airbnb/search-date-range-picker.md
  - ../observations/netflix/faq-single-open.md
  - ../observations/nike/homepage-hero-touch-swipe-no-advance.md
  - ../observations/netflix/tudum-fan-favorites-next-at-final-position.md
confidence: high
counterexamples: []
---
## Cross-site invariant

Across nine independent sites, a user action changed the current item, visible group, or position in a finite featured set and the interface reflected that state. On Apple, AMD, NVIDIA, Figma, and GitHub, the active item's supporting copy, media, or links were also observed to update. Nike and Tesla snapshots verified the current-slide or selected-tab state. IKEA's Next control shifted the visible two-card window from David Wahl and Friso Wiersma to Friso Wiersma and Wiebke Braasch, with the URL unchanged. Netflix advanced the Fan Favorites carousel to a new group of cards and moved the page indicator.

## Boundary cases

Amazon and Spotify search expose query-based results, and Airbnb asks for search parameters. Those mechanisms do not revolve around one active item in a finite featured sequence. Netflix FAQ items disclose separate answers rather than advancing a featured sequence.

## Validation limits

Desktop interactions, mouse drag, and a touch-emulated swipe that advanced Figma's carousel were observed. A touch-emulated swipe did not advance Nike's hero carousel in one session; this is a boundary, not a claim about physical devices. Netflix's Next items control remained enabled at position 4 of 4 but produced no observed change when clicked; wrapping was not observed in that session. Keyboard operation and reduced-motion behavior were not tested consistently. Automatic progression was observed on Nike only. The usage guidance is an inference from the cases and should be revisited as the corpus grows.
