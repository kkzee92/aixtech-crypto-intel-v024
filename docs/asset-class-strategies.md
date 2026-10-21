# Asset-class strategy notes (v0.24)

Research heuristics with completed multi-factor rules, Bollinger Band squeeze proxy, VWAP deviation, adaptive multi-TF, and anomaly overlays. Not forecasts.

Regime: trend / range / stress. Volatility tier: low/normal/high. Anomaly score includes kurtosis, volume-price divergence, volatility adjustment. Correlation proxy for portfolio gates and sizing.

## Major

Hypothesis: Liquid majors trend with Ichimoku + ADX + Bollinger mid + Supertrend + VWAP alignment outside stress/high anomaly/RSI divergence, controlled correlation.
Entry: Ichimoku up, ADX > 0.4, price above Bollinger mid and VWAP, Supertrend up, positive volume-delta, no RSI div, corr < 0.75.
Invalidation: Stress, high anomaly, RSI divergence, or Supertrend/Bollinger flip.
Horizon: 8/20 bars. Cap 8%. Cost 8 bps. Adaptive size by vol/corr.

## Large-cap alt

Hypothesis: Breakouts need volume-delta confirmation, multi-TF momentum, ADX, Bollinger upper and Keltner outside stress.
Entry: Close above prior high and Bollinger upper, volume-delta > 0.15, multi-period momentum positive, ADX > 0.35.
Cap 4%. Cost 14 bps.

## Stablecoin

Hypothesis: Statistical multi-metric peg deviation (z-score, consecutive, skew, kurtosis, VWAP deviation).
Alerts only. Size zero.

## DeFi

Hypothesis: Trend only in calm non-stress with Ichimoku, Supertrend, Bollinger support, ADX, low anomaly.
Cap 2%. Cost 22 bps.

## Meme

Hypothesis: Qualified bursts with volume-delta consistency, StochRSI not extreme, RSI filter, short 3-bar horizon.
Hard cap 0.5%. Cost 45 bps.

## L2

Hypothesis: Multi-period relative strength with volume-delta, ADX, VWAP, and correlation vs non-stress benchmark.
Cap 3%. Cost 16 bps.

## RWA

Hypothesis: Slow Ichimoku/Bollinger trend in low-vol; halt on adaptive gap or stress; ADX confirmation.
Cap 2%. Cost 12 bps.

## Perpetual

Hypothesis: Negative funding with contained drift, Supertrend/Ichimoku alignment, low anomaly, VWAP support.
Cap 2%. Cost 10 bps.

Out of scope: live orders, trade keys, future return claims.
