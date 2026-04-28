# Agent instructions for the Binibit docs repository

This file briefs AI coding agents (Claude Code, Cursor, Copilot, etc.) working in this repository.

## About the project

- Source for [docs.binibit.com](https://docs.binibit.com)
- Built on [Mintlify](https://mintlify.com) — pages are MDX with YAML frontmatter
- Configuration in `docs.json` (theme, colors, navigation, footer)
- Run `mint dev` to preview locally; `mint broken-links` to validate

## Project scope

Documents the **Binibit Spot Market API** — the public REST surface for market data of the Binibit centralized spot exchange.

Endpoints documented:

- `GET /tickers`
- `GET /orderbook`
- `GET /historical_trades`
- `GET /asset`

Production API base: `https://internal-api.binibit.com/api/marketdata/getcoingecko`.

The schema happens to align with CoinGecko Integration API Standards v8 so aggregators can ingest without translation, but framing in user-facing docs should be **brand-agnostic**: "Binibit Spot Market API", not "Binibit's CoinGecko endpoint". Mention CG compatibility once, in a "Standards" section, not as the primary pitch.

Out of scope: account / KYC / trading / WebSocket APIs. v2 will introduce those — not yet.

## Terminology

- **Pair** / **market** / **ticker** — the same thing in this exchange context. Prefer "pair" in user-facing copy and "ticker" only when referring to the literal `ticker_id` field.
- **Base** / **target** — match the CoinGecko spec. `target_currency` is the **quote** asset; do not introduce the word "quote" in docs to avoid confusion with the older CoinMarketCap convention.
- **`ticker_id`** — uppercase symbols joined by `_`, e.g. `BTC_USDT`. Always backtick.

## Style preferences

- Active voice, second person ("you")
- Sentence case headings
- One idea per sentence
- Backticks for code, paths, field names, HTTP methods
- Live, copy-paste-runnable examples (not pseudocode)
- No filler words: drop "simply", "just", "basically", "in order to"
- Use Mintlify components (`<Card>`, `<CodeGroup>`, `<ParamField>`, `<ResponseField>`, `<Note>`, `<Warning>`, `<Accordion>`) when they improve scanability
- Numeric values in examples should be **real values** taken from the live API, not invented

## Content boundaries

Do not document:

- Internal admin or operations endpoints
- Trading / withdrawal / KYC flows
- Anything behind authentication (until v2)
- Roadmap items beyond what's already on the [Changelog](/changelog) page

## Common tasks

- **Add a new endpoint:** create `api-reference/<name>.mdx`, register in `docs.json` under `Market Data`, link from `api-reference/introduction.mdx` and `index.mdx` if relevant
- **Fix a field rename:** update `api-reference/*.mdx`, `general/response-format.mdx`, and any code samples
- **Bump CG spec version:** update `changelog.mdx` and `introduction.mdx`

## Before opening a PR

1. `mint broken-links` passes
2. All curl examples actually work against production
3. Mobile rendering checked
4. Link to the relevant CoinGecko spec section in PR description if changing schema docs
