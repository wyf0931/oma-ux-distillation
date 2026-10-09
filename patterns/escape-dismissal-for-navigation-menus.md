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
## Cross-site invariant

Across Tesla, Figma, Vercel, Porsche, and AMD, pressing Escape while a primary-navigation menu was open closed the menu and left the current page loaded. Tesla's menu had been opened by hover; Figma's, Vercel's, Porsche's, and AMD's had been opened by activating a control.

## Boundaries and counterexamples

This pattern applies only when a primary-navigation menu is open. Vercel's direct Pricing link navigates without opening a menu ([observation](../observations/vercel/pricing-direct-link.md)), so it is outside this interaction. The evidence does not claim that Escape closes every overlay, dialog, or nested interaction. No direct counterexample occurred in the five tested menus; other sites, nested menus, and competing dialogs remain untested.

## Validation limits

Focus returned to the invoking control on Vercel. It remained on BODY after dismissal on Porsche; return focus was not verified on Tesla, Figma, or AMD. Keyboard opening, touch behavior, nested menu behavior, and concurrent overlays were not tested.
