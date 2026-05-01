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

每個交易日（週一至週五）台北時間 14:00（台股 13:30 收盤後 30 分鐘）由 GitHub Actions 自動產生。

## 授權

報告內容採 [CC BY-NC 4.0](LICENSE) — 個人、研究、教學免費使用，不得商業利用未經授權。
