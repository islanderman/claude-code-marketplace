---
name: portfolio-analysis
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: "Run institutional-grade portfolio analysis across 15 quantitative finance firm methodologies in parallel, generating a comprehensive PDF report with visualizations and reallocation recommendations."
command: /portfolio-analysis
arguments:
  - name: portfolio
    description: "Path to portfolio file (CSV/JSON) or inline portfolio specification"
    required: true
  - name: timeframe
    description: "Reallocation suggestion timeframe: weekly, quarterly, or overall"
    required: false
category: finance-pack
skill_ref: portfolio-deep-analysis
---

# /portfolio-analysis

Activate EXPERT MODE with ULTRATHINK: execute the full portfolio deep analysis pipeline with systematic precision.

## Purpose

This command orchestrates the complete portfolio analysis workflow: parsing the user's portfolio, validating holdings, launching 15 firm-based analytical agents in parallel, synthesizing their outputs, generating visualizations, and compiling a comprehensive PDF report with actionable reallocation recommendations.

---

## Workflow

### Step 1: Input Parsing

Accept the portfolio from one of these sources:

**File path argument:**
```
/portfolio-analysis ./my-portfolio.csv
/portfolio-analysis /path/to/portfolio.json
```

**Inline specification (when no file is provided):**
```
/portfolio-analysis "150 AAPL, 80 MSFT, 45 GOOGL, 60 AMZN, 100 NVDA"
```

**Parsing logic:**
1. If the argument is a valid file path, read the file and detect format (CSV or JSON) by extension and content structure
2. If the argument is not a file path, parse as inline text -- extract ticker symbols and share counts using pattern matching
3. If a screenshot path is provided, use the bloomberg-data-pipeline agent to OCR-extract holdings
4. Normalize all inputs into a standard internal format:
```json
[
  {"ticker": "AAPL", "shares": 150, "cost_basis": null, "entry_date": null},
  {"ticker": "MSFT", "shares": 80, "cost_basis": null, "entry_date": null}
]
```

### Step 2: Validation

Run portfolio validation checks before launching the analysis pipeline. Use step-by-step verification:

1. **Resolve tickers** -- Verify each ticker against known market data. For unrecognized tickers, search for close matches and present suggestions to the user.
2. **Compute weights** -- If shares are provided, fetch current prices and compute portfolio weights. If weights are provided, verify they sum to 100%.
3. **Check data availability** -- Confirm sufficient historical data exists for each holding. Flag holdings with limited history (<1 year).
4. **Detect asset classes** -- Classify each holding (US equity, international equity, fixed income, commodity, REIT, crypto, ETF).
5. **Run pre-analysis skills:**
   - `valuation-sanity-check` on all equity holdings
   - `portfolio-overlap-detector` to identify redundant positions

**If validation fails critically** (>50% of tickers unresolvable or total portfolio value cannot be computed), halt and report errors to the user.

**If validation has warnings** (limited data, minor overlaps), log warnings and proceed.

### Step 3: Timeframe Selection

If the `timeframe` argument was not provided, ask the user before proceeding.

**Question to present:**
```
Before running the analysis, I need to know your preferred timeframe for
reallocation recommendations:

1. Weekly   -- Tactical adjustments driven by momentum and near-term catalysts.
               Higher turnover. Best for active traders.
2. Quarterly -- Strategic rebalancing driven by factor and macro analysis.
               Moderate turnover. Best for most investors.
3. Overall  -- Long-term structural improvements driven by fundamentals.
               Low turnover. Best for long-term or retirement accounts.

Which timeframe would you like? (1/2/3)
```

Wait for the user's response before proceeding to Step 4.

### Step 4: Parallel Agent Execution

Launch all 15 firm agents simultaneously. Each agent receives the validated portfolio data and operates independently.

**Execution pattern -- all launch in a single parallel batch:**

