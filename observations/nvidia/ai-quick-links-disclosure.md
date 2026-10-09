---
record_type: observation
site: NVIDIA
page: Homepage Artificial Intelligence module
context: The Artificial Intelligence module shows its first descriptive carousel slide; Quick Links is collapsed.
trigger: explicit activation of the Quick Links control
action: Activate Quick Links in the Artificial Intelligence module.
response:
  - Quick Links enters an expanded state.
  - Seven related destinations appear in the current module, including Overview, Data Analytics, Machine Learning, Recommender Systems, Speech AI, Apache Spark, and RAPIDS.
  - The browser remains on the NVIDIA homepage.
state: The Quick Links region changes from collapsed to expanded without a page navigation.
intent: explore related AI topics from the homepage module
purpose: "hypothesis — expose related destinations in the context of the current AI topic"
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-sg/
    page_title: World Leader in Artificial Intelligence Computing | NVIDIA
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the NVIDIA homepage, locate the Artificial Intelligence module, and activate its collapsed Quick Links control.
    before: The AI module shows descriptive content and a collapsed Quick Links control.
    after: The control is expanded and seven related links are visible; the page URL is unchanged.
    screenshot: null
confidence: high
---

## Notes

The page's separate primary hero carousel advanced from slide 2 to slide 3 during the capture interval. The AI module's Quick Links state transition was independently visible; the carousel timing was not measured.
