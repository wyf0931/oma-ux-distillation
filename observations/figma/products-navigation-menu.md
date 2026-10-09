---
record_type: observation
site: Figma
page: Homepage primary navigation
context: The primary navigation shows Products, Solutions, Community, and Resources as collapsed controls.
trigger: explicit activation of a top-level navigation control
action: Activate Products.
response:
  - Products enters an expanded state.
  - A Products navigation region appears with grouped destination links.
  - The links include product names and short descriptions, such as Figma Design — Design and prototype in one place, Figma Make — Prompt to code anything you can imagine, and Dev Mode — Translate designs into code.
state: The Products navigation changes from collapsed to expanded while the homepage remains loaded.
intent: explore Figma products and choose a destination
purpose: "hypothesis — expose product destinations and help visitors distinguish them before navigating"
evidence:
  - evidence_class: observed
    url: https://www.figma.com/
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public homepage in an isolated context, dismiss the cookie dialog using Do not allow cookies, then activate Products in the primary navigation.
    before: Products, Solutions, Community, and Resources appear as collapsed primary-navigation controls.
    after: Products is marked expanded and a navigation region lists product destinations with explanatory text; the page URL remains https://www.figma.com/.
    screenshot: null
confidence: high
---

## Notes

The menu opening and its destination labels were directly visible in the accessibility snapshot. Destination-link behavior was not tested.
