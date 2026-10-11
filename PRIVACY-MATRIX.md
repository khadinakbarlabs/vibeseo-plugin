# Field-level data handling

Revision: 2026-10-11. This matrix describes intended workflow handling, not an assertion that an external provider deletes data on a fixed schedule. Use only the inputs required for the chosen task.

| Data | Purpose | Handling and destination | Retention and control |
| --- | --- | --- | --- |
| Public domains and HTTP(S) URLs | Select the site, competitor or page to research | Local context; approved selected inputs may go through the official CLI to Apify, the chosen Actor and its relevant website/provider | Local files remain until removed; cloud retention follows the calling account and provider |
| Keywords, country, language, device and search depth | Define comparable search research | Only approved relevant fields go to the selected Apify Actor and its search-data provider | Same local/cloud controls; report the observation window and market |
| Build, result/time/memory bounds and cost cap | Bound and reconcile a proposed operation | Local plan and approved Apify run parameters | Keep a minimal receipt; a saved plan or budget is not fresh authority |
| Run IDs, dataset IDs, output status and reported charges | Retrieve and verify the exact operation | User's Apify account and local evidence records | Keep private run pointers local; do not include them in shared reports unless authorized |
| Search metrics, SERP rows, audit findings and link prospects | Produce an evidence-based SEO deliverable | Returned from the specific Apify run or supplied export to the assistant and chosen local folder | User-controlled local reports and platform-governed cloud records; missing values stay unknown |
| Public names and business contact details | Qualify a relevant editorial contact when actually observed | Minimize to the task; may appear in page results and local prospect records; no automated contact | Remove unnecessary identifiers; no customer-list enrichment or hidden contact upload |
| User-supplied drafts and authorized CSV/JSON exports | Work offline and edit content | Assistant context and the chosen local folder; not automatically uploaded to an Actor | Follow the selected model host's handling and user's local file choices |
| Project goal, audience, decisions and action queue | Resume the chosen project | Visible local project folder; no publisher synchronization | User can edit/remove records; reconcile with the current request |
| Apify authentication and optional provider secrets | Authenticate independently approved operations | Entered by the user through official CLI/provider/Apify controls; never opened or copied by the plugin | Governed by those services; never put secrets in chat, examples, reports or issue trackers |

There is no publisher-hosted VibeSEO plugin service, credential collector or package telemetry. That does not make an Actor run local-only: Apify and authorized Actor operators may have access to run inputs, logs and outputs under platform permissions. Account-wide billing, retention, credentials and permissions are not modified by the plugin.

The privacy disclosures are “Reads and stores”, external transfers described in the README, and retention potentially longer than 30 days. Local reports have no automatic deletion period; no fixed cloud deletion date is promised. Before a live operation, inspect the selected Actor's current README/schema and disclose its applicable providers. DataForSEO is one possible provider, not a universal destination for every Actor.

Applicable service policies: [Apify privacy](https://docs.apify.com/legal/privacy-policy), [DataForSEO privacy](https://dataforseo.com/privacy-policy) when that provider is used, and the selected model host's policies. See [PRIVACY.md](PRIVACY.md) for the complete package disclosure and [README.md](README.md) for execution and cost boundaries.
