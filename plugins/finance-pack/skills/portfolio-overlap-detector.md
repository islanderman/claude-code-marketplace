---
name: portfolio-overlap-detector
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: Detect hidden correlations, duplicate bets, factor exposures, and concentration risks in a portfolio that go beyond simple sector labels, with stress testing and actionable trim recommendations.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "portfolio overlap"
  - "hidden correlation"
  - "concentration risk"
  - "duplicate bet"
  - "factor exposure"
  - "diversification check"
  - "portfolio stress test"
modes:
  standalone: true
  teammate: true
---

# Portfolio Overlap Detector

## ULTRATHINK Activation

**Mode**: ENGINEER MODE with CRITIC MODE -- institutional-grade portfolio risk decomposition
**Optimization**: Multi-dimensional overlap detection across correlation, factor, geographic, and supply-chain dimensions
**Focus**: Surfacing hidden concentration risks that standard sector-based analysis misses, with quantified stress-test impacts and specific actionable recommendations

---

## Purpose

Standard portfolio analysis groups holdings by sector and calls it diversification. This is dangerously superficial. A portfolio of MSFT, GOOGL, AMZN, META, and CRM looks like "five different companies" but is effectively a single bet on US large-cap quality-growth with high advertising/cloud exposure. This skill performs thorough multi-dimensional overlap detection: correlation clustering, duplicate bet identification, hidden factor exposures, revenue-weighted geographic concentration, supply chain dependencies, and single-factor stress tests. The output reveals the true risk structure of a portfolio and produces specific trim/rebalance recommendations.

**When to use**: After building or modifying a portfolio, during periodic risk reviews, before adding a new position that may increase hidden concentration, or when market conditions change and correlation regimes shift.

---

## Methodology (4-Phase)

### Phase 1: Analysis -- Multi-Dimensional Decomposition

Analyze with deliberation to decompose every portfolio position across multiple dimensions simultaneously. Do not rely on sector labels -- a "Healthcare" company deriving 60% of revenue from China has more in common with a "Consumer" company in China than with a US healthcare peer. Step-by-step, map each holding across: return correlation clusters, factor exposures, geographic revenue breakdown, customer/supplier dependencies, and macro sensitivities. Use context-sensitive reflection to identify which dimensions matter most for the specific portfolio.

### Phase 2: Plan -- Overlap Identification and Quantification

Apply multi-layer analysis to identify where positions overlap. Categorize overlaps as: direct (same thesis), indirect (correlated exposures), or conditional (overlaps emerge only under stress). Evaluate assumptions about diversification -- does owning 20 stocks actually provide 20 independent bets, or is the effective number of bets much lower? Quantify the degree of overlap using correlation data and factor loadings.

### Phase 3: Execution -- Stress Testing and Vulnerability Mapping

Apply systematic stress testing across key macro scenarios. For each scenario (rate spike, USD strength, recession, etc.), estimate portfolio-level impact by aggregating position-level sensitivities. Build the macro sensitivity matrix. Identify single-factor vulnerabilities where the portfolio has extreme exposure. Use breadth-first reasoning to ensure no material risk dimension is overlooked.

### Phase 4: Validation -- Diversification Grading and Recommendations

Self-check the complete analysis by verifying that overlap detection is evidence-based, not assumption-based. Produce the diversification grade across 5 dimensions. Generate specific, actionable trim/add recommendations with rationale. Verify logic: Do the recommendations actually improve diversification without sacrificing expected return quality? Would implementing the recommendations meaningfully reduce portfolio vulnerability?

---

## Detailed Framework

### Correlation Cluster Analysis

Group portfolio positions by actual return correlation, not sector classification. Two stocks in the same "sector" may have low correlation (a US domestic utility vs an international energy company, both "Utilities/Energy"), while two stocks in different sectors may be highly correlated (a semiconductor company and a cloud company, both trading on the same AI CapEx cycle).

**Methodology**:
1. Estimate trailing 12-month and 3-year pairwise correlations for all positions
2. Group positions into clusters where intra-cluster correlation exceeds 0.65
3. Label each cluster by its dominant driver (not sector label)
4. Calculate cluster weight as sum of constituent position weights

```
| Cluster Name              | Dominant Driver          | Positions              | Combined Weight | Intra-Cluster Corr |
|---------------------------|--------------------------|------------------------|-----------------|---------------------|
| [e.g., AI CapEx Cycle]    | [e.g., AI infrastructure spending] | NVDA, AVGO, ANET      | XX%             | 0.XX                |
| [e.g., US Consumer Spend] | [e.g., discretionary income]       | AMZN, COST, HD        | XX%             | 0.XX                |
| [e.g., Rate Sensitive]    | [e.g., long-duration growth]       | MSFT, CRM, NOW        | XX%             | 0.XX                |
```

