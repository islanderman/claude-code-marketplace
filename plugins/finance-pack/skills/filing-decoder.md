---
name: filing-decoder
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: >
  Analyze SEC filings (10-K, 10-Q, 8-K, proxy statements) through forensic lenses
  to detect risk factor changes, accounting red flags, cash flow vs income discrepancies,
  insider and governance signals, and year-over-year deltas that reveal what management
  does not want investors to notice.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "analyze SEC filing"
  - "decode filing"
  - "10-K analysis"
  - "10-Q analysis"
  - "8-K analysis"
  - "proxy statement analysis"
  - "filing red flags"
  - "forensic accounting analysis"
  - "what changed in the filing"
modes:
  standalone: true
  teammate: true
---

# Filing Decoder

## ULTRATHINK Activation

**Mode**: EXPERT MODE with FOCUS MODE -- forensic financial analysis
**Optimization**: Systematic multi-lens examination, delta detection, quantitative red flag scoring
**Focus**: Extract signals hidden in regulatory filings by analyzing what changed, what was buried, and what the numbers say when the narrative is stripped away

---

## Purpose

SEC filings are the only legally mandated source of truth about a public company. Unlike earnings calls, press releases, or investor presentations, filings carry legal liability for misstatement. This makes them simultaneously the most reliable and the most carefully constructed documents a company produces. The most valuable information is not in the headline numbers -- it is in the risk factor changes, footnote disclosures, accounting policy shifts, and cash flow patterns that most investors never read.

**Core Value**: Perform institutional-grade forensic analysis of regulatory filings to identify material signals, accounting red flags, and governance concerns that are not surfaced in management narratives or sellside research summaries.

---

## Methodology (4-Phase Framework)

### Phase 1: Risk Factor Delta Analysis

Analyze with deliberation by performing a precise comparison of risk factors between the current filing and the prior comparable filing (10-K to prior 10-K, 10-Q to prior 10-Q).

**Delta Categories**:

| Delta Type | What It Means | Severity Signal |
|---|---|---|
| **New risk added** | A threat that management now considers material enough to disclose | High -- investigate why now |
| **Risk removed** | A previously disclosed risk is no longer mentioned | Medium -- resolved or reclassified? |
| **Language intensified** | Same risk, stronger wording (e.g., "may" changed to "likely") | High -- threat is escalating |
| **Language softened** | Same risk, weaker wording | Low -- may signal resolution |
| **Risk reordered** | Moved higher or lower in the list | Medium -- priority shift |
| **Risk merged or split** | Combined with another risk or separated into sub-risks | Medium -- assess whether this obscures or clarifies |
| **Quantification added** | Previously qualitative risk now has dollar figures or probabilities | High -- risk has become measurable (often means it has materialized) |
| **Quantification removed** | Previously quantified risk now described only qualitatively | High -- may signal uncertainty or desire to obscure magnitude |

**Step-by-step process**:
1. Extract the full risk factor section from the current and prior filings
2. Perform paragraph-level comparison to identify additions, deletions, and modifications
3. Classify each change by delta type
4. Assess materiality: Does this risk factor change align with or contradict management's public narrative?
5. Cross-reference: Do new risks appear in recent 8-K filings, news, or litigation?

**Self-check**: Are there risks that should be disclosed based on public information but are conspicuously absent? This is the highest-signal finding.

### Phase 2: Accounting Red Flag Detection

Apply multi-layer analysis using quantitative forensic accounting screens. Each screen targets a specific manipulation pattern.

**Revenue Recognition Analysis**:

| Screen | What to Calculate | Red Flag Threshold |
|---|---|---|
| **Days Sales Outstanding (DSO)** | (Accounts Receivable / Revenue) x Days in Period | DSO increasing faster than revenue growth |
| **Deferred Revenue Trend** | Current deferred revenue vs prior periods | Declining deferred revenue with "growing" reported revenue |
| **Revenue Concentration** | Top customer % of total revenue | Increasing concentration or undisclosed customer identity |
| **Channel Stuffing Indicators** | Q4 revenue spike relative to Q1-Q3 pattern | Abnormal seasonality patterns appearing recently |
| **Bill-and-Hold Arrangements** | Revenue recognized before delivery | Any material amount warrants investigation |

