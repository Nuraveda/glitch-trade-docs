# Glitch Executor — Docs

> **Proprietary.** All rights reserved. Part of the Glitch Executor platform.

**The public product documentation for Glitch Executor** — the all-in-one cockpit for traders
("ChatGPT for traders" plus live trading & challenge monitoring). Getting-started guides, broker
connection walkthroughs, trading concepts, and plan/pricing pages, authored in **MDX** and
published with **Mintlify**.

**One of Glitch Executor's three production repos:**
[`glitch-trade-app`](https://github.com/Nuraveda-Labs/glitch-trade-app) (web SPA + trade-api +
mobile) · [`glitchexecutor-sso`](https://github.com/Nuraveda-Labs/glitchexecutor-sso) (auth) ·
**`glitch-trade-docs`** (this repo — public docs).

---

## Where it lives

Served at **<https://glitchexecutor.com/docs>** — same-origin under the Trade app, via a
Cloudflare Pages Function (`functions/docs/[[path]].ts` in `glitch-trade-app`) that proxies to the
Mintlify origin `glitchexecutorlab.mintlify.dev`. Same-origin keeps analytics, cookies, and CSP trivial.

## Local preview

```bash
npm install -g mintlify
mintlify dev
# opens on http://localhost:3000
```

## Add or edit a doc

1. Drop/edit an `.mdx` file in the right section folder (`getting-started/`, `concepts/`, `brokers/`, `plans/`).
2. Add its path to `docs.json` under the right `group.pages` array.
3. Push to `main` — **Mintlify rebuilds within ~60 seconds**.

## Conventions

See [`AGENTS.md`](AGENTS.md) for terminology, MDX/component preferences, and which sibling repos are
off-limits. **Reference material only** — marketing copy belongs on the app's marketing routes, not here.

## Git model

- **GitHub (`Nuraveda-Labs/glitch-trade-docs`) is the single point of push** — Mintlify builds from
  it on every push to `main`.
- **GitLab (`nuraveda-lab/glitch-trade-docs`) is a mirror copy** of the code.

> The `glitch-trade-api` and `glitch-trade-core` "companion repos" referenced in older docs no longer
> exist standalone — the API and the backtest/IR engine were both folded into `glitch-trade-app`.
