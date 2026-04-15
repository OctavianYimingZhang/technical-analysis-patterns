---
name: technical-analysis
description: >
  Pattern-based technical analysis and trade decision-making — focused on Bull Flag
  Breakout, W Bottom Breakout, Inverse Head & Shoulders Breakout, Spring, Cup & Handle,
  Descending Wedge, and Monthly Breaking Previous High. Two output modes: (1) standalone
  detailed pattern analysis, (2) report-embed mode producing a 150-200 word block + one
  small price-level table + mandatory trade plan for the stock-research-report orchestrator.
triggers:
  - technical analysis
  - chart pattern
  - trade decision
  - Wyckoff
  - 技术分析
  - 形态分析
  - pattern recognition
---

# Technical Analysis: Pattern Recognition & Trade Decisions

## Output Modes

This skill has **two output modes**:

### Mode 1: Standalone Detailed Analysis (Default)
The full pattern-by-pattern detailed analysis below. Use when the user directly asks for a technical review of a ticker.

### Mode 2: Report-Embed Mode (When Called by stock-research-report Orchestrator)
A compact, 150-200 word block + one small price-level table + **mandatory trade plan**. This is what gets woven into the 技术分析 section of the final analyst report.

**Report-Embed Mode output template:**

```
## 技术分析

[Paragraph 1 — 50-80 words]
从技术面看，[TICKER] 目前处于 [primary pattern, plain language — 例如"W 底形成右底，颈线在 $65"].
月线 [趋势], 周线 [趋势], 日线 [趋势]. [Volume confirmation status in one phrase].

[Paragraph 2 — 50-80 words]
[关键位判断]. 当前若 [scenario trigger] , 可能 [result]. [One sentence on
technical-fundamental alignment: "技术面与基本面 [aligned / divergent],
[one-sentence reason]".]

| 位置 | 价位 | 说明 |
|------|------|------|
| 即时阻力 | $XX | [brief reason] |
| 主要阻力 | $XX | [brief reason] |
| 强支撑 | $XX | [brief reason] |
| 关键支撑 | $XX | [thesis invalidation if broken] |

交易计划:
- 入场区间: $X - $Y（[reason]）
- 止损位: $Z（对应 [what invalidates]）
- 第一止盈位: $A（[method]）
- 第二止盈位: $B（[method]）
```

**Report-Embed Rules:**
1. **NO Wyckoff vocabulary in the output.** Translate to plain Chinese: 投降 / 反弹 / 回测 / 突破 / 上升趋势. "Spring", "SOS", "LPS", "Markup" only exist in the analyst's private reasoning — the reader sees plain Chinese.
2. **NO multi-subsection format** ("形态识别 / 突破成交量确认 / 关键价位 / Wyckoff / 综合判断"). That's Mode 1, not Mode 2.
3. **ALWAYS output a trade plan** (entry / stop / TP1 / TP2). If you cannot identify entry/stop/targets, state "当前无明确入场点，建议观望" and give the next observable event.
4. **Technical-fundamental alignment** must be explicitly stated: aligned, divergent, or neutral. This is the GLUE between the technical and fundamental chapters.
5. **Cap at 150-200 words total** (excluding the trade plan bullets).
6. **Price-level table has max 4 rows.**

---

# Standalone Mode: Full Pattern Recognition & Trade Decisions

A pattern-based trading system synthesized from three classic technical analysis books:

- **Technical Analysis of the Futures Markets** (John J. Murphy)
- **Japanese Candlestick Charting Techniques** (Steve Nison)
- **Wyckoff Method: Trades About to Happen** (Edward Meng)

## Core Principles

### Multi-Timeframe Framework
- **Daily chart (core)**: All pattern identification and trade execution is based on the daily chart
- **Weekly chart (reference)**: Used to confirm trend direction and validate support/resistance levels
- **Monthly chart (only for previous-high breakouts)**: Only used when evaluating "monthly breaking previous high" — short-term patterns like bull flags do NOT require monthly chart reference