```
Tier 1 -- Foundational:
  Task(finance-pack:bloomberg-data-pipeline,
    "Fetch and validate market data for portfolio: [holdings_json].
     Return: current prices, fundamentals (P/E, P/B, revenue growth, margins,
     debt ratios), dividend history, earnings calendar, corporate actions.
     Flag any data quality issues.")

  Task(finance-pack:aqr-factor-model-builder,
    "Decompose portfolio factor exposures: [holdings_json].
     Apply Fama-French 5-factor + momentum + quality model.
     Return: per-holding factor loadings, portfolio aggregate exposures,
     factor contribution to historical returns, crowding score,
     benchmark comparison.")

  Task(finance-pack:man-group-portfolio-optimizer,
    "Optimize portfolio allocation: [holdings_json].
     Run mean-variance, Black-Litterman, and risk-parity optimization.
     Return: efficient frontier, optimal weights (min-var, max-Sharpe,
     risk-parity), current portfolio position on frontier, marginal risk
     contributions, rebalancing trades to reach optimal.")

Tier 2 -- Strategy & Signals:
  Task(finance-pack:gs-quant-strategy-architect,
    "Evaluate portfolio strategy alignment: [holdings_json].
     Detect implicit systematic strategy, score coherence, identify drift.
     Return: detected strategy, coherence score (0-100), deviating holdings,
     strategy attribution, refinement recommendations.")

  Task(finance-pack:citadel-alpha-signal-research,
    "Score alpha signals for portfolio: [holdings_json].
     Compute composite alpha across momentum, earnings, fundamental, sentiment,
     and flow signals. Return: per-holding alpha score (-100 to +100), signal
     decomposition, conviction level, ranked holdings, decay analysis.")

  Task(finance-pack:point72-ml-alpha-researcher,
    "ML prediction for portfolio holdings: [holdings_json].
     Run ensemble models for 1M/3M/6M return predictions.
     Return: per-holding predicted returns with 80% confidence intervals,
     prediction confidence, top 5 features per holding, portfolio-level
     forecast, uncertainty flags.")

  Task(finance-pack:bridgewater-macro-strategist,
    "Assess macro regime and portfolio alignment: [holdings_json].
     Classify current regime (growth x inflation quadrant), compute
     transition probabilities. Return: regime classification, transition
     matrix, per-holding regime sensitivity, portfolio alignment score,
     misaligned holdings, hedging recommendations.")

  Task(finance-pack:de-shaw-stat-arb,
    "Identify stat-arb opportunities in portfolio: [holdings_json].
     Analyze pairs, relative value dislocations, mean-reversion setups.
     Return: cointegrated pairs, relative value signals, mean-reversion
     scores, intra-portfolio arb opportunities, spread forecasts.")

Tier 3 -- Risk & Execution:
  Task(finance-pack:two-sigma-risk-management,
    "Full risk assessment for portfolio: [holdings_json].
     Compute VaR (parametric, historical, Monte Carlo), CVaR, drawdown
     analysis, correlation regimes, stress tests (2008, 2020, 2022,
     rate spike, recession, geopolitical). Return: VaR table, CVaR,
     drawdown analysis, correlation matrix, stress results, tail metrics,
     risk concentration analysis.")

  Task(finance-pack:rentech-backtesting-engine,
    "Backtest portfolio allocation: [holdings_json].
     Walk-forward analysis over 20+ years, test across market regimes.
     Return: equity curve, rolling Sharpe, crisis performance, regime
     returns, turnover-adjusted metrics, out-of-sample validation.")

  Task(finance-pack:dimensional-factor-backtester,
    "Long-term factor premium analysis: [holdings_json].
     Analyze historical factor premium capture, persistence, cyclicality,
     current valuations. Return: premium capture, persistence scores,
     factor valuations, expected return decomposition, timing signals.")

  Task(finance-pack:jane-street-market-making,
    "Liquidity assessment for portfolio: [holdings_json].
     Evaluate bid-ask spreads, volume, depth, price impact for each holding.
     Return: per-holding liquidity score (1-10), spread analysis, volume
     and days-to-liquidate, impact estimates, portfolio liquidity score,
     illiquidity premium assessment.")

  Task(finance-pack:virtu-execution-algorithm,
    "Execution cost modeling for portfolio: [holdings_json].
     Estimate all-in costs for rebalancing using Almgren-Chriss.
     Return: per-trade cost estimates, optimal schedule, implementation
     shortfall, strategy comparison, net-of-cost benefit, break-even
     horizon per trade.")

Tier 4 -- Compliance & Implementation:
  Task(finance-pack:gs-algo-compliance,
    "Regulatory and tax analysis for portfolio: [holdings_json].
     Screen for wash sales, concentration limits, compute tax implications.
     Return: wash sale risks, tax lot analysis, tax-loss harvesting
     opportunities, estimated tax impact, compliance flags, tax-optimized
     rebalancing alternative.")

  Task(finance-pack:millennium-live-trading,
    "Implementation plan for portfolio changes: [holdings_json].
     Translate recommendations into execution plan with order types,
     routing, timing, risk controls. Return: order plan, routing
     recommendations, pre-trade checks, timeline, reconciliation
     checklist, monitoring specs.")
```

