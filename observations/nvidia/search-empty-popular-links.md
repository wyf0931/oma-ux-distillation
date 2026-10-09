---
record_type: observation
site: NVIDIA
page: Homepage Search surface
context: The NVIDIA homepage shows a collapsed Search NVIDIA control.
trigger: explicit activation of the global search control
action: Activate Search NVIDIA without entering a query.
response:
  - A search surface opens with an empty AI-powered search field.
  - A Popular Links section appears with destinations including Developers, Partners, Executive Insights, Startups and VCs, Documentation, and Technical Training.
  - The homepage remains loaded at the same URL.
state: The search control changes from collapsed to an open empty-query surface with default popular links.
intent: begin a search or choose a common NVIDIA destination
purpose: "hypothesis — surface popular destinations before visitors enter a query"
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-sg/
    page_title: World Leader in Artificial Intelligence Computing | NVIDIA
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the public NVIDIA homepage and activate Search NVIDIA without typing.
    before: Search NVIDIA is collapsed; no search surface is visible.
    after: A blank AI-powered search field and Popular Links appear; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The search input was visible and empty in read-only DOM inspection. The Popular Links list was visible in the accessibility snapshot.
