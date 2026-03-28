---
name: portfolio-deep-analysis
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: "Institutional-grade portfolio analysis that runs your holdings through 15 quantitative finance firm methodologies in parallel, synthesizing results into a comprehensive PDF report with visualizations and actionable reallocation recommendations."
category: finance-pack
agents:
  - finance-pack:gs-quant-strategy-architect
  - finance-pack:rentech-backtesting-engine
  - finance-pack:two-sigma-risk-management
  - finance-pack:citadel-alpha-signal-research
  - finance-pack:jane-street-market-making
  - finance-pack:aqr-factor-model-builder
  - finance-pack:de-shaw-stat-arb
  - finance-pack:bridgewater-macro-strategist
  - finance-pack:bloomberg-data-pipeline
  - finance-pack:virtu-execution-algorithm
  - finance-pack:point72-ml-alpha-researcher
  - finance-pack:man-group-portfolio-optimizer
  - finance-pack:millennium-live-trading
  - finance-pack:dimensional-factor-backtester
  - finance-pack:gs-algo-compliance
triggers:
  - "analyze my portfolio"
  - "portfolio deep analysis"
  - "run portfolio analysis"
  - "comprehensive portfolio review"
  - "institutional portfolio analysis"
  - "multi-firm portfolio analysis"
modes:
  standalone: true
  teammate: true
---

# Portfolio Deep Analysis

Activate ULTRATHINK mode with MAX-PRECISION: use deep, structured, deliberate reasoning across all quantitative dimensions.

## Overview

Portfolio Deep Analysis is the flagship orchestration skill of the finance-pack plugin. It takes a user's portfolio holdings and runs them through 15 independent quantitative finance firm agents in parallel, each applying its own proprietary methodology. The results are synthesized into a unified, institutional-grade analysis with consensus scoring, conflict transparency, and actionable reallocation recommendations delivered as a formatted PDF report with visualizations.

This skill coordinates the full analytical firepower of the finance-pack: data ingestion, factor decomposition, alpha signal scoring, risk assessment, backtesting, optimization, execution cost modeling, and compliance review -- all operating simultaneously, then merged through a rigorous synthesis framework.

---

## 1. Input Requirements

### Portfolio Specification Format

The portfolio must include, at minimum, a ticker symbol and a position size for each holding. Additional fields improve analysis quality.

**Required fields:**
- `ticker` -- Stock/ETF/fund ticker symbol (e.g., AAPL, SPY, BRK.B)
- `shares` OR `weight` -- Either the number of shares held or the percentage weight in portfolio

**Optional fields (improve analysis depth):**
- `cost_basis` -- Average purchase price per share (enables tax-loss harvesting analysis)
- `entry_date` -- Date the position was opened (enables holding period analysis)
- `asset_class` -- Override for non-equity assets (bond, commodity, crypto, option)
- `account_type` -- Taxable, IRA, 401k, Roth (affects tax optimization)

### Supported Input Formats

**CSV file:**
```csv
ticker,shares,cost_basis,entry_date
AAPL,150,142.50,2023-03-15
MSFT,80,285.00,2023-06-01
GOOGL,45,125.30,2024-01-10
AMZN,60,145.00,2023-09-20
NVDA,100,450.00,2024-02-01
```

**JSON file:**
```json
{
  "portfolio": [
    {"ticker": "AAPL", "shares": 150, "cost_basis": 142.50, "entry_date": "2023-03-15"},
    {"ticker": "MSFT", "shares": 80, "cost_basis": 285.00, "entry_date": "2023-06-01"},
    {"ticker": "GOOGL", "shares": 45, "cost_basis": 125.30, "entry_date": "2024-01-10"}
  ],
  "account_type": "taxable",
  "benchmark": "SPY"
}
```

**Plain text (inline):**
```
150 shares AAPL @ $142.50 (bought Mar 2023)
80 shares MSFT @ $285.00 (bought Jun 2023)
45 shares GOOGL @ $125.30 (bought Jan 2024)
```

**Screenshot:** The system can parse brokerage screenshots. The bloomberg-data-pipeline agent extracts ticker/share data using OCR and validates against market data.

### Portfolio Validation

Before launching the analysis pipeline, validate the portfolio with these checks:

1. **Ticker verification** -- Confirm every ticker resolves to an active, tradeable security. Flag delisted or unrecognized symbols with suggested corrections.
2. **Weight normalization** -- If weights are provided, verify they sum to 100% (with a 0.5% tolerance for rounding). If shares are provided, compute weights from current market prices.
3. **Data availability** -- Confirm sufficient historical data exists for each holding (minimum 1 year for factor analysis, 3 years preferred for backtesting). Flag holdings with limited history.
4. **Asset class detection** -- Automatically classify each holding (US equity, international equity, fixed income, commodity, REIT, crypto) for proper factor model assignment.
5. **Concentration check** -- Warn if any single position exceeds 25% of portfolio or if fewer than 5 holdings are present (limited diversification analysis).
6. **Duplicate detection** -- Identify and merge duplicate tickers, flag overlapping ETF holdings (e.g., both SPY and VOO).

---

## 2. Analysis Pipeline: 15 Firms in Parallel

The analysis pipeline operates in four tiers. All tiers launch simultaneously -- the tier structure describes logical dependency, not sequential execution. Each agent receives the validated portfolio and operates independently. The synthesis phase waits for all 15 agents to complete before merging results.

### Tier 1 -- Foundational Analysis

These agents provide the data layer and structural decomposition that other agents' outputs are validated against during synthesis.

