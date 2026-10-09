# Corpus

Initial research targets from the project brief. The focus column records a question to explore, not a conclusion about the site's UX. Revisit selection after each batch when sites prove inaccessible or redundant. After initial coverage, add a targeted follow-up only when an open cross-site question cannot be resolved within the active corpus; document the question and reason. Do not add a site solely to reach a preferred support count—it should expose a distinct context that can test or challenge the invariant.

| # | Site | URL | Batch | Exploration focus | Status |
|---:|---|---|---:|---|---|
| 1 | Apple | https://www.apple.com/ | 1 | Product discovery, navigation, product page progression | 15 interactions recorded |
| 2 | NVIDIA | https://www.nvidia.com/ | 1 | Technical product exploration and information progression | 8 interactions recorded |
| 3 | AMD | https://www.amd.com/ | 1 | Product comparison and technical information | 7 interactions recorded |
| 4 | Nike | https://www.nike.com/ | 1 | Catalog exploration and product discovery | 11 interactions recorded |
| 5 | Tesla | https://www.tesla.com/ | 1 | Product exploration and conversion path | 5 interactions recorded |
| 6 | Porsche | https://www.porsche.com/ | 2 | Vehicle discovery and product configuration | 9 interactions recorded |
| 7 | Amazon | https://www.amazon.com/ | 2 | Search, filtering, comparison, and purchase discovery | 17 interactions recorded |
| 8 | IKEA | https://www.ikea.com/ | 2 | Category discovery and room/product planning | 7 interactions recorded; lower slideshow autoplay state unresolved |
| 9 | Figma | https://www.figma.com/ | 2 | Product education and collaboration entry points | 9 interactions recorded |
| 10 | Linear | https://linear.app/ | 2 | Workflow exploration and product navigation | 5 interactions recorded |
| 11 | Stripe | https://stripe.com/ | 3 | Information architecture and developer task paths | 6 interactions recorded |
| 12 | Notion | https://www.notion.com/ | 3 | Use case exploration and onboarding entry points | 7 interactions recorded |
| 13 | Mistral AI | https://mistral.ai/ | 3 | AI product navigation and language choice; replaces blocked OpenAI target | 6 interactions recorded |
| 14 | Anthropic | https://www.anthropic.com/ | 3 | Product and research content exploration | 5 interactions recorded |
| 15 | DuckDuckGo / Duck.ai | https://duckduckgo.com/ | 3 | Search and optional AI chat handoff; replaces blocked Perplexity target | 4 interactions recorded |
| 16 | Vercel | https://vercel.com/ | 4 | Documentation navigation and conversion path | 7 interactions recorded |
| 17 | GitHub | https://github.com/ | 4 | Repository discovery and collaboration paths | 24 interactions recorded |
| 18 | Netflix | https://www.netflix.com/ | 4 | Content discovery and selection | 7 interactions recorded |
| 19 | Spotify | https://open.spotify.com/ | 4 | Search, discovery, and recommendation exploration | 5 interactions recorded |
| 20 | Airbnb | https://www.airbnb.com/ | 4 | Search, filtering, and listing exploration | 22 interactions recorded |
| 21 | Intel | https://www.intel.com/ | 5 | Targeted follow-up: product category to family and series choices | 3 interactions recorded |
| 22 | eBay | https://www.ebay.com/ | 6 | Targeted follow-up: search category scope, facet counts, and filtered sorting | 5 interactions recorded |
| 23 | Best Buy | https://www.bestbuy.com/ | 7 | Targeted follow-up: query-dependent help in another retail marketplace | 1 interaction recorded |

Site-specific notes and interaction observations live in `corpus/<site>/` and `observations/<site>/` respectively. New `site.md` records use [`_site-template.v1.md`](_site-template.v1.md); validate their metadata front matter with [`site.yaml`](../ux-extractor/schemas/site.yaml). Site metadata identifies research targets but does not count as interaction evidence.

## Deferred initial candidates

OpenAI (`https://openai.com/`) and Perplexity (`https://www.perplexity.ai/`) displayed Cloudflare human-verification challenges in the browser session. Neither challenge was completed or bypassed. They remain deferred unless an accessible public route becomes available; Mistral AI and DuckDuckGo / Duck.ai fill the active 20-site corpus meanwhile.

- [OpenAI access note](deferred/openai.md)
- [Perplexity access note](deferred/perplexity.md)

## Deferred targeted follow-up

- [Target access note](deferred/target.md) — selected to investigate the open zero-count facet question after active-corpus comparisons did not expose zero-count states; search results were blocked by a human-verification challenge.
- [Walmart access note](deferred/walmart.md) — selected for the same validation question after Target was blocked; search results were blocked by a “Robot or human?” challenge.
- [Wayfair interaction note](deferred/wayfair.md) — selected as a furniture-marketplace follow-up; price and color checkboxes changed, but GraphQL 429 responses prevented verification of the result change.
