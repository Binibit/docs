# Binibit API Documentation

Source for [docs.binibit.com](https://docs.binibit.com) — public market data API documentation for the Binibit centralized spot exchange.

Built with [Mintlify](https://mintlify.com).

## Contents

| Path | What |
|---|---|
| `index.mdx` | Landing page |
| `introduction.mdx` | API overview |
| `general/` | Base URL, auth, rate limits, response format, timestamps, errors |
| `api-reference/` | REST endpoint reference (`/tickers`, `/orderbook`, `/historical_trades`, `/asset`) |
| `reference/` | ticker_id format, trading pairs, supported assets |
| `verification.mdx` | Live data snapshot for aggregator verification |
| `changelog.mdx` | API version history and roadmap |
| `faq.mdx` | Frequently asked questions |
| `support.mdx` | Contact channels |
| `docs.json` | Mintlify navigation, theme, and site config |

## Local preview

Install the Mintlify CLI:

```bash
npm i -g mint
```

Run from the repo root (where `docs.json` lives):

```bash
mint dev
```

Preview at http://localhost:3000.

To validate links and broken references:

```bash
mint broken-links
```

## Deployment

Pushes to `main` are deployed automatically via the Mintlify GitHub App. Pull requests get a preview URL.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md).

For typos, broken links, or unclear wording, open an [issue](https://github.com/Binibit/docs/issues) or a PR.

## License

[MIT](./LICENSE).