**Red flag**: Any cluster exceeding 30% of portfolio weight represents dangerous concentration regardless of how many individual positions it contains.

### Duplicate Bet Detection

A duplicate bet occurs when two or more positions express fundamentally the same investment thesis. These provide no diversification benefit and amplify risk without proportional return improvement.

**Detection criteria**:
- Same revenue driver (e.g., two companies primarily monetizing the same customer segment)
- Same competitive outcome required (e.g., both need AI CapEx to accelerate)
- Same macro sensitivity profile (e.g., both benefit from falling rates, both hurt by strong USD)
- Correlation >0.75 over 3-year period

```
| Duplicate Pair  | Shared Thesis                        | Correlation | Combined Weight | Recommendation        |
|-----------------|--------------------------------------|-------------|-----------------|----------------------|
| [STOCK A / B]   | [What thesis they share]             | 0.XX        | XX%             | [Keep stronger, trim weaker] |
```

**Important distinction**: Two stocks in the same industry are not automatically duplicate bets. PG and COST are both "consumer" but express very different theses (brand premium pricing vs membership-model volume). Duplicate detection requires shared thesis, not shared sector.

### Hidden Factor Exposure Mapping

Decompose each position's return into factor exposures. A portfolio may look diversified by name but be concentrated in a single factor.

| Factor | Description | Portfolio Exposure | Benchmark Exposure | Active Tilt |
|--------|-------------|-------------------|-------------------|-------------|
| **Growth** | Revenue growth rate, forward P/E | XX% weight to high-growth | XX% | +/- XX% |
| **Value** | Low P/E, low P/B, high dividend yield | XX% weight to value | XX% | +/- XX% |
| **Momentum** | 6-12 month price trend | XX% weight to positive momentum | XX% | +/- XX% |
| **Quality** | High ROE, low debt, stable earnings | XX% weight to quality | XX% | +/- XX% |
| **Size** | Market capitalization tilt | XX% avg market cap | XX% | +/- XX% |
| **Volatility** | Beta and realized volatility | XX portfolio beta | XX% | +/- XX% |

**Critical insight**: Most self-selected portfolios have extreme quality-growth factor concentration. This feels safe in bull markets but creates severe drawdown risk during factor rotations (growth-to-value rotations in 2022 caused 30-50% drawdowns in quality-growth portfolios even when underlying businesses performed well).

### Geographic Concentration Analysis

Use revenue-weighted geographic exposure, NOT headquarters location. A "US company" deriving 50% of revenue from China has 50% China exposure regardless of where it is listed.

```
| Region          | HQ-Based Weight | Revenue-Weighted Weight | Delta | Risk Implication |
|-----------------|-----------------|-------------------------|-------|------------------|
| United States   | XX%             | XX%                     | XX%   | [Implication]    |
| China           | XX%             | XX%                     | XX%   | [Implication]    |
| Europe          | XX%             | XX%                     | XX%   | [Implication]    |
| Rest of Asia    | XX%             | XX%                     | XX%   | [Implication]    |
| Rest of World   | XX%             | XX%                     | XX%   | [Implication]    |
```

**Red flag**: Revenue-weighted concentration >60% in any single country/region. Even higher threshold for US (>75% is worth flagging given most investors are already overweight US through other assets like real estate and employment income).

### Customer/Supplier Overlap Detection

Identify positions with shared mega-customers or critical suppliers, creating hidden correlation through supply chain linkage.

**Mega-customer exposure**: If Apple, Amazon, or another mega-buyer represents >10% of revenue for multiple portfolio holdings, those holdings are effectively correlated through a single customer's purchasing decisions.

```
| Mega-Customer/Supplier | Portfolio Positions Exposed | Exposure Level | Combined Portfolio Weight |
|------------------------|-----------------------------|----------------|--------------------------|
| [e.g., Apple]          | [QCOM, AVGO, SWKS, ...]    | [Revenue % each] | XX%                      |
| [e.g., Amazon/AWS]     | [AMZN, MDB, DDOG, ...]     | [Revenue % each] | XX%                      |
```

### Single-Factor Stress Tests

Model portfolio impact under specific macro scenarios. For each scenario, estimate the direction and magnitude of impact on every position.

