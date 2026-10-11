# Release evidence — VibeSEO 0.1.0

Evidence date: 2026-10-11. This file distinguishes package checks, backend observations, host behavior, and directory state.

## Completed package checks

- Authoritative `claude plugin validate --strict`: passed with no warnings.
- Portable Agent Plugins 1.0 schema: passed.
- Anthropic display name 42 characters; description 419 characters. Private Plugin Creator display name 22 characters; subtitle 29 characters. Identity/version are synchronized across manifests.
- Seven skill names/frontmatter and local reference paths: checked.
- Eight illustrative Actor inputs: validated against the live schemas read on 2026-10-11, including types/enums, known keys and omission of secret fields.
- Credential-pattern, file-size, case-collision and runtime-component checks: passed before packaging. Final archive checks are recorded below when completed.

## Backend observations

The eight selected Actors were public with succeeded tagged builds at readback. Their live schemas and public metadata were retrieved through ordinary CLI access. Output field types, summary/output presence and outcome categories were read from existing runs on those builds; raw rows, run inputs, credentials and private customer data were not stored in the package. This is contract discovery, not new billable canary execution or release-level reliability proof.

Existing readback returned substantive nonempty shapes and `COMPLETE` for keyword research, volume, SERP, opportunity finder, broken links and audit. Domain keyword research yielded a `VALID_EMPTY` marker-only row and remains optional/unqualified for substantive competitor data. The sampled rank result was `VALID_EMPTY` with a no-match row. The skills preserve these distinctions.

No new billable Actor run was started. Current Apify documentation describes `maxTotalChargeUsd` as total Apify run-cost control across pricing models; separate provider costs, aggregate operations and later data reads still require appropriate bounds.

## Host behavior checks

Seven authored native evaluation cases cover evidence missingness, content originality, link-state integrity, upstream failure, prompt injection, rank comparability and spend consent. The native runner resolved VibeSEO 0.1.0 and parsed the first case, but stopped immediately on expired Claude OAuth authentication (`auth_failed`); cost was $0 and no meaningful workflow evaluation completed. The user was asked to refresh their local Claude Code login. Cases and routing graders were structurally checked for all seven scenarios; they are not passed behavior tests. Live CLI research is targeted to Claude Code. Cowork and browser-chat live execution are not validated.

## Release and directory states

- Local source package: authored and manifest/input validated.
- Final archive inspection: pending.
- Plugin Creator private save: pending.
- GitHub source upload: saved privately at `khadinakbarlabs/vibeseo-plugin`; public source release awaits owner approval.
- Anthropic portal validation: pending.
- Owner approval of final metadata/public release/submission: pending, explicitly requested by the owner.
- Submitted for Anthropic review: no.
- Anthropic reviewer approval: no.
- Live directory publication: no.

Directory checks, security scan, authorized publisher attestations and reviewer decisions remain separate from these local checks. A package cannot guarantee directory approval.
