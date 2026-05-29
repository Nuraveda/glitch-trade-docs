# glitch-trade-docs

Mintlify-powered documentation site for **Glitch Executor**, the AI trading automation platform at <https://glitchexecutor.com>.

Lives at <https://glitchexecutor.com/docs> — same-origin under the Trade app, served via a Cloudflare Pages Function (`functions/docs/[[path]].ts` in `glitch-trade-app`) that proxies to the Mintlify origin `glitchexecutorlab.mintlify.dev`. Same-origin keeps analytics, cookies, and CSP trivial.

## Local preview

```bash
npm install -g mintlify
mintlify dev
# opens on http://localhost:3000
```

## Add a doc

1. Drop a `.mdx` file in the right section folder (`getting-started/`, `concepts/`, `brokers/`, `plans/`)
2. Add the path to `docs.json` under the right `group.pages` array
3. Push to `main` — Mintlify rebuilds within ~60 seconds

## Conventions

See [`AGENTS.md`](AGENTS.md) for terminology, MDX/component preferences, and which sibling repos are off-limits.

## Companion repos

- **`glitch-trade-app`** — the React SPA at <https://glitchexecutor.com>
- **`glitch-trade-api`** — FastAPI backend
- **`glitch-trade-core`** — backtest engine, IR layer, IR→C# compiler, firm rule sets

Marketing copy belongs on the unified app's marketing routes, **not** here. Docs are reference material; marketing is persuasion.
