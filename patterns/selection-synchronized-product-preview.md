---
record_type: pattern
status: validated
name: Selection-Synchronized Product Preview
definition: In a product configurator, selecting a product variant or option updates the live preview to reflect the current build; dependent specifications, price, or summaries may update as well.
problem:
  - Visitors need to understand how an option changes the configured product before continuing.
mechanism: Mirror the selected option in a rendered product preview and keep the current build state identifiable.
trigger:
  - A product configurator exposes selectable variants or options.
action:
  - Select a product variant or configurable option.
response:
  - The product representation updates to show the selected configuration.
  - Where relevant, associated specifications, price estimates, or build summaries update.
use_when:
  - A product has meaningful configurable attributes that can be represented in an interactive preview.
avoid_when:
  - The choice has no visible effect on the product representation or the preview cannot faithfully reflect it.
variants:
  - Drivetrain choice updates the vehicle representation, specifications, and finance estimate (Tesla).
  - Complete model-variant selection changes the vehicle representation and available build summary (Tesla).
  - Exterior color choice updates the vehicle preview and build URL while displayed pricing remains unchanged (Porsche).
  - Shoe-part color choice updates the 3D model and selected swatch while the step and displayed price remain unchanged (Nike).
  - Laptop color selection updates the product image and selected-color label while the displayed price remains unchanged (Apple).
  - Laptop model-size selection updates the gallery image description and price estimate while the selected color remains unchanged (Apple).
examples:
  - Tesla
  - Porsche
  - Nike
  - Apple
evidence:
  - ../observations/tesla/model-y-trim-selection-updates-specs.md
  - ../observations/tesla/model-y-selects-complete-long-wheelbase-variant.md
  - ../observations/porsche/taycan-color-choice-updates-preview.md
  - ../observations/nike/air-force-1-by-you-color-selection-preview.md
  - ../observations/apple/macbook-pro-color-selection-updates-preview.md
  - ../observations/apple/macbook-pro-model-size-selection-updates-preview.md
boundaries:
  - ../observations/porsche/model-series-filter-replaces-results.md
counterexamples: []
confidence: high
---

## Cross-site invariant

Across Tesla, Porsche, Nike, and Apple, choosing a configurable product option changed the live product representation to match the current build. Tesla changed the selected drivetrain or complete model variant, its vehicle image description, performance figures, finance estimate, and configuration summary. Porsche changed the rendered Taycan color and serialized the build selection while its displayed total remained the same. Nike changed one shoe section in a 3D preview while keeping the same customization step and price. Apple changed the MacBook preview from Space Black to Silver while keeping the 14-inch model and displayed price estimates unchanged; selecting the 16-inch model also updated the gallery description and purchase estimates while retaining Silver.

The shared mechanism is the preview responding to the selected build. Specification and price updates are implementation-dependent details, not required parts of the pattern.

## Boundaries and counterexamples

Porsche's Model overview has a model-series filter that updates the result set and URL hash. It is adjacent product-discovery behavior, not a selection within the configurator, so it does not support this pattern.

No direct counterexample has been observed. A direct counterexample would require a product configurator to accept an option change while leaving its live product representation unchanged after the selection is confirmed.

## Validation limits

Four independent public configurators were observed, covering vehicle drivetrain and model-variant selection, vehicle exterior color, shoe-part color, and laptop color and model size. Tesla's visual response was verified through updated accessibility image descriptions; Porsche, Nike, and Apple have viewport screenshots. Apple's dependent chip and display options remained disabled because no delivery ZIP was entered. Saving, sharing, pricing persistence after reload, and purchase flows were not tested. The purpose and use guidance remain inferences from the observed feedback.
