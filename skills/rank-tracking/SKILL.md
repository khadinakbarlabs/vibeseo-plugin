---
name: rank-tracking
description: Establish or compare sampled Google keyword rankings using the owned Apify rank Actor or supplied snapshots. Use for keyword positions, rank baselines, competitor rank reviews and suspected ranking changes. Matches domain, keyword, geography, language, device, search depth and capture time; missing results are outside the sample or unknown, never rank zero.
---

# Comparable ranking snapshots

Read [shared rules](../vibeseo/references/workflow-common.md), [CLI guidance](../vibeseo/references/apify-cli.md), and [Actor contracts](../vibeseo/references/actor-contracts.md).

1. Reuse the target domain, exact keyword panel and requested market/device. Define what is being measured: organic position within an explicit search depth. No scheduled runs are created by this skill.
2. Use supplied snapshots or plan `keyword-rank-tracker` with exact `targetDomain`, `keywords`, `locationCode`, `languageCode`, `device`, compatible `os`, small `depth` and `maxKeywords`. Check optional provider access. Approve the input/build/budget before starting.
3. Collect the run and interpret its actual output shape. Save keyword, matched URL, sampled rank/null, source, market/device/depth, time and completeness. Distinguish organic rank from ads or unrelated SERP features. Don't reconstruct a position from arbitrary row order.
4. Compare only equivalent panels: domain canonicalization, keyword, country/location, language, device, provider/method and depth. Retain new/removed keywords separately. Incompatible snapshots can be shown side by side but yield **Not comparable** for a change calculation.
5. “Not found” means no match in the sampled depth or an unknown/failed capture as described by evidence. It isn't rank zero, deindexing, or proof of lost visibility. Within matched valid observations, calculate change with a documented sign convention: previous position minus current position; positive means a better numerical position.
6. Report meaningful observed changes and their uncertainty, coverage and next check. Do not attribute a ranking shift to a content/link change without stronger evidence. A proposed follow-up date doesn't create a scheduler or approve future spending.

Deliver the rank table in [report template](../vibeseo/references/report-template.md), plus next actions. Recurring monitoring requires a separately available scheduler and explicit authorization for timing, budget and notifications.
