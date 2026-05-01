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