| Scenario | Trigger | Positions Hurt | Positions Helped | Net Portfolio Impact |
|----------|---------|---------------|-----------------|---------------------|
| **Rates +200bps** | Fed hiking cycle | [Long-duration growth, REITs, leveraged] | [Banks, insurance, short-duration value] | -XX% estimated |
| **USD +10%** | Dollar strengthening | [International revenue, commodity exporters] | [US domestic, importers] | -/+XX% estimated |
| **Recession** | GDP contraction | [Cyclicals, discretionary, financials] | [Staples, utilities, healthcare] | -XX% estimated |
| **Oil +50%** | Supply disruption | [Airlines, transport, consumer] | [Energy, materials] | -/+XX% estimated |
| **China -30%** | Geopolitical escalation | [China revenue exposure, semis] | [US domestic, defense] | -XX% estimated |
| **Growth-to-Value Rotation** | Multiple compression | [High P/E growth, unprofitable tech] | [Low P/E value, dividend payers] | -XX% estimated |

### Macro Sensitivity Matrix

Map each position's directional response to key macro variables:

```
| Position | Rates Up | USD Up | Oil Up | Recession | China Risk | Growth Rotation |
|----------|----------|--------|--------|-----------|------------|-----------------|
| AAPL     | -        | --     | 0      | -         | --         | -               |
| JPM      | ++       | +      | 0      | --        | -          | ++              |
| XOM      | +        | -      | ++     | -         | 0          | +               |
```

Legend: ++ strong positive, + moderate positive, 0 neutral, - moderate negative, -- strong negative

### Diversification Grade

Grade portfolio diversification across 5 dimensions. Each dimension graded A through F.

| Dimension | Grade | Criteria for A | Criteria for C | Criteria for F |
|-----------|-------|---------------|---------------|---------------|
| **Correlation** | X | No cluster >20% weight, avg pairwise corr <0.40 | One cluster 25-35%, avg corr 0.40-0.55 | Multiple clusters >30%, avg corr >0.60 |
| **Factor** | X | No factor tilt >1.5 standard deviations from benchmark | One factor tilt 1.5-2.5 SD | Multiple factor tilts >2.5 SD |
| **Geographic** | X | No region >50% revenue-weighted (excl. US at 70%) | One region 50-65% | Single region >75% or non-US region >60% |
| **Supply Chain** | X | No mega-customer shared across >15% of portfolio | One mega-customer across 15-25% | Mega-customer across >25% of portfolio |
| **Stress Resilience** | X | No single scenario causes >15% portfolio drawdown | One scenario causes 15-25% drawdown | Multiple scenarios cause >25% drawdown |

**Overall Grade**: Average of 5 dimensions (A=4, B=3, C=2, D=1, F=0). Round to nearest letter grade.

### Correlation Regime Analysis

Correlations are not stable. They change dramatically between calm and crisis markets. A portfolio that appears diversified in normal conditions may converge during stress.

| Pair/Cluster | Calm Market Correlation | Crisis Market Correlation | Regime Delta | Implication |
|-------------|------------------------|--------------------------|-------------|-------------|
| [Cluster A] | 0.XX | 0.XX | +0.XX | [Diversification benefit disappears in crisis] |
| [Cluster B] | 0.XX | 0.XX | +0.XX | [Correlation stable -- genuine diversifier] |

**Key insight**: Most equity-equity correlations increase during market stress (correlations converge toward 1.0 in a crash). True diversifiers are assets or positions whose correlations remain low or go negative during stress (e.g., long-duration treasuries in equity selloffs, although this relationship has broken down in inflationary environments).

### Position Trim/Add Recommendations

Produce exactly 2 specific, actionable recommendations:

```
RECOMMENDATION 1: [TRIM/CUT] [TICKER]
Current weight: XX%
Recommended weight: XX% (reduce by XX%)
Rationale: [Specific overlap or concentration problem this addresses]
Diversification impact: [Which grade dimension improves and by how much]

RECOMMENDATION 2: [TRIM/CUT or ADD] [TICKER or asset class]
Current weight: XX%
Recommended weight: XX%
Rationale: [Specific gap or vulnerability this addresses]
Diversification impact: [Which grade dimension improves and by how much]
```

---

## Output Format

