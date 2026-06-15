# Thailand Fund Dashboards

Four interactive dashboards covering ~3,300 Thai mutual funds, built from the
Thailand SEC Open Data API (api.sec.or.th) and auto-refreshed daily at 11:00 AM
Bangkok time.

| Dashboard | Purpose |
|---|---|
| **[Risk Return](./index.html)** | Risk-return scatter with sub-category and SCB shelf filters, OR-style search, master-fund SD proxies, 1-Year spider benchmark, Top-20 / Worst-20 tables. |
| **[Growth Comparison](./growth.html)** | Cumulative growth overlay — pick funds to compare price performance over 1W → Max. Raw NAV per class (ex-dividend dips visible). |
| **[Trend](./trend.html)** | Sub-category return vs AUM-change bubble chart with drill-down per category. |
| **[Portfolio Construction](./portfolio.html)** | Build a model portfolio of up to 15 funds with 0-100% weight sliders. Weighted 1Y expected return (manual override per fund), naive-weighted SD / Sharpe / Max Drawdown. |

## Dividend treatment

Returns and risk stats use a **Total Return proxy**: dividend share classes (e.g. `LHSEMICON-D`) borrow the metrics of their sister Acc class (which auto-reinvests, so it IS the total-return series). 154 Div funds are covered this way. 22 pure-Div funds with no Acc sibling are tagged `price-only` — their numbers under-report total return.

The Growth Comparison chart intentionally keeps raw NAV per class so users can see price performance and ex-date dips.

## Data freshness

Each dashboard's footer shows its own as-of date. The pipeline pulls the previous business day's NAVs after 11:00 AM each weekday.

Source: Thailand SEC Open Data API (<https://api.sec.or.th>). Stats are computed locally from daily NAV history (no Morningstar dependency).

## License / usage

Research preview. For internal use; not investment advice.
