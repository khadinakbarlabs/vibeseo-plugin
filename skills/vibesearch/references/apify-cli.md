# Official Apify CLI: preflight, start, status, collect

This package doesn't contain or install a CLI runtime automatically. The supported external dependency is `apify-cli@1.10.0` from the public npm registry. Check `apify --version` and `apify api --help` before using these examples. If absent, give the user the pinned install step in the README and let the normal host permission flow apply. The user completes `apify login` interactively. Never open auth/config files or print a token. Do not read an environment credential and send it to a destination.

Commands below are explicit examples, not instructions to execute without the task's approval. Fixed Actor IDs are from live owned public metadata read on 2026-10-11. Current documentation: [CLI reference](https://docs.apify.com/cli/docs/reference), [run API](https://docs.apify.com/api/v2/actors-runs-post).

## 1. Read current contract and prepare

Use the existing CLI for read-only checks:

```bash
apify actors info khadinakbar/dataforseo-keyword-research --input
apify api GET /v2/acts/8RW7Ow9S3hRAnX1ye
```

Read schema, `isPublic`, tagged build, defaults and currently effective pricing including access/tier/provider requirements. Check pricing's effective dates; do not assume the first or last pricing record applies. Read the Actor README when provider coverage or credentials are unclear. See [actor-contracts.md](actor-contracts.md) and [actors-live.json](actors-live.json). Snapshots aid input planning and are not permanent live authority.

Copy an appropriate static input from [inputs](inputs/) into the chosen project folder. Replace the illustrative domain/keywords with the approved scope using a file editor. Validate types, enum values, required fields and conditional constraints against the fresh schema. Don't invent a shared input shape: `seedKeywords`, `keywords`, `queries`, `siteUrl` and `targetDomain` differ. `locationCode: 2840` is a US example; some Actors use `countryCode`, others `countryName`. Obtain the target market and resolve an actual supported code, not a guessed number.

Keep secrets out of ordinary input files and run receipts. If a mode requires provider credentials, explain the dependency and let the user enter them through secure official controls; don't retrieve the secrets into chat. Pause that mode if no supported secure path exists.

Before start, show the exact scope and ask for approval. Pick the smallest inputs, finite timeout, appropriate memory and a per-run `maxTotalChargeUsd`. Check that any Actor minimum charge fits the approved ceiling. The current API describes that limit as total Apify run cost across pricing models; it does not cap separately billed provider accounts, several runs in aggregate, or all later data retrieval. Track those separately. The sample below uses a $1 cap purely to illustrate syntax; it is not approval or an assertion that the actual job costs $1.

## 2. Start once, with bounded options

After the actual operation has been approved, use a supported exact build number obtained during preflight, then the asynchronous start endpoint. This build number is a dated example and must be checked against the selected Actor's intended current build:

```bash
apify api POST /v2/acts/8RW7Ow9S3hRAnX1ye/runs \
  --params '{"build":"1.0.13","timeout":180,"memory":256,"maxTotalChargeUsd":1,"restartOnError":false,"waitForFinish":0}' \
  --body - < input.json > run-receipt.json
```

No token, shell expansion or command substitution appears in this command. Use `--body -` with a validated file on stdin. Never concatenate a raw domain, keyword or snippet into shell syntax. Normal CLI authentication supplies account access to Apify. Keep output private locally; `data.id`, `data.buildId`, `data.defaultDatasetId` and `data.defaultKeyValueStoreId` belong to this operation.

If the client loses the start response, the run may still exist. Inspect the calling account's recent runs for the exact Actor/time/input scope before considering another start. Do not duplicate a charge on an uncertain outcome. No automatic retries, resurrects or restarts are authorized.

## 3. Resume by the exact run ID

```bash
apify api GET /v2/actor-runs/RUN_ID
```

Replace `RUN_ID` only with a validated alphanumeric ID returned for this operation; don't execute literal placeholders. Poll a bounded number of times with increasing intervals and communicate progress. A still-running job is pending, not failed. Record the ID and resume later rather than waiting indefinitely or starting a second run. Abort only the run whose ID and ownership were verified, and only within the user's approved stop/budget rule:

```bash
apify api POST /v2/actor-runs/RUN_ID/abort
```

## 4. Collect from the same terminal run

Take IDs from that exact run. For one bounded page:

```bash
apify api GET /v2/datasets/DATASET_ID/items \
  --params '{"offset":0,"limit":100,"clean":true}' > results-page-000.json
apify api GET /v2/key-value-stores/STORE_ID/records/RUN_SUMMARY > run-summary.json
apify api GET /v2/key-value-stores/STORE_ID/records/OUTPUT > output.json
apify api GET /v2/actor-runs/RUN_ID > final-run.json
```

Read `total`/dataset item count where available and increment offset until the requested bounded scope is complete. Preserve each page. Never overwrite one page with the next, silently truncate, or fetch an unrelated “latest” dataset. Large collection changes scope/cost and needs review. Optional CSV export is made from authorized collected rows with formula-safe escaping.

Check terminal status, `RUN_SUMMARY.outcome`, `OUTPUT`, real useful rows and error/no-data markers. Exclude sentinel `_note`/`_status` records from keyword counts. SERP rows can contain nested `organic_results`; one dataset row need not mean one result. Audit data contains a nested page sample. Rank data can validly contain `found: false` and null target ranks. Use the actual row shape, not fabricated normalized fields.

Record build IDs/numbers, requested/returned coverage, summary outcome and effective `pricingInfo`, `chargedEventCounts`, `usageTotalUsd`, pricing/usage payer fields and any reported provider cost. Do not blindly add values that are already included in a reported total, or assume a provider cost is a second user charge. Where charge reconciliation isn't established, label it incomplete. Re-read final metadata after a short bounded delay for late usage changes; show the observation time. Keep scope and receipts in the local evidence ledger.

`COMPLETE` requires meaningful expected rows and coverage; `PARTIAL` retains useful rows plus gaps; `VALID_EMPTY` requires a valid completed query with no substantive results. `UPSTREAM_FAILED`, `CONFIG_ERROR`, unexpected marker-only data or failed status can't support live findings. A partial/empty/failed result never authorizes an extra paid run.
