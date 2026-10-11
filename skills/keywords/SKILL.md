---
name: keywords
description: Research and prioritize SEO keywords, search intent, topic clusters, competitor keyword gaps and keyword-to-page mappings. Use when asked what to rank for, keyword opportunities, long-tail keywords, a content calendar, or a keyword plan. Uses owned Apify keyword/SERP Actors with approved budgets, or supplied exports offline. Does not invent volume or organic difficulty.
---

# Keyword research and content plan

Read [shared rules](../vibeseo/references/workflow-common.md). Use [CLI guidance](../vibeseo/references/apify-cli.md) and [Actor contracts](../vibeseo/references/actor-contracts.md) for live work.

1. Reuse the site's product, audience, goal and market. Get seeds from the actual product, customer questions and approved competitor pages. A list of 3–5 meaningful seeds is usually enough to start. Use the provided data immediately when live collection isn't authorized.
2. Plan bounded expansion with `dataforseo-keyword-research` (`mode: keyword_ideas`). Use `keyword-search-volume-api` only when metrics enrichment adds value; its `free_tier` mode name does not mean the Apify run has no charge. Check provider requirements and pricing. Use `seo-domain-keyword-scraper` (`ranked_keywords`) for a specified competitor, and `scrape-google-serp` for a small shortlist's intent. Prepare inputs from the exact templates in [inputs](../vibeseo/references/inputs/).
3. Normalize keywords without collapsing different languages or meanings. Deduplicate within the same market/source window. Preserve supplied numbers, nulls and row references. Separate brand and non-brand terms. A missing value is Unknown, not zero.
4. Classify informational, navigational, commercial and transactional intent as editorial inference backed by query/SERP evidence. Retain forums, videos, directories and shopping results when they explain real search intent; do not remove them to make a term look easy.
5. Cluster by shared user need and actual result overlap where observed. Map each cluster to an existing verified URL or a proposed new page. Flag possible cannibalization for review; intent similarity alone isn't proof. Don't assign ten pages the same primary intent.
6. Prioritize High/Medium/Low by business relevance, intent, available demand evidence, current foothold, realistic ability to contribute and effort. Explain the reasons. Don't manufacture organic difficulty from advertising competition or a universal “opportunity score.” Keep keywords with missing demand in a validation queue if demand is decision-critical.
7. Deliver the columns in [report template](../vibeseo/references/report-template.md): keyword/cluster, intent, demand metric and source/date, organic difficulty if actually supplied, current page/new page, business fit, priority, original contribution, next check. Include 3–5 first actions and a short content calendar; treat dates as proposed editorial slots.

If the user has an authorized Search Console export, use its clicks, impressions and query/page positions as first-party observations over the stated window. They are not keyword monthly search-volume estimates. VibeSEO has no bundled Search Console integration.

Done when a writer/owner can identify what to target, which page owns each intent, why it matters, and what evidence is still missing. Hand a chosen cluster to [content-brief](../content-brief/SKILL.md).
