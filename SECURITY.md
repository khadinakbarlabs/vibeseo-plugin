# Security reporting

## Supported release

Security fixes target the latest 0.1.x VibeSearch package. Update to the latest reviewed version before reproducing a package problem. Apify, the independent CLI, model hosts and upstream data providers maintain their own security policies.

## Report a concern

If GitHub's private vulnerability-reporting option is available on [the repository's Security page](https://github.com/khadinakbarlabs/vibeseo-plugin/security), use it for a confidential package report. Its availability is not promised by this package.

Otherwise, open a [GitHub issue](https://github.com/khadinakbarlabs/vibeseo-plugin/issues) titled “Security report: request private contact”. Include only the affected package version and a general problem category. Request a private follow-up before sharing exploit details or a reproduction containing sensitive information. Never post tokens, credential files, private run links, customer records or raw logs publicly. This is a contact route, not a promise of a response time.

For an Apify account or platform concern, use [Apify support](https://apify.com/contact). Identify the public Actor name where relevant; share private account details only through the service's authorized private support channel.

## Package boundaries

The package contains skills and static supporting resources. It does not install executable code, collect credentials or send telemetry. The assistant can invoke the independently installed official Apify CLI only within the user's authorized scope; approved cloud inputs are subject to Apify and Actor-operator access. Read [PRIVACY.md](PRIVACY.md) and [PRIVACY-MATRIX.md](PRIVACY-MATRIX.md) for those boundaries.

Prompt-injection content, invalid/private-network targets, spreadsheet formula payloads, unintended paid operations and false claims of publishing or acquired backlinks are relevant package security concerns. Report a minimal synthetic example rather than real user data. The workflow's written controls do not replace the host's tool permissions or sandbox.
