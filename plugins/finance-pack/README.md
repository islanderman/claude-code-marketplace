# finance-pack

Institutional-grade quantitative finance toolkit for Claude Code. Analyze portfolios, manage risk, research alpha signals, and design systematic trading strategies using methodologies from the world's leading quantitative finance firms.

## What's Included

### Skills (11 analytical frameworks)

| Skill | Purpose |
|-------|---------|
| `adversarial-business-model` | Skeptical acquirer lens — stress-test revenue, growth, and moats |
| `bull-bear-steelman` | Maximum-strength adversarial argumentation on both sides |
| `catalyst-timeline-builder` | Prioritized catalyst timeline with impact scoring and response matrices |
| `competitive-moat-audit` | 6-dimension moat scoring with trajectory and disruptor analysis |
| `earnings-call-translator` | Forensic linguistics on management language and dodge detection |
| `filing-decoder` | SEC filing forensics — accounting red flags, cash flow analysis |
| `investment-thesis-one-pager` | Strict-format thesis with scenario analysis and drawdown plan |
| `portfolio-overlap-detector` | Hidden correlations, factor concentrations, and stress testing |
| `sector-theme-mapper` | Theme-to-value-chain mapping with pure-play scoring |
| `valuation-sanity-check` | Multi-method valuation with implied growth and scenario pricing |
| `portfolio-deep-analysis` | Flagship: orchestrates all 15 agents in parallel |

### Agents (15 firm-based expert personas)

| Agent | Firm | Focus |
|-------|------|-------|
| `gs-quant-strategy-architect` | Goldman Sachs | Systematic trading strategy design |
| `rentech-backtesting-engine` | Renaissance Technologies | Rigorous backtesting and statistical validation |
| `two-sigma-risk-management` | Two Sigma | Risk frameworks, VaR, stress testing |
| `citadel-alpha-signal-research` | Citadel | Alpha signal discovery and decay analysis |
| `jane-street-market-making` | Jane Street | Market-making algorithms and inventory management |
| `aqr-factor-model-builder` | AQR Capital | Multi-factor model construction |
| `de-shaw-stat-arb` | D.E. Shaw | Statistical arbitrage and pairs trading |
| `bridgewater-macro-strategist` | Bridgewater Associates | Macro regime trading and All-Weather allocation |
| `bloomberg-data-pipeline` | Bloomberg | Market data pipeline infrastructure |
| `virtu-execution-algorithm` | Virtu Financial | TWAP/VWAP/IS execution algorithms |
| `point72-ml-alpha-researcher` | Point72 | ML-based alpha signal prediction |
| `man-group-portfolio-optimizer` | Man Group | Portfolio optimization (MVO, Black-Litterman, HRP) |
| `millennium-live-trading` | Millennium Management | Live trading system architecture |
| `dimensional-factor-backtester` | Dimensional Fund Advisors | Factor premium backtesting |
| `gs-algo-compliance` | Goldman Sachs | Algorithmic trading compliance frameworks |

### Commands (1 executable workflow)

| Command | Purpose |
|---------|---------|
| `/portfolio-analysis` | Run all 15 agents in parallel on your portfolio, generate PDF report |

## Usage

### Individual Skills

Ask Claude to use any skill by triggering it naturally:

```
Analyze AAPL's competitive moat
Build the bull and bear case for NVDA
Decode TSLA's latest earnings call
What's the fair value for MSFT?
```

### Portfolio Analysis

Run the full multi-firm analysis:

```
/portfolio-analysis portfolio.csv
```

Or describe your portfolio inline:

```
Analyze my portfolio: AAPL 25%, NVDA 20%, MSFT 15%, GOOGL 15%, AMZN 10%, META 10%, TSLA 5%
```

You will be asked to choose a reallocation timeframe:
- **Weekly** — tactical, momentum-driven adjustments
- **Quarterly** — strategic rebalancing, factor-driven
- **Overall** — long-term allocation, fundamental-driven

### Individual Agents

Invoke specific firm expertise directly:

```
Use the Two Sigma risk management agent to assess my portfolio's VaR
Run the AQR factor model on my holdings
Design a pairs trading strategy using the D.E. Shaw agent
```

## Installation

Install via the Claude Code plugin marketplace:

```
/plugin install finance-pack
```

## Disclaimer

See [DISCLAIMER.md](DISCLAIMER.md) for the full legal disclaimer.

**This plugin provides analytical frameworks for educational and research purposes only. It does not constitute investment advice. See DISCLAIMER.md before use.**
