---
record_type: observation
site: NVIDIA
page: Manual Driver Search
context: "Product Category is GeForce. The visitor manually selected GeForce RTX 40 Series, which changed the Product selector to NVIDIA GeForce RTX 4090 D."
trigger: "A downstream series and model are selected in the manual driver form."
action: "Change Product Category to NVIDIA RTX PRO / RTX / Quadro."
response:
  - "Series changes from the manually selected GeForce RTX 40 Series to the default NVIDIA RTX PRO Series."
  - "Product changes from NVIDIA GeForce RTX 4090 D to the default NVIDIA RTX PRO 6000 Blackwell Workstation."
  - "The URL remains https://www.nvidia.com/en-us/drivers/ and Find is not activated."
state: "Changing to an incompatible parent category resets the manually selected series and its product to compatible defaults."
intent: "Switch the driver lookup from GeForce to RTX PRO products."
purpose: "hypothesis — prevent the driver lookup from retaining child values that do not match the new product category."
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-us/drivers/
    page_title: "Download The Official NVIDIA Drivers | NVIDIA"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-09"
    tool: Chrome DevTools MCP
    reproduction: "Open NVIDIA's public driver page in an isolated context. Choose GeForce, manually select GeForce RTX 40 Series, then change Product Category to NVIDIA RTX PRO / RTX / Quadro. Do not activate Find or download a driver."
    before: "Product Category is GeForce, Series is manually set to GeForce RTX 40 Series, and Product is NVIDIA GeForce RTX 4090 D."
    after: "Product Category is NVIDIA RTX PRO / RTX / Quadro, Series is NVIDIA RTX PRO Series, and Product is NVIDIA RTX PRO 6000 Blackwell Workstation. The URL is unchanged and the form is not submitted."
    screenshot: null
confidence: high
---

## Notes

The selected child values before and after the category change were confirmed in the accessibility snapshot and native select DOM. The child selection was incompatible with the new parent; behavior when a child remains valid under both parent choices is untested.
