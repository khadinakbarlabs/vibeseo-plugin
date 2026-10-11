# Privacy and data handling

Effective draft: 2026-10-11. Publisher: Khadin Akbar. Applies to the VibeSEO skills package, not an independently operated SaaS service.

VibeSEO bundles instructions and static supporting files. It does not operate a publisher-hosted service, collect credentials, or add telemetry. The assistant uses task context already provided in the conversation, authorized exports, and a visible project folder the user selects.

## Information used

Research can include public site URLs, domains, keywords, competitors, geographic/language settings, content drafts, search metrics and project decisions. Public web pages may incidentally contain names or public business contact details. The plugin does not need customer lists, account passwords, cookies, payment details or sensitive personal data; do not include those in research inputs. Outreach research defaults to public business information and user-provided authorized contacts, with minimization and source recording.

## External transfers

After the user approves the input scope and budget, the official Apify CLI submits those research inputs to `api.apify.com` using the user's ordinary CLI authentication. The selected Actors may query search engines, websites and upstream data providers such as DataForSEO. Their implementation, mode and current access determine the precise providers. Before a run, the assistant links the Actor, checks its current README/schema and explains the applicable destinations. No credential file is opened or copied by the plugin. Optional provider-secret entry is completed by the user in the provider/Apify interface rather than chat.

The publisher controls the listed Actor source but does not receive a separate copy of your local project folder. Running an Actor uses Apify's platform; Actor operators and Apify may have access to run inputs, logs and stored outputs under their platform permissions. Therefore approved cloud inputs and outputs should not be treated as private local-only data. Review [Apify privacy](https://apify.com/privacy-policy) and [Apify terms](https://apify.com/terms-of-use) before sending data. The assistant/model host has its own handling of conversations, files and tool responses. The independent CLI may have its own optional anonymous telemetry behavior.

## Storage and retention

Local reports, context and action records stay in the chosen local folder until the user edits or removes them. The package imposes no automatic deletion period and does not synchronize the folder. Cloud runs, datasets and key-value records remain subject to the calling Apify account's retention settings, plan and provider policies. No specific cloud deletion period is promised. Remove cloud data through Apify when needed; removal, sharing changes and recurring collection are not automatic plugin actions.

## Choices and support

Use supplied exports for offline work, decline any proposed transfer/run, omit unnecessary identifiers, or choose a separate local project folder. No outreach, publication, paid placement or report sharing occurs without the user's specific instruction. To report a privacy problem, follow [SUPPORT.md](SUPPORT.md); send a redacted description and no API keys, raw customer records, or private run links in public issues.