**Accruals and Earnings Quality**:

| Screen | What to Calculate | Red Flag Threshold |
|---|---|---|
| **Accruals Ratio** | (Net Income - Operating Cash Flow) / Total Assets | Ratio > 10% or increasing trend over 3+ quarters |
| **GAAP vs Non-GAAP Gap** | Non-GAAP EPS minus GAAP EPS | Gap widening; non-GAAP adjustments growing as % of GAAP earnings |
| **Stock-Based Compensation** | SBC as % of revenue and as % of operating income | SBC > 15% of revenue or excluded from "adjusted" profitability |
| **One-Time Charges Frequency** | Number of "one-time" or "non-recurring" charges in trailing 8 quarters | More than 2 "one-time" charges in 8 quarters = not one-time |
| **Reserve Releases** | Reversals of prior accruals or provisions | Material reserve releases that inflate current-period earnings |
| **Capitalization Policy Changes** | Costs previously expensed now being capitalized | Any change that shifts costs from income statement to balance sheet |

**Depreciation and Amortization Forensics**:
- Compare useful life assumptions to industry peers (longer lives = lower annual expense = inflated earnings)
- Detect changes in depreciation method
- Assess whether capitalized software development costs are growing disproportionately to revenue

### Phase 3: Cash Flow Forensics

Use root-cause analysis and depth-first reasoning to reconcile the income statement narrative with cash flow reality.

**Operating Cash Flow vs Net Income Divergence**:

This is the single most important forensic screen. Sustained divergence where net income exceeds operating cash flow indicates earnings quality problems.

| Pattern | Interpretation | Severity |
|---|---|---|
| **OCF > Net Income (sustained)** | Healthy -- non-cash charges (D&A) create gap; cash generation exceeds accounting earnings | Green |
| **OCF ~ Net Income** | Neutral -- earnings approximately match cash generation | Green |
| **OCF < Net Income (1-2 quarters)** | Caution -- may be timing (working capital swings); investigate specifics | Yellow |
| **OCF < Net Income (3+ quarters)** | Warning -- earnings quality deterioration; net income may be overstated through accruals | Red |
| **OCF negative, Net Income positive** | Critical -- company reports profits but burns cash; unsustainable without explaining cause | Red |

**Working Capital Manipulation Detection**:

| Component | Manipulation Pattern | How to Detect |
|---|---|---|
| **Accounts Receivable** | Aggressive revenue recognition inflates AR | AR growth >> Revenue growth |
| **Inventory** | Understating write-downs inflates inventory value | Inventory growth >> COGS growth; inventory days increasing |
| **Accounts Payable** | Extending payment terms to suppliers to boost OCF | AP days increasing significantly; check supplier concentration |
| **Prepaid Expenses** | Capitalizing costs that should be expensed | Prepaid growing faster than revenue |
| **Accrued Liabilities** | Under-accruing expenses to inflate near-term earnings | Accrued liabilities declining while business is growing |

**CapEx Classification Analysis**:
- Compare maintenance capex vs growth capex breakdown (if disclosed)
- Assess total capex as % of revenue vs historical trend and peers
- Detect whether spending is shifting from capex (balance sheet) to opex (income statement) or vice versa to manage reported metrics
- Free cash flow should be calculated using total capex, not management-defined "adjusted free cash flow" that excludes convenient items

**Self-check**: Does the cash flow statement tell a consistent story with the income statement and balance sheet? If management says "strong growth" but working capital is deteriorating and OCF lags net income, the cash flow statement is the more reliable indicator.

### Phase 4: Governance, Insider Signals, and Footnote Mining

Apply systematic, thorough analysis to the sections of filings that receive the least attention but contain disproportionate signal.

**Related Party Transaction Scanning**:
- Identify all related party transactions disclosed in footnotes
- Assess materiality (dollar amounts relative to revenue or net income)
- Evaluate whether transaction terms are arm's-length (would a third party agree to these terms?)
- Flag transactions involving board members, executives, or their family members
- Check for entities controlled by insiders that do business with the company

