# Owned Actor map and acceptance checks

Live schemas, public metadata, build numbers and existing-run output field types were read on 2026-10-11. This is contract discovery, not a fresh release-acceptance canary or a reliability claim. [actors-live.json](actors-live.json) and [observed-output-shapes.json](observed-output-shapes.json) preserve those public metadata/type snapshots without raw run inputs or customer rows.

| Actor / ID | Snapshot build | Input fields to use | Interpret useful outputs |
| --- | --- | --- | --- |
| `dataforseo-keyword-research` / `8RW7Ow9S3hRAnX1ye` | 1.0.13 | `seedKeywords`, `mode`, `locationCode`, `languageCode`, `maxResults` | `keyword`, `searchVolume`, `cpcUsd`, returned `keywordDifficulty` and `searchIntent`, provenance/time; nulls remain unknown |
| `keyword-search-volume-api` / `B7Wq9VHcVFdfNqNBI` | 0.1.7 | `keywords`, `mode`, `countryName`, `languageName`, `maxKeywordsPerBatch` | One metric/status row per normalized keyword; `competition` is advertising competition. `free_tier` is a mode name, not an Apify price guarantee |
| `scrape-google-serp` / `z0r97dqhtUQk2AXd8` | 1.0.21 | `queries`, `countryCode`, `languageCode`, `maxResultsPages`, `resultsPerPage`, feature flags | Query-page rows with nested `organic_results`, questions/features when returned; missing features are not proof no feature exists |
| `seo-domain-keyword-scraper` / `7XL6DUjjDCqltKeBg` | 1.0.8 | `mode`, conditional `target` or `keywords`, `locationCode`, `languageCode`, `maxResults` | Mode-specific keyword/domain outputs. Existing inspected run was `VALID_EMPTY` with marker-only data: substantive competitor/backlink data is not qualified by that readback. Treat as optional and verify useful rows before making a claim |
| `backlink-opportunity-finder` / `n1uR8aWhzOBYhxLJl` | 1.0.14 | `keywords`, `targetDomain`, `opportunityTypes`, excludes, `countryCode`, `languageCode`, bounds | `url`, `prospectDomain`, `opportunityType`, source query, snippet, heuristic relevance/date. These are discovered opportunities, not existing links |
| `broken-link-checker` / `a2yeVoO8SdJgVEgbK` | 1.2.5 | `mode`, mode-specific `startUrl`/`urls`, `maxPages`, `maxLinksToCheck`, concurrency | URL/status/classification, referring source and check time. Inspect `blocked`, `timeout` and errors before calling a link broken |
| `complete-seo-audit` / `iC8z4bnewATHdZdiZ` | 1.0.6 | `siteUrl`, `maxPages`, link bounds, `respectRobotsTxt`, `demoMode: false` | Nested sampled `pages`, `issues`, coverage and heuristic category scores. An Actor score is not a Google ranking factor or SEO certification |
| `keyword-rank-tracker` / `ufcrXss0mJzYLRgWW` | 1.1.5 | `targetDomain`, `keywords`, location/language, `device`, compatible `os`, `depth`, `maxKeywords` | `found`, `targetRank`, `targetRankAbsolute`, `rankingUrl`, panel settings/date. Last sampled readback was `VALID_EMPTY` with a no-match row; no-match is not rank zero |

Use [input-schemas](input-schemas/) and [illustrative inputs](inputs/) together. Reread the live schema before starting. Do not transmit the example site/topic without the user's actual research request and approval.

DataForSEO-powered modes have optional `dataforSeoLogin`/`dataforSeoPassword` fields marked secret in their schema. The rank Actor also has optional rank-provider credential fields. An optional field doesn't prove publisher-funded access will be available for every caller or tier. The selected live run's returned outcome controls what can be reported. Do not substitute unavailable providers or change owner pricing.

Bound live usage: small seed/keyword lists, one search page, a small page audit, finite time/memory, current build and explicit cost ceiling. Advanced `backlinks_summary` can supply aggregate context only when actual rows are returned; the package claims no full backlink database. Complete page reads, Search Console, analytics and publishing/sending integrations are not bundled.
