# Backtesting Trading Strategies

Backtest crypto and traditional trading strategies against historical data — before risking real capital.

> **Results describe a historical simulation, not expected future performance.** Backtesting is a research tool, not financial advice.

## What it is

An agent skill (v1.30.0) that simulates trading strategies against historical market data, calculates performance metrics, generates equity curves, and optimizes strategy parameters.

**8 pre-built strategies:** SMA, EMA, RSI, MACD, Bollinger, Breakout, Mean Reversion, Momentum.

**Performance metrics:** Sharpe, Sortino, Calmar, VaR, max drawdown — plus trade-by-trade analysis.

## What's inside

- `SKILL.md` — the skill definition, instructions, and usage
- `scripts/` — data fetching (`fetch_data.py`) and the backtest engine (`backtest.py`)
- `data/` — cached historical data for reuse

## Quick start

Install dependencies:

```bash
pip install pandas numpy yfinance matplotlib
```

Fetch historical data:

```bash
python scripts/fetch_data.py --symbol BTC-USD --period 2y --interval 1d
```

Run a backtest:

```bash
python scripts/backtest.py --strategy sma_crossover --symbol BTC-USD --period 1y
python scripts/backtest.py --strategy rsi_reversal --symbol ETH-USD --period 1y --capital 10000 --params '{"period": 14, "overbought": 70, "oversold": 30}'
```

## Use it when

- Testing a trading strategy against history
- Validating signals before trading them
- Comparing two approaches on the same data
- Optimizing strategy parameters with grid search

## Disclaimer

Historical performance does not predict future results. Markets change; a strategy that backtests well can still lose money live. Never trade money you cannot afford to lose.

## License

MIT — see [LICENSE](LICENSE).
