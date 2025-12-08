### KO/PEP Pairs Trading Analysis
This project implements a full end-to-end pairs trading workflow using Coca-Cola (KO) and PepsiCo (PEP) as the asset pair. The analysis downloads historical price data, computes the log price spread between the assets, transforms the spread into a rolling Z-score, generates long/short trading signals based on mean-reversion thresholds, backtests a simple relative-value trading strategy, and visualizes the results.

### Objectives
* Evaluate whether KO and PEP exhibit a stable long-run price relationship.
* Test whether deviations from this relationship (measured via Z-score signals) generate profitable mean-reversion trades.
* Compare empirical results with the classical view of pairs trading introduced by Gatev, Goetzmann, & Rouwenhorst (2006).

### Methodology
* Data Retrieval: KO and PEP adjusted closing prices are fetched using the yahoofinancer package and merged into a clean time-series tibble.
* Spread Construction: The log price spread (log(KO) − log(PEP)) is computed and standardized into a rolling Z-score using a 30-day window.
* Signal Generation: A state-machine rule opens positions when the spread exceeds ±2 standard deviations from its rolling mean and closes when it reverts toward zero.
* Backtesting: Daily returns are computed from long/short spread positions, and cumulative performance is tracked over time.
* Visualization: The final figure shows: The log spread and Z-score with mean-reversion thresholds and the cumulative P&L from the strategy

### Key Findings
* KO and PEP move together, but their spread does not revert consistently enough to produce stable profits.
* The backtest shows a prolonged decline in cumulative returns, especially in later years.
* These results suggest that industry peers—despite similar fundamentals—may not reliably mean-revert in liquid, large-cap U.S. equity markets.