### Volume Rules
- **Only check volume at the breakout moment**: Volume at the breakout candle is the key confirmation signal
- **No volume analysis needed outside of breakouts**: Avoid over-reading volume during normal consolidation
- **Valid breakout volume**: Breakout-day volume should be notably higher than recent (5-20 day) average volume

### Supply & Demand Core (Wyckoff Theory)
- Price moves are fundamentally driven by supply/demand imbalances
- Volume at breakout confirms whether demand (buying) truly exceeds supply (selling)
- False breakouts occur when demand fails to absorb supply

---

## Pattern 1: Bull Flag Breakout

### Definition
A brief pullback consolidation within an uptrend, forming a downward-sloping parallel channel (the flag), followed by an upward breakout continuing the prior advance.

### Identification Criteria (Daily Chart)
1. **Flagpole**: A sharp, nearly vertical advance preceding the flag, accompanied by rising volume
2. **Flag body**: Price enters a narrow, downward- or sideways-sloping channel with progressively declining volume
3. **Duration**: The flag typically lasts 1-3 weeks (5-15 trading days), no more than 4 weeks
4. **Pullback depth**: The flag retraces 1/3 to 2/3 of the flagpole's advance
5. **Tightening action**: Candles within the flag progressively shorten and volatility narrows

### Breakout Confirmation
- **Breakout signal**: Daily close above the flag's upper boundary
- **Volume confirmation**: Breakout-day volume expands notably versus the consolidation period
- **Follow-through**: Bullish candles should follow within 1-2 days (higher highs, higher lows, higher closes)

### Target Measurement
- **Minimum target**: From the breakout point, project upward a distance equal to the flagpole length
- **Conservative target**: 50%-75% of the flagpole length

### Stop-Loss Placement
- Place the stop below the flag's lowest point

### Murphy's Supplementary Rules
- Flags appear at the **midpoint** of the overall move ("half-mast" analogy)
- After completion, the market repeats the first half of the move (flagpole length = subsequent advance)
- The flag must slope **against** the prevailing trend (downward slope in an uptrend)
- Flag vs. Pennant: flag has parallel boundaries; pennant has converging boundaries

### Key Notes
- Bull flags are short-term daily patterns — **no monthly chart reference needed**
- Flag duration exceeding 4 weeks may morph into a different pattern
- Reliability declines if the pullback exceeds 2/3 of the flagpole

---

## Pattern 2: W Bottom Breakout (Double Bottom)

### Definition
After a decline, price forms two lows at approximately the same level (W shape). The neckline (rally high between the two bottoms) is broken to confirm a reversal.

### Identification Criteria (Daily Chart)
1. **First bottom (left)**: A clear support area forms during a downtrend, triggering a rally
2. **Neckline**: The rally high between the two bottoms creates a horizontal resistance level
3. **Second bottom (right)**: Price declines again near the first bottom's level
   - Ideal: right bottom slightly higher than left (shows strengthening demand)
   - Right bottom slightly below left but with a swift rebound is also valid (Spring characteristic)
4. **Spacing**: Typically 1-3 months between the two bottoms
5. **Symmetry**: Perfect symmetry is not required — focus on supply/demand dynamics

### Breakout Confirmation
- **Breakout signal**: Daily close above the neckline (must wait for the closing price — intraday penetration does not count)
- **Volume confirmation**: Expanded volume on the neckline breakout day
- **Pullback test**: A post-breakout pullback to the neckline on declining volume confirms validity
- **Filters**: 3% penetration rule or two-day closing rule (two consecutive closes above neckline)

### Target Measurement
- **Minimum target**: From the neckline, project upward the vertical distance from neckline to the bottom
- **Alternative**: Measure the first upward leg's range, project the same distance from the breakout point

### Stop-Loss Placement
- Place the stop below the right bottom's lowest point