#### Bloomberg Data Pipeline Agent
**Role:** Market data acquisition, validation, and enrichment
**Methodology:** Fetch real-time and historical price data, fundamental data (P/E, P/B, revenue growth, margins, debt ratios), dividend history, earnings dates, and corporate actions for every holding. Construct the master data set that all other analyses reference during synthesis cross-validation.
**Output:**
- Current market prices and 52-week ranges for each holding
- Fundamental data matrix (20+ metrics per holding)
- Dividend schedule and yield analysis
- Upcoming earnings dates and corporate event calendar
- Data quality flags (stale data, adjusted prices, stock splits)

#### AQR Factor Model Builder Agent
**Role:** Multi-factor decomposition of portfolio exposures
**Methodology:** Apply the Fama-French five-factor model extended with momentum (UMD) and quality (QMJ) factors. Decompose each holding and the aggregate portfolio into systematic factor exposures. Identify unintended factor bets and factor crowding.
**Output:**
- Per-holding factor loadings: Market (MKT-RF), Size (SMB), Value (HML), Profitability (RMW), Investment (CMA), Momentum (UMD), Quality (QMJ)
- Portfolio-level aggregate factor exposures
- Factor contribution to historical returns (attribution)
- Factor crowding score (how concentrated factor bets are)
- Comparison to benchmark factor profile

#### Man Group Portfolio Optimizer Agent
**Role:** Mean-variance and advanced optimization
**Methodology:** Run Markowitz mean-variance optimization, Black-Litterman with market-implied equilibrium returns, and risk-parity allocation. Generate the efficient frontier and locate the current portfolio relative to it. Propose the minimum-variance, maximum-Sharpe, and risk-parity optimal portfolios.
**Output:**
- Efficient frontier curve with current portfolio position plotted
- Optimal portfolio weights (minimum variance, maximum Sharpe, risk parity)
- Distance from efficient frontier (quantified suboptimality)
- Marginal contribution to risk for each holding
- Rebalancing trades to reach each optimal portfolio

### Tier 2 -- Strategy and Signal Analysis

These agents evaluate the portfolio through the lens of active strategy, alpha generation, and macro context.

#### Goldman Sachs Quant Strategy Architect Agent
**Role:** Systematic strategy alignment assessment
**Methodology:** Evaluate whether the portfolio implicitly or explicitly follows a recognizable systematic strategy (momentum, value rotation, quality growth, dividend income, sector rotation). Score the portfolio's strategic coherence and identify drift from any detected strategy.
**Output:**
- Detected strategy profile (closest matching systematic approach)
- Strategy coherence score (0-100)
- Holdings that deviate from the detected strategy (potential pruning candidates)
- Strategy performance attribution (how much return comes from strategy vs idiosyncratic)
- Recommended strategy refinements

#### Citadel Alpha Signal Research Agent
**Role:** Multi-signal alpha scoring for each holding
**Methodology:** Score every holding across a composite alpha signal framework: price momentum (1M, 3M, 6M, 12M), earnings momentum (revision trends, surprise history), fundamental momentum (margin expansion, revenue acceleration), sentiment signals (analyst consensus shifts, short interest changes), and flow signals (institutional buying/selling patterns).
**Output:**
- Per-holding composite alpha score (-100 to +100)
- Signal decomposition (which signals are positive/negative for each holding)
- Signal conviction level (high/medium/low based on signal agreement)
- Holdings ranked by alpha potential
- Decay analysis (how quickly current signals are likely to fade)

#### Point72 ML Alpha Researcher Agent
**Role:** Machine-learning-based trajectory prediction
**Methodology:** Apply gradient-boosted ensemble models trained on fundamental, technical, and alternative data features to predict each holding's risk-adjusted return over the next 1, 3, and 6 months. Provide prediction intervals and feature importance for interpretability.
**Output:**
- Per-holding predicted return (1M, 3M, 6M) with 80% confidence intervals
- Prediction confidence score per holding
- Top 5 driving features per holding (why the model predicts up or down)
- Portfolio-level expected return and risk forecast
- Model uncertainty flags (holdings where prediction confidence is low)

#### Bridgewater Macro Strategist Agent
**Role:** Macro regime assessment and portfolio alignment
**Methodology:** Identify the current macroeconomic regime using Bridgewater's four-quadrant framework (rising/falling growth crossed with rising/falling inflation). Assess how each holding and the aggregate portfolio perform in the current regime and likely regime transitions.
**Output:**
- Current macro regime classification with confidence level
- Regime transition probabilities (next 3-6 months)
- Per-holding regime sensitivity scores
- Portfolio-level regime alignment score
- Holdings misaligned with current regime (potential risk)
- Macro hedging recommendations

#### D.E. Shaw Statistical Arbitrage Agent
**Role:** Relative value and mean-reversion opportunity identification
**Methodology:** Analyze the portfolio for pairs-trading opportunities, sector-neutral relative value dislocations, and mean-reversion setups among holdings. Identify positions that are statistically cheap or expensive relative to their historical relationships with other portfolio constituents.
**Output:**
- Identified pairs within portfolio with cointegration scores
- Relative value signals (which holdings are cheap/expensive vs peers)
- Mean-reversion probability scores per holding
- Intra-portfolio arbitrage opportunities (long/short within existing holdings)
- Spread compression/expansion forecasts

### Tier 3 -- Risk and Execution Analysis

These agents assess the portfolio's vulnerability, historical behavior, and the practical cost of rebalancing.

