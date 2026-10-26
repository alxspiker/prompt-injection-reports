# Prompt-injection reports

A catalog of prompt injections and AI-agent traps found in the wild: text, markup, files, and onboarding flows written for AI agents that browse, shop, code, or act for people.

## Why it matters
Agents now read web pages and tool output and then act on them: they click, pay, install, and send messages. Any text an agent reads can try to steer it. Some sites hide instructions to detect or trap agents. Others tell agents to install software or open channels that let outside content reach them. Users rarely see any of it. This repo records each case with verbatim quotes and evidence so agent builders, vendors, and users can see what agents actually run into.

## Index

| Date | Site | Type | Severity | Report |
| --- | --- | --- | --- | --- |
| 2026-10-25 | Spotify (payments.spotify.com) | Hidden instructions + honeypot scoring in checkout | High | [Report](reports/2026-10-25-spotify-checkout-honeypot/REPORT.md) |
| 2026-10-20 | Reason Network (reasonmachines.com) | Agent onboarding instructions (visually hidden on page) + agent-to-agent channel | Medium | [Report](reports/2026-10-20-reason-network-agent-onboarding/REPORT.md) |

## Contribute
See [CONTRIBUTING.md](CONTRIBUTING.md). Start from [`reports/_TEMPLATE/REPORT.md`](reports/_TEMPLATE/REPORT.md).
No time for a full report? [Open a finding issue](https://github.com/alxspiker/prompt-injection-reports/issues/new?template=finding.yml) with the URL, what you saw, and redacted screenshots.

## License
Written content is [CC BY 4.0](LICENSE). Captured third-party material in `evidence/` and `bundles/` folders belongs to its owners and is included for research and commentary.