### Murphy's Supplementary Rules
- The two bottoms do not need to be at exactly the same level. Right bottom slightly higher = normal (strengthening demand)
- Right bottom slightly below left, followed by a quick snap-back = Spring characteristic, stronger signal
- Wider spacing between bottoms (at least 1 month, ideally 2-3 months) and greater height = greater reversal potential
- "Double bottom" is an overused term: a bounce from a prior low is a natural reaction at support — the pattern is NOT confirmed until the neckline is actually broken

### Weekly / Monthly Reference
- **Weekly**: Confirm the W bottom sits within a weekly-level support zone
- **Monthly**: If the W bottom breakout coincides with a monthly close above a previous high, the signal is significantly stronger

### Wyckoff Perspective
- Left bottom corresponds to the "Selling Climax" (SC) or "Preliminary Support" (PS)
- The rally between bottoms corresponds to the "Automatic Rally" (AR)
- Right bottom corresponds to the "Secondary Test" (ST) — a successful ST (declining volume, narrow range) confirms the downtrend has stopped
- If the right bottom produces a Spring (briefly breaks below the left bottom then snaps back), it is an extremely strong buy signal

---

## Pattern 3: Inverse Head & Shoulders Breakout

### Definition
Price forms three troughs — the middle one deepest (the head), flanked by two shallower, roughly symmetrical troughs (left and right shoulders). A neckline break confirms the reversal.

### Identification Criteria (Daily Chart)
1. **Left shoulder**: A rally within a downtrend forms the first trough. Corresponds to Wyckoff's "Preliminary Support"
2. **Head**: Price falls again, breaking below the left shoulder's low to form a deeper trough. Corresponds to the "Selling Climax"
3. **Neckline**: The line connecting the rally highs between left shoulder-to-head and head-to-right shoulder (can be horizontal or slightly upward-sloping)
4. **Right shoulder**: Price drops a third time but fails to reach the head's low. Corresponds to the "Secondary Test"
   - Right shoulder bottom higher than head bottom (evidence of strengthening demand)
   - Right shoulder volume should be less than head volume (supply is drying up)
5. **Duration**: Several weeks to several months

### Breakout Confirmation
- **Breakout signal**: Daily close above the neckline
- **Volume confirmation**: Volume **must surge dramatically** at the neckline break — this is the absolute key condition for bottom breakouts
- **Pullback test**: Throwbacks are more common at bottoms than tops; declining volume on the throwback confirms validity

### Murphy's Volume Sequence (Critical)
- Head decline phase: volume somewhat higher than the left shoulder (opposite of the topping pattern)
- Right shoulder decline: volume is **very light** (the single most important confirmation signal)
- Neckline breakout: volume surges dramatically (absolutely essential)
- Principle: "Markets fall under their own weight, but rallies require buying pressure"

### Target Measurement
- **Method 1**: Measure the vertical distance from the head's low to the neckline; project that distance upward from the breakout point
- **Method 2**: Measure the first upward leg (head low to the rally high between head and right shoulder); double that distance from the rally high

### Stop-Loss Placement
- Place the stop below the right shoulder's lowest point

### Weekly / Monthly Reference
- **Weekly**: Confirm the inverse H&S forms at the tail end of a weekly-level downtrend
- **Monthly**: If the breakout coincides with a monthly close above a previous high, it is a large-scale reversal confirmation

### Wyckoff Perspective
- Left shoulder = initial area of supply exhaustion (Preliminary Support)
- Head = Selling Climax (high-volume long bearish candle followed by a rally)
- Rally between head and right shoulder = Automatic Rally
- Right shoulder = Secondary Test (critical: both volume and candle range must contract)
- Neckline breakout = Sign of Strength (SOS) or Jump over the Creek (JOC)
- Low-volume pullback to the neckline after breakout = best entry point (Last Point of Support / LPS)

---

## Pattern 4: Spring / False Breakdown Reversal (Wyckoff)

### Definition
Price briefly breaks below an established support level then quickly snaps back above it. This is a core Wyckoff trading signal — essentially the Composite Man (CM / institutional operators) testing whether supply has been exhausted.