#### Two Sigma Risk Management Agent
**Role:** Comprehensive multi-dimensional risk assessment
**Methodology:** Compute Value at Risk (parametric, historical, Monte Carlo), Conditional VaR (Expected Shortfall), maximum drawdown analysis, correlation regime analysis, tail risk assessment, and stress testing against historical crisis scenarios (2008 GFC, 2020 COVID, 2022 rate shock) and hypothetical scenarios (rate spike, recession, geopolitical shock).
**Output:**
- VaR at 95% and 99% confidence (1-day, 1-week, 1-month)
- Expected Shortfall (CVaR) at 95% and 99%
- Maximum drawdown analysis (historical and simulated)
- Correlation matrix with regime-conditional correlations
- Stress test results across 6+ scenarios
- Tail risk metrics (skewness, kurtosis, tail dependence)
- Risk concentration analysis (which holdings drive most portfolio risk)

#### Renaissance Technologies Backtesting Engine Agent
**Role:** Historical scenario backtesting and walk-forward analysis
**Methodology:** Backtest the current portfolio allocation against 20+ years of historical data using walk-forward analysis. Test performance across different market regimes, volatility environments, and crisis periods. Compute rolling risk-adjusted metrics.
**Output:**
- Backtest equity curve with benchmark overlay
- Rolling Sharpe ratio (1Y, 3Y windows)
- Performance in each historical crisis period
- Regime-conditional returns (bull/bear/sideways markets)
- Turnover-adjusted returns (accounting for rebalancing frequency)
- Walk-forward out-of-sample performance metrics