### Step 5: Result Collection

Wait for all 15 agents to complete. Track completion status:

```
Agent Status Tracker:
  [DONE] bloomberg-data-pipeline      (23s)
  [DONE] aqr-factor-model-builder     (45s)
  [DONE] man-group-portfolio-optimizer (67s)
  [DONE] gs-quant-strategy-architect   (38s)
  [DONE] citadel-alpha-signal-research (52s)
  [DONE] point72-ml-alpha-researcher   (71s)
  [DONE] bridgewater-macro-strategist  (41s)
  [DONE] de-shaw-stat-arb             (55s)
  [DONE] two-sigma-risk-management    (88s)
  [DONE] rentech-backtesting-engine   (94s)
  [DONE] dimensional-factor-backtester (63s)
  [DONE] jane-street-market-making    (29s)
  [DONE] virtu-execution-algorithm    (47s)
  [DONE] gs-algo-compliance           (36s)
  [DONE] millennium-live-trading      (33s)

  15/15 complete. Proceeding to synthesis.
```

**Failure handling:**
- If an agent times out (>120s), mark it as FAILED and continue
- If fewer than 8 agents complete, abort the analysis and report failures to the user
- If 8-14 agents complete, proceed with a degraded analysis and flag missing components in the report

### Step 6: Synthesis

Apply the synthesis framework defined in the `portfolio-deep-analysis` skill:

1. **Classify each agent's stance** on each holding (bullish / neutral / bearish)
2. **Compute consensus scores** for each holding using the formula:
   `consensus = (bullish - bearish) / agents_with_opinion`
3. **Apply domain-specific conflict weighting** when agents disagree
4. **Compute confidence-weighted recommendations** combining agent conviction, consensus strength, and data quality
5. **Compare risk-adjusted returns** for current portfolio vs recommended portfolio vs benchmark
6. **Generate reallocation trades** for the user's selected timeframe

### Step 7: Visualization Generation

Generate all charts using Python. Write a temporary Python script and execute it:

