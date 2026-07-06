# Bitcoin EMA/SMA Crossover Strategy (Pine Script v6)

A simple long-only trend-following strategy for TradingView, using a moving-average crossover as the entry signal and a fixed Stop Loss / Take Profit for exits. Works on **any symbol** (crypto, stocks, forex, etc.) — not limited to Bitcoin, despite the name.

## How it works

- **Entry (Long):** when the SMA (fast, default period 5) crosses **above** the EMA (slow, default period 100)
- **Exit:** only two ways to close a trade —
  - **Stop Loss:** -8% from entry price
  - **Take Profit:** +56% from entry price
- No death-cross exit, no shorting — this is a long-only "let it ride until SL/TP" approach
- Uses a **fixed 100 EUR per trade** (no compounding), so results reflect realistic, non-inflated capital growth
- Every closed trade is labeled directly on the chart as **WIN +X EUR** or **LOSS -X EUR**, so you can see the exact result of each trade at a glance
- Built-in on-chart table shows: current settings, live Net Profit %, Final Capital in EUR, Total Trades, Win Trades, Loss Trades, and Win Rate %

## Settings (adjustable via the indicator's Inputs panel)

| Input | Default |
|---|---|
| EMA Period (Fast) | 100 |
| SMA Period (Slow) | 5 |
| Stop Loss % | 8% |
| Take Profit % | 56% |
| Commission | 0.1% per side |
| Starting capital | 100 EUR (fixed, no compounding) |
| Suggested timeframe | Daily (1D) |

## How to use

1. Open TradingView → Pine Editor
2. Paste the script from `EMA13_SMA20_Strategy.pine`
3. Click **Add to Chart**
4. Open the **Strategy Tester** tab to see full backtest results (Net Profit, Win Rate, Max Drawdown, trade list, etc.)
5. Adjust the EMA/SMA periods, Stop Loss %, or Take Profit % from the settings (gear icon) to test different combinations

## ⚠️ Disclaimer

This is a **learning / educational project**, not financial advice and not a proven profitable strategy.

- Backtest results reflect **past price data only** and do not guarantee future performance
- The strategy has **not been validated** across multiple assets, timeframes, or market regimes
- A fixed 8%/56% Stop Loss / Take Profit with no other exit logic can perform poorly during prolonged downtrends (large drawdowns are possible)
- Stop orders can be filled at a worse price than expected during sharp market gaps
- Use at your own risk. Always do your own research (DYOR) before trading with real capital.

## License

MIT License — free to use, modify, and learn from this code.
