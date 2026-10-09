---
record_type: observation
site: Figma
page: Pricing
context: "The Professional plan has Annual selected. Full seat is $16/month, Dev seat is $12/month, and Collab seat is $3/month. Organization and Enterprise plans are labeled Billed annually."
trigger: "A pricing card offers an annual/monthly billing toggle."
action: "Select Monthly on the Professional plan."
response:
  - "The billing toggle changes from Annual selected to Monthly selected."
  - "Professional Full seat changes from $16 to $20/month."
  - "Professional Dev seat changes from $12 to $15/month."
  - "Professional Collab seat changes from $3 to $5/month."
  - "Organization and Enterprise remain labeled Billed annually."
  - "The URL remains https://www.figma.com/pricing/."
state: "The Professional plan changes from annual to monthly prices in place; other plan cards remain annual-only and the URL is unchanged."
intent: "Compare monthly Professional plan seat prices."
purpose: "hypothesis — show the price difference for the selected billing cadence without leaving the plan comparison."
evidence:
  - evidence_class: observed
    url: https://www.figma.com/pricing/
    page_title: "Plans & Pricing | Figma"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Figma Pricing in an isolated logged-out context and activate ‘Show annual billing prices: Annual selected’ on the Professional plan."
    before: "Professional is Annual selected at $16 Full seat, $12 Dev seat, and $3 Collab seat per month. Organization and Enterprise are marked Billed annually."
    after: "Professional is Monthly selected at $20 Full seat, $15 Dev seat, and $5 Collab seat per month. Organization and Enterprise remain Billed annually, and the URL remains unchanged. No plan was selected or purchased."
    screenshot: null
confidence: high
---

## Notes

The toggle applies to the Professional plan; Organization and Enterprise show annual billing only. Price figures are capture-time UI state, not stable product facts.
