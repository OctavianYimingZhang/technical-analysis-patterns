# Quant Factor Glossary

Lifted from `microsoft/qlib` Alpha158 / Alpha360 reference libraries (MIT), `wilsonfreitas/awesome-quant`, and standard factor-investing literature (Fama-French, Asness, AQR).

This file provides a citable, standardized vocabulary for classical quantitative factors so the `technical-analysis-patterns` skill can reference them in Report-Embed Mode without reinventing definitions.

---

## When to Use

In **Report-Embed Mode**, the technical analysis output is 150-200 words + one price-level table. Factor scores are OPTIONAL and should appear only when the user explicitly asks for them OR when the target stock is an obvious factor-tilt (e.g., deep-value, high-momentum, high-quality).

In **Standalone Mode**, a compact factor scorecard may appear as a 4-row table listing the stock's factor tilts vs its sector.

---

## The Canonical Factor Families

### 1. Momentum Factors

| Factor | Formula (Qlib notation) | Interpretation |
|--------|--------------------------|----------------|
| **RESI20** | Residual from 20-day regression of returns on market | Pure idiosyncratic momentum (strips market beta) |
| **RSQR5** | R² from 5-day regression of returns on market | Trend-strength; high R² = pure beta move; low R² = stock-specific |
| **CNTP20** | Count of positive-return days in last 20 | Persistence of uptrend |
| **CNTN20** | Count of negative-return days in last 20 | Persistence of downtrend |
| **12M-1M momentum** | (Return Y-1 to T-1M) | Classic academic momentum (Jegadeesh-Titman 1993) |

### 2. Mean-Reversion Factors

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **RSI14** | Relative Strength Index, 14-period | Overbought >70, Oversold <30 |
| **ROC5** | (Close - Close_t-5) / Close_t-5 | 5-day rate of change; extreme reads suggest snap-back |
| **Z-score(20)** | (Close - mean_20) / stdev_20 | How many std devs from 20-day mean |

### 3. Volatility Factors

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **VSTD20** | Std dev of 20-day returns | Realized volatility |
| **VMACD(12,26)** | MACD of volume | Volume momentum; spike vs trend |
| **ATR14** | Average True Range, 14-period | Absolute dollar volatility; use for stops |
| **High-Low range / Price** | (H-L) / ((H+L)/2) | Intraday range as % of price; volatility |

### 4. Liquidity / Volume Factors

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **VRS20** | Volume ratio vs 20-day average | 2+ = breakout volume |
| **VMACD** | MACD of volume | Volume trend acceleration |
| **OBV** | On-Balance Volume | Cumulative signed volume; divergence from price signals reversal |
| **Amihud Illiquidity** | \|Return\| / Volume | Illiquidity — higher = more slippage |

### 5. Value / Fundamental Factors (when integrated into TA context)

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **P/E ratio** | Price / Forward EPS | Standard value metric |
| **EV/EBITDA** | Enterprise Value / EBITDA | Capital-structure-neutral value |
| **P/B** | Price / Book Value per Share | Value, especially for financials |
| **FCF Yield** | FCF / Market Cap | Cash-generation yield |

### 6. Quality Factors

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **ROIC** | NOPAT / Invested Capital | Return on invested capital |
| **Gross Margin stability** | Stdev of 5-year gross margin | Lower = more durable moat |
| **Piotroski F-Score** | 9-factor composite (profitability, leverage, efficiency) | 7-9 = high quality, 0-3 = low quality |

### 7. Low-Volatility / Defensive Factors

| Factor | Formula | Interpretation |
|--------|---------|----------------|
| **Beta** | Regression slope vs market | <1 = defensive, >1 = aggressive |
| **Downside Beta** | Beta computed on down-days only | Captures asymmetric exposure |

---

## Factor Tilt Scoring (Compact Scorecard)

For Standalone Mode reports, a compact factor tilt scorecard can appear as a 4-row table. Score the stock's tilt on each family on a -2 to +2 scale:

| Factor Family | Score | Interpretation |
|---------------|-------|----------------|
| Momentum | +2 = strong uptrend, top quintile 12-month return | +2/+1/0/-1/-2 |
| Value | +2 = bottom quintile P/E + P/B + EV/EBITDA | +2 = deep value, -2 = expensive |
| Quality | +2 = top quintile ROIC + margin stability + F-Score | +2 = high quality |
| Volatility | +2 = bottom quintile realized vol | +2 = defensive, -2 = high vol |
| Size | +2 = mega-cap (>$200B), -2 = micro-cap (<$300M) | size tilt |

**Example scorecard** (for a mid-cap tech momentum name):

| Family | Score | Comment |
|--------|-------|---------|
| Momentum | +1 | 12M return top tercile, 1M return top decile |
| Value | -2 | Forward PE 45x (top quintile), EV/EBITDA 22x |
| Quality | +1 | ROIC 18%, gross margin 68% stable |
| Volatility | -1 | Beta 1.3, realized vol 35% (above market) |
| Size | 0 | ~$15B market cap |

---

## Integration with Report-Embed Mode

The Report-Embed Mode output (150-200 words + price table) should generally **omit** factor scores unless:

1. The user asks for factor tilts specifically
2. The stock has a lopsided tilt that materially affects the trade (e.g., "factor setup is pure momentum + low quality — vulnerable to a quality rotation")

If included, append a single-line factor note, not a full table. Example:

> "动量 +2 / 价值 -2 / 质量 +1,非对称偏动量,一旦风格切换到高质量防御,此票有 15-25% 估值压缩空间。"

---

## Anti-Patterns

- Do NOT list all 158 Alpha158 factors in the report — it's inventory noise
- Do NOT compute Beneish M-score or Altman Z here — that's the short-seller skill's domain
- Do NOT use factor scores as the PRIMARY valuation method — they are sanity checks
- Do NOT claim factor exposures without citing the specific metric (momentum +1 ≠ "strong momentum")

---

## References

- microsoft/qlib — `qlib/contrib/data/handler.py` Alpha158 / Alpha360 definitions (MIT)
- Fama, E.F. & French, K.R. (1993). "Common risk factors in the returns on stocks and bonds." *Journal of Financial Economics*, 33(1), 3-56.
- Asness, C.S. (1994). "Variables that Explain Stock Returns." Ph.D. Dissertation.
- Jegadeesh, N. & Titman, S. (1993). "Returns to Buying Winners and Selling Losers." *Journal of Finance*, 48(1), 65-91.
- Piotroski, J.D. (2000). "Value Investing: The Use of Historical Financial Statement Information." *Journal of Accounting Research*, 38, 1-41.
- Beneish, M.D. (1999). "The Detection of Earnings Manipulation." *Financial Analysts Journal*, 55(5), 24-36.
