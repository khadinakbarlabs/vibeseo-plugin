---
name: link-building
description: Find and qualify relevant link-building opportunities, resource pages, broken-link prospects and editorial pitches, then draft outreach for review. Use for backlink opportunities, link prospect research, competitor link research from supplied exports, or outreach drafts. Uses owned Apify Actors and source evidence; never treats a prospect as an acquired backlink or sends messages automatically.
---

# Qualified link opportunities

Read [shared rules](../vibeseo/references/workflow-common.md), [CLI guidance](../vibeseo/references/apify-cli.md), and [Actor contracts](../vibeseo/references/actor-contracts.md).

1. Reuse the site/audience and identify the useful asset: original research, a tool, a guide, a template or an expert contribution. With no useful asset, prepare an asset plan first. Obtain relevant topics, market/language, preferred opportunity types and excluded domains.
2. Use supplied backlink/prospect exports or plan a bounded `backlink-opportunity-finder` run. Its rows are search-derived candidate opportunities. The `seo-domain-keyword-scraper` backlink summary is aggregate context, not a complete competitor backlink index. Don't claim URL-level link gaps without actual link rows.
3. Deduplicate normalized source URLs and domains, retaining evidence of distinct editorial opportunities. Qualify topical/audience fit, current page existence, visible editorial purpose, whether the proposed asset adds value, and where a relevant link could appear. Keep unvisited pages **Needs verification**. Don't fabricate contacts, authority ratings, traffic or placement availability.
4. For a broken-link pitch, validate the exact outgoing link with `broken-link-checker` within approved bounds or an existing checked export. A timeout, block or 403 alone does not prove a dead link. Recheck ambiguous failures and inspect the referring page/context before proposing a replacement. The checker proves only its sampled observation.
5. Prefer earned editorial relevance, useful resources and honest contributions. Exclude spam networks, automated comment links, manipulative exchanges and guarantees. Paid advertising/sponsorship requires a separate explicit user decision, disclosure and appropriate link qualification; this plugin does not buy placements. Review [Google link-spam policies](https://developers.google.com/search/docs/essentials/spam-policies#link-spam).
6. Deliver a shortlist: source URL, topic/asset fit, opportunity type, observed evidence/date, verified/proposed link context, missing checks, public business contact if actually observed, priority/reason and next step. Distinguish **Discovered → Qualified → Drafted → Contacted → Responded → Placement observed**. Only update later stages with evidence of the actual action/result.
7. Draft a short relevant pitch with the real reason to contact that publisher and the supplied asset. Use placeholders for unknown recipient details. Never add fake praise, first-hand claims or promised benefits. Do not send it. Sending later needs the exact recipient and message approved through a separately available authorized channel.

Done when the owner can review the prospects and drafts. No hidden self-promotion or affiliate link is appended to the user's deliverable. Use [report template](../vibeseo/references/report-template.md).
