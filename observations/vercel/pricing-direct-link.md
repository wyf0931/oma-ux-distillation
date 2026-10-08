---
site: Vercel
page: Homepage, Pricing navigation
observed_at: 2026-10-08
viewport: 1512x727 CSS pixels
browser: Chrome DevTools MCP
tool: take_snapshot + click
evidence_class: observed
---

# Pricing link navigates directly to the pricing page

## Context

URL: https://vercel.com/. The header exposed Products as an expandable button and Pricing as a direct link to `/pricing`.

## Interaction

```yaml
trigger: explicit navigation
user_intent: view plan pricing
user_action: click Pricing
system_response:
  - the browser navigates to /pricing
  - the new page title is "Vercel Pricing: Hobby, Pro, and Enterprise plans"
state_change: homepage route changes to the pricing page
feedback: the destination page and URL identify the pricing content
animation: unknown
purpose_hypothesis: provide a direct route for visitors who already know which information they need
```

## Evidence

- Reproduction: open the URL and click Pricing in the header.
- Result: the browser navigated to https://vercel.com/pricing and the page title changed to the pricing title.
- Screenshot: not captured.
- Notes / limits: no signup or plan selection was performed.
