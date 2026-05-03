# Project context for Claude Code

You are working on **tw-stocks-daily-report** — the **public data repository**
for the DappGo TW Stocks mobile app. Sibling to `options-daily-report`.

## What this repo is

A read-mostly archive of **generated artifacts**:
- `reports/YYYY-MM-DD.md` — daily TW stock analysis reports
- `dashboard/data.json` — aggregate payload consumed by the mobile app
- `dashboard/index.html` — static web viewer (GitHub Pages)

## What this repo is NOT

- **Not** a place for Python source code. The engine lives in a separate
  private repo (`tw-stocks-core`).
- **Not** for contributors modifying reports. They're auto-generated.

## Before committing

- **Never** add `.py` files — guarded by CI workflow
- **Never** modify files in `reports/` or `dashboard/data.json` by hand —
  next pipeline run overwrites them

## Language

User's primary language is 繁體中文. Respond in 繁體中文 unless the user
writes in English. Code / docs in English.


## DappGo Stocks family

This repo is part of the **DappGo Stocks** family. The coordination repo
[`dappgo-stocks-meta`](https://github.com/YanlongLai/dappgo-stocks-meta)
holds:

- [STACK.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/STACK.md) — TLDR of all 12 repos at a glance
- [CLAUDE.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/CLAUDE.md) — entry point for fresh Claude Code sessions
- [docs/ARCHITECTURE.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/ARCHITECTURE.md) — full data flow diagram
- [docs/CONVENTIONS.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/CONVENTIONS.md) — TS / Python / commit / a11y standards
- [docs/UI_DESIGN_SYSTEM.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/UI_DESIGN_SYSTEM.md) — design tokens + sync rules
- [docs/LAYOUT_PATTERNS.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/LAYOUT_PATTERNS.md) — standard screen patterns (loading/error/empty/refresh)
- [docs/WORKFLOW.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/WORKFLOW.md) — multi-repo task recipes
- [docs/INTEGRATION_STRATEGY.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/INTEGRATION_STRATEGY.md) — 5-rung migration ladder for shared code
- [docs/RELEASE.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/RELEASE.md) — release runbook
- [docs/ONBOARDING.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/ONBOARDING.md) — new dev box setup
- [docs/DEPENDENCY_FLOW.md](https://github.com/YanlongLai/dappgo-stocks-meta/blob/main/docs/DEPENDENCY_FLOW.md) — "when changing X, what else needs updating"

Cross-repo scripts at `~/git/dappgo-stocks-meta/scripts/` (status-all,
pull-all, verify-apps, deploy-mobile, run-engines, sync-shared, sync-ui,
drift-check, clone-all).
