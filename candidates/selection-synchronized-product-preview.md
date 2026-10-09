---
record_type: pattern
status: validated
name: Selection-Synchronized Product Preview
definition: In a product configurator, selecting an option updates the product representation to reflect the current build; dependent specifications or price may update with it.
problem:
  - Visitors need to understand how an option changes the configured product before continuing.
mechanism: Mirror the selected option in the rendered product preview and keep the current build state identifiable.
trigger:
  - A product configurator exposes selectable product variants or options.
action:
  - Select a variant or configurable option.
response:
  - The product preview changes to reflect the selected configuration.
  - Where relevant, related specifications, price estimates, and the build summary update.
use_when:
  - A product has meaningful configurable attributes that can be represented in an interactive preview.
avoid_when:
  - The selected option has no visible effect on the product representation or the preview cannot faithfully reflect it.
variants:
  - Drivetrain selection changes the vehicle representation and dependent specifications or payment estimate (Tesla).
  - Exterior color selection changes the vehicle image and serialized build state while price remains unchanged (Porsche).
  - A custom shoe-part color changes the 3D preview while the step and price remain unchanged (Nike).
  - A laptop color selection changes the product image and selected-color label while the displayed price remains unchanged (Apple).
  - A laptop model-size selection updates the gallery image description and price estimate while the selected color remains unchanged (Apple).
examples:
  - Tesla
  - Porsche
  - Nike
  - Apple
evidence:
  - ../observations/tesla/model-y-trim-selection-updates-specs.md
  - ../observations/porsche/taycan-color-choice-updates-preview.md
  - ../observations/nike/air-force-1-by-you-color-selection-preview.md
  - ../observations/apple/macbook-pro-color-selection-updates-preview.md
  - ../observations/apple/macbook-pro-model-size-selection-updates-preview.md
boundaries:
  - ../observations/porsche/model-series-filter-replaces-results.md
counterexamples: []
confidence: high
---

# Validation record

## Hypothesis

Selecting a product configuration option updates the live preview so the current build is visible as it changes. Dependent specifications, pricing, or a summary may also update, but those secondary changes are not required by the invariant.

## Evidence comparison

- [Tesla: Model Y drivetrain selection](../observations/tesla/model-y-trim-selection-updates-specs.md) — All-Wheel Drive changed the vehicle image description, selected build summary, estimated range, acceleration, and monthly financing estimate in place.
- [Tesla: Model Y L variant selection](../observations/tesla/model-y-selects-complete-long-wheelbase-variant.md) — selecting the complete long-wheelbase variant updated the image description, range, acceleration, finance estimate, and build summary without navigation.
- [Porsche: Taycan color selection](../observations/porsche/taycan-color-choice-updates-preview.md) — selecting Black changed the rendered vehicle image and serialized the selected build in the URL while the displayed total remained unchanged.
- [Nike: Air Force 1 By You color selection](../observations/nike/air-force-1-by-you-color-selection-preview.md) — selecting Black for Vamp / Quarter updated the custom shoe's 3D preview and selected swatch while the customization step, URL, and price remained unchanged.
- [Apple: MacBook Pro color selection](../observations/apple/macbook-pro-color-selection-updates-preview.md) — selecting Silver changed the preview from the Space Black MacBook to a silver MacBook while the selected 14-inch model and displayed price estimates remained unchanged. Chip and display choices were disabled without a delivery ZIP, which was not entered.
- [Apple: MacBook Pro model size](../observations/apple/macbook-pro-model-size-selection-updates-preview.md) — selecting 16-inch changed the gallery image description from a 14-inch to a 16-inch MacBook Pro and updated the purchase estimates while retaining Silver and the current URL. The selection reproduced after returning to 14-inch.

The shared response is a product representation updated to reflect the selected build. Tesla's captured evidence uses an accessibility image description; Porsche, Nike, and Apple have viewport screenshots. No evidence establishes that every configurator uses this behavior.

## Boundaries

- [Porsche: model-series filter](../observations/porsche/model-series-filter-replaces-results.md) — selecting Taycan updates a model listing and URL hash, but this catalog filter does not select an option inside a product configurator.

## Validation questions

- **Resolved for initial validation:** Tesla, Porsche, and Nike update their product representation after different configurable choices.
- Which kinds of option need a visual preview, and which only change specifications or price?
- Are there direct counterexamples where a selected build option changes state but leaves the preview unchanged?

## Validation outcome

Four independent public product configurators updated their product preview after a user choice: vehicle drivetrain on Tesla, vehicle exterior color on Porsche, a shoe-part color on Nike, and laptop color on Apple. The preview response is the invariant; dependent specifications and price changes vary by implementation. The Porsche model-series filter is a related catalog interaction but does not select a configurator option, so it remains a boundary.
