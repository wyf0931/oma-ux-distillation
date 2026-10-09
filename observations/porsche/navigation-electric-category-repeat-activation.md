---
record_type: observation
site: Porsche
page: Singapore homepage navigation modal
context: The navigation dialog is open; the Electric category is collapsed.
trigger: repeated activation of a collapsed navigation category
action: Activate Electric again after an initial activation focused the control but left it collapsed.
response:
  - The Electric category enters an expanded state.
  - Electric and hybrid destination links and supporting media appear in the dialog.
  - The homepage remains loaded and the URL is unchanged.
state: Electric changes from collapsed to expanded on the second activation; the dialog remains open.
intent: inspect electric and hybrid destinations
purpose: "hypothesis — group electric-model and charging destinations under one category"
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/singapore/en/?cs_redirect=1
    page_title: unknown
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open Menu, activate Electric once and observe focus without expansion, then activate Electric a second time and inspect the dialog snapshot. This sequence was repeated after closing and reopening the menu.
    before: After the first activation, Electric is focused but collapsed; only the default model entries are visible.
    after: After the second activation, Electric is marked expanded and the dialog exposes Overview, Electric and Hybrid Models, Charging & Range, and E-Performance Guide content; the URL is unchanged.
    screenshot: null
confidence: medium
---

## Notes

The two-step activation sequence reproduced after resetting the menu. The reason for the first focus-only response is unknown; do not generalize it to other Porsche controls.