```python
# Generate portfolio analysis visualizations
import matplotlib
matplotlib.use('Agg')  # Non-interactive backend
import matplotlib.pyplot as plt
import matplotlib.gridspec as gridspec
import numpy as np
import json
import os

output_dir = os.path.join(os.getcwd(), 'portfolio_analysis_charts')
os.makedirs(output_dir, exist_ok=True)

# Data from synthesis (passed as JSON)
portfolio_data = json.loads('''{ ... }''')

# 1. Allocation pie charts (current vs recommended) -- side by side
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(14, 6))
# ... render current and recommended allocations
fig.savefig(os.path.join(output_dir, '01_allocation_comparison.png'), dpi=150, bbox_inches='tight')

# 2. Correlation heatmap
fig, ax = plt.subplots(figsize=(12, 10))
# ... render correlation matrix with color coding
fig.savefig(os.path.join(output_dir, '02_correlation_heatmap.png'), dpi=150, bbox_inches='tight')

# 3. Historical drawdown chart
fig, ax = plt.subplots(figsize=(14, 6))
# ... render drawdown time series with crisis annotations
fig.savefig(os.path.join(output_dir, '03_drawdown_chart.png'), dpi=150, bbox_inches='tight')

# 4. Factor exposure radar chart
fig, ax = plt.subplots(figsize=(8, 8), subplot_kw=dict(polar=True))
# ... render 7-factor radar: MKT, SMB, HML, RMW, CMA, UMD, QMJ
fig.savefig(os.path.join(output_dir, '04_factor_radar.png'), dpi=150, bbox_inches='tight')

# 5. Efficient frontier
fig, ax = plt.subplots(figsize=(12, 8))
# ... render frontier curve, current portfolio, optimal points, individual holdings
fig.savefig(os.path.join(output_dir, '05_efficient_frontier.png'), dpi=150, bbox_inches='tight')

# 6. Sector exposure grouped bar chart
fig, ax = plt.subplots(figsize=(14, 6))
# ... render current vs recommended vs benchmark sector weights
fig.savefig(os.path.join(output_dir, '06_sector_exposure.png'), dpi=150, bbox_inches='tight')

# 7. Performance attribution waterfall
fig, ax = plt.subplots(figsize=(12, 6))
# ... render allocation, selection, interaction effects
fig.savefig(os.path.join(output_dir, '07_performance_attribution.png'), dpi=150, bbox_inches='tight')

# 8. Risk contribution stacked bar chart
fig, ax = plt.subplots(figsize=(14, 6))
# ... render each holding's contribution to total portfolio risk
fig.savefig(os.path.join(output_dir, '08_risk_contribution.png'), dpi=150, bbox_inches='tight')

# 9. Signal strength heatmap
fig, ax = plt.subplots(figsize=(14, 8))
# ... render holdings x signal_types heatmap
fig.savefig(os.path.join(output_dir, '09_signal_heatmap.png'), dpi=150, bbox_inches='tight')

# 10. Consensus bar chart
fig, ax = plt.subplots(figsize=(14, 6))
# ... render per-holding consensus with bullish/neutral/bearish decomposition
fig.savefig(os.path.join(output_dir, '10_consensus_scores.png'), dpi=150, bbox_inches='tight')

plt.close('all')
print(f"Charts saved to {output_dir}")
```

### Step 8: PDF Generation

Compile all sections into a formatted PDF report. Use Python with `reportlab` or `fpdf2`:

```python
from fpdf import FPDF
import os

class PortfolioReport(FPDF):
    def header(self):
        self.set_font('Helvetica', 'B', 10)
        self.cell(0, 8, 'Portfolio Deep Analysis Report', align='C', new_x='LMARGIN', new_y='NEXT')
        self.line(10, self.get_y(), 200, self.get_y())
        self.ln(4)

    def footer(self):
        self.set_y(-15)
        self.set_font('Helvetica', 'I', 8)
        self.cell(0, 10, f'Page {self.page_no()}/{{nb}}', align='C')

pdf = PortfolioReport()
pdf.alias_nb_pages()
pdf.set_auto_page_break(auto=True, margin=20)

# Section 1: Executive Summary
pdf.add_page()
pdf.set_font('Helvetica', 'B', 18)
pdf.cell(0, 12, 'Executive Summary', new_x='LMARGIN', new_y='NEXT')
# ... populate with synthesis data

# Section 2: Portfolio Overview + allocation charts
pdf.add_page()
pdf.image('portfolio_analysis_charts/01_allocation_comparison.png', w=180)

# Section 3: Per-Holding Analysis (iterate over holdings)
# Section 4: Risk Dashboard + risk visualizations
# Section 5: Factor Exposure Analysis + radar chart
# Section 6: Macro Regime Assessment
# Section 7: Alpha Signal Summary + signal heatmap
# Section 8: Optimization Results + efficient frontier
# Section 9: Reallocation Recommendations
# Section 10: Compliance & Tax Summary
# Section 11: Appendix -- Firm-by-Firm Detail

output_path = os.path.join(os.getcwd(), 'portfolio_analysis_report.pdf')
pdf.output(output_path)
print(f"Report saved to {output_path}")
```

### Step 9: Delivery

Present results to the user in two formats:

