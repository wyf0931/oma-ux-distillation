---
record_type: pattern
status: validated
name: Expanded Primary Navigation
definition: A top-level navigation control opens a menu of related destinations in place, so visitors can inspect routes before
  choosing one.
problem:
- Several related destinations sit beneath one broad product or topic label.
- A visitor needs enough context to choose the right destination.
mechanism: Reveal a set of related destinations from a top-level control while keeping the current page context available.
trigger:
- Activate or hover over an expandable top-level navigation control.
action:
- The visitor opens the menu and selects one destination or dismisses it.
response:
- The control enters an expanded state.
- A set of links appears without changing the current page.
- Some menus group links and add short descriptions.
use_when:
- A top-level topic contains several destinations that visitors may need to compare.
- Group labels or short descriptions help distinguish destinations.
avoid_when:
- A top-level item has one clear destination.
- Users need to scan a long, filterable catalog rather than a small navigation group.
variants:
- 'Grouped product catalog with descriptions: Stripe, Notion, Vercel, Figma.'
- 'Topic menu with direct links: Linear, Anthropic.'
- 'Hover-open vehicle menu with Learn and Order actions: Tesla.'
- 'Keyboard activation moves focus into the revealed destination group: Vercel.'
- 'Modal destination index with expandable model groups: Porsche.'
- 'Tabbed product-category menu with grouped destinations and in-place panel switching: AMD.'
- 'Click-open product panel with destinations grouped by product family: NVIDIA.'
examples:
- Linear
- Stripe
- Notion
- Anthropic
- Vercel
- Figma
- Tesla
- Porsche
- AMD
- NVIDIA
evidence:
- ../observations/linear/product-navigation-menu.md
- ../observations/stripe/product-navigation-menu.md
- ../observations/notion/product-navigation-menu.md
- ../observations/anthropic/research-navigation-menu.md
- ../observations/vercel/products-menu.md
- ../observations/vercel/products-menu-keyboard-activation.md
- ../observations/figma/products-navigation-menu.md
- ../observations/tesla/vehicles-navigation-menu-hover.md
- ../observations/porsche/navigation-menu-open.md
- ../observations/amd/products-mega-menu.md
- ../observations/amd/products-menu-category-tab.md
- ../observations/nvidia/products-menu-opens-destination-group.md
confidence: high
boundaries:
- ../observations/vercel/pricing-direct-link.md
counterexamples: []
---
## Cross-site invariant

Across ten sites, clicking or hovering over an expandable top-level control exposed related destination links while the browser remained on the same page. Menu contents differed: AMD used tabs to switch product-category panels in place, NVIDIA's Products menu grouped destinations by product family, Tesla's vehicle menu included Learn and Order actions, Porsche used a modal destination index, and a research menu exposed topic links.

## Boundary cases

Direct links such as Pricing appear beside expandable controls in the Vercel and Notion headers ([Vercel page map](../corpus/vercel/page-inventory.md), [Notion page map](../corpus/notion/page-inventory.md)). Vercel's Pricing link was tested and navigated directly to the pricing route ([observation](../observations/vercel/pricing-direct-link.md)); it is outside the menu pattern. Search forms and FAQ disclosures also have different triggers and state changes.

## Validation limits

Click and keyboard activation were observed; keyboard opening moved focus into the revealed links on Vercel. Hover behavior was observed on Tesla. Touch behavior, arrow-key traversal, focus return after dismissal, and nested submenu behavior were not tested consistently. Anthropic required a second activation in this session before the expanded menu became visible.
