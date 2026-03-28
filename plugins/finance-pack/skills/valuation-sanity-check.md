---
name: valuation-sanity-check
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: Multi-method valuation framework that maps business types to appropriate metrics, reverse-engineers implied growth, and produces scenario-weighted fair value estimates with margin of safety calculations.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "valuation check"
  - "is this overvalued"
  - "fair value"
  - "valuation sanity"
  - "price target"
  - "margin of safety"
  - "implied growth"
modes:
  standalone: true
  teammate: true
---

# Valuation Sanity Check

## ULTRATHINK Activation

**Mode**: MAX-PRECISION MODE with CRITIC MODE -- institutional-grade valuation analysis
**Optimization**: Multi-method cross-validation with scenario-weighted probability distributions
**Focus**: Avoiding overpayment through rigorous, assumption-explicit valuation that separates hype premium from quality premium

---

## Purpose

Deliver a comprehensive, multi-method valuation assessment that prevents both overpaying for growth narratives and missing genuine quality at reasonable prices. This skill maps each business to its appropriate valuation framework, reverse-engineers what the market is implying, stress-tests key assumptions, and produces probability-weighted fair value ranges with explicit margin of safety thresholds.

**When to use**: Before initiating any position, when evaluating whether to add to or trim an existing position, or when market price has moved significantly from your last assessment.

---

## Methodology (4-Phase)

### Phase 1: Analysis -- Business Classification and Metric Selection

Analyze with deliberation to correctly classify the business type. The single most common valuation error is applying the wrong metric to the wrong business. A pre-revenue biotech cannot be valued on P/E. A mature utility cannot be valued on revenue multiples. Step-by-step, identify the business model, growth stage, capital intensity, and margin profile to select primary and secondary valuation metrics.

### Phase 2: Plan -- Historical Context and Peer Calibration

Establish valuation context through systematic multi-layer analysis. Examine the company's own 3-5 year valuation range (what has the market historically paid?). Compare against growth-adjusted peer multiples (is this company cheap or expensive relative to similar businesses?). Reverse-engineer implied growth rates (what must happen for the current price to be justified?). Evaluate assumptions: Are implied growth rates achievable given TAM, competitive position, and historical execution?

### Phase 3: Execution -- Scenario Modeling and Fair Value Estimation

Produce 3 candidate valuations (Bull, Base, Bear) with explicit assumptions for each. Use breadth-first reasoning to ensure scenarios cover meaningfully different outcomes, not just plus/minus 10% variations. Build DCF sensitivity tables for key variables. Calculate probability-weighted expected value. Determine margin of safety thresholds. Assess whether any premium is driven by hype (narrative without fundamentals) or quality (sustainable competitive advantages).

### Phase 4: Validation -- Cross-Method Reconciliation and Self-Check

Self-check the entire valuation by cross-referencing methods. If DCF says $150 but comps say $90, investigate the discrepancy -- do not average blindly. Verify logic: Do your growth assumptions match the moat assessment? Does the implied margin trajectory make sense given competitive dynamics? Would a skeptical analyst with access to the same data reach a substantially different conclusion?

---

## Detailed Framework

### Business-Type-to-Metric Mapping Table

Select the primary and secondary valuation metrics based on business classification. Using the wrong metric is the most frequent source of valuation error.