**Console summary (always shown):**
```
=== Portfolio Deep Analysis Complete ===

Overall Health Score: [XX]/100
Holdings Analyzed: [N]
Firms Consulted: [15/15] (or [N/15] if some failed)
Timeframe: [Weekly/Quarterly/Overall]

TOP 3 FINDINGS:
1. [Most significant finding]
2. [Second most significant finding]
3. [Third most significant finding]

TOP 3 RECOMMENDATIONS:
1. [Highest confidence trade] (Confidence: [HIGH/MED/LOW])
2. [Second highest confidence trade] (Confidence: [HIGH/MED/LOW])
3. [Third highest confidence trade] (Confidence: [HIGH/MED/LOW])

RISK SNAPSHOT:
  Portfolio VaR (95%, 1M): $[amount] ([%] of portfolio)
  Max Historical Drawdown: [%]
  Sharpe Ratio (trailing 1Y): [ratio]

Full report saved to: ./portfolio_analysis_report.pdf
Chart files saved to: ./portfolio_analysis_charts/
```

**PDF report:** Saved to the current working directory as `portfolio_analysis_report.pdf`.

---

## Error Handling

### Input Errors

| Error | Response |
|-------|----------|
| File not found | Report the error, ask user to verify the path |
| Unparseable file format | Report what was expected vs what was found, suggest corrections |
| No valid tickers found | Report the parsing failure, show the raw input and ask for clarification |
| Empty portfolio | Report that no holdings were detected, ask for portfolio input |

### Agent Execution Errors

| Error | Response |
|-------|----------|
| Single agent timeout | Log failure, continue with remaining 14 agents, flag gap in report |
| Multiple agent timeouts (3+) | Warn user about degraded analysis quality, proceed if 8+ agents completed |
| Catastrophic failure (<8 agents) | Abort analysis, report which agents failed and suggest re-running |
| Data fetch failure (Bloomberg) | Attempt fallback data source, proceed with limited data if partial |

### Synthesis Errors

| Error | Response |
|-------|----------|
| Insufficient data for consensus | Lower confidence score, flag holdings with limited coverage |
| All agents neutral on a holding | Report as "No Signal" rather than "Hold" to distinguish from active Hold |
| Conflicting risk assessments | Present the range of risk estimates rather than a single number |

### Output Errors

| Error | Response |
|-------|----------|
| Visualization generation fails | Skip failed chart, note it in the report, continue with remaining charts |
| PDF generation fails | Fall back to markdown report saved as .md file |
| Disk space insufficient | Warn user, output console summary only |

---

## Usage Examples

### Basic usage with CSV file
```
/portfolio-analysis ./portfolio.csv
```

### With explicit timeframe
```
/portfolio-analysis ./portfolio.json quarterly
```

### Inline portfolio specification
```
/portfolio-analysis "100 AAPL, 50 MSFT, 75 GOOGL, 40 AMZN, 60 NVDA"
```

### With cost basis in inline format
```
/portfolio-analysis "100 AAPL @150, 50 MSFT @280, 75 GOOGL @130"
```

---

## Dependencies

### Required Python packages (installed automatically if missing)
- `matplotlib` -- Static chart generation
- `numpy` -- Numerical computations
- `fpdf2` -- PDF report generation
- `Pillow` -- Image handling for PDF embedding

### Required skill
- `portfolio-deep-analysis` -- Full knowledge base for the analysis pipeline, synthesis framework, and report structure

### Required agents (all 15)
- `finance-pack:bloomberg-data-pipeline`
- `finance-pack:aqr-factor-model-builder`
- `finance-pack:man-group-portfolio-optimizer`
- `finance-pack:gs-quant-strategy-architect`
- `finance-pack:citadel-alpha-signal-research`
- `finance-pack:point72-ml-alpha-researcher`
- `finance-pack:bridgewater-macro-strategist`
- `finance-pack:de-shaw-stat-arb`
- `finance-pack:two-sigma-risk-management`
- `finance-pack:rentech-backtesting-engine`
- `finance-pack:dimensional-factor-backtester`
- `finance-pack:jane-street-market-making`
- `finance-pack:virtu-execution-algorithm`
- `finance-pack:gs-algo-compliance`
- `finance-pack:millennium-live-trading`

### Optional skills (enhance analysis if available)
- `valuation-sanity-check` -- Pre-analysis valuation screening
- `portfolio-overlap-detector` -- Redundant position detection
- `sector-theme-mapper` -- Thematic exposure mapping
- `catalyst-timeline-builder` -- Forward event calendar
