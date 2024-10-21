# Algorithmic Trading System Overview -- Iris Li

## Introduction

This algorithmic trading system automates the execution of a trading strategy on the Alpaca platform, focusing on the long-short term moving average crossover. The primary objectives are to achieve consistent returns, manage risk through stop-loss orders, and adapt to dynamic market conditions using backtesting and performance metrics such as Monte Carlo simulations and sharp ratio.

## Market Data Retrieval

### Alpaca-py Library Usage

Market data is retrieved from Alpaca using the `alpaca-py` library, which provides a Python interface to the Alpaca API. The data includes historical stock prices that are essential for calculating technical indicators and backtesting the strategy.

## Data Storage Strategy
### Storage Method
Market data is retrieved directly from the Alpaca API and used in real-time for both backtesting and live trading. Data is processed and analyzed within the script.

### Timestamps and Timezones
All timestamps are handled in Coordinated Universal Time (UTC) directly from the API, ensuring consistency and eliminating timezone-related issues.

## Trading Strategy Development

### Instrument Selection

We selected **TSLA** (Tesla Inc.) for its high trading volume and volatility, providing ample opportunities for the moving average crossover strategy to be tested and refined.

### Technical Indicators

The core of the strategy is based on two moving averages:
- **Short-term Moving Average (50-day):** Represents shorter trends.
- **Long-term Moving Average (200-day):** Represents longer trends.

A buy signal is generated when the short-term moving average crosses above the long-term moving average, indicating potential upward momentum. Conversely, a sell signal is generated when the short-term moving average crosses below the long-term moving average, indicating potential downward momentum.

### Risk Management

Risk management is enhanced through the use of stop-loss orders, which automatically trigger a sale if the price falls by 5% from the purchase price. This prevents significant losses during unexpected market downturns.

### Position Sizing

Position sizing is kept small for initial testing to minimize risk while evaluating the strategy's effectiveness.

## Code Explanation

### Core Functions

#### Data Retrieval and Moving Average Calculation

This section of the code retrieves historical stock data for **TSLA** using the Alpaca API and computes the short-term and long-term moving averages, which are essential for identifying trading signals.

#### Backtesting the Strategy

The backtesting function simulates trading based on historical data. It checks for crossover events between the short-term and long-term moving averages, recording the profits or losses for each trade. This allows us to evaluate the strategy's performance before deploying it in live trading.

### Performance metrics

Performance metrics, such as the Sharpe Ratio and maximum drawdown, are calculated to assess the strategy's risk-adjusted performance. Additionally, a Monte Carlo simulation is implemented to evaluate the robustness of the strategy under different market conditions.


#### Live Trading with Stop-Loss Orders

This section implements the trading strategy in a live paper trading environment. The code continuously monitors real-time data, places buy or sell orders based on crossover signals, and sets a stop-loss order for risk management.

### Error Handling and Monitoring

Robust error handling is integrated to capture any issues during data retrieval or order execution. The system also monitors live market conditions, adjusting positions based on real-time moving average crossovers.

## Testing and Optimization

### Backtesting

The trading strategy is rigorously backtested using historical data. This helps refine the parameters and provides insights into the strategy's potential performance in various market conditions.

### Optimization

Key parameters, such as the moving average windows were optimized to balance the trade-off between risk and reward. The were optimized using backtesting results.

## Automation and Scheduling

### Data Retrieval Automation

The data retrieval process is automated using a loop that continually fetches the latest market data and calculates moving averages. This ensures the system is always updated with the most current information for making trading decisions.

### Script Version Control

Script version control was improved to track changes more effectively and ensure that any modifications are well-documented.

## Paper Trading and Monitoring

### Alpaca Paper Trading

The algorithm is tested in a simulated environment using Alpaca's paper trading feature, allowing for risk-free simulation of live market conditions. This provides a realistic assessment of the strategy's performance without financial risk.

### Performance Monitoring

Real-time monitoring tools track the algorithm's performance, capturing key metrics such as returns, trade frequency, and success rate. This data is crucial for further refining the strategy.

## Results and Lessons Learned

### Challenges

One challenge encountered was optimizing the strategy to respond effectively to different market conditions. The backtesting process revealed that while the moving average crossover strategy works well in trending markets, it may struggle in sideways or highly volatile markets.

### Lessons Learned

Key lessons learned include the importance of thorough backtesting and optimization before live trading. Understanding the limitations of the moving average strategy is also crucial for managing expectations and risks.

### Improvements

Future improvements include refining the stop-loss mechanism and exploring additional technical indicators to complement the moving average strategy. A potential combined metric score could give better backtesting results. These enhancements could further optimize performance and reduce risk.

## Compliance and Legal Considerations

### Regulatory Alignment

The algorithmic trading system adheres to relevant financial regulations, including those governing automated trading and data privacy.

## Conclusion

In conclusion, this algorithmic trading system leverages the long-short term moving average crossover strategy, combined with backtesting and risk management techniques, to automate trading decisions on the Alpaca platform. The lessons learned from this project provide valuable insights for future iterations, and the system's compliance with legal requirements positions it for potential deployment in live markets.