**Insider and Governance Signals**:

| Signal | Where to Find | Interpretation |
|---|---|---|
| **Executive compensation changes** | Proxy statement / DEF 14A | Performance metrics changed to easier targets = lowered expectations |
| **Metric changes in incentive plans** | Proxy statement | Switching from revenue to "adjusted EBITDA" targets = margin pressure |
| **Board turnover** | 10-K Part III or Proxy | Multiple departures in 12 months = governance concerns |
| **Auditor change** | 8-K Item 4.01 | Auditor dismissed or resigned = investigate immediately |
| **Insider trading patterns** | Form 4 filings | Systematic selling during open windows while maintaining bullish guidance |
| **10b5-1 plan adoption** | Form 4 footnotes | New plan adopted shortly before material disclosure = timing concern |
| **Material weakness disclosure** | 10-K Item 9A | Internal control deficiency that could result in material misstatement |
| **Going concern qualification** | Auditor's report | Auditor doubts the company can continue operating for 12 months |

**Footnote Mining Priority Areas**:

Footnotes contain legally required disclosures that management would prefer investors not read. Priority mining areas:

1. **Revenue recognition policy changes** -- Any modification signals a shift in how revenue is measured
2. **Lease obligations and off-balance-sheet arrangements** -- Hidden liabilities
3. **Segment reporting changes** -- Combining or eliminating segments often obscures underperformance
4. **Contingent liabilities and litigation provisions** -- Quantified legal exposure
5. **Subsequent events** -- Material events after the filing period but before filing date
6. **Pension and post-retirement obligations** -- Assumption changes (discount rate, return rate) that alter reported obligations
7. **Goodwill and intangible asset impairment testing** -- Assumptions about fair value; declining headroom = future write-down risk
8. **Variable interest entities** -- Consolidated or unconsolidated entities that may carry hidden risk

**Year-over-Year Language Comparison**:
- Compare MD&A (Management Discussion and Analysis) sections word-for-word between filings
- Identify language that was added, removed, or materially modified
- Pay special attention to forward-looking statement qualifiers becoming more hedged
- Track changes in how management describes competitive position, customer demand, and pricing power

---

## Red Flag Severity Scoring

Every finding is scored on a three-tier system with required evidence:

| Severity | Criteria | Required Evidence | Action |
|---|---|---|---|
| **GREEN** | Normal business variation; consistent with narrative | Quantitative context showing metric within historical range | Note and monitor |
| **YELLOW** | Unusual pattern that warrants monitoring; may indicate emerging issue | Specific metric or language change identified with 2+ data points | Investigate deeper; compare to peers |
| **RED** | Material concern that contradicts management narrative or indicates manipulation | Quantified divergence with historical comparison; specific quotes or metrics | Immediate deep dive; consider position adjustment |

**Scoring Rules**:
- Every RED flag must cite specific numbers, quotes, or filing references
- YELLOW flags require at least two supporting data points
- GREEN ratings should explain why the finding is not concerning despite appearing anomalous
- Overall filing score = weighted average considering number and severity of flags

---

## Output Format

```markdown
# Filing Decoder: [Company] [Filing Type] [Period]
## Filing Date: [Date] | Analysis Date: [Date]

### Executive Summary
[3-5 sentences: Filing health assessment, highest-severity findings, overall signal]

### Risk Factor Deltas
[Table: Delta Type | Risk Description | Prior Language | Current Language | Severity | Interpretation]
- New risks: [count]
- Intensified risks: [count]
- Removed risks: [count]

### Accounting Red Flags
[Table: Screen | Current Value | Prior Value | Trend | Peer Comparison | Severity]
- Revenue quality: [GREEN/YELLOW/RED]
- Earnings quality: [GREEN/YELLOW/RED]
- Accruals health: [GREEN/YELLOW/RED]

### Cash Flow Forensics
- OCF vs Net Income: [Ratio and trend with 4-quarter history]
- Working Capital Analysis: [Component-level assessment]
- CapEx Classification: [Maintenance vs growth; trend assessment]
- Free Cash Flow Quality: [Assessment]

### Governance and Insider Signals
[Table: Signal Type | Finding | Severity | Evidence]

### Footnote Findings
[Prioritized list of material footnote disclosures with interpretation]

### Year-over-Year Language Changes
[Key MD&A language modifications with before/after comparison]

### Red Flag Summary
| # | Finding | Severity | Evidence | Filing Reference |
|---|---|---|---|---|
| 1 | ... | RED | ... | Note X, Page Y |
| 2 | ... | YELLOW | ... | ... |

### Overall Filing Health Score: [GREEN / YELLOW / RED]
[Justification based on aggregate findings]

### Top 3 Actionable Findings
1. **Finding**: ... | **Significance**: ... | **Action**: ... | **Confidence**: ...
2. ...
3. ...
```

