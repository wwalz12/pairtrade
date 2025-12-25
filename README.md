### KO/PEP Pairs Trading Analysis
This project implements a pairs trading strategy using Coca-Cola (KO) and PepsiCo (PEP). It pulls historical prices, tracks the log-price spread between the two stocks, and trades deviations from the spread’s historical mean. The strategy is backtested and the results are visualized.

### Objectives
* Evaluate whether or not KO and PEP display a stable price relationship
* Test whether or not deviations (Z-score signals) from this relationship generate profitable mean-reversion trades
* Compare empirical results with the classical view of pairs trading

### Methodology
* Data: KO and PEP adjusted closing prices are acquired using the yahoofinancer package and merged into a clean time-series tibble
* Spread: The log price spread (log(KO) - log(PEP)) is computed and standardized into a rolling Z-score over a 30-day window
* The strategy opens a position when the spread drifts beyond ±2 standard deviations from its rolling mean and closes it as the spread normalizes back to zero
* Backtest: Daily returns are computed from long/short spread positions and cumulative performance is tracked over time
* Visualize: The final figure shows the log spread and Z-score with mean-reversion thresholds, as well as the cumulative profit and loss from the strategy

### Key Findings
* KO and PEP move together, but their spread does not revert consistently enough to earn consistent profits
* The backtest shows a prolonged decline in cumulative returns, especially in later years
* These results indicate that industry peers, regardless of similar fundamentals, may not reliably mean-revert in liquid, large-cap US equity markets
