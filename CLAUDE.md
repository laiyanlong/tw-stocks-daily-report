# tw-stocks-daily-report

> **Part of the [DappGo Stocks family](https://github.com/YanlongLai/dappgo-stocks-meta) (14 sibling repos).**
> If you've never worked on this family before, read `~/git/dappgo-stocks-meta/CLAUDE.md` first — it's the canonical entry point.

## Family quick links
- Repo map: `~/git/dappgo-stocks-meta/docs/REPO_MAP.md` — what each repo does
- Dependency flow: `~/git/dappgo-stocks-meta/docs/DEPENDENCY_FLOW.md` — when changing X, also touch Y
- Architecture: `~/git/dappgo-stocks-meta/docs/ARCHITECTURE.md` — data flow + diagrams
- Conventions: `~/git/dappgo-stocks-meta/docs/CONVENTIONS.md` — TS / Python / commit standards

## This repo's role
**Tier 2** | **Data-only / machine-emitted** | Public archive of generated artifacts for the DappGo TW Stocks mobile app.

- **Inputs**: nightly engine push from `~/git/tw-stocks-core` (Tier 1 Python engine).
- **Outputs**: jsDelivr CDN consumption by `~/git/dappgo-tw-stocks-app` (Tier 3) and `~/git/dappgo-stocks-mcp` (Tier 4).
- **When to touch**: **NEVER manually**. Reports and `dashboard/data.json` are emitted by the engine. If you find yourself wanting to edit content here, you almost certainly want `~/git/tw-stocks-core` instead.

## Sibling repos commonly edited together
- `~/git/tw-stocks-core` — the engine producing the data in this repo.
- `~/git/dappgo-tw-stocks-app` — the consumer mobile app.

## What this repo is

A read-mostly archive of **generated artifacts**:
- `reports/YYYY-MM-DD.md` — daily TW stock analysis reports
- `dashboard/data.json` — aggregate payload consumed by the mobile app
- `dashboard/index.html` — static web viewer (GitHub Pages)

## What this repo is NOT

- **Not** a place for Python source code. The engine lives in `~/git/tw-stocks-core`.
- **Not** for contributors modifying reports. They're auto-generated.

## Before committing

- **Never** add `.py` files — guarded by CI workflow
- **Never** modify files in `reports/` or `dashboard/data.json` by hand —
  next pipeline run overwrites them

## Language

User's primary language is 繁體中文. Respond in 繁體中文 unless the user
writes in English. Code / docs in English.
