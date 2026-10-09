---
record_type: observation
site: Linear
page: Pricing
context: "Basic is billed yearly at $10 per user/month and Business is billed yearly at $16 per user/month. Enterprise is labeled Annual billing only."
trigger: "The visitor compares monthly and yearly billing on the pricing page."
action: "Activate Billed yearly on the Basic plan to switch it off."
response:
  - "The Basic and Business Billed yearly checkboxes become unchecked together."
  - "Basic changes from $10 to $12 per user/month."
  - "Business changes from $16 to $18 per user/month."
  - "Enterprise remains Custom pricing and Annual billing only."
  - "The URL remains https://linear.app/pricing."
state: "The Basic and Business plans change from annual to monthly prices in place; Enterprise remains annual-only and the page URL is unchanged."
intent: "Compare the monthly recurring prices for Linear's paid plans."
purpose: "hypothesis — make the price effect of changing billing cadence visible on the pricing page."
evidence:
  - evidence_class: observed
    url: https://linear.app/pricing
    page_title: "Pricing – Linear"
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open Linear Pricing in an isolated logged-out context. Activate the visible Billed yearly label on the Basic plan; the label click is used because the underlying checkbox is visually hidden."
    before: "Basic is $10 and Business is $16 per user/month; both Billed yearly checkboxes are checked. Enterprise is Custom with Annual billing only."
    after: "Basic is $12 and Business is $18 per user/month; both Billed yearly checkboxes are unchecked. Enterprise remains Custom with Annual billing only. The URL is unchanged; no Get started or Contact sales link was activated."
    screenshot: null
confidence: high
---

## Notes

The displayed price values are capture-time UI state. This records only a local billing-mode display change; no signup, sales, or billing flow was entered.