| Business Type | Primary Metric | Secondary Metric | Avoid Using | Rationale |
|---------------|---------------|-----------------|-------------|-----------|
| **High-Growth SaaS** (>30% rev growth) | EV/Revenue, EV/ARR | Rule of 40, NTM EV/FCF | P/E (earnings distorted by growth investment) | Revenue is the cleanest signal; earnings are intentionally depressed |
| **Moderate-Growth SaaS** (15-30%) | EV/NTM Revenue | EV/EBITDA, FCF Yield | Trailing multiples (forward more relevant at this growth) | Transitioning from growth to profitability metrics |
| **Mature Software** (<15% growth) | EV/EBITDA, FCF Yield | P/E, EV/Revenue | EV/Revenue alone (must show margin leverage) | Profitability matters at this stage |
| **Consumer Staples** | P/E, EV/EBITDA | Dividend Yield, FCF Yield | EV/Revenue (margins are the value driver) | Stable earnings make P/E reliable |
| **Consumer Discretionary** | P/E (normalized), EV/EBITDA | PEG Ratio | Single-year P/E (cyclicality distorts) | Normalize for cycle position |
| **Financials / Banks** | P/TBV, P/E | ROE-adjusted P/B, Dividend Yield | EV/EBITDA (capital structure is the product) | Book value and returns on equity are core |
| **REITs** | P/FFO, P/AFFO | NAV Discount/Premium, Dividend Yield | P/E (depreciation makes earnings meaningless) | FFO removes non-cash distortions |
| **Biotech (Pre-Revenue)** | rNPV (risk-adjusted NPV) | Pipeline Value, Cash Runway | P/E, EV/Revenue (no revenue to value) | Probability-weighted pipeline is only valid approach |
| **Biotech (Commercial)** | EV/Revenue, P/E | Pipeline rNPV, PEG | Cash burn rate alone (revenue changes the picture) | Hybrid of commercial value + pipeline optionality |
| **Industrials / Cyclicals** | Normalized P/E, EV/EBITDA | FCF Yield (mid-cycle), Replacement Value | Peak-year P/E (appears cheap at cycle top) | Normalize across full cycle |
| **Utilities / Infrastructure** | Dividend Yield, P/E | EV/EBITDA, Rate Base Growth | EV/Revenue (regulated margins are fixed) | Yield and regulated return are core value drivers |
| **E-Commerce / Marketplace** | EV/GMV, EV/Revenue | Take Rate trends, P/E (if profitable) | P/E for early-stage (reinvestment distorts) | GMV captures platform scale; take rate captures monetization |

### Historical Range Analysis

For the target company, chart the 3-5 year valuation range for the primary metric:

```
| Period     | Metric Value | Context (what drove the extreme) |
|------------|-------------|----------------------------------|
| 5Y High    | XX.Xx       | [Specific catalyst or sentiment]  |
| 5Y Low     | XX.Xx       | [Specific catalyst or sentiment]  |
| 3Y Median  | XX.Xx       | [Normal operating environment]    |
| Current    | XX.Xx       | [Current context]                 |
| Percentile | XXth        | [Where current sits in range]     |
```

**Key question**: Is the current valuation at the high end because fundamentals improved, or because sentiment inflated? Context-sensitive reflection is critical here.

### Growth-Adjusted Peer Comparison

Raw multiples without growth adjustment are misleading. A company trading at 30x earnings growing 25% is cheaper than a company at 20x earnings growing 8%.

| Company | Primary Multiple | Growth Rate | Growth-Adjusted (PEG or equiv.) | Premium/Discount to Peer Median |
|---------|-----------------|-------------|--------------------------------|-------------------------------|
| Target  | XX.Xx           | XX%         | X.Xx                           | +/-XX%                        |
| Peer 1  | XX.Xx           | XX%         | X.Xx                           | +/-XX%                        |
| Peer 2  | XX.Xx           | XX%         | X.Xx                           | +/-XX%                        |
| Peer 3  | XX.Xx           | XX%         | X.Xx                           | +/-XX%                        |

### Implied Growth Reverse-Engineering

The market price implies specific expectations. Calculate what must be true for the current price to be fair value:

- **Implied revenue growth rate** (next 3-5 years)
- **Implied terminal margin** (what margins must reach)
- **Implied duration of growth** (how many years at elevated growth)
- **Reasonableness check**: Compare implied growth to historical execution, TAM constraints, and competitive dynamics

**Red flag thresholds**: Implied growth >2x historical sustained rate, implied margins >industry best-in-class, implied growth duration >10 years.

### DCF Sensitivity Analysis

Identify the 2-3 variables that most affect fair value and build a sensitivity matrix:

```
| Revenue CAGR \ WACC | 8%    | 9%    | 10%   | 11%   | 12%   |
|---------------------|-------|-------|-------|-------|-------|
| 25%                 | $XXX  | $XXX  | $XXX  | $XXX  | $XXX  |
| 20%                 | $XXX  | $XXX  | $XXX  | $XXX  | $XXX  |
| 15%                 | $XXX  | $XXX  | $XXX  | $XXX  | $XXX  |
| 10%                 | $XXX  | $XXX  | $XXX  | $XXX  | $XXX  |
```

