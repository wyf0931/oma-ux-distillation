---
record_type: observation
site: NVIDIA
page: Manual Driver Search
context: "Product Category is NVIDIA RTX PRO / RTX / Quadro; Series is NVIDIA RTX PRO Series; Product is NVIDIA RTX PRO 6000 Blackwell Workstation; Operating System is Windows 10 64-bit."
trigger: "The visitor changes Product Category after the form has populated downstream selectors."
action: "Change Product Category to GeForce."
response:
  - "Series resets to GeForce RTX 50 Series (Notebooks), with 42 GeForce series options available."
  - "Product resets to NVIDIA GeForce RTX 5090 Laptop GPU, with six GeForce RTX 50 Series notebook models available."
  - "Operating System remains Windows 10 64-bit."
  - "The URL stays https://www.nvidia.com/en-us/drivers/; Find is not activated."
state: "Changing the product category replaces the previously selected RTX PRO series and model with GeForce defaults without navigating or submitting the form."
intent: "Switch the driver lookup to GeForce products."
purpose: "hypothesis — keep downstream driver choices valid when the product category changes."
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-us/drivers/
    page_title: "Download The Official NVIDIA Drivers | NVIDIA"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open NVIDIA's public driver page in an isolated context, choose NVIDIA RTX PRO / RTX / Quadro, then change Product Category to GeForce. Do not activate Find or download a driver."
    before: "The category is NVIDIA RTX PRO / RTX / Quadro, Series is NVIDIA RTX PRO Series, and Product is NVIDIA RTX PRO 6000 Blackwell Workstation."
    after: "The category is GeForce, Series is GeForce RTX 50 Series (Notebooks), and Product is NVIDIA GeForce RTX 5090 Laptop GPU. The URL is unchanged and the form is not submitted."
    screenshot: null
confidence: high
---

## Notes

The selector values and option counts were confirmed in the accessibility snapshot and native select DOM. The category change reset the child selectors to GeForce defaults; no driver result was requested.
