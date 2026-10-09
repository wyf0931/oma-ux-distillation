---
record_type: observation
site: NVIDIA
page: Homepage Artificial Intelligence module
context: The Artificial Intelligence module has Quick Links expanded and its related destination links visible.
trigger: explicit activation of an expanded Quick Links control
action: Activate Quick Links again to collapse it.
response:
  - Quick Links returns to its collapsed state.
  - The related destination links disappear.
  - The module heading and descriptive text remain visible; the browser stays on the homepage.
state: The AI module changes from expanded Quick Links to collapsed Quick Links without navigation.
intent: hide the related-link list and return to the module summary
purpose: unknown
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-sg/
    page_title: World Leader in Artificial Intelligence Computing | NVIDIA
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Expand Quick Links in the Artificial Intelligence module, then activate the expanded control again.
    before: Quick Links is expanded with seven related destinations listed under the AI module description.
    after: Quick Links is collapsed; the link list is absent and the heading/description remain; the URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The main hero carousel continued running independently; its slide position is not part of this interaction's state change.
