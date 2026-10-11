---
name: site-audit
description: Produce a prioritized technical and on-page SEO audit with page URLs, observed evidence, repair steps and verification criteria. Use for SEO audits, crawl errors, title/meta issues, indexability checks or broken-link diagnosis. Uses bounded owned Apify audit/link Actors or supplied exports. Reports crawl coverage and does not invent Core Web Vitals or index status.
---

# Bounded SEO audit

Read [shared rules](../vibesearch/references/workflow-common.md), [CLI guidance](../vibesearch/references/apify-cli.md), and [Actor contracts](../vibesearch/references/actor-contracts.md).

1. Reuse the authorized site and business goal. Confirm scope: a page, a representative sample, or a larger bounded crawl. Reject private-network targets and credential-bearing URLs. Choose key page types rather than treat a ten-page sample as the entire site.
2. Use a provided audit export or plan `complete-seo-audit` with exact `siteUrl`, small `maxPages`, `respectRobotsTxt: true`, and `demoMode: false`. Add `broken-link-checker` only for gaps that matter. Bound external links, request counts and timeout; obtain the concrete run approval.
3. Read the same run's dataset/summary/output. Determine page coverage, exclusions, blocked pages and partial findings. Distinguish rendered/static observations and limits described by the Actor. A robots directive or canonical tag alone isn't proof of Google's actual indexing; do not infer Search Console state.
4. Group observed issues into access/indexability, status/redirect/canonical, titles/headings, content/intent, internal links, and supported technical signals. Prioritize blockers affecting useful pages, then material user/discovery issues, then polish. Mark severity as an editorial assessment.
5. Each finding needs an affected URL, raw observed signal, why it matters, a concrete proposed fix, and how to verify that fix. Read actual evidence before suggesting changes. Return Unknown when a signal such as field Core Web Vitals, full-site coverage or a current index state was not measured.
6. Deliver 3–5 first actions and a full finding table. Changes to code, robots, redirects, canonical tags or publishing require the user's separate scope/authorization and appropriate testing; don't modify a site merely because an audit was requested.

Use [report template](../vibesearch/references/report-template.md). The audit is complete when its bounded evidence and missing coverage are clear; it does not certify a site's SEO or security.
