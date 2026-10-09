---
record_type: observation
site: Apple
page: iPhone overview to country selector
context: The US iPhone overview is loaded; the footer shows “United States. Choose your country or region”.
trigger: explicit activation of the country/region control
action: Activate “United States. Choose your country or region”.
response:
  - The browser navigates to Apple’s Choose Your Country or Region page.
  - A list of country and region links appears, including United Kingdom.
  - The original iPhone page is no longer the current page.
state: The visitor moves from the US iPhone overview to a dedicated market selector.
intent: choose another Apple market or region
purpose: "hypothesis — provide a central route for choosing a market-specific Apple site"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/iphone/
    page_title: iPhone - Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: Open the US iPhone overview and activate the footer's United States. Choose your country or region link.
    before: The US iPhone overview is visible; no country selector is open.
    after: The browser is at https://www.apple.com/choose-country-region/ and the country/region chooser is visible.
    screenshot: null
confidence: high
---

## Notes

The country selector exposed regional site destinations. Selecting a market was tested separately.
