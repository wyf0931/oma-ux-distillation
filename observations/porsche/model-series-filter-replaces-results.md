---
record_type: observation
site: Porsche
page: Model overview
context: "Model overview initially shows the All model-series filter selected, with a count of 76 variants and results from multiple model series such as 718 and 911."
trigger: "The visitor narrows the model overview by model series."
action: "Select Taycan in the Model series filter."
response:
  - "Taycan becomes the selected model-series radio option."
  - "The model-variant region changes to ‘Taycan Model variants’ and displays Taycan-specific cards."
  - "The URL hash changes to #modelRangeId=taycan while the page remains on Model overview."
state: "The model series changes from All to Taycan; the result region updates from a mixed-series listing to Taycan variants, and the selection is reflected in the URL hash."
intent: "Browse Taycan models without leaving the overview."
purpose: "hypothesis — reduce a broad model catalog to the selected series while preserving the overview context."
evidence:
  - evidence_class: observed
    url: https://www.porsche.com/usa/models/
    page_title: "Model Overview and Configurator | Porsche USA"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the Porsche USA model overview in an isolated context, choose Required Only for cookies, then select Taycan under Model series."
    before: "All is selected with 76 variants. The visible results include 718 Cayman variants and the 911 Carrera series."
    after: "Taycan is selected; the results heading becomes Taycan Model variants and Taycan cards are shown. The URL hash becomes #modelRangeId=taycan. The page title and page remain the Model overview."
    screenshot: null
confidence: high
---

## Notes

This records the model-series filter response only. The eight-item count was shown beside Taycan before and after the selection, but the visible viewport included only part of the result list. No vehicle configuration or purchase was started.
