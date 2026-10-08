---
site: Notion
page: Homepage, Product navigation
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Product menu reveals feature groups and summaries

## Context

URL: https://www.notion.com/. The main navigation exposed a Product button with a menu.

## Interaction

```yaml
trigger: explicit navigation
user_intent: learn which product capabilities are available
user_action: click Product
system_response:
  - the Product button enters an expanded state
  - the menu reveals a See all features link
  - Capture, Find, and Automate destinations appear with short explanatory descriptions
  - a release link and Notion App download link also appear
state_change: product navigation changes from closed to expanded
feedback: grouped destinations and descriptions become visible
animation: unknown
purpose_hypothesis: give users a brief capability overview before sending them to a product page
```

## Evidence

- Reproduction: open the URL and click Product in the main navigation.
- Result: the post-action snapshot marked the button expanded and exposed the feature groups, summaries, release link, and download link.
- Screenshot: not captured.
- Notes / limits: only the opening state was observed; no menu destination was followed.
