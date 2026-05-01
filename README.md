# TW Stocks Daily Report — Data

> Auto-generated daily reports + structured JSON for the **DappGo TW Stocks** mobile app.

This repo contains only the **published outputs** of the analysis pipeline.
The engine itself is proprietary and lives in a separate private repo.

## Contents

```
reports/YYYY-MM-DD.md          每日台股策略報告 (markdown)
dashboard/data.json            App 與 dashboard 共用的結構化資料
dashboard/index.html           簡易公開瀏覽介面 (GitHub Pages)
schemas/                       JSON Schema 定義
```

## 資料來源

- 股價：FinMind API（free tier）+ TWSE 公開 API fallback
- 三大法人 / 融資融券：FinMind
- AI 解讀：Google Gemini

## 涵蓋標的

16 檔，跨 8 個產業：
- 半導體：2330 台積電、2454 聯發科、2303 聯電
- 電子代工：2317 鴻海、2382 廣達
- 光電：3008 大立光、2409 友達
- 航運：2603 長榮、2609 陽明
- 航空：2618 長榮航、2610 華航
- 金融：2882 國泰金、2891 中信金
- 鋼鐵：2002 中鋼
- ETF：0050、0056

## 排程

每個交易日（週一至週五）台北時間 14:10（台股 13:30 收盤後 40 分鐘）由 GitHub Actions 自動產生。

## CDN 取用方式

App 透過 jsDelivr 公開 CDN 取資料（避開 GitHub raw 的 cache header 限制）：

```
https://cdn.jsdelivr.net/gh/laiyanlong/tw-stocks-daily-report@main/dashboard/data.json
```

## 三 repo 協同

```
┌─ tw-stocks-core (private) ──────────┐
│  Python 引擎 — 每日 GitHub Action  │
│  推送輸出 →                         │
└──────────────┬──────────────────────┘
               │
┌──────────────▼──────────────────────┐
│  tw-stocks-daily-report (本 repo)   │
│  reports/*.md, dashboard/data.json, │
│  schemas/data.schema.json,          │
│  dashboard/index.html (GH Pages)    │
└──────────────┬──────────────────────┘
               │ jsDelivr CDN
┌──────────────▼──────────────────────┐
│  dappgo-tw-stocks-app (private)     │
│  React Native + Expo 行動 App       │
└─────────────────────────────────────┘
```

| Repo | Visibility | 用途 |
|---|---|---|
| [tw-stocks-core](https://github.com/laiyanlong/tw-stocks-core) | private | 引擎 — 每日跑分析 |
| **tw-stocks-daily-report** (本 repo) | public | 已發布報告 + JSON + 公開 viewer |
| [dappgo-tw-stocks-app](https://github.com/laiyanlong/dappgo-tw-stocks-app) | private | iOS/iPadOS/macOS 行動 App |

姐妹產品：**DappGo Options** ([options-core](https://github.com/laiyanlong/options-core) · [options-daily-report](https://github.com/laiyanlong/options-daily-report) · [dappgo-options-app](https://github.com/laiyanlong/dappgo-options-app)) — 三 repo 架構完全相同。

> **Schema 變動**請先在本 repo 更新 `schemas/data.schema.json`（CI 會擋住格式錯誤的 push），再依序部署 engine、app。

## 授權

報告內容採 [CC BY-NC 4.0](LICENSE) — 個人、研究、教學免費使用，不得商業利用未經授權。