### Identification Criteria (Daily Chart)
1. **Prerequisite**: A well-established support level must exist (trading range floor, prior low, demand zone)
2. **Breakdown**: Price breaks below the support
3. **Key judgment**: Volume and candle size at the breakdown determine the Spring type

### Three Types of Spring

#### Type 1: Low-Volume, Small-Candle Spring (Best — enter immediately)
- Both candle range and volume are small at the breakdown
- Indicates supply at the support level is exhausted (no significant sell orders remain)
- **Action**: Enter long immediately

#### Type 2: Moderate-Volume Spring (Wait for secondary test)
- Slightly expanded volume and moderate candle at the breakdown
- Some supply exists but is not overwhelming
- **Action**: Wait for a secondary test. If the test shows dramatically reduced volume and range, enter

#### Type 3: High-Volume, Large-Candle Spring (Shakeout — high risk)
- Both volume and candle range are large, deeply penetrating support
- Supply is heavy, but this may be an institutional terminal shakeout
- **Action**: Must wait for a secondary test confirming supply exhaustion. If a rapid rally (SOS) follows, enter on the pullback test

### Special Spring: Closing Position Rule
- If the breakdown candle closes above its 50% midpoint (lower shadow / hammer shape), even with high volume, it leans bullish
- The closing position shows demand absorbed supply before the close

### Confirmation (Signs of a Successful Spring)
- After the Spring, price must produce: consecutively higher highs, higher lows, and higher closes
- Volume should increase steadily (not spike) as price rises
- If the post-Spring rally is weak (no volume, shrinking candles), the Spring has failed

### Stop-Loss Placement
- Place the stop below the Spring's lowest point

### Critical Rules
- **Springs have the highest success rate in bullish contexts** — this is an iron rule
- **Springs in downtrends are traps** — do not use them to bottom-fish
- Consecutive failed Springs are a warning that the uptrend is ending
- In a supply-dominated environment, Spring failure probability is very high
- A Spring is fundamentally a supply test — after entry, you must see demand follow through

### Spring vs. Terminal Shakeout

| Feature | Spring | Terminal Shakeout |
|---------|--------|-------------------|
| Penetration depth | Slight break below support | Deep penetration through all support levels |
| Volume | Low to moderate | Extremely high |
| Location | Trading range floor / pullback low | Late-stage accumulation |
| Purpose | Test supply, clear floating supply | Final blow to force out the most committed holders |
| Action | Low-volume type can be entered directly | Must wait for secondary test |

---

## Pattern 5: Monthly Breaking Previous High

### Definition
On the monthly chart, price breaks above a significant prior high, confirming the continuation or initiation of a long-term uptrend.

### Identification Criteria (Monthly Chart)
1. **Previous high**: A significant peak on the monthly chart (typically the highest point within the last 6-24 months)
2. **Breakout method**: Monthly closing price above the previous high
3. **Volume confirmation**: Breakout-month volume should be somewhat elevated

### Breakout Confirmation
- **Valid breakout**: Monthly close above the previous high (only the closing price counts — intraday/wick spikes do not)
- **Pullback test**: If price retests the previous high and finds support (prior resistance becomes support), the breakout is more reliable

### Use Cases
- This is a **standalone monthly-level signal**
- When a daily pattern (W bottom, inverse H&S) breaks out and the monthly chart simultaneously clears a previous high, the resonance makes the signal extremely strong
- **Bull flag breakouts do NOT need this reference** (bull flags are short-term daily patterns)

### Operating Guidelines
- After a monthly breakout above the previous high, daily pullbacks are buying opportunities
- A failed monthly breakout (closing back below the previous high) is a risk signal
- Combine with weekly trend direction to assess breakout quality

---

## Pattern 6: Cup-and-Handle Breakout

### Definition
A rounded bottom (cup) followed by a short consolidation (handle), then an upward breakout. This pattern indicates a gradual shift from distribution to accumulation, followed by a continuation breakout.