---

## Quality Criteria

- [ ] Risk factor comparison performed against correct prior comparable filing (10-K to 10-K, not 10-K to 10-Q)
- [ ] All quantitative screens calculated with actual numbers from the filing, not estimated
- [ ] Cash flow forensics include at least 4-quarter trend analysis, not just current period
- [ ] GAAP vs non-GAAP gap quantified with specific dollar amounts and percentage impact
- [ ] Every RED flag cites specific filing section, page, or note number
- [ ] Related party transactions assessed for arm's-length terms
- [ ] Footnote mining covers all 8 priority areas listed in methodology
- [ ] Year-over-year language comparison uses actual quoted text, not paraphrased summaries
- [ ] Overall filing health score justified by aggregated evidence
- [ ] Self-check: Could a forensic accountant reproduce these findings from the same filing?

---

## Common Pitfalls

1. **Reading only the MD&A and skipping footnotes**: Management controls the MD&A narrative. Footnotes contain legally required disclosures that often contradict the optimistic tone of the narrative section. The footnotes are where companies disclose what they must, not what they want to.

2. **Comparing the wrong filing periods**: A 10-Q should be compared to the same quarter's prior-year 10-Q (seasonality matters) and to the sequential 10-Q (trend matters). Comparing Q1 to the annual 10-K produces misleading deltas. Always use the correct comparable.

3. **Ignoring non-GAAP reconciliation details**: The reconciliation table between GAAP and non-GAAP figures is where companies reveal the magnitude and nature of their adjustments. A company that adds back stock-based compensation, restructuring, acquisition costs, and litigation in every quarter is not reporting "one-time" items -- it is systematically inflating reported profitability.

4. **Treating cash flow as manipulation-proof**: While harder to manipulate than earnings, operating cash flow can be managed through payment timing (extending AP), factoring receivables, reclassifying items between operating and investing sections, and other techniques. Always decompose OCF into its components rather than using the headline number.

5. **Missing the significance of accounting policy changes**: A change in revenue recognition timing, depreciation method, or capitalization policy in the footnotes is often the single most important signal in the entire filing. These changes are made deliberately and their impact should be quantified.

---

## Examples

### Example 1: Pharma Company with New Regulatory Risk Factors

**Context**: BioHealth Corp (fictional) files 10-K for fiscal year. Lead product faces patent cliff in 18 months. Pipeline drug in Phase 3.

**Risk Factor Deltas**:

| Delta Type | Finding | Severity |
|---|---|---|
| **New risk added** | "We may face additional generic competition earlier than anticipated due to pending Paragraph IV certifications" | RED |
| **Language intensified** | Prior: "We believe our IP portfolio provides adequate protection." Current: "While we intend to vigorously defend our intellectual property, there can be no assurance that our patents will not be successfully challenged." | RED |
| **New risk added** | "Changes in drug pricing legislation, including the Inflation Reduction Act, may materially impact revenue from our Medicare-exposed products" | YELLOW |
| **Risk removed** | Prior filing disclosed clinical trial enrollment risk for Phase 3 drug. Now absent. | GREEN (trial fully enrolled; risk resolved) |
| **Quantification added** | "Products representing approximately 42% of current revenue face loss of exclusivity within the next 24 months" | RED (previously disclosed qualitatively without percentage) |

**Accounting Red Flags**:

