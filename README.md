# glitch-trade-docs

Mintlify-powered documentation site for **Glitch Trade**, the AI trading automation platform at <https://trade.glitchexecutor.com>.

Lives at <https://docs.trade.glitchexecutor.com> (configure custom domain in the Mintlify dashboard once the space is live; the default `trade.mintlify.app` works in the meantime).

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

- **`glitch-trade-app`** — the React SPA at <https://trade.glitchexecutor.com>
- **`glitch-trade-api`** — FastAPI backend
- **`glitch-trade-core`** — backtest engine, IR layer, IR→C# compiler, firm rule sets

Marketing copy belongs on the unified app's marketing routes, **not** here. Docs are reference material; marketing is persuasion.