### Identification Criteria (Daily/Weekly Chart)
1. **Cup**: A rounded, U-shaped bottom forming over 1-6 months. V-shaped bottoms are less reliable
2. **Cup depth**: Typically retraces 12-33% of the prior advance (deeper cups up to 50% can work but are riskier)
3. **Handle**: A short pullback forming in the upper third of the cup, lasting 1-4 weeks
4. **Handle characteristics**: Slight downward drift on declining volume; handle should NOT retrace more than 50% of the cup's depth
5. **Volume**: Declining through the cup's right side; very light during handle formation

### Breakout Confirmation
- **Breakout signal**: Daily close above the handle's upper boundary (resistance line)
- **Volume confirmation**: Volume must expand significantly on the breakout day
- **Alternative entry**: If the handle forms a bull flag, apply bull flag entry rules

### Target Measurement
- **Minimum target**: Cup depth (distance from cup rim to cup bottom) projected upward from the breakout point
- **Conservative target**: 50-75% of cup depth

### Stop-Loss Placement
- Place the stop below the handle's lowest point

### Key Notes
- The cup-and-handle is a continuation pattern — it works best in established uptrends
- Cup rims should be approximately equal in height (left and right sides)
- Weekly cup-and-handle patterns produce larger, more reliable moves than daily patterns
- Volume pattern is critical: declining through cup formation, light in handle, surge at breakout

---

## Pattern 7: Descending Wedge Breakout (Falling Wedge)

### Definition
Two converging downward-sloping trendlines containing price action. Despite the downward slope, this is typically a bullish pattern — a controlled descent that resolves with an upward breakout.

### Identification Criteria (Daily/Weekly Chart)
1. **Upper boundary**: Connects successive lower highs (resistance line slopes down)
2. **Lower boundary**: Connects successive lower lows (support line slopes down, but less steeply)
3. **Convergence**: The two lines must converge — the range narrows over time
4. **Duration**: Typically 3 weeks to 3 months on daily charts; longer on weekly charts
5. **Volume**: Progressively declining during the wedge formation

### Breakout Confirmation
- **Breakout signal**: Daily close above the upper boundary of the wedge
- **Volume confirmation**: Notable volume expansion on the breakout day
- **Pullback test**: A throwback to the broken upper boundary on declining volume confirms

### Target Measurement
- **Minimum target**: The widest part of the wedge (height at entry) projected upward from the breakout point
- **Alternative**: If the wedge is a correction within an uptrend, the target equals the prior advance's length

### Stop-Loss Placement
- Place the stop below the last swing low within the wedge

### Descending Wedge vs Descending Triangle
| Feature | Descending Wedge (Bullish) | Descending Triangle (Bearish) |
|---------|---------------------------|------------------------------|
| Support line | Slopes downward | Horizontal (flat) |
| Resolution | Upward breakout (typically) | Downward breakdown (typically) |
| Volume | Declining throughout | Declining, then expanding on breakdown |

### Weekly/Monthly Reference
- Weekly descending wedges often mark the end of multi-month corrections
- Monthly breakout from a descending wedge is a powerful long-term reversal signal
- If the wedge breakout coincides with a monthly close above a previous high, the signal is significantly stronger

---

## Pattern 8: Converging/Symmetrical Triangle

### Definition
Two converging trendlines — one descending from lower highs, one ascending from higher lows — forming a coiling price pattern. This is a neutral pattern that breaks in the direction of the prevailing trend.

### Identification Criteria (Daily Chart)
1. **Upper boundary**: At least two lower highs
2. **Lower boundary**: At least two higher lows
3. **Convergence**: Lines converge toward an apex
4. **Duration**: Typically 1-3 months; breakout usually occurs between 50-75% of the way to the apex
5. **Volume**: Progressively declining during formation

### Breakout Confirmation
- **Breakout signal**: Daily close beyond either boundary with expanded volume
- **Direction bias**: In an uptrend, expect upward breakout; in a downtrend, expect downward
- **Timing**: Breakouts occurring after 75% of the way to the apex are less reliable