```markdown
## Portfolio Overlap Analysis: [Portfolio Name/Description]

### Correlation Clusters
[Cluster table with positions, weights, and intra-cluster correlations]

### Duplicate Bets
[Duplicate pairs with shared thesis and recommendations]

### Factor Exposure Map
[Factor table with portfolio vs benchmark exposure and active tilts]

### Geographic Concentration
[HQ-based vs revenue-weighted comparison]

### Supply Chain Overlap
[Mega-customer/supplier shared exposure table]

### Stress Test Results
[Scenario impact table]

### Macro Sensitivity Matrix
[Position-level directional responses]

### Diversification Grade
[5-dimension grade card with overall grade]

### Correlation Regime Warning
[Calm vs crisis correlation comparison]

### Recommendations
[2 specific trim/add recommendations with rationale]

### Portfolio Risk Summary
[3-sentence executive summary of key vulnerabilities]
```

---

## Quality Criteria

- Correlation clusters based on return data, not sector labels
- Duplicate bets identified by shared thesis, not just shared sector
- Factor exposures quantified relative to benchmark (active tilts)
- Geographic analysis uses revenue-weighted exposure, not HQ location
- Stress tests cover at least 5 distinct macro scenarios
- Diversification grade has specific, measurable criteria for each level
- Recommendations are specific (named positions, specific weight changes)
- Self-check: Do the recommendations actually reduce the identified concentrations?
- Correlation regime analysis distinguishes calm from crisis behavior

---

## Common Pitfalls

1. **Sector-label diversification**: Treating a portfolio as diversified because it holds stocks from 8 different GICS sectors, when 6 of those sectors are all driven by the same macro factor (US economic growth). Correlation clustering reveals the true number of independent bets, which is often 3-4 even in a 20-stock portfolio.

2. **HQ-based geographic analysis**: Classifying AAPL as "100% US exposure" because it is headquartered in Cupertino. Apple derives ~20% of revenue from Greater China. Revenue-weighted geographic analysis is mandatory. HQ-based analysis is actively misleading.

3. **Ignoring correlation regime shifts**: Assuming that because two positions had 0.3 correlation over the last 3 years, they will continue to diversify each other. In the 2020 COVID crash, nearly all equity correlations spiked above 0.8 for weeks. Diversification disappears exactly when you need it most unless you hold genuinely uncorrelated assets.

4. **Factor blindness**: Not recognizing that a portfolio of MSFT, GOOGL, AAPL, AMZN, and META -- "five different businesses" -- is a single bet on US mega-cap quality-growth. When quality-growth underperforms (as in Jan-Oct 2022), all five decline together regardless of individual fundamentals. Factor exposure analysis reveals this concentration.

5. **Confusing position count with diversification**: Believing that 30 positions is more diversified than 15. A 30-stock portfolio where all positions are correlated above 0.7 has fewer effective bets than a 10-stock portfolio with low pairwise correlations. Effective diversification is about independence of return drivers, not number of ticker symbols.

---

## Examples

### Example 1: Tech-Heavy Portfolio with Hidden China Exposure

**Portfolio**: AAPL (15%), MSFT (12%), NVDA (10%), GOOGL (8%), AMZN (8%), TSLA (7%), META (6%), CRM (5%), AVGO (5%), QCOM (4%), remaining 20% in SPY.

**Correlation cluster analysis**:
- Cluster 1 "AI CapEx Cycle": NVDA, AVGO, QCOM -- combined 19%, intra-cluster correlation 0.78. These three positions move almost identically on AI spending news.
- Cluster 2 "US Mega-Cap Growth": MSFT, GOOGL, AMZN, META, CRM -- combined 39%, intra-cluster correlation 0.72. All trade on the same growth/quality factor.
- Cluster 3 "Consumer Hardware/EV": AAPL, TSLA -- combined 22%, intra-cluster correlation 0.45 (lower, genuinely different businesses but shared China exposure).
- Effective number of independent bets: approximately 4 (three clusters + SPY index), despite holding 11 positions.

**Hidden geographic exposure**: HQ-based analysis says 100% US. Revenue-weighted analysis: US 62%, China/Greater China 18% (AAPL 20%, NVDA 25%, QCOM 65%, TSLA 15%, AVGO 30% of their respective revenues), Europe 12%, Rest of World 8%. The 18% China revenue exposure creates material vulnerability to US-China tensions that sector-based analysis completely misses.

**Factor exposure**: Extreme quality-growth tilt (+3.2 SD above benchmark). Extreme large-cap tilt (+2.8 SD). Low value exposure (-2.5 SD). Portfolio beta: 1.15. This portfolio will dramatically underperform during any growth-to-value rotation.