#### Dimensional Factor Backtester Agent
**Role:** Long-term factor premium analysis and persistence testing
**Methodology:** Analyze the portfolio's historical returns through the lens of long-term factor premia. Test whether the portfolio's factor exposures have historically been compensated, assess factor premium persistence and cyclicality, and evaluate whether current factor valuations suggest above or below-average future premia.
**Output:**
- Historical factor premium capture (how much of each factor premium the portfolio harvested)
- Factor premium persistence analysis (are the portfolio's factor bets in factors with durable premia?)
- Factor valuation assessment (are value/momentum/quality cheap or expensive currently?)
- Long-term expected return decomposition (risk-free + factor premia + alpha)
- Factor timing signals (factors likely to outperform in coming period)

#### Jane Street Market Making Agent
**Role:** Liquidity assessment and market microstructure analysis
**Methodology:** Evaluate the liquidity profile of each holding using bid-ask spreads, average daily volume, market depth, and price impact models. Assess portfolio-level liquidity risk and estimate the time required to liquidate various percentages of the portfolio without excessive market impact.
**Output:**
- Per-holding liquidity score (1-10 scale)
- Bid-ask spread analysis (current vs historical average)
- Average daily volume and days-to-liquidate per position
- Price impact estimate for various trade sizes
- Portfolio-level liquidity score
- Illiquidity premium assessment (are illiquid holdings compensating for their illiquidity?)

#### Virtu Execution Algorithm Agent
**Role:** Transaction cost analysis and execution cost modeling
**Methodology:** Estimate the all-in execution costs for any proposed rebalancing trades using market impact models (Almgren-Chriss), commission estimates, spread costs, and timing risk. Optimize execution schedule to minimize total implementation cost.
**Output:**
- Per-trade estimated execution cost (spread + impact + commission)
- Optimal execution schedule (VWAP, TWAP, or IS-optimal)
- Implementation shortfall estimate for full rebalancing
- Cost comparison across execution strategies
- Net-of-cost expected benefit for each proposed trade
- Break-even horizon (when does the expected alpha overcome execution costs?)

### Tier 4 -- Compliance and Implementation

These agents address regulatory, tax, and practical implementation concerns.

#### Goldman Sachs Algo Compliance Agent
**Role:** Regulatory compliance and tax optimization
**Methodology:** Screen the portfolio and any proposed trades for regulatory issues (wash sale violations, concentration limits, restricted lists). Compute tax implications of proposed rebalancing including short-term vs long-term capital gains, tax-loss harvesting opportunities, and estimated tax liability.
**Output:**
- Wash sale risk assessment for proposed trades
- Tax lot analysis with short-term vs long-term classification
- Tax-loss harvesting opportunities with replacement security suggestions
- Estimated tax impact of proposed rebalancing
- Regulatory compliance flags (if any)
- Tax-optimized rebalancing alternative (same target allocation, lower tax cost)

#### Millennium Live Trading Agent
**Role:** Implementation architecture and execution readiness
**Methodology:** Translate recommended portfolio changes into a concrete implementation plan with order types, routing decisions, timing considerations, and risk controls. Design the execution workflow including pre-trade checks, order staging, and post-trade reconciliation.
**Output:**
- Order generation plan (order type, size, limit prices)
- Execution routing recommendations per trade
- Pre-trade risk checks and limits
- Implementation timeline with staging
- Post-trade reconciliation checklist
- Monitoring dashboard specifications for tracking execution

---

## 3. Synthesis Framework

After all 15 agents complete, the synthesis phase merges their outputs into a unified analysis. This phase uses STRATEGIST MODE with breadth-first reasoning to reconcile diverse perspectives.

### Consensus Scoring

For each holding in the portfolio, compute a consensus score based on directional agreement across the firm agents:

**Directional classification per agent:**
- **Bullish**: Agent's output implies the holding should be overweighted or retained (alpha score positive, ML prediction positive, factor exposure favorable, etc.)
- **Neutral**: Agent's output implies no strong directional view
- **Bearish**: Agent's output implies the holding should be underweighted or exited

**Consensus score formula:**
```
consensus_score = (bullish_count - bearish_count) / total_agents_with_opinion
```
Range: -1.0 (unanimous bearish) to +1.0 (unanimous bullish)

**Consensus categories:**
- Strong Buy: consensus >= 0.6 (9+ of 15 agents bullish)
- Buy: consensus >= 0.3
- Hold: consensus between -0.3 and 0.3
- Sell: consensus <= -0.3
- Strong Sell: consensus <= -0.6

### Conflict Resolution

When firm agents disagree on a holding, the synthesis applies a structured conflict resolution protocol:

1. **Identify the disagreement axis** -- Is it about direction (up vs down), magnitude (how much), or timeframe (when)?
2. **Weight by relevance** -- For risk questions, weight Two Sigma and RenTech higher. For alpha questions, weight Citadel and Point72 higher. For execution, weight Jane Street and Virtu higher. For macro, weight Bridgewater higher.
3. **Present both sides transparently** -- Never hide disagreement. The report explicitly states "Citadel rates AAPL +72 alpha score (bullish) while D.E. Shaw identifies mean-reversion signal suggesting near-term pullback."
4. **Confidence-weight the aggregate** -- Agents with higher conviction (narrower confidence intervals, stronger signal strength) receive proportionally more weight.

**Domain-specific conflict weighting:**

| Domain | Primary Weight (2x) | Standard Weight (1x) | Advisory Weight (0.5x) |
|--------|---------------------|----------------------|------------------------|
| Alpha / Direction | Citadel, Point72, GS Strategy | AQR, D.E. Shaw, Bridgewater | Bloomberg, Jane Street |
| Risk Assessment | Two Sigma, RenTech | AQR, Dimensional, Bridgewater | Man Group, D.E. Shaw |
| Factor Analysis | AQR, Dimensional | Man Group, GS Strategy | Bridgewater, Citadel |
| Execution / Liquidity | Jane Street, Virtu | Millennium, Bloomberg | GS Compliance |
| Macro / Regime | Bridgewater | GS Strategy, Two Sigma | AQR, Dimensional |
| Optimization | Man Group | AQR, Dimensional | GS Strategy, Two Sigma |

### Confidence-Weighted Recommendations

Each recommendation carries a composite confidence score:

```
confidence = weighted_average(agent_conviction_scores) * consensus_strength * data_quality_factor
```

Where:
- `agent_conviction_scores` -- Each agent's self-reported confidence in its assessment
- `consensus_strength` -- Absolute value of the consensus score (agreement level)
- `data_quality_factor` -- Penalty for holdings with limited data, stale prices, or low liquidity

Recommendations are categorized:
- **High confidence (>0.7):** Present as primary recommendations with strong emphasis
- **Medium confidence (0.4 - 0.7):** Present as suggested actions with caveats
- **Low confidence (<0.4):** Present as considerations with full disclosure of uncertainty

### Risk-Adjusted Return Comparison

Compute and compare risk-adjusted expected returns for:
- **Current portfolio** -- Based on factor exposures, current signals, and risk metrics
- **Recommended portfolio** -- After applying the highest-confidence reallocation suggestions
- **Benchmark** -- SPY or user-specified benchmark for reference

Metrics for comparison:
- Expected annualized return
- Expected annualized volatility
- Expected Sharpe ratio
- Expected maximum drawdown (95th percentile)
- Expected VaR (95%, 1-month)

---

## 4. Reallocation Recommendations

**CRITICAL: Before generating recommendations, the system MUST ask the user which timeframe they want.**

### Timeframe Selection

Present the user with three options:

- **Weekly** -- Short-term tactical adjustments driven by momentum signals, flow data, and near-term catalysts. Higher turnover, focused on capturing short-term alpha. Best for active traders or tactical overlay accounts.
- **Quarterly** -- Medium-term strategic rebalancing driven by factor exposures, macro regime shifts, and optimization targets. Moderate turnover, focused on maintaining strategic alignment. Best for most investors.
- **Overall** -- Long-term strategic allocation driven by fundamental analysis, long-term factor premia, and portfolio construction principles. Low turnover, focused on structural improvements. Best for long-term investors or retirement accounts.

### Recommendation Format

For each timeframe, provide specific, actionable trades:

**Per-trade specification:**
```
Action: SELL / BUY / TRIM / ADD
Ticker: [symbol]
Current Position: [shares] shares ([weight]% of portfolio)
Recommended Position: [shares] shares ([weight]% of portfolio)
Trade Size: [shares] shares ([dollar_amount])
Rationale: [which firms support this, consensus score, key signals]
Expected Impact:
  - Portfolio Sharpe: [current] -> [projected]
  - Portfolio VaR (95%, 1M): [current] -> [projected]
  - Factor exposure change: [specific factor shifts]
Execution Cost Estimate: [spread + impact + commission]
Tax Impact: [short-term gain/loss, long-term gain/loss, wash sale risk]
Confidence: [HIGH / MEDIUM / LOW]
Supporting Firms: [list of firms that agree]
Dissenting Firms: [list of firms that disagree, with their reasoning]
```

### Weekly Recommendations

Analyze with deliberation using depth-first reasoning for each tactical trade:

- Focus on holdings with strong short-term momentum signals (Citadel alpha score, Point72 ML 1M prediction)
- Incorporate near-term catalysts (earnings dates from Bloomberg, macro events from Bridgewater)
- Size trades conservatively (maximum 5% portfolio rebalance per week)
- Prioritize trades with favorable execution cost profiles (Virtu analysis)
- Check wash sale rules for any sells (GS Compliance)

### Quarterly Recommendations

Apply systematic, multi-layer analysis for strategic rebalancing:

- Target factor exposure alignment with the AQR-recommended profile
- Move toward the Man Group optimizer's recommended allocation (weighted by conviction)
- Address macro regime misalignment identified by Bridgewater
- Harvest tax losses where opportunities exist (GS Compliance)
- Limit turnover to 15-25% of portfolio to control transaction costs
- Sequence trades to minimize market impact (Virtu execution schedule)

### Overall Recommendations

Use STRATEGIST MODE with breadth-first reasoning for long-term structural improvements:

- Assess whether portfolio construction aligns with stated objectives (growth, income, balanced)
- Recommend sector and geographic diversification improvements
- Address concentration risk and correlation clustering
- Optimize factor tilts toward historically compensated premia (Dimensional analysis)
- Consider tax-efficient implementation path that may span multiple quarters
- Evaluate whether current holdings are the best expression of desired exposures (or if substitutes exist)

---

## 5. PDF Report Structure

The final deliverable is a professionally formatted PDF report. Target length: 25-40 pages depending on portfolio complexity.

### Section 1: Executive Summary (1 page)

- Portfolio snapshot: total value, number of holdings, inception date
- Overall health score (composite of all 15 firm assessments, 0-100)
- Top 3 strengths and top 3 risks identified
- Key recommendation summary (top 3 highest-confidence trades)
- Performance vs benchmark (trailing 1M, 3M, 6M, 1Y)

### Section 2: Portfolio Overview (1-2 pages)

- Holdings table with current price, weight, gain/loss, and sector
- Allocation pie chart (by sector)
- Allocation pie chart (by asset class)
- Geographic exposure breakdown
- Market cap distribution (mega, large, mid, small, micro)

### Section 3: Per-Holding Analysis (1 page per holding, or half-page for portfolios >15 holdings)

For each holding:
- Multi-firm consensus score with visual indicator (strong buy to strong sell)
- Alpha signal summary (Citadel composite score, Point72 ML prediction, D.E. Shaw relative value)
- Factor exposure profile (mini radar chart)
- Risk contribution to portfolio
- Liquidity assessment (Jane Street score)
- Key catalysts (earnings dates, macro sensitivity)
- Firm agreement/disagreement summary

### Section 4: Risk Dashboard (2-3 pages)

- VaR summary table (parametric, historical, Monte Carlo at 95% and 99%)
- Expected Shortfall (CVaR) analysis
- Historical drawdown chart with annotated crisis periods
- Correlation heatmap (all holdings)
- Stress test results table (6+ scenarios with portfolio P&L impact)
- Risk concentration chart (which holdings contribute most to portfolio risk)
- Tail risk assessment (skewness, kurtosis visualization)

### Section 5: Factor Exposure Analysis (1-2 pages)

- Factor exposure radar chart (current portfolio vs benchmark)
- Factor contribution to historical returns (stacked bar chart)
- Factor crowding assessment
- Factor valuation status (which factors are cheap/expensive)
- Factor premium persistence analysis (Dimensional output)

### Section 6: Macro Regime Assessment (1 page)

- Current regime quadrant with historical context
- Regime transition probability matrix
- Portfolio-regime alignment score
- Holdings most/least aligned with current regime
- Macro risk factors and hedging suggestions

### Section 7: Alpha Signal Summary (1-2 pages)

- Composite signal strength heatmap (all holdings across all signal types)
- Signal agreement/disagreement visualization
- Signal decay analysis (how long current signals are expected to persist)
- Ranked holdings by alpha potential

### Section 8: Optimization Results (1-2 pages)

- Efficient frontier plot with current portfolio, optimal portfolios, and benchmark plotted
- Current vs recommended allocation comparison (side-by-side bar chart)
- Marginal contribution to risk analysis
- Distance-from-frontier quantification
- Optimization trade-offs (Sharpe vs tracking error vs turnover)

### Section 9: Reallocation Recommendations (2-4 pages)

- Recommended trades table with full specification (see Section 4 format)
- Before/after portfolio comparison (allocation pie charts side by side)
- Expected impact on key metrics (table)
- Implementation timeline
- Priority ranking of trades

### Section 10: Compliance and Tax Summary (1 page)

- Tax lot analysis summary
- Tax-loss harvesting opportunities with estimated savings
- Wash sale risks for proposed trades
- Short-term vs long-term capital gains breakdown
- Tax-optimized trade sequencing

### Section 11: Appendix -- Detailed Firm-by-Firm Analysis (5-10 pages)

Complete output from each of the 15 firm agents, organized by tier:
- Tier 1: Bloomberg, AQR, Man Group
- Tier 2: GS Strategy, Citadel, Point72, Bridgewater, D.E. Shaw
- Tier 3: Two Sigma, RenTech, Dimensional, Jane Street, Virtu
- Tier 4: GS Compliance, Millennium

---

## 6. Visualization Requirements

Generate the following visualizations using Python (matplotlib for static charts, plotly for interactive where supported):

### Allocation Charts
- **Current allocation pie chart** -- Sector breakdown with percentage labels
- **Recommended allocation pie chart** -- Side-by-side comparison with current
- **Market cap distribution bar chart** -- Mega/large/mid/small/micro

### Risk Visualizations
- **Correlation heatmap** -- All holdings, color-coded with correlation coefficients, clustered by similarity
- **Historical drawdown chart** -- Time series showing drawdown depth with crisis periods annotated
- **VaR fan chart** -- Forward-looking VaR at multiple confidence levels
- **Risk contribution stacked bar chart** -- Each holding's contribution to total portfolio risk

### Factor Analysis
- **Factor exposure radar chart** -- Current portfolio vs benchmark on 7 factors (MKT, SMB, HML, RMW, CMA, UMD, QMJ)
- **Factor attribution waterfall chart** -- How much each factor contributed to historical returns
- **Factor valuation scatter plot** -- Current factor valuations vs historical distribution

### Performance Analysis
- **Efficient frontier plot** -- Frontier curve with current portfolio, optimal portfolios, and individual holdings plotted
- **Performance attribution waterfall** -- Allocation effect, selection effect, interaction effect
- **Rolling Sharpe ratio line chart** -- 1Y rolling window with benchmark overlay

### Signal Dashboard
- **Signal strength heatmap** -- Holdings (rows) x signal types (columns), color intensity = signal strength
- **Consensus bar chart** -- Each holding's consensus score with bullish/neutral/bearish decomposition

### Geographic and Sector Exposure
- **Sector exposure grouped bar chart** -- Current vs recommended vs benchmark
- **Geographic exposure bar chart** -- Domestic vs international with country-level breakdown for significant exposures

---

## 7. Quality Criteria

Every output from this skill must satisfy these quality gates. Apply self-check at each phase.

### Recommendation Integrity
- Every recommendation MUST cite at least 2 firm agents that support it
- Conflicting recommendations MUST be transparently presented with both sides
- No recommendation may be presented without an estimated confidence score
- Recommendations that would increase portfolio risk must be explicitly flagged

### Quantitative Rigor
- All risk metrics MUST include confidence intervals or estimation uncertainty
- All numerical claims MUST have supporting calculations or data sources
- Backtest results MUST report in-sample and out-of-sample performance separately
- Return projections MUST be presented as ranges, not point estimates

### Data Quality
- Holdings with less than 1 year of historical data MUST be flagged
- Stale price data (>24h for equities) MUST trigger a warning
- Factor model residuals exceeding 2 standard deviations MUST be investigated
- Any agent that fails to complete MUST be reported in the output

### Transparency
- The report MUST disclose which agents completed successfully and which failed
- Consensus scores MUST show the underlying vote distribution, not just the aggregate
- Conflict resolution weighting MUST be explained (not hidden)
- Limitations of each methodology MUST be acknowledged in the appendix

### Validation Checklist
- [ ] All tickers validated against live market data
- [ ] Portfolio weights sum to 100% (within 0.5% tolerance)
- [ ] All 15 agents produced output (or failures are documented)
- [ ] Consensus scores computed with proper weighting
- [ ] Conflicts transparently presented with both perspectives
- [ ] Recommendations include confidence scores and supporting citations
- [ ] Risk metrics include confidence intervals
- [ ] Tax implications computed for proposed trades
- [ ] Execution costs estimated for proposed rebalancing
- [ ] PDF report contains all 11 sections
- [ ] All visualizations render correctly
- [ ] Report file size is reasonable (<50MB)

---

## 8. Examples

### Example 1: Simple 5-Stock Tech-Heavy Portfolio

**Input:**
```csv
ticker,shares,cost_basis,entry_date
AAPL,200,145.00,2023-01-15
MSFT,100,280.00,2023-03-01
NVDA,75,420.00,2024-01-10
GOOGL,60,130.00,2023-06-15
AMZN,50,140.00,2023-09-01
```

**Validation output:**
```
Portfolio validated:
  - 5 holdings, all US large-cap technology sector
  - Total estimated value: $287,450
  - Weight distribution: NVDA 32%, AAPL 28%, MSFT 22%, AMZN 10%, GOOGL 8%
  - WARNING: 100% technology sector concentration
  - WARNING: 100% US domestic exposure
  - WARNING: Single sector exceeds 25% threshold
  - All tickers active, sufficient data history (3+ years)
```

**Synthesis summary (abbreviated):**
```
OVERALL HEALTH SCORE: 62/100

KEY FINDINGS:
1. STRENGTH: Strong alpha signals across all holdings (Citadel avg score +45)
2. STRENGTH: Factor exposure aligned with quality-growth premium (AQR)
3. RISK: Extreme sector concentration (100% tech) creates correlated drawdown risk
   (Two Sigma: portfolio VaR is 40% higher than diversified equivalent)
4. RISK: Macro regime sensitivity -- portfolio underperforms in rising-rate
   environments (Bridgewater: -2.1 sigma sensitivity to rate shocks)
5. OPPORTUNITY: D.E. Shaw identifies GOOGL as relatively undervalued vs MSFT
   on 3M mean-reversion signal

CONSENSUS SCORES:
  NVDA:  +0.53 (Buy)   -- 10 bullish, 3 neutral, 2 bearish
  AAPL:  +0.40 (Buy)   -- 8 bullish, 5 neutral, 2 bearish
  MSFT:  +0.27 (Hold)  -- 7 bullish, 5 neutral, 3 bearish
  GOOGL: +0.47 (Buy)   -- 9 bullish, 4 neutral, 2 bearish
  AMZN:  +0.33 (Buy)   -- 8 bullish, 4 neutral, 3 bearish

TOP RECOMMENDATION (Quarterly timeframe):
  Action: Reduce concentration risk by trimming NVDA to 20% and deploying
  proceeds into VGT (broad tech ETF) and VIG (dividend growth ETF).
  Confidence: HIGH (0.78)
  Supporting: Man Group, Two Sigma, AQR, GS Strategy, Bridgewater
  Dissenting: Citadel (NVDA alpha signal still strong), Point72 (ML predicts
  continued outperformance)
```

### Example 2: Complex 20-Position Diversified Portfolio

**Input:**
```json
{
  "portfolio": [
    {"ticker": "AAPL", "shares": 100, "cost_basis": 150.00, "entry_date": "2022-06-01"},
    {"ticker": "MSFT", "shares": 60, "cost_basis": 260.00, "entry_date": "2022-08-15"},
    {"ticker": "JNJ", "shares": 80, "cost_basis": 165.00, "entry_date": "2022-01-10"},
    {"ticker": "JPM", "shares": 50, "cost_basis": 135.00, "entry_date": "2023-03-15"},
    {"ticker": "XOM", "shares": 70, "cost_basis": 95.00, "entry_date": "2023-01-05"},
    {"ticker": "PG", "shares": 45, "cost_basis": 145.00, "entry_date": "2022-11-20"},
    {"ticker": "UNH", "shares": 20, "cost_basis": 490.00, "entry_date": "2023-05-10"},
    {"ticker": "HD", "shares": 30, "cost_basis": 305.00, "entry_date": "2022-09-01"},
    {"ticker": "V", "shares": 40, "cost_basis": 220.00, "entry_date": "2023-02-14"},
    {"ticker": "MA", "shares": 25, "cost_basis": 365.00, "entry_date": "2023-04-01"},
    {"ticker": "COST", "shares": 15, "cost_basis": 520.00, "entry_date": "2023-07-01"},
    {"ticker": "VZ", "shares": 120, "cost_basis": 38.00, "entry_date": "2022-12-01"},
    {"ticker": "BND", "shares": 200, "cost_basis": 74.00, "entry_date": "2023-06-01"},
    {"ticker": "GLD", "shares": 50, "cost_basis": 178.00, "entry_date": "2023-08-15"},
    {"ticker": "VWO", "shares": 100, "cost_basis": 40.00, "entry_date": "2023-01-20"},
    {"ticker": "IYR", "shares": 60, "cost_basis": 85.00, "entry_date": "2023-03-10"},
    {"ticker": "TLT", "shares": 80, "cost_basis": 102.00, "entry_date": "2023-09-01"},
    {"ticker": "DBA", "shares": 150, "cost_basis": 24.00, "entry_date": "2023-11-01"},
    {"ticker": "SCHD", "shares": 90, "cost_basis": 72.00, "entry_date": "2023-02-01"},
    {"ticker": "QQQ", "shares": 35, "cost_basis": 350.00, "entry_date": "2024-01-15"}
  ],
  "account_type": "taxable",
  "benchmark": "SPY"
}
```

**Validation output:**
```
Portfolio validated:
  - 20 holdings across 8 sectors, 4 asset classes
  - Total estimated value: ~$185,000
  - Asset class mix: US Equity 58%, Fixed Income 14%, International 5%,
    Real Estate 5%, Commodities 6%, Broad ETFs 12%
  - Sector diversification: Technology 22%, Healthcare 10%, Financials 10%,
    Consumer 12%, Energy 5%, Utilities/Telecom 4%, Other 37% (ETFs/alternatives)
  - No single position exceeds 12% -- good diversification
  - All tickers active, BND/TLT/GLD are ETFs (use ETF factor models)
  - VWO has different factor model (international emerging markets)
  - DBA is agriculture commodity ETF (limited factor model applicability)
```

**Synthesis summary (abbreviated):**
```
OVERALL HEALTH SCORE: 74/100

KEY FINDINGS:
1. STRENGTH: Well-diversified across sectors and asset classes (Two Sigma:
   portfolio correlation to SPY is 0.72, vs 0.95+ for typical retail portfolios)
2. STRENGTH: Quality factor tilt provides defensive characteristics (AQR:
   +0.4 sigma quality exposure)
3. STRENGTH: Bond allocation (BND + TLT) provides crisis hedging
   (RenTech backtest: portfolio drew down 18% in 2022 vs 25% for SPY)
4. RISK: VZ has negative alpha consensus -- Strong Sell (-0.60)
   (Citadel: -65 alpha score, Point72: negative ML prediction, D.E. Shaw:
   expensive vs telecom peers)
5. RISK: TLT duration risk in current rate environment (Bridgewater:
   rising-rate regime probability 45%)
6. OPPORTUNITY: Emerging market allocation (VWO) is underweight relative to
   optimization target (Man Group: increase to 8% from current 5%)
7. TAX ALERT: VZ position has harvestable loss of ~$1,200 (GS Compliance)

CONSENSUS SCORES (top 5 and bottom 5):
  XOM:   +0.67 (Strong Buy) -- energy macro alignment + value signal
  UNH:   +0.60 (Strong Buy) -- defensive quality + earnings momentum
  COST:  +0.53 (Buy)        -- quality-growth + consumer resilience
  JPM:   +0.47 (Buy)        -- financials benefiting from rate environment
  V:     +0.47 (Buy)        -- payment network moat + global growth exposure
  ...
  DBA:   -0.13 (Hold)       -- limited alpha signal, commodity uncertainty
  TLT:   -0.27 (Hold)       -- duration risk in current regime
  IYR:   -0.33 (Sell)       -- REIT headwinds from rates, better alternatives
  VZ:    -0.60 (Strong Sell) -- negative signals across multiple dimensions
  QQQ:   -0.07 (Hold)       -- overlaps with existing tech holdings (AAPL, MSFT)

TOP 3 RECOMMENDATIONS (Quarterly timeframe):
1. SELL VZ (120 shares) -> BUY TMUS (35 shares)
   Rationale: Tax-loss harvest VZ, redeploy into higher-quality telecom
   Confidence: HIGH (0.82), Supporting: 12 of 15 firms

2. TRIM QQQ to 0% -> ADD to VWO and SCHD
   Rationale: QQQ overlaps with AAPL/MSFT (portfolio-overlap-detector confirms
   68% overlap), better to increase EM and dividend exposure
   Confidence: HIGH (0.75), Supporting: 10 of 15 firms

3. TRIM TLT to 40 shares -> BUY VTIP (inflation-protected bonds)
   Rationale: Reduce duration risk while maintaining fixed income allocation
   Confidence: MEDIUM (0.58), Supporting: 8 of 15 firms
   Dissenting: Dimensional (long-term term premium is attractive at current levels)
```

---

## 9. Integration Map

This skill is the capstone orchestrator that connects to every other component in the finance-pack plugin.

### Connection to Original 10 Skills

| Skill | Integration Point |
|-------|-------------------|
| `valuation-sanity-check` | Pre-analysis validation: Run on all holdings before launching firm agents to flag obviously mispriced positions |
| `portfolio-overlap-detector` | Overlap analysis: Identify redundant ETF/stock overlaps within the portfolio (e.g., QQQ + AAPL + MSFT) |
| `sector-theme-mapper` | Thematic exposure: Map holdings to investment themes and identify thematic concentration or gaps |
| `bull-bear-steelman` | Conflict presentation: When firms disagree, structure the bull and bear cases for each holding |
| `competitive-moat-audit` | Per-holding quality: Assess competitive moat for each equity holding to inform quality factor analysis |
| `earnings-call-translator` | Catalyst identification: Parse recent earnings calls for holdings approaching earnings dates |
| `filing-decoder` | Fundamental validation: Cross-reference agent findings with recent SEC filings |
| `catalyst-timeline-builder` | Event calendar: Build a forward-looking catalyst timeline for the portfolio |
| `adversarial-business-model` | Risk identification: Stress-test business models for holdings flagged as high-risk |
| `investment-thesis-one-pager` | Per-holding summary: Generate a concise thesis for each holding in the portfolio |

### Connection to 15 Firm Agents

All 15 agents are invoked directly by this skill's analysis pipeline (see Section 2). Each agent operates independently with the validated portfolio as input and produces structured output consumed by the synthesis framework.

### Data Flow Architecture

```
User Portfolio Input
       |
       v
  [Validation Layer]
       |
       v
  [Pre-Analysis Skills] -- valuation-sanity-check, portfolio-overlap-detector
       |
       v
  [15 Firm Agents in Parallel] -- All Tiers launch simultaneously
       |
       v
  [Result Collection] -- Wait for all agents, track failures
       |
       v
  [Synthesis Framework] -- Consensus scoring, conflict resolution, confidence weighting
       |
       v
  [Reallocation Engine] -- Timeframe-specific recommendations
       |
       v
  [Visualization Generator] -- Python matplotlib/plotly charts
       |
       v
  [PDF Compiler] -- Assemble report with all sections
       |
       v
  [Delivery] -- Save PDF, present summary to user
```

### Standalone vs Teammate Mode

**Standalone mode:** The portfolio-deep-analysis skill runs as a single orchestrator, launching all sub-agents via the Task tool and collecting results. The user interacts with one conversation thread.

**Teammate mode:** When operating as part of a multi-agent team, this skill can be assigned as a task to the tech-lead or product-manager agent. The orchestrating agent launches firm agents as sub-tasks and reports results back to the team lead. In teammate mode, the timeframe question is answered by the assigning agent based on the user's original request.

---

## 10. Error Handling and Graceful Degradation

### Agent Failure Handling

If any of the 15 firm agents fails to produce output (timeout, data error, computation failure):

1. **Log the failure** with the agent name, error type, and timestamp
2. **Continue with remaining agents** -- Never fail the entire analysis because one agent failed
3. **Adjust consensus scoring** -- Reduce the denominator to reflect only agents that completed
4. **Flag the gap** -- In the report, clearly state which firm analyses are missing and what aspects of the analysis are therefore less reliable
5. **Suggest re-run** -- If 3+ agents fail, recommend the user re-run the analysis

**Minimum viable analysis:** At least 8 of 15 agents must complete for the report to be generated. If fewer than 8 complete, abort and report the failures.

### Data Quality Degradation

| Issue | Response |
|-------|----------|
| Ticker not found | Suggest closest match, exclude from analysis if unresolvable |
| <1 year of data | Include in analysis with reduced confidence, flag in report |
| Stale price data | Use most recent available, flag the staleness |
| Missing fundamentals | Exclude from fundamental-based analyses, note the gap |
| International ticker | Adjust factor models for international markets |
| Crypto/alternative asset | Use limited analysis (liquidity, correlation, macro sensitivity only) |

### Timeout Management

- Individual agent timeout: 120 seconds
- Total pipeline timeout: 300 seconds
- If total pipeline exceeds 300 seconds, compile report with completed agents and flag incomplete ones
