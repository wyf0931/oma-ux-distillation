# Selectable Featured Content

```yaml
name: Selectable Featured Content
definition: >
  A bounded set of featured items offers direct selection or sequential controls.
  The active item changes in place and the interface identifies which item is current.
  Implementations may also replace the associated copy, image, or actions.
user_problem:
  - Visitors need to inspect several featured items without leaving the page.
  - A sequence needs a visible current position.
trigger:
  - Select an item tab, or use Previous / Next controls.
interaction:
  - The visitor selects a specific item or advances through the sequence.
system_response:
  - The active item changes.
  - The interface marks the selected or current item.
  - Where tested, the active item's supporting content changes with it.
purpose:
  - Support in-place browsing of a finite featured set.
when_to_use:
  - A small set of featured products, stories, capabilities, or resources should share one page region.
  - Visitors benefit from one active item at a time and a way to inspect alternatives.
when_not_to_use:
  - The user needs search, filters, or comparison across a large or unbounded set.
  - All information needs to remain visible together for reference.
variants:
  - Direct tab selection: Apple, Tesla, GitHub.
  - Sequential Previous / Next: AMD, NVIDIA, Nike, Figma.
  - Timed progression with a pause control: Nike.
examples:
  - Apple
  - AMD
  - NVIDIA
  - Nike
  - Tesla
  - Figma
  - GitHub
evidence:
  - ../observations/apple/hero-product-tab-replacement.md
  - ../observations/amd/ai-portfolio-next-carousel.md
  - ../observations/nvidia/homepage-feature-carousel-next.md
  - ../observations/nike/homepage-hero-next-slide.md
  - ../observations/nike/homepage-hero-autoplay.md
  - ../observations/tesla/homepage-vehicle-slide-selection.md
  - ../observations/figma/community-carousel-next.md
  - ../observations/github/features-tab-plan.md
```

## Cross-site invariant

Across seven independent sites, a user action changed the current item in a finite featured set and the interface reflected that state. On Apple, AMD, NVIDIA, Figma, and GitHub, the active item's supporting copy, media, or links were also observed to update. Nike and Tesla snapshots verified the current-slide or selected-tab state; their full associated-content update was not separately verified.

## Boundary cases

Amazon and Spotify search expose query-based results, and Airbnb asks for search parameters. Those mechanisms do not revolve around one active item in a finite featured sequence. Netflix FAQ items disclose separate answers rather than advancing a featured sequence.

## Validation limits

Desktop interactions were observed. Touch swiping, keyboard operation, reduced-motion behavior, and boundary wrapping were not tested consistently. Automatic progression was observed on Nike only. The usage guidance is an inference from the cases and should be revisited as the corpus grows.
