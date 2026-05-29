# Documentation project instructions

> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

## About this project

- This is the Mintlify-powered documentation site for **Glitch Executor**, the AI trading
  automation platform at <https://glitchexecutor.com>.
- Pages are MDX files with YAML frontmatter.
- Configuration lives in `docs.json`. Brand color is `#00d177` (emerald, matches the
  Cyber Cobra mascot). Don't drift the color without updating the SPA + marketing site
  at the same time.
- Run `mint dev` to preview locally; `mint broken-links` to validate references.
- Deploys via Mintlify's git integration on every push to `main`.

## Companion repos

| Repo | What | Touch from here? |
|---|---|---|
| `glitch-trade-api` | FastAPI backend | No — only consume the OpenAPI URL when API reference lands |
| `glitch-trade-app` | React SPA at `glitchexecutor.com` | No |
| `glitch-trade-core` | Backtest engine, Strategy IR, firm rule sets | No — but doc PRs may need to be paired with code PRs there |
| `glitch-trade-docs` | **This repo** | Yes |

Future: API reference will be auto-generated from `glitch-trade-api`'s OpenAPI spec
once it ships a public `openapi.json`. Add a `tabs.openapi` entry in `docs.json`
mirroring `glitch-edge-docs`'s setup.

## Terminology (use these spellings)

- **Strategy** — the user-authored rule document. Not "bot", not "model".
- **Quick rule** — the natural-language one-liner authored at `/app/quick`. Always two
  words.
- **Firm Mode** — capitalized as a feature name. Not "firm mode".
- **Backtest** — one word. Not "back-test" or "back test".
- **Walk-forward** — hyphenated. Not "walk forward" (the noun).
- **Track** — when referring to the dashboard, capitalize. Otherwise lowercase verb.
- **cBot** — lowercase 'c', uppercase 'B'. cTrader's own spelling.
- **MetaApi** — capital A. Not "Metaapi" or "Meta API".
- **MetaTrader 4** / **MetaTrader 5** — full words on first mention; **MT4** / **MT5**
  thereafter is fine.
- **Investor password** — when contrasting with master password on MT accounts.
- **Trailing DD** / **static DD** — the two drawdown styles. Always identify which a
  firm uses on first mention in any doc.
- **Prop firm** — two words. Not "propfirm".

## Brokers (canonical list — don't add others without a code change)

- **cTrader** — OAuth, read-only, 🔐 OAuth badge
- **TradeLocker** — credentialed, 🔑 Creds badge
- **DXtrade** — credentialed, 🔑 Creds badge (live integration in progress)
- **MT4 / MT5 via MetaApi** — cloud-bridged, 🌉 Cloud badge

## Firms (canonical list — keep in sync with `glitch-trade-core/backtest/rules/`)

- FundingPips Zero
- FTMO Phase 1
- MyForexFunds
- Apex
- The5ers High Stakes
- GetLeveraged Turbo

## Don't promise

- No performance numbers, "X% returns", "guaranteed pass" language
- No "AI picks" / signal-vendor framing
- No "we trade for you" / managed-account framing — Glitch Executor is **tooling**

## Style

- Cards on landing/concept pages, plain prose on reference pages
- Steps for any flow ≥ 3 actions
- Warning callouts for honesty notes (e.g. "this rule has no stop-loss")
- Tip callouts for non-obvious shortcuts
- Tables for firm comparisons + tier comparisons
