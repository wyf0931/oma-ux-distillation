---
record_type: pattern
status: validated
name: Escape Dismissal for Navigation Menus
definition: Pressing Escape dismisses an open primary-navigation menu while keeping the current page loaded.
problem:
- An open navigation menu can obscure the page or delay returning to the current context.
mechanism: Press Escape while the navigation menu is open to close it without navigating away.
trigger:
- A primary-navigation menu is open and the user presses Escape.
action:
- Press Escape.
response:
- The navigation menu closes.
- The current page remains loaded.
use_when:
- An expandable primary-navigation menu can be opened by a user.
avoid_when:
- Escape is needed to resolve a more immediate nested interaction; preserve that interaction’s expected key behavior.
variants:
- 'Menu opened by pointer hover: Tesla.'
- 'Menu opened by explicit activation: Figma, Vercel.'
- 'Modal navigation closes but focus remains on the page body: Porsche.'
- 'Tabbed product menu closes while a category tab is focused: AMD.'
examples:
- Tesla
- Figma
- Vercel
- Porsche
- AMD
evidence:
- ../observations/tesla/vehicles-navigation-escape-dismissal.md
- ../observations/figma/products-menu-escape-dismissal.md
- ../observations/vercel/products-menu-escape-dismissal.md
- ../observations/porsche/navigation-modal-escape-dismissal.md
- ../observations/amd/products-menu-escape-dismissal.md
confidence: high
boundaries:
  - ../observations/vercel/pricing-direct-link.md
counterexamples: []
---
# Candidate: Escape Dismissal for Navigation Menus

**Status:** first promoted to [Escape Dismissal for Navigation Menus](../patterns/escape-dismissal-for-navigation-menus.md) after replication across three independent sites; Porsche extended it to four and AMD to five.

## Hypothesis

Pressing Escape while an expanded primary-navigation menu is open closes that menu while preserving the current page.

Possible invariant:

```text
navigation menu open → press Escape → menu closes → page context remains
```

## Supporting observations

- [Tesla: Vehicles menu Escape dismissal](../observations/tesla/vehicles-navigation-escape-dismissal.md) — the hover-open dialog closed and the homepage remained loaded.
- [Figma: Products menu Escape dismissal](../observations/figma/products-menu-escape-dismissal.md) — the activated menu returned to its collapsed state and the homepage URL remained unchanged.
- [Vercel: Products menu Escape dismissal](../observations/vercel/products-menu-escape-dismissal.md) — the activated menu closed, focus returned to Products, and the Pricing URL remained unchanged.
- [Porsche: navigation modal Escape dismissal](../observations/porsche/navigation-modal-escape-dismissal.md) — the modal closed and the France homepage remained loaded; focus was left on BODY.
- [AMD: Products menu Escape dismissal](../observations/amd/products-menu-escape-dismissal.md) — Escape closed the tabbed menu while Graphics was selected and focused.

## Validation questions

- Do menus opened by click, hover, and keyboard consistently respond to Escape?
- Does focus return to the invoking control after dismissal?
- Which other overlay-like navigation patterns use Escape, and which intentionally do not?
- Does Escape close only the menu or also dismiss another active layer?

## Validation outcome

The same Escape → menu closed → current page preserved transition was observed on Tesla, Figma, Vercel, Porsche, and AMD. Porsche did not return focus to Menu; AMD focus return is unverified. Focus return is not part of the invariant.

## Boundary evidence

Vercel's Pricing control navigates directly without opening a menu, so the Escape dismissal pattern does not apply to that control: [direct Pricing link observation](../observations/vercel/pricing-direct-link.md).