**Stress test** -- "China tensions escalate, 30% China revenue at risk": Portfolio impact estimated -8% to -12% from direct China revenue disruption (QCOM hardest hit at -25%, AAPL at -10%, NVDA at -15%), plus additional -5% from sentiment contagion. Total estimated impact: -13% to -17%.

**Diversification grade**: Correlation: D (two clusters >30%). Factor: F (quality-growth tilt >2.5 SD). Geographic: C (China 18% revenue-weighted, hidden). Supply Chain: D (Apple as mega-customer for QCOM, AVGO). Stress Resilience: D (multiple scenarios >25% impact). **Overall: D**.

**Recommendation 1**: TRIM QCOM from 4% to 1%. Rationale: Highest China revenue exposure (65%), duplicates semiconductor thesis already expressed through NVDA and AVGO, and adds Apple supply-chain concentration. Improves geographic grade (China exposure drops from 18% to 15.5%) and supply chain grade.

**Recommendation 2**: ADD 3% to International Developed Markets ex-US (e.g., VEA or individual European quality names). Rationale: Portfolio has zero non-US-listed positions. Even revenue-weighted, 62% US is high. Adding developed international reduces geographic concentration, lowers quality-growth factor loading, and provides correlation benefit (US-International equity correlation ~0.65 in calm, lower than intra-US tech correlation).

### Example 2: "Diversified" Portfolio with Quality-Growth Factor Concentration

**Portfolio**: MSFT (8%), UNH (7%), V (7%), MA (6%), COST (6%), HD (5%), LLY (5%), ISRG (5%), ADBE (4%), NOW (4%), INTU (4%), MCO (3%), SPGI (3%), ODFL (3%), remaining 30% in BND (bond ETF).

**Duplicate bet detection**:
- V (7%) and MA (6%) = 13% combined: Identical thesis (global digital payments duopoly). Correlation: 0.89. These are the same bet expressed through two tickers. Owning both provides zero diversification.
- SPGI (3%) and MCO (3%) = 6% combined: Identical thesis (credit ratings duopoly). Correlation: 0.82. Same dynamic as V/MA.

**Factor exposure**: This portfolio looks diversified across sectors (Tech, Healthcare, Financials, Consumer, Industrials). But factor analysis reveals extreme concentration: Quality factor: +3.0 SD (every single equity position is high-ROE, low-debt, stable earnings). Growth factor: +2.1 SD. The portfolio is effectively a single bet on "quality compounders outperform." In 2022, this factor underperformed by 15-20%, and a portfolio like this would have declined 25-30% despite holding "defensive" quality names.

**Stress test** -- "Growth-to-value rotation (multiple compression)": Estimated impact on equity portion: -18% to -25%. Every position except BND is vulnerable. The 30% BND allocation provides partial cushion, but overall portfolio estimated impact: -13% to -18%. This is the single largest vulnerability.

**Diversification grade**: Correlation: C (multiple overlapping clusters in quality-growth). Factor: F (quality +3.0 SD, growth +2.1 SD). Geographic: B (revenue-weighted: US 72%, International 28% -- better than typical). Supply Chain: B (no major mega-customer concentration). Stress Resilience: C (growth rotation scenario severe, but BND provides partial offset). **Overall: C+**.

**Recommendation 1**: TRIM MA from 6% to 2%. Rationale: V/MA duplicate bet at 13% combined is the most concentrated overlap. Keep V (slightly higher margins, marginally better long-term positioning). Redirect 4% toward a position with low correlation to the quality-growth factor (e.g., BRK.B for quality-value, or XLE for energy/commodity exposure that is negatively correlated with the rest of the portfolio).

**Recommendation 2**: ADD 4% to a quality-value or cyclical-value position (e.g., BRK.B at 2% + XLE at 2%). Rationale: Portfolio has zero value-factor exposure. Adding even modest value tilt reduces factor concentration from F to D grade and provides meaningful cushion during growth-to-value rotations. BRK.B offers quality-value (maintains portfolio's quality bias but adds value exposure), while XLE provides commodity/inflation hedge that is negatively correlated with the growth factor.

---

## Integration

- **Receives from**: `competitive-moat-audit` (moat scores justify maintaining concentrated positions)
- **Receives from**: `valuation-sanity-check` (overvalued positions in concentrated clusters are highest priority trims)
- **Receives from**: `sector-theme-mapper` (thematic positions may unknowingly create cluster concentration)
- **Update frequency**: Run after any position change, quarterly at minimum, and whenever correlation regimes shift (market stress events)
- **Companion analysis**: Pair with valuation sanity check -- if a concentrated cluster is also overvalued, the trim recommendation becomes urgent
