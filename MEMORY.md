# MEMORY.md

Taiwan Semiconductor (NYSE: TSM, ADR 1:5) tracking dashboard. Static single page
served by GitHub Pages. This repo is independent of all other dashboard repos;
keep it separate (own quote.json, own workflow, own public link).

## Deployment
- Public link: https://tonytcfu.github.io/tsm-dashboard/
- Source: `index.html` at the `main` branch root, generated from the
  `tsm-dashboard` web artifact (re-export on data updates; do not hand-edit).
- GitHub Pages setting: Deploy from a branch / main / /(root).

## Quote snapshot
- `quote.json` at repo root; refreshed by `.github/workflows/quote.yml`
  (cron `*/15 13-21 * * 1-5` UTC, Mon-Fri, plus manual dispatch).
- Source: Nasdaq official API (`api.nasdaq.com/api/quote/TSM/info`), real-time.
- Page fallback chain: quote.json -> Nasdaq direct -> Yahoo Finance -> Stooq (tsm.us).
- Format: {"symbol":"TSM","price":..,"netChange":..,"pctChange":..,"prevClose":..,
  "quoteTime":"YYYY-MM-DD HH:MM","status":"intraday|postmarket|close","source":"Nasdaq"}.

## Data baseline
- Price: 2026-10-02 close $472.78 (+$13.58 / +2.96%; prev close $459.20; O/H/L/V $465.64/$474.79/$464.10/9.93M); 52-week range $275.03-$477.27 (OptiView 10-02); market cap ~$2.45T; TTM P/E 28.73 (Finnhub).
- Q2 2026 (2026-07-16): revenue NT$1,270.38B (+36% YoY, US$40.20B), net income NT$706.56B, diluted EPS NT$27.25 (US$4.31/ADR), gross margin 67.7% (record), OP margin 60.3%. Node mix: 2nm 3% / 3nm 30% / 5nm 33% / 7nm 11%; platform: HPC 66% / Smartphone 22% / IoT 5% / Automotive 3-4% / DCE 1%. Q3 2026 guide: revenue US$44.6-45.8B, GM 65-67%, OP margin 56-58%; FY2026 revenue slightly above +40% YoY (US$), capex raised to US$60-64B. Dividend Q1 2026 NT$7.0/ordinary share, payable 2026-10-08.
- Short interest (FINRA 2026-09-15): 27,789,695 shares, 0.54% of float, 2.8 days to cover.
- Analyst ladder (ADR): Barclays $650 OW, BofA $590 Buy, Bernstein $554 OP, Needham $530, Stifel $515, Morningstar FV $534; consensus mean ~$524-552, Strong Buy. Susquehanna $400 ⚠️ unverified caliber.
- Options (2026-10-02): dealer GEX +$532.3M (FlashAlpha 15:49 ET); call wall $500 / put wall $400; max pain $410 (all-expiries, -13.6%); P/C OI 1.03; 30d ATM IV 33.3% (rank 38/100 OptiView); expected move ±$37.93 (±8.0%); hottest strike $470, volume/OI 0.66. Options-analysis section included (video-style regime reading).
- Next earnings: 2026-10-15 (Q3 call, 14:00 Taipei time). September revenue typically ~10/10 (not yet published as of 10/05).