| Screen | Current | Prior Year | Trend | Severity |
|---|---|---|---|---|
| DSO | 78 days | 71 days | Increasing 3 consecutive quarters | YELLOW |
| Accruals Ratio | 8.2% | 5.1% | Significant increase | YELLOW |
| GAAP vs Non-GAAP EPS gap | $1.42 | $0.88 | Gap widening 61% YoY | RED |
| SBC as % of revenue | 4.2% | 3.8% | Modest increase | GREEN |

**Cash Flow Forensics**:
- OCF / Net Income ratio: 0.82 (current) vs 1.15 (prior year)
- Divergence driver: AR increase ($340M) outpacing revenue growth (6%); DSO trending up
- Working capital: Inventory build (+$180M) ahead of product launch -- reasonable if launch on track, concerning if launch delays
- CapEx: $420M capex classified as "growth," but $280M appears to be manufacturing capacity for existing products (maintenance misclassified)

**Footnote Finding (Critical)**:
- Note 14 discloses a change in revenue recognition for managed care rebates: "Effective Q1, the Company revised its estimate of Medicaid rebate accruals, resulting in a $95M favorable adjustment to net revenue." This one-time adjustment represents 3.2% of quarterly revenue. Without this adjustment, revenue growth would have been 2.8%, not 6.0%.

**Top 3 Actionable Findings**:
1. **Finding**: Patent cliff risk quantified at 42% of revenue; language shifted from confident to defensive. **Significance**: Management's own filing reveals they are less confident in IP defense than public statements suggest. **Action**: Model revenue decline scenarios starting 12 months pre-patent expiry. **Confidence**: High.
2. **Finding**: Revenue growth of 6% includes $95M one-time rebate adjustment. Underlying growth approximately 2.8%. **Significance**: Headline revenue growth is materially overstated by an accounting adjustment buried in Note 14. **Action**: Adjust revenue growth models to exclude one-time benefit; compare to sellside estimates that may not have caught this. **Confidence**: High.
3. **Finding**: GAAP/non-GAAP gap widened 61% YoY, primarily from "restructuring" and "acquisition integration" charges. **Significance**: Recurring charges labeled as non-recurring inflate non-GAAP profitability. Fourth consecutive year of "one-time" restructuring. **Action**: Evaluate the company on GAAP metrics only; discount non-GAAP earnings narrative. **Confidence**: High.

---

### Example 2: Software Company with Widening GAAP/Non-GAAP Gap

**Context**: DataFlow Systems (fictional) files 10-Q for Q3. SaaS platform showing "strong ARR growth" per management. Stock trades at 15x forward non-GAAP revenue.

**Risk Factor Deltas**:

| Delta Type | Finding | Severity |
|---|---|---|
| **New risk added** | "Increasing competition from open-source alternatives and cloud-native solutions may require us to reduce pricing or increase sales and marketing expenditures" | YELLOW |
| **Language intensified** | Customer concentration risk: prior "No single customer exceeds 5% of revenue." Current: "Our top 10 customers represent approximately 38% of ARR, and the loss of any significant customer could materially impact results." | RED |
| **New risk added** | "We may not achieve the expected benefits from recent acquisitions within the anticipated timeframe, and integration may require additional resources" | YELLOW |

**Accounting Red Flags**:

| Screen | Current | Prior Year | Trend | Severity |
|---|---|---|---|---|
| GAAP Net Income | ($45M) loss | ($22M) loss | Loss doubling | RED |
| Non-GAAP Net Income | $38M profit | $31M profit | Profitable and growing | See gap analysis |
| GAAP/Non-GAAP gap | $83M | $53M | Gap widened 57% | RED |
| SBC as % of revenue | 24.6% | 19.1% | Increasing rapidly | RED |
| SBC as % of non-GAAP operating income | 148% | 112% | SBC exceeds "profits" | RED |
| Remaining Performance Obligations (RPO) growth | 18% | 29% | Decelerating | YELLOW |
| Deferred Revenue growth | 14% | 26% | Decelerating faster than revenue | RED |

**GAAP/Non-GAAP Reconciliation Breakdown**:

