# Technical Analysis Patterns

A pattern-based technical analysis skill for [Claude Code](https://claude.ai/claude-code), covering five core chart patterns with precise identification rules, breakout confirmation criteria, and risk management guidelines.

Synthesized from three classic technical analysis books:

- **Technical Analysis of the Futures Markets** (John J. Murphy)
- **Japanese Candlestick Charting Techniques** (Steve Nison)
- **Wyckoff Method** (Edward Meng)

## Patterns Covered

| Pattern | Timeframe | Monthly Check |
|---------|-----------|---------------|
| Bull Flag Breakout | Daily | Not needed |
| W Bottom (Double Bottom) | Daily | Resonance boost |
| Inverse Head & Shoulders | Daily | Resonance boost |
| Spring / False Breakdown (Wyckoff) | Daily | N/A |
| Monthly Breaking Previous High | Monthly | Core signal |

## Key Principles

- **Daily chart is core** for all pattern identification and trade execution
- **Weekly chart is reference** for trend context and support/resistance validation
- **Monthly chart** is only checked for "breaking previous high" signals
- **Volume matters only at the breakout moment** -- no need to analyze volume during consolidation
- **Supply & demand** (Wyckoff theory) is the foundation for all pattern analysis

## Installation

### As a Claude Code Skill

Copy the `SKILL.md` file to your Claude Code skills directory:

```bash
mkdir -p ~/.claude/skills/technical-analysis
cp SKILL.md ~/.claude/skills/technical-analysis/SKILL.md
```

The skill will automatically appear in your Claude Code session and be invoked when discussing technical analysis topics.

### Manual Reference

You can also use `SKILL.md` as a standalone reference guide for chart pattern trading.

## What's Inside

### Pattern Identification Rules
Each pattern includes:
- Formation conditions and identification checklist
- Breakout confirmation criteria (price + volume)
- Target measurement methods
- Stop-loss placement rules
- Pattern-specific failure conditions

### Wyckoff Supply/Demand Framework
- Accumulation & distribution stages
- Spring (false breakdown) classification -- 3 types based on volume
- SOS (Sign of Strength) and SOW (Sign of Weakness) signals
- CM (Composite Man) behavior analysis

### Candlestick Confirmation (Nison)
- Bullish confirmation candles at breakout points (hammer, engulfing, morning star)
- Pattern-candle integration rules

### Money Management (Murphy)
- Position sizing: max 5% risk per trade
- Reward-to-risk ratio: minimum 3:1
- Pyramid adding rules

### Complete Glossary
All Wyckoff terminology with English abbreviations and Chinese translations.

## Disclaimer

This skill is for **educational and informational purposes only**. It does not constitute financial advice, investment advice, or trading advice. Trading involves substantial risk of loss and is not suitable for every investor.

- Past performance does not guarantee future results
- Always do your own research before making any investment decisions
- The authors are not responsible for any financial losses incurred from using this material

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

Areas where contributions are especially valuable:
- Additional real-world pattern examples
- Translations to other languages
- Integration with other trading frameworks
- Corrections or refinements to pattern rules

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

This skill was created by synthesizing knowledge from:
- John J. Murphy -- *Technical Analysis of the Futures Markets*
- Steve Nison -- *Japanese Candlestick Charting Techniques*
- Edward Meng -- *Wyckoff Method* (Trades About to Happen)
- Richard D. Wyckoff -- original Wyckoff trading methodology
