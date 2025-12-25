### KO/PEP Pairs Trading Analysis
This project implements a pairs trading strategy using Coca-Cola (KO) and PepsiCo (PEP). It pulls historical prices, tracks the log-price spread between the two stocks, and trades deviations from the spread’s historical mean. The strategy is backtested and the results are visualized.

## Objectives
The goal of this study is to establish whether or not KO and PEP have a predictable long term price relationship. It also looks at whether deviations from the relationship (Z-score signals) can be used to produce profitable mean-reversion trades. Finally, the empirical findings are compared to the traditional theoretical framework for pairs trading.

## Methodology
* Data: KO and PEP adjusted closing prices are acquired using the yahoofinancer package and merged into a clean time-series tibble
* Spread: The log price spread (log(KO) - log(PEP)) is computed and standardized into a rolling Z-score over a 30-day window
* The strategy opens a position when the spread drifts beyond ±2 standard deviations from its rolling mean and closes it as the spread normalizes back to zero
* Backtest: Daily returns are computed from long/short spread positions and cumulative performance is tracked over time
* Visualize: The final figure shows the log spread and Z-score with mean-reversion thresholds, as well as the cumulative profit and loss from the strategy

## Key Findings
The key findings show that, while KO and PEP tend to move together, their price spread does not revert consistently enough to guarantee consistent profitability. Backtesting results show that cumulative returns have been declining steadily, particularly in the sample's later years. Overall, the evidence suggests that even closely related industry peers with similar fundamentals may not show consistent mean reversion in the highly liquid, large-cap US equity markets.

**Report (PDF):** [Download/View](main.pdf)
