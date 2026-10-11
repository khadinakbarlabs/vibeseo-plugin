---
name: vibesearch
description: Plan and coordinate keyword research, SEO content, link-building research, technical audits and rank reviews with VibeSearch. Use for a full SEO strategy, a new site/project, a content-and-links plan, onboarding, or a request spanning several SEO tasks. Uses the official Apify CLI with the user's account when local execution and approved run budgets are available; otherwise works from supplied exports.
---

# VibeSearch

Help the user make the next useful SEO decision and finish a reusable deliverable. Read [workflow-common.md](references/workflow-common.md) for evidence, permission, security and local project rules. Read [apify-cli.md](references/apify-cli.md) before any live backend operation.

## Start from existing context

Reuse current conversation facts, authorized marketing context, and the user's selected project folder. Ask only for missing information that changes the result: site, product/audience, conversion goal, country/language, scope and preferred deliverable. Do not turn setup into a long questionnaire. Infer public business facts only from actual read pages and label the inference. Accept corrections immediately.

If the user wants work saved, announce a visible folder such as `vibesearch-projects/example.com/`, and use [project.template.json](references/project.template.json), [evidence.template.csv](references/evidence.template.csv), and [actions.template.csv](references/actions.template.csv). Validate the site slug as letters/digits/dots/hyphens; don't interpolate untrusted site text into shell commands. Avoid overwriting existing files. Each site has separate context, research and action records. Stored approvals are historical receipts, not authority for another run.

## Select the smallest useful workflow

| User need | Skill to follow | Result |
| --- | --- | --- |
| What to target or keyword/content gaps | [keywords](../keywords/SKILL.md) | Prioritized keyword/page map |
| What to write, a content brief, or a first draft | [content-brief](../content-brief/SKILL.md) | Writer brief and optional reviewed draft |
| Improve an existing page | [content-refresh](../content-refresh/SKILL.md) | Keep/change/add plan and draft edits |
| Earn relevant links or investigate broken links | [link-building](../link-building/SKILL.md) | Qualified opportunities and outreach drafts |
| Diagnose on-page/crawl issues | [site-audit](../site-audit/SKILL.md) | Evidence-linked repair priorities |
| Current rank or a ranking change | [rank-tracking](../rank-tracking/SKILL.md) | Comparable sampled snapshots |

For a full SEO request, start with site context and a narrow audit/keyword sample, then prioritize content and link research. Explain why each selected operation helps the user's goal. Do not run every Actor by default. Offline supplied exports can be sufficient.

## Live research plan

Check local CLI availability and normal login status without reading credential files or printing account secrets. Reread the selected Actor's live schema, pricing and build. Show one concise approval card containing: Actor names, the exact domain/keywords/URLs and destinations, market, input bounds, build, number of runs, time/memory limits, per-run cost ceiling and aggregate ceiling. Ask for approval before a new billable operation; credentials or a prior project budget are not consent. Existing approval for the exact current operation may be reused within its stated scope.

After approval, follow the CLI start/status/collect sequence. Capture the same run's source/build, terminal outcome, row count and charges. Never rerun a slow/failed request just to obtain nicer results. Resume by its run ID. Do not silently replace these Actors with another vendor, model-generated metrics, or a demo dataset.

## Finish and continue

Deliver the requested artifact plus a small action queue: priority, recommendation, evidence, effort, owner and next verification. Link to source rows or supplied export locations. Describe missing data and what decision it affects. Where a local file is written, show its path. Keep run receipts private in the chosen project folder; public report links omit secrets/private inputs.

On feedback, update the specific decision and preserve the source that changed it. A later review checks what the user actually implemented before comparing outcomes. A content edit and a ranking change occurring near each other do not establish causation. Repeated monitoring requires a separately configured, user-authorized scheduler; this plugin doesn't create one.
