---
record_type: observation
site: Apple
page: Country selector from iPhone overview
context: Apple’s Choose Your Country or Region page is open after leaving the US iPhone overview; United Kingdom is listed.
trigger: explicit selection of a market destination
action: Select United Kingdom.
response:
  - The browser navigates to https://www.apple.com/uk/.
  - The resulting page is the Apple UK homepage with a localized product navigation and homepage content.
  - The US iPhone overview is not preserved as the selected content page.
state: The path changes from the iPhone overview through the country selector to the UK homepage.
intent: view Apple content for the UK market
purpose: "hypothesis — route a market choice to the region's primary Apple site"
evidence:
  - evidence_class: observed
    url: https://www.apple.com/choose-country-region/
    page_title: Choose your country or region - Apple
    viewport: unknown
    browser: Chrome
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: From the US iPhone overview, open the country selector and choose United Kingdom.
    before: The country selector lists United Kingdom as a destination; the prior page was the US iPhone overview.
    after: The browser is at https://www.apple.com/uk/ and shows the Apple UK homepage, including a link to the UK iPhone page at /uk/iphone/.
    screenshot: null
confidence: high
---

## Notes

This market selector did not preserve the specific iPhone page path. It does not establish how Apple handles other market selections.
