# AIxTech crypto intel v0.24: paper-only trading information system

Advanced research harness for automated cryptocurrency **information** and paper strategy evaluation.
Builds on [kkzee92/aixtech-crypto-intel-v023](https://github.com/kkzee92/aixtech-crypto-intel-v023), prior versions, and the [zeekiankok92/aixtech-agent-harness-demo](https://github.com/zeekiankok92/aixtech-agent-harness-demo) style.

It does not place live orders, does not store exchange secrets, and is not financial advice.

![Python](https://img.shields.io/badge/python-3.10%2B-blue)
![version](https://img.shields.io/badge/version-0.24.0-blue)
![mode](https://img.shields.io/badge/execution-paper%20only-orange)
![Licence](https://img.shields.io/badge/licence-MIT-green)

## Enhancements in v0.24

- Completed multi-factor strategies for all 8 asset classes (no more placeholders).
- Bollinger Band squeeze proxy and VWAP deviation filters for better entry quality.
- Adaptive multi-timeframe momentum consistency and correlation-adjusted sizing.
- Enhanced anomaly scoring with volatility-adjusted thresholds.
- Strengthened zero-trust: expanded redaction (Solana addresses, more seed proxies), improved lineage Merkle simulation with double-hash, isolation checks.
- Updated per-class risk caps and costs with adaptive overlays.

## What it does

- Eight asset classes with refined multi-factor research rules including Bollinger/VWAP/Ichimoku/ADX.
- Multi-scale regime + volatility tier + advanced anomaly scoring + correlation gates.
- Signals with adaptive filters, then multi-gate risk.
- Paper-only backtests with class costs; enhanced hash-chained audit with improved lineage.
- Synthetic candles only. No network by default.

| Asset class | Enhanced research rule (v0.24) | Risk cap | Cost |
|---|---|---|---|
| Major | Multi-EMA + Ichimoku + ADX + Bollinger mid + Supertrend + VWAP + volume-delta + no RSI div; stand aside stress/high-vol/anomaly | 8% | 8 bps |
| Large-cap alt | Volume-delta + Bollinger breakout + multi-TF + ADX + Keltner | 4% | 14 bps |
| Stablecoin | Adaptive peg + multi-stat (z, consecutive, skew, kurtosis, VWAP) alerts only | 0% | n/a |
| DeFi | Calm multi-scale + Ichimoku + Supertrend + Bollinger + low anomaly + ADX | 2% | 22 bps |
| Meme | Qualified burst with volume-delta, StochRSI, consistency, RSI, short horizon | 0.5% | 45 bps |
| L2 | Multi-period RS + relative volume-delta + corr vs benchmark + ADX + VWAP | 3% | 16 bps |
| RWA | Slow Ichimoku/Bollinger low-vol trend; adaptive gap halt + ADX | 2% | 12 bps |
| Perpetual | Funding carry with adaptive drift, Supertrend/Ichimoku, low anomaly, VWAP align | 2% | 10 bps |

## Run

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements-dev.txt
# Generate fixtures if scripts present
PYTHONPATH=src python -m crypto_intel scan fixtures/candles_synthetic.json
```

## Controls

Paper-only. No live credentials. Class caps, adaptive confidence and sizing, kill switch, drawdown, statistical anomaly + correlation gates, hash-chained audit with improved lineage, expanded redaction, PDPA tripwire, gitleaks. Zero-trust research design.

## Honesty

No live exchange connector. Scores describe synthetic fixtures. Not investment, legal, or compliance advice. Research only.