Highlight the cell that matches current market price. This reveals what the market is pricing in.

### Scenario Pricing Table

| Scenario | Probability | Key Assumptions | Fair Value | Upside/Downside |
|----------|------------|-----------------|------------|-----------------|
| **Bull** | XX% | [Specific growth, margin, multiple assumptions] | $XXX | +XX% |
| **Base** | XX% | [Specific growth, margin, multiple assumptions] | $XXX | +/-XX% |
| **Bear** | XX% | [Specific growth, margin, multiple assumptions] | $XXX | -XX% |
| **Expected Value** | 100% | Probability-weighted | **$XXX** | **+/-XX%** |

**Rules for scenario construction**:
- Bull is NOT "everything goes right." It is the realistic upside with specific catalysts.
- Bear is NOT "the company goes bankrupt." It is the realistic downside with specific risks.
- Probabilities must reflect actual likelihood, not 33/34/33 lazy splits.
- Assumptions must be internally consistent within each scenario.

### Hype Premium vs Quality Premium Assessment

Not all premiums are created equal. Distinguish between:

**Quality Premium** (justified):
- Backed by superior ROIC, durable moat, consistent execution
- Company has earned its premium through 5+ years of results
- Premium is stable or slowly expanding with fundamental improvement

**Hype Premium** (dangerous):
- Driven by narrative, momentum, or fear of missing out
- Premium expanded rapidly without proportional fundamental improvement
- Relies on future scenarios that have never been achieved at scale

**Assessment**: State whether the current premium (vs peers or history) is primarily quality or hype, with specific evidence.

### Margin of Safety Calculation

```
Margin of Safety = (Expected Value - Current Price) / Expected Value

Bargain Threshold:  $XXX  (>30% margin of safety -- strong buy zone)
Fair Value Zone:    $XXX - $XXX  (0-15% margin of safety -- hold/accumulate)
Expensive Threshold: $XXX  (negative margin of safety -- trim/avoid)
```

---

## Output Format

```markdown
## Valuation Sanity Check: [Company Name] ([Ticker]) at $[Price]

### Business Classification
[Type, primary metric, secondary metric, rationale]

### Historical Valuation Range
[3-5 year range table with context]

### Peer Comparison (Growth-Adjusted)
[Comparison table with premium/discount assessment]

### Implied Growth Analysis
[What must be true for current price to be fair]

### DCF Sensitivity Matrix
[Key variable sensitivity table]

### Scenario Pricing
[Bull/Base/Bear with probabilities and expected value]

### Premium Assessment
[Quality premium vs hype premium determination]

### Margin of Safety
[Bargain threshold, fair value zone, expensive threshold]

### Verdict
[Overvalued / Fairly Valued / Undervalued with confidence level and action]
```

---

## Quality Criteria

- Business type correctly identified and appropriate metrics selected
- Historical range includes context (not just numbers)
- Peer comparison is growth-adjusted (raw multiples alone are insufficient)
- Implied growth rates are explicitly calculated and reasonableness-checked
- Scenarios have differentiated assumptions (not lazy +/-10% variations)
- Probability weights reflect actual assessment (not 33/34/33)
- Premium assessment distinguishes quality from hype with evidence
- Margin of safety thresholds produce specific price levels
- Self-check: Cross-method reconciliation performed and discrepancies explained

---

## Common Pitfalls

1. **Wrong metric for the business type**: Valuing a high-growth SaaS company on P/E when earnings are intentionally depressed by growth investment, or valuing a REIT on P/E when depreciation makes earnings meaningless. Always start with the mapping table.

2. **Raw multiple comparison without growth adjustment**: Concluding that a 40x P/E stock is "expensive" without checking that it is growing 3x faster than a 20x P/E peer. PEG or equivalent growth-adjusted metrics are mandatory for cross-company comparison.

3. **Anchoring to current price**: Unconsciously building DCF assumptions that reverse-engineer to the current price. Build the model with independent assumptions first, then compare to market price. If your "independent" fair value is within 5% of market price, you probably anchored.

