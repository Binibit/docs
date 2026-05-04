# Contributing

Thank you for helping improve the Binibit API documentation. This repository is the source for [docs.binibit.com](https://docs.binibit.com).

## Quick fixes

For typos, broken links, unclear wording, or small clarifications:

1. Click **Edit this page** at the bottom of any page on [docs.binibit.com](https://docs.binibit.com), or open the file directly on GitHub.
2. Make the change and submit a pull request.
3. A Mintlify preview URL will be generated automatically on the PR.

## Larger changes

For new pages, restructured navigation, or substantial rewrites:

1. Open an [issue](https://github.com/Binibit/docs/issues) first to discuss scope and approach.
2. Fork and clone the repository.
3. Create a feature branch: `git checkout -b docs/your-change`.
4. Install the Mintlify CLI and preview locally:

   ```bash
   npm i -g mint
   mint dev
   ```

   Preview at http://localhost:3000.
5. Validate links before pushing:

   ```bash
   mint broken-links
   ```
6. Commit, push, and open a pull request against `main`.

## Style

- **Active voice and second person.** Write "Send a `GET` request..." not "A `GET` request should be sent...".
- **Concise sentences.** One idea per sentence.
- **Sentence case headings.** "Rate limits" not "Rate Limits".
- **Backticks for code, paths, and field names.** `ticker_id`, `/tickers`, `docs.json`.
- **Live examples.** Code samples must be runnable against the production API.
- **No filler.** Drop "simply", "just", "basically", "in order to".

## Scope

This repository documents the **public market data API**. Out of scope:

- Account / KYC / fiat onboarding flows — see [binibit.com/help](https://binibit.com/?i=7r2c8t).
- Trading API (HMAC, WebSocket) — planned for v2, not yet documented here.
- Internal dashboards or admin endpoints.

## Reporting API issues

For bugs in the API itself (wrong values, server errors, schema regressions), email [api@binibit.com](mailto:api@binibit.com). Documentation issues stay in this repository.
