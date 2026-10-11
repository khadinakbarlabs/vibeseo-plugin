# VibeSEO: Keywords, Content & Link Building

![VibeSEO](assets/icon.svg)

Turn search data into an SEO plan, useful content, and a qualified list of link-building opportunities. VibeSEO is a skills-only plugin for Claude Code that uses Khadin Akbar's Apify Actors through the official Apify CLI. It helps founders, content teams, and agencies research what to target, decide what to write or improve, and prepare relevant outreach with evidence attached.

## What you can do

| Skill | Finished deliverable |
| --- | --- |
| `vibeseo` | Site context, research plan, visible project folder, action queue |
| `keywords` | Keyword clusters, intent, priorities, keyword-to-page map and content calendar |
| `content-brief` | SERP-informed writer brief, original angle, outline, title/meta options, reviewed draft when requested |
| `content-refresh` | Keep/change/add plan for an existing page, evidence checks and draft edits |
| `link-building` | Qualified prospect list, broken-link checks, relevant pitches and outreach drafts |
| `site-audit` | Prioritized technical and on-page findings with URLs, evidence and fix criteria |
| `rank-tracking` | Sampled ranking baseline and comparisons for matching keywords and markets |

Every workflow distinguishes observed data, supplied exports, editorial judgments, synthetic examples, and unknown values. Link prospects are opportunities to investigate; they are not acquired backlinks. Google Ads competition is not organic keyword difficulty. Ranking and traffic gains are not guaranteed.

## Start a useful workflow

Ask Claude:

> Find keyword opportunities for my agency software and turn them into a 30-day content plan.

> Create an SEO content brief for “agency client onboarding checklist,” including the original evidence we need to add.

> Find relevant resource pages for our original checklist and draft outreach for my review.

Or use `/vibeseo:keywords`, `/vibeseo:content-brief`, `/vibeseo:link-building`, and the other namespaced skills. The assistant asks only for the site, audience, market, goal, or permissions that are missing from the conversation and chosen project folder.

## Install and requirements

The initial release is prepared for Anthropic directory review. A directory listing is available only after Anthropic's review and publication steps; a local package or a private Plugin Creator save does not establish that status.

For a local source checkout, load the plugin with the [supported Claude Code development flow](https://code.claude.com/docs/en/plugins):

```bash
claude --plugin-dir ./vibeseo-plugin
```

For live research, install the official CLI from npm at the tested version:

```bash
npm install -g apify-cli@1.10.0
apify --version
apify login
```

You complete Apify's interactive login yourself. VibeSEO never asks you to paste tokens or provider passwords into chat and never opens credential files. Existing CLI authentication alone does not authorize a run. The third-party CLI has its own dependencies, authentication storage and optional telemetry settings; see [Apify CLI documentation](https://docs.apify.com/cli).

Live data collection requires a host that can execute the CLI, an Apify account, an available Actor build and a user-approved run budget. Optional caller-supplied provider credentials may be required for some advanced modes. Configure those through Apify's own secure controls and review its input-storage practices; ordinary examples include no secrets. If the backend needs unavailable provider access, the workflow reports that limitation. No paid provider subscription is bundled.

The skills can also analyze authorized CSV/JSON exports and draft plans offline without a new Actor run. Native CLI execution is the supported live path in Claude Code. Chat or other hosts without local execution can use supplied exports; live Cowork/browser-chat execution has not been established by this release.

## Actor backend

| Actor | Purpose |
| --- | --- |
| [Keyword research](https://apify.com/khadinakbar/dataforseo-keyword-research) | Seed expansion and returned keyword metrics |
| [Keyword search volume](https://apify.com/khadinakbar/keyword-search-volume-api) | Batch keyword metric enrichment |
| [Google SERP scraper](https://apify.com/khadinakbar/scrape-google-serp) | Organic results, questions and available SERP features |
| [Domain keyword research](https://apify.com/khadinakbar/seo-domain-keyword-scraper) | Competitor keywords and available domain/backlink summaries |
| [Backlink opportunity finder](https://apify.com/khadinakbar/backlink-opportunity-finder) | Candidate resource pages and other relevant link prospects |
| [Broken link checker](https://apify.com/khadinakbar/broken-link-checker) | Bounded checks of supplied or crawled URLs |
| [Complete SEO audit](https://apify.com/khadinakbar/complete-seo-audit) | Page-level SEO and available crawl findings |
| [Keyword rank tracker](https://apify.com/khadinakbar/keyword-rank-tracker) | Keyword rankings within the sampled search depth |

The release contains dated schema and build snapshots. The assistant rereads current schemas and pricing before a live operation. An Actor being public or a run being marked `SUCCEEDED` is not enough: it checks the same run's dataset, `OUTPUT`, `RUN_SUMMARY`, completeness, build and charge receipt. Empty or failed upstream results are reported honestly. Actor availability and third-party search coverage can change.

## What runs and where data goes

The plugin contains Markdown skills, JSON schemas/templates, evaluation cases, and an SVG icon. It bundles no executable runtime, server, MCP connector, hooks, automatic startup, scheduler, email sender or hidden telemetry.

On an approved live research operation, the assistant invokes the independently installed `apify` command. That CLI sends the approved domains, keywords, URLs, geographic/language settings and bounds to `api.apify.com`, then retrieves that run's metadata and outputs. Actors may visit the named websites, Google search pages and provider services such as DataForSEO according to their current implementation and input mode. No publisher account credentials are included. The user owns the calling Apify account and pays its applicable charges.

Reports and project context are saved in a visible local folder you choose, typically `vibeseo-projects/<site>/`. The assistant records only task-relevant context, sources, decisions and action status there. It does not upload that folder or share it with the publisher. Model-host chat/file handling, Apify storage/retention and the CLI's own behavior are governed by those services. See [Privacy and data handling](PRIVACY.md).

Before each new billable operation the assistant shows the exact Actors, input scope, market, build, limits and budget for approval. Apify currently documents `maxTotalChargeUsd` as a total Apify run-cost cap across pricing models. A separate provider account's charges, several runs together, and later data retrieval still need their own budget review; this is not a universal account spending limit. Time, memory and result limits are set too. The plugin never changes billing or provider plans.

Publishing content, sending an outreach message, buying a placement, scheduling repeated runs and sharing reports are separate actions requiring explicit authorization. The package prepares drafts and plans and includes no mechanism that performs those actions automatically.

## Quality, support and license

Workflow instructions were authored for this Actor-backed package after reviewing leading open-source SEO skill projects. Their stars, commits, licenses and specific design lessons are documented in [UPSTREAM_SOURCES.md](UPSTREAM_SOURCES.md). Upstream install scripts, servers, agents, promotional instructions and credentials are not incorporated.

See [RELEASE-EVIDENCE.md](RELEASE-EVIDENCE.md) for the exact checks completed and the remaining review steps, [SUPPORT.md](SUPPORT.md) for help, [TERMS.md](TERMS.md) for use conditions and [LICENSE](LICENSE) for the MIT license. Backend data and third-party websites retain their own terms and rights.
