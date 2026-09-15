# Thailand Fund Dashboards

Four interactive dashboards covering ~3,300 Thai mutual funds, built from the
Thailand SEC Open Data API (api.sec.or.th) and auto-refreshed daily at 11:00 AM
Bangkok time.

| Dashboard | Purpose |
|---|---|
| **[Dashboard Hub](./hub.html)** | Unified navigation for the three fund dashboards, Long-term Markets, and an in-hub dropdown for Arnupap's Market Signals and SET100 Signals feeds. |
| **[Risk Return](./index.html)** | Risk-return scatter with sub-category and SCB shelf filters, OR-style search, master-fund SD proxies, 1-Year spider benchmark, Top-20 / Worst-20 tables. |
| **[Growth Comparison](./growth.html)** | Cumulative growth overlay — pick funds to compare price performance over 1W → Max. Raw NAV per class (ex-dividend dips visible). |
| **[Trend](./trend.html)** | Sub-category return vs AUM-change bubble chart with drill-down per category. |
| **[Long-term Markets](https://pippono9g-cloud.github.io/longterm-markets-chart/)** | Stocks, bonds and cash with historical event context and post-event market performance. |

The signal panels load Arnupap's published JSON feeds directly inside our themed hub and retain a visible source credit: [Market Signals by Arnupap](https://arnupapchomsri-cloud.github.io/market-signal/hub.html).

## Dividend treatment

Returns and risk stats use a **Total Return proxy**: dividend share classes (e.g. `LHSEMICON-D`) borrow the metrics of their sister Acc class (which auto-reinvests, so it IS the total-return series). 154 Div funds are covered this way. 22 pure-Div funds with no Acc sibling are tagged `price-only` — their numbers under-report total return.

The Growth Comparison chart intentionally keeps raw NAV per class so users can see price performance and ex-date dips.

## Data freshness

Each dashboard's footer shows its own as-of date. The pipeline pulls the previous business day's NAVs after 11:00 AM each weekday.

Source: Thailand SEC Open Data API (<https://api.sec.or.th>). Stats are computed locally from daily NAV history (no Morningstar dependency).

## License / usage

Research preview. For internal use; not investment advice.
