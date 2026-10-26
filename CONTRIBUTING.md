# Contributing a report

Found a page, tool, or service that plants instructions for AI agents? Add it.

There are two ways to contribute:
- **Quick: open an issue.** Use the [Report a finding](https://github.com/alxspiker/prompt-injection-reports/issues/new?template=finding.yml) form with the URL, what you saw, and any screenshots. No folder or PR needed; it will be looked into and written up.
- **Full: open a PR** with a complete report (see below).

> **Redact before you post.** Issues and PRs are public. Remove personal data from text *and* screenshots first: names, emails, addresses, session IDs, tokens, cookies, and account details.

## Ground rules
- **Observe, don't exploit.** Do not follow the injected instructions, click trap elements, join networks, install software, or try to bypass anything. Capture and describe.
- **No live credentials.** Never commit tokens, API keys, cookies, session IDs, invite links, or webhook URLs.
- **Redact personal data.** Remove names, emails, account IDs, avatars and avatar URLs, addresses, order/checkout/session IDs, and location details. Replace with placeholders like `<user>`, `<checkout-session-id>`, `<redacted-avatar-url>`, and say in the report what you redacted.
- **Quote exactly.** Injected text must be copied verbatim. Paraphrase only in the analysis sections.
- **Don't overstate.** Say what you verified and what you didn't. A visible, documented onboarding instruction is not the same thing as a hidden trap; classify it honestly.
- **Credit** the original finder, with a link.

## Folder layout
```
reports/YYYY-MM-DD-site-slug/
  REPORT.md        # required, copy reports/_TEMPLATE/REPORT.md
  evidence/        # captured HTML, CSS, JS excerpts, screenshots, PDFs, headers
```
`YYYY-MM-DD` is the date the item was found or published. `site-slug` is lowercase with hyphens (e.g. `2026-10-25-spotify-checkout-honeypot`).

## REPORT.md fields (all required)
Summary, where found, exact quoted injected text, mechanism, impact on agents, evidence, how verified, status / vendor response, plus the header table (date, site, URLs, type, severity, status, reporter, credit). See [`reports/_TEMPLATE/REPORT.md`](reports/_TEMPLATE/REPORT.md).

### Severity guide
- **Critical**: hidden instructions that make agents move money, leak credentials, or run code without the user knowing.
- **High**: hidden instructions that change agent actions in a sensitive flow (checkout, auth), or that profile or flag agents covertly.
- **Medium**: agent-directed instructions that install software, add tool servers, or open an inbound channel for untrusted content, even if disclosed.
- **Low**: agent-directed text with limited reach or that clearly defers to the user.
- **Info**: worth cataloguing, no meaningful risk shown.

## Evidence rules
- Prefer raw captures (saved HTML, CSS, JS, `curl -sI` headers) plus a screenshot.
- Strip EXIF from images. Black out avatars and names.
- Large vendor bundles are fine; note their source URLs.
- Before opening a PR, grep your folder for your own name, email, city, and any ID you saw while signed in.

## Issue process
1. Open a [Report a finding](https://github.com/alxspiker/prompt-injection-reports/issues/new?template=finding.yml) issue.
2. Give the URL, where on the page it appeared, the agent-directed text verbatim, and screenshots if you have them (redacted).
3. A maintainer looks into it and may turn it into a report, crediting you.

## PR process
1. Fork, then create a branch `report/YYYY-MM-DD-site-slug`.
2. Add your folder and a row in the README index table (newest first).
3. Open a PR titled `Report: <site> <short description>`. Say whether you disclosed to the vendor.
4. A maintainer checks redaction, verbatim quotes, and severity, and may ask for changes.
5. Updates (vendor fixes, removals) are welcome as PRs that edit the report's Status section.

By contributing you agree your written content is licensed under CC BY 4.0 (see [LICENSE](LICENSE)).