### Target Measurement
- **Minimum target**: Height of the triangle (widest part) projected from the breakout point

### Stop-Loss Placement
- Place the stop on the other side of the triangle from the breakout direction

---

## Output Format

When presenting technical analysis, use this structured format:

```
### Market Environment
| Dimension | Direction | Description |
|-----------|-----------|-------------|
| Daily Trend | uptrend/downtrend/sideways | Description with evidence |
| Weekly Trend | uptrend/downtrend/sideways | Description with evidence |
| Wyckoff Phase | accumulation/markup/distribution/markdown | Phase with evidence |
| Trend Maturity | early/middle/late | Assessment of how far the trend has progressed |

### Pattern Identification
Primary Pattern: [Pattern Name] — [Status: forming/confirmed/failed]
[Description of pattern elements with specific price levels]

### Breakout + Volume Confirmation Status
| Pattern | Breakout Status | Volume | Assessment |
|---------|----------------|--------|------------|
| [Name] | confirmed/pending/failed | expanded/declining/neutral | [one-liner] |

### Key Price Levels
| Type | Price Level | Significance |
|------|------------|--------------|
| Immediate Support | $XX | Description |
| Strong Support | $XX | Description |
| Major Support | $XX | Description |
| Immediate Resistance | $XX | Description |
| Major Resistance | $XX | Description |

### Wyckoff Phase Analysis
| Element | Observation |
|---------|-------------|
| [Wyckoff element] | Evidence from price/volume action |
| Current Phase | [Phase name] with confidence level |

### Comprehensive Assessment
| Field | Value |
|-------|-------|
| Technical Posture | bullish/cautiously_bullish/neutral/cautiously_bearish/bearish |
| Trend-Volume Alignment | aligned/divergent |
| Phase-Trend Consistency | consistent/inconsistent |
| Key Inflection Point | $XX — [rationale] |
| Candlestick Signal | [strongest pattern and location] |
```

---

## Technical-Fundamental Resonance

When technical analysis is performed alongside fundamental analysis, assess whether technical signals CONFIRM or CONTRADICT fundamental conclusions:

### Resonance Assessment
| Dimension | Technical Signal | Fundamental Signal | Alignment |
|-----------|-----------------|-------------------|-----------|
| Direction | bullish/bearish pattern | positive/negative thesis | aligned/divergent |
| Timing | breakout imminent/confirmed | catalyst approaching | synchronized/disconnected |
| Magnitude | pattern target $XX (+XX%) | fair value $XX (+XX%) | consistent/inconsistent |

### Resonance Classification
- **Strong Resonance**: Technical breakout aligns with fundamental catalyst (e.g., W bottom breakout on earnings beat) — HIGH CONFIDENCE
- **Moderate Resonance**: Technical is neutral while fundamental is positive (or vice versa) — MEDIUM CONFIDENCE
- **Divergence**: Technical bearish while fundamental bullish (or vice versa) — CAUTION, investigate which signal is leading

Hard rule: When technical and fundamental signals diverge significantly, the divergence itself is the most important signal — it requires investigation, not automatic resolution.

---

## Integrated Decision Process

### Step 1: Establish Market Context (Daily + Weekly)
1. Determine current daily trend direction (up, down, range-bound)
2. Weekly trend provides the broader directional context
3. Identify the current Wyckoff phase (accumulation, markup, distribution, markdown)

### Step 2: Identify Patterns (Daily Chart)
Prioritize in this order:
1. Is there a Spring / false breakdown? — Highest priority, offers the lowest-risk entry
2. Is there a bull flag? — Continuation signal within an uptrend
3. Is there a W bottom or inverse H&S? — Bottom reversal signal
4. Is the monthly chart breaking a previous high? — Long-term confirmation

### Step 3: Wait for Breakout + Volume Confirmation
- Observe volume on the breakout day
- Do not enter prematurely — wait for the breakout to be confirmed

