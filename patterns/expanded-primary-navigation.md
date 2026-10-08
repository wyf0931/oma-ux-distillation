# Expanded Primary Navigation

```yaml
name: Expanded Primary Navigation
definition: >
  A top-level navigation control opens a menu of related destinations in place,
  so visitors can inspect routes before choosing one.
user_problem:
  - Several related destinations sit beneath one broad product or topic label.
  - A visitor needs enough context to choose the right destination.
trigger:
  - Activate an expandable top-level navigation control.
interaction:
  - The visitor opens the menu and selects one destination or dismisses it.
system_response:
  - The control enters an expanded state.
  - A set of links appears without changing the current page.
  - Some menus group links and add short descriptions.
purpose:
  - Expose a destination set while preserving the visitor's current context.
when_to_use:
  - A top-level topic contains several destinations that visitors may need to compare.
  - Group labels or short descriptions help distinguish destinations.
when_not_to_use:
  - A top-level item has one clear destination.
  - Users need to scan a long, filterable catalog rather than a small navigation group.
variants:
  - Grouped product catalog with descriptions: Stripe, Notion, Vercel.
  - Topic menu with direct links: Linear, Anthropic.
examples:
  - Linear
  - Stripe
  - Notion
  - Anthropic
  - Vercel
evidence:
  - ../observations/linear/product-navigation-menu.md
  - ../observations/stripe/product-navigation-menu.md
  - ../observations/notion/product-navigation-menu.md
  - ../observations/anthropic/research-navigation-menu.md
  - ../observations/vercel/products-menu.md
```

## Cross-site invariant

Across five sites, activating an expandable top-level control exposed related destination links while the browser remained on the same page. Menu contents differed: product menus could include groups and summaries, while a research menu exposed topic links.

## Boundary cases

Direct links such as Pricing appear beside expandable controls in the Vercel and Notion headers ([Vercel page map](../corpus/vercel/page-inventory.md), [Notion page map](../corpus/notion/page-inventory.md)). Vercel's Pricing link was tested and navigated directly to the pricing route ([observation](../observations/vercel/pricing-direct-link.md)); it is outside the menu pattern. Search forms and FAQ disclosures also have different triggers and state changes.

## Validation limits

Click activation was observed. Hover behavior, touch behavior, keyboard dismissal, focus return, and nested submenu behavior were not tested across sites. Anthropic required a second activation in this session before the expanded menu became visible.
