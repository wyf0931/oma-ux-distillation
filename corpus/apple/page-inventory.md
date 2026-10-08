# Apple: iPhone page map

- URL: https://www.apple.com/iphone/
- Page title: iPhone - Apple
- Captured: 2026-10-08
- Browser: Google Chrome
- Surface: Chrome accessibility tree through the connected computer-use browser
- Evidence class: page evidence only

## Visible structure

The accessibility tree exposed a global product navigation, an iPhone family navigation, a hero gallery with `iPhone Duo` and `iPhone 18 Pro` tabs, an `Explore the lineup` section with model cards and a `Compare all models` link, and later sections for shopping support, iPhone features, accessories, and relationships with other Apple devices. The hero also exposes a `Play Hero gallery` button. The lineup and later galleries expose previous/next controls.

The initial capture is a page map. A later DevTools MCP session selected the `iPhone 18 Pro` hero tab from `iPhone Duo`; the active tabpanel changed its heading, supporting copy, image, and links. That interaction is recorded separately in `observations/apple/hero-product-tab-replacement.md`.

## Tool notes

- Chrome DevTools MCP could not list pages because its configured Chrome profile was already running.
- The connected browser surfaced this page. Its state changed during the session, and the gallery response could not be confirmed.
- Playwright CLI 0.1.22 is available. Its managed browser launch reported that `chrome-for-testing` is not installed; no browser was installed.
