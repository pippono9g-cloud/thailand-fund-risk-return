# Thailand Fund Dashboards

Six interactive dashboards covering ~3,300 Thai mutual funds, built from the
Thailand SEC Open Data API (api.sec.or.th) and auto-refreshed daily at 11:00 AM
Bangkok time.

| Dashboard | Purpose |
|---|---|
| **[Investment Insights Hub](./hub.html)** | Unified navigation for the six fund dashboards, Long-term Markets, and an in-hub dropdown for Arnupap's Market Signals and SET100 Signals feeds. |
| **[Risk Return](./index.html)** | Risk-return scatter with sub-category and SCB shelf filters, OR-style search, master-fund SD proxies, 1-Year spider benchmark, Top-20 / Worst-20 tables. |
| **[Efficient Frontier](./frontier.html)** | Efficient frontier of the selected fund universe (Historical or Black-Litterman), solved in the browser with weight, asset-class and fund-count limits. |
| **[Growth Comparison](./growth.html)** | Cumulative growth overlay — pick funds to compare price performance over 1W → Max. Raw NAV per class (ex-dividend dips visible). |
| **[Flow](./trend.html)** | Sub-category return vs AUM-change bubble chart with drill-down per category (menu name "Flow"; file stays `trend.html`). |
| **[Trend](./ma-quadrant.html)** | MA-Quadrant: AIMC sub-category position vs fast (default 30d) and slow (default 200d) moving averages, with sliders for the MA windows and zone-change lookback. |
| **[Portfolio Analysts](./portfolio.html)** | Build a portfolio from the fund universe: allocation by asset class / sub-sector, buy-and-hold NAV performance, risk vs return and comparison with the SCB model and Efficient Frontier. |
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
