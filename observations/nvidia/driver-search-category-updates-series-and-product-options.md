---
record_type: observation
site: NVIDIA
page: Manual Driver Search
context: "The NVIDIA driver form has no category, series, product, or operating system selected. Its unselected Series options are GeForce-only, and Product options list GeForce RTX 50 Series laptop GPUs."
trigger: "The visitor starts a manual driver search with dependent selectors available."
action: "Select NVIDIA RTX PRO / RTX / Quadro as the product category."
response:
  - "The category selector shows NVIDIA RTX PRO / RTX / Quadro."
  - "The Series options change from 42 GeForce series to 18 RTX PRO or Quadro series, and NVIDIA RTX PRO Series is selected by default."
  - "The Product options change from six GeForce RTX 50 Series laptop GPUs to eight RTX PRO models, and NVIDIA RTX PRO 6000 Blackwell Workstation is selected by default."
  - "Windows 10 64-bit is selected by default from the operating system options."
  - "The URL remains https://www.nvidia.com/en-us/drivers/; no search results are shown until Find is activated."
state: "Choosing the product category replaces the available downstream series and model choices and automatically selects defaults without navigating or submitting the form."
intent: "Set the product family for a manual driver lookup."
purpose: "hypothesis — constrain driver lookup choices to product-compatible series, models, and operating systems."
evidence:
  - evidence_class: observed
    url: https://www.nvidia.com/en-us/drivers/
    page_title: "Download The Official NVIDIA Drivers | NVIDIA"
    viewport: 1280x727 CSS pixels
    browser: Chrome 154
    captured_at: "2026-10-08"
    tool: Chrome DevTools MCP
    reproduction: "Open NVIDIA's public driver download page in a fresh isolated context, leave all manual search controls unselected, and choose NVIDIA RTX PRO / RTX / Quadro in Product Category. Do not activate Find or download a driver."
    before: "The four primary selectors show Select Product Category, Select Product Series, Select Product, and Select Operating System. The Series selector contains 42 GeForce choices; Product contains six GeForce RTX 50 Series notebook models."
    after: "Product Category is NVIDIA RTX PRO / RTX / Quadro; Series has 18 RTX PRO or Quadro choices and defaults to NVIDIA RTX PRO Series; Product has eight RTX PRO models and defaults to NVIDIA RTX PRO 6000 Blackwell Workstation; Operating System defaults to Windows 10 64-bit. The URL is unchanged."
    screenshot: null
confidence: high
---

## Notes

The dropdown values and option lists were checked in the accessibility snapshot and native select DOM before and after the category change. The form was not submitted, and no driver download began. This supports [Upstream Selection Constrains Downstream Options](../../patterns/upstream-selection-constrains-downstream-options.md) as an independent site example.