| Adjustment | Current Q | Prior Year Q | Change | Assessment |
|---|---|---|---|---|
| Stock-based compensation | $58M | $41M | +41% | SBC growing faster than revenue (28% growth) |
| Acquisition-related costs | $12M | $5M | +140% | Acquisitions increasing; integration costs rising |
| Restructuring charges | $8M | $4M | +100% | Second consecutive quarter of "restructuring" |
| Amortization of acquired intangibles | $5M | $3M | +67% | Directly related to acquisition strategy |
| **Total adjustments** | **$83M** | **$53M** | **+57%** | Adjustments growing 2x revenue growth rate |

**Critical finding**: Stock-based compensation of $58M in the quarter exceeds non-GAAP net income of $38M. The company is not profitable after accounting for the cost of equity compensation used to pay employees. Non-GAAP profitability is an illusion created by excluding the company's largest expense after COGS.

**Cash Flow Forensics**:
- OCF: $22M (current Q) vs $28M (prior year Q) -- declining despite "growth"
- Net Income: ($45M) loss. OCF is positive only because of $58M SBC add-back (non-cash) and $15M increase in deferred revenue
- Free Cash Flow: ($8M) after $30M capex (primarily capitalized software development)
- Capitalized software development costs: $18M this quarter vs $11M prior year (+64%). This spending would be expensed under more conservative accounting, increasing the reported GAAP loss
- Working capital: AR up 34% on 28% revenue growth. DSO increased from 62 to 67 days

**Footnote Finding (Critical)**:
- Note 7: Goodwill impairment testing reveals that one of three reporting segments has fair value exceeding carrying value by only 8% (down from 22% in the prior year). An impairment charge becomes probable if growth assumptions decline further. Potential impairment magnitude: $120M-$180M based on segment goodwill balance.

**Governance Signal**:
- Proxy statement: CEO compensation plan metric changed from "GAAP operating income" to "Non-GAAP operating income" for FY bonus determination. This means management is now incentivized to maximize the metric that excludes their own stock compensation -- a direct conflict of interest.
- Form 4 filings: CFO sold $2.4M in shares via 10b5-1 plan in each of the last 3 months. Plan was adopted 6 weeks before the filing.

**Top 3 Actionable Findings**:
1. **Finding**: SBC ($58M) exceeds non-GAAP net income ($38M). Company is not profitable on a fully-loaded basis. **Significance**: The entire profitability narrative relies on excluding the single largest non-COGS expense. At 24.6% of revenue and accelerating, SBC is a permanent cost of doing business, not a "non-cash adjustment" to ignore. **Action**: Revalue the company on GAAP metrics. At 15x non-GAAP revenue, the stock is dramatically more expensive on a GAAP basis. **Confidence**: High.
2. **Finding**: Deferred revenue growth (14%) decelerating faster than reported revenue growth (28%). RPO growth also slowing (18% vs 29%). **Significance**: These are leading indicators. Reported revenue reflects past bookings; deferred revenue and RPO reflect future revenue. The divergence signals that revenue growth will decelerate in 2-3 quarters. **Action**: Model revenue deceleration to 18-22% and assess valuation impact. **Confidence**: High.
3. **Finding**: Goodwill impairment headroom declined from 22% to 8% in one segment; capitalized software costs growing 64% (faster than revenue). **Significance**: Two balance sheet items are at risk of future write-downs, which would further widen the GAAP loss. Capitalizing software costs aggressively also flatters current-period GAAP losses. **Action**: Stress-test the balance sheet under a growth deceleration scenario; quantify impairment and write-down exposure. **Confidence**: Medium.

---

## Integration

**Upstream dependencies**: Requires the full SEC filing (EDGAR or company IR site). For delta analysis, requires the prior comparable filing. For insider analysis, requires Form 4 and proxy statement data.

**Downstream outputs**: Feed risk factor findings and red flag severity into `catalyst-timeline-builder` as risk modifiers for upcoming catalysts. Connect accounting red flags to `earnings-call-translator` to assess whether management addresses the issues found in the filing. Use governance signals to adjust management credibility scoring.

**Refresh cadence**: Apply to every 10-K, 10-Q, and material 8-K filing. Proxy statement analysis annually. Maintain a rolling tracker of red flag severity trends across filings to detect deterioration patterns over 4-8 quarters.