### Step 4: Entry & Risk Management
- **Entry point**: The low-volume pullback test after the confirmed breakout (lowest risk)
- **Stop-loss**: Below the pattern's key low
- **Target**: Based on pattern measurement rules
- **Iron rule**: After entry, you must see demand follow through (consecutive bullish candles + steadily rising volume) — otherwise, exit

---

## Pattern Failure & Risk Management

### Universal Failure Signals
- No follow-through after breakout (no volume, no new high)
- Bearish high-volume candle appears after breakout (supply expanding)
- Abnormal volume pattern (no volume on breakout, or heavy volume during consolidation)

### Pattern-Specific Failure Conditions
- **Bull flag**: Consolidation exceeds 4 weeks; pullback exceeds 2/3 of flagpole; no volume on breakout
- **W bottom**: Right bottom breaks below left bottom and cannot recover (not a Spring); neckline breaks then falls back on heavy volume
- **Inverse H&S**: Right shoulder volume exceeds head volume (supply not exhausted); neckline breaks then falls back below on heavy volume
- **Spring**: Post-Spring rally is weak (no demand); consecutive failed Springs (uptrend ending warning)
- **Monthly breakout**: Following month closes back below the previous high

### Wyckoff Risk Management Principles
1. The theoretical basis for the trade must be established (supply/demand confirmation)
2. If market action negates your thesis after entry -> exit immediately
3. Do not substitute hope or emotion for market behavior
4. Do not trade inside a trading range — wait for SOS or SOW on the right-hand side

---

## Candlestick Confirmation (Nison)

At breakout points, the following candlestick patterns strengthen the signal:

### Bullish Confirmation Candles
- **Hammer**: Long lower shadow, small real body near the top — bottom reversal signal
- **Bullish Engulfing**: Bullish candle completely engulfs the prior bearish candle — demand overwhelms supply
- **Morning Star**: Three-candle combination (long bearish + small body + long bullish) — bottom reversal
- **Piercing Line**: Bullish candle closes above the midpoint of the prior bearish candle — demand entering

### Application to Each Pattern
- Hammer at the W bottom's right low -> strengthens reversal signal
- Bullish engulfing at the Spring location -> confirms strong demand
- Morning star at the inverse H&S right shoulder low -> strengthens buy signal
- Bullish engulfing on the bull flag breakout day -> increases breakout reliability

---

## Money Management (Murphy's Principles)

### Position Sizing
- Risk per trade: no more than **5%** of total capital
- Exposure per market: no more than **10-15%** of total capital
- Total invested capital: no more than **50%** of total capital

### Reward-to-Risk Ratio
- Minimum requirement: **3:1** (potential profit must be at least 3x potential loss)
- Calculate using the pattern's measured target and the stop-loss distance

### Adding to Positions
- Pyramid style: each addition is smaller than the previous one
- **Only add to winning positions — never add to losing positions**
- After adding, move the stop to breakeven or above

---

## Glossary

| Abbreviation | Full Name | Description |
|--------------|-----------|-------------|
| CM | Composite Man | Institutional operators / smart money |
| Spring | Spring | False breakdown reversal (Wyckoff) |
| SOS | Sign of Strength | Demand takes control; often a strong rally breaking out of a range |
| SOW | Sign of Weakness | Supply takes control; often a sharp decline breaking support |
| JOC | Jump over the Creek | Price leaps above the trading range's supply zone |
| UT | Upthrust | False upward breakout that reverses back into the range |
| SOT | Shortening of Thrust | Diminishing breakout distance — trend exhaustion signal |
| LPS | Last Point of Support | Low-risk pullback entry after an SOS |
| LPSY | Last Point of Supply | Low-risk short entry after an SOW |
| BC | Buying Climax | Frenzied public buying at the top — supply floods in |
| SC | Selling Climax | Panic selling at the bottom — demand absorbs supply |
| AR | Automatic Rally / Reaction | Natural bounce (bottom) or natural pullback (top) after a climax |
| ST | Secondary Test | Retest of the climax area to confirm supply/demand shift |
| PS | Preliminary Support | First sign of demand during a downtrend |