4. **Lazy scenario construction**: Bull/Base/Bear scenarios that differ only in multiple applied to the same earnings estimate. Each scenario must have distinct fundamental assumptions (growth rate, margins, competitive outcome).

5. **Ignoring regime changes**: Using 5-year average multiples when interest rates, growth expectations, or competitive dynamics have structurally changed. Historical ranges are context, not destiny.

---

## Examples

### Example 1: High-Growth SaaS at 20x Revenue

**Context**: Evaluating Datadog (DDOG) trading at $130/share, ~20x NTM revenue.

**Business classification**: High-Growth SaaS (30%+ revenue growth). **Primary metric**: EV/NTM Revenue. **Secondary**: Rule of 40, NTM EV/FCF. **Avoid**: P/E (growth investment distorts earnings).

**Historical range**: 5Y high 45x NTM revenue (2021 peak), 5Y low 12x (2022 trough), 3Y median 18x. Current 20x sits at 58th percentile. Context: 2021 peak driven by zero-rate euphoria; 2022 trough by rate shock. Current level reflects normalized growth expectations.

**Implied growth analysis**: At 20x NTM revenue with ~25% growth, market implies sustained 20%+ growth for 5+ years with FCF margins expanding to 25%+. **Reasonableness**: Achievable given observability TAM expansion, but requires continued best-in-class execution and no meaningful competitive erosion from cloud-native alternatives.

**Scenario table**: Bull (25% probability): 30% revenue CAGR sustained, multiple expansion to 25x, fair value $185 (+42%). Base (50% probability): 22% revenue CAGR, multiple stable at 18x, fair value $125 (-4%). Bear (25% probability): 15% revenue CAGR, multiple compression to 12x, fair value $75 (-42%). **Expected value**: $127. **Margin of safety**: -2% (essentially at fair value).

**Verdict**: Fairly Valued. No margin of safety at current price. Would become attractive below $105 (>15% margin of safety). Premium is primarily quality (consistent execution, best-in-class metrics), not hype.

### Example 2: Mature Dividend Stock at 15x Earnings

**Context**: Evaluating Johnson & Johnson (JNJ) trading at $160/share, ~15x NTM P/E.

**Business classification**: Consumer Staples / Diversified Healthcare. **Primary metric**: P/E, EV/EBITDA. **Secondary**: Dividend Yield, FCF Yield. **Avoid**: EV/Revenue alone (margin structure is the value driver).

**Historical range**: 5Y high 19x P/E (2020 COVID safety trade), 5Y low 13x (2023 talc litigation peak fear), 3Y median 16x. Current 15x sits at 38th percentile. Context: Discount reflects litigation overhang and MedTech segment growth deceleration.

**Implied growth analysis**: At 15x P/E, market implies low-single-digit EPS growth (3-5%) in perpetuity. **Reasonableness**: Conservative. JNJ has delivered 5-7% EPS CAGR historically. If litigation resolves favorably, current price undervalues normalized earnings power.

**Scenario table**: Bull (20% probability): Litigation resolved below reserve, MedTech accelerates, multiple re-rates to 18x, fair value $195 (+22%). Base (55% probability): Litigation settles within range, 5% EPS growth, multiple stable at 16x, fair value $170 (+6%). Bear (25% probability): Litigation exceeds reserves, pharma patent cliff worse than expected, multiple compresses to 13x, fair value $130 (-19%). **Expected value**: $165. **Margin of safety**: 3% (thin but positive).

**Verdict**: Slightly Undervalued. Modest margin of safety with 3.1% dividend yield providing downside support. Attractive entry below $150 (>9% margin of safety). Premium assessment: No hype premium -- trading at a discount to historical norms. Discount reflects real litigation risk, not irrational fear.

---

## Integration

- **Receives from**: `competitive-moat-audit` (moat score informs appropriate premium level)
- **Feeds into**: `portfolio-overlap-detector` (valuation drives position sizing decisions)
- **Companion**: Run valuation check alongside moat audit for complete investment thesis
- **Update frequency**: Re-run after earnings reports, significant price moves (>15%), or material news events
