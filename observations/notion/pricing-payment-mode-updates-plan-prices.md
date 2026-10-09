---
record_type: observation
site: Notion
page: Pricing
context: "The public Pricing page shows Pay yearly selected, a ‘Save up to 20% with yearly’ message, and USD plan prices. Plus is $10 and Business is $20 per member/month."
trigger: "The visitor compares the monthly and yearly payment modes."
action: "Select Pay monthly."
response:
  - "Pay monthly becomes selected and Pay yearly is deselected."
  - "The Plus price changes from $10 to $12 per member/month."
  - "The Business price changes from $20 to $24 per member/month."
  - "The Free plan remains $0 and Enterprise remains Custom pricing."
  - "The page URL stays https://www.notion.com/pricing."
state: "Payment mode changes from yearly to monthly; displayed plan prices update in place while plan content and URL remain on Pricing."
intent: "Compare plan costs for monthly payment."
purpose: "hypothesis — make recurring plan cost transparent for the selected billing cadence."
evidence:
  - evidence_class: observed
    url: https://www.notion.com/pricing
    page_title: "Notion Pricing Plans: Free, Plus, Business, & Enterprise."
    viewport: 1280x727
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open the public Pricing page in an isolated context and click the visible Pay monthly label."
    before: "Pay yearly is selected; Plus is $10 and Business is $20 per member/month; the page says ‘Save up to 20% with yearly’."
    after: "Pay monthly is selected; Plus is $12 and Business is $24 per member/month. Free remains $0, Enterprise remains Custom pricing, the yearly savings message remains visible, and the URL is unchanged."
    screenshot: null
confidence: high
---

## Notes

Only the pricing display was observed. No Get started, Contact Sales, signup, or payment action was activated. Prices are capture-time display values, not stable facts.
