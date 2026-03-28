---
name: catalyst-timeline-builder
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: >
  Build a prioritized timeline of upcoming catalysts for a stock or portfolio,
  mapping bull/bear outcomes, scoring impact asymmetry, analyzing catalyst clustering
  effects, and constructing pre-planned response matrices for each scenario.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "build catalyst timeline"
  - "map upcoming catalysts"
  - "catalyst analysis"
  - "event calendar"
  - "what are the upcoming catalysts"
  - "catalyst stack"
  - "event-driven analysis"
modes:
  standalone: true
  teammate: true
---

# Catalyst Timeline Builder

## ULTRATHINK Activation

**Mode**: EXPERT MODE with MAX-PRECISION -- institutional event-driven analysis
**Optimization**: Systematic catalyst identification, probabilistic impact scoring, clustering correlation analysis
**Focus**: Prioritized catalyst mapping with pre-planned response matrices and asymmetric opportunity detection

---

## Purpose

Catalysts move markets. The difference between retail and institutional analysis is not whether you know a catalyst exists -- it is whether you have rigorously scored its probability-weighted impact, mapped its bull/bear outcome distributions, identified how it interacts with adjacent catalysts, and pre-planned your response before the event occurs. This skill builds that complete framework.

**Core Value**: Transform a loose calendar of upcoming events into a scored, correlated, actionable decision matrix that eliminates reactive decision-making under pressure.

---

## Methodology (4-Phase Framework)

### Phase 1: Catalyst Identification and Taxonomy

Analyze with deliberation to construct a comprehensive catalyst inventory. Use breadth-first reasoning to ensure no material event is missed.

**Catalyst Taxonomy**:

| Category | Examples | Typical Lead Time | Date Precision |
|---|---|---|---|
| **Earnings** | Quarterly reports, pre-announcements, guidance updates | 3-12 weeks | Confirmed (exact date) |
| **FDA / Regulatory** | PDUFA dates, advisory committees, EUA decisions, CRL responses | 1-12 months | Confirmed or estimated window |
| **Macro / Policy** | FOMC meetings, CPI/PPI prints, fiscal policy votes, tariff deadlines | Known schedule | Confirmed |
| **Product Launch** | New product releases, platform updates, service expansions | Variable | Estimated (often leaked) |
| **M&A / Corporate Action** | Acquisition close, spin-off, tender offer expiration, shareholder vote | 1-6 months | Estimated with regulatory dependency |
| **Insider / Ownership** | 13F filings, insider buying windows, lockup expirations, activist campaigns | Known schedule | Confirmed |
| **Legal / Litigation** | Trial dates, settlement deadlines, patent rulings, class action milestones | Variable | Estimated |
| **Technical / Market Structure** | Index rebalance, options expiration, short interest report, Russell reconstitution | Known schedule | Confirmed |

**Identification Checklist**:
- Review company IR calendar, SEC filings, and press releases
- Check regulatory body calendars (FDA, FCC, EPA, DOJ)
- Review macro calendar for relevant economic data releases
- Scan for analyst day, investor day, or conference appearances
- Check for lockup expirations, secondary offering windows, or debt maturities
- Identify any pending litigation milestones or regulatory decisions
- Note sector-level catalysts that affect the company indirectly

### Phase 2: Impact Scoring and Outcome Mapping

Apply multi-layer analysis to score each catalyst. Use depth-first reasoning on the highest-impact events.

**Impact Score Formula**:

```
Impact Score = Magnitude x Probability x Asymmetry Factor

Where:
  Magnitude   = Expected % move on bull outcome (1-10 scale)
  Probability = Likelihood the catalyst resolves favorably (0.0-1.0)
  Asymmetry   = |Bull upside| / |Bear downside| ratio
                (>1.0 = positive skew, <1.0 = negative skew)
```

**Bull/Bear Outcome Mapping** (for each catalyst):

| Dimension | Bull Case | Base Case | Bear Case |
|---|---|---|---|
| **Outcome description** | What specifically happens | Status quo / in-line | What specifically goes wrong |
| **Estimated price move** | +X% to +Y% | -1% to +1% | -X% to -Y% |
| **Probability** | P(bull) | P(base) | P(bear) |
| **Duration of impact** | Transient vs persistent | Neutral | Transient vs persistent |
| **Second-order effects** | What it unlocks next | Nothing changes | What it blocks or breaks |

**Self-check**: Do bull + base + bear probabilities sum to ~100%? Is the magnitude estimate grounded in comparable historical moves for similar catalysts?

### Phase 3: Catalyst Clustering and Correlation Analysis

Use systematic, context-sensitive reflection to identify how catalysts interact when they converge in time.

**Clustering Analysis**:
- **Temporal clustering**: Identify windows where 2+ catalysts fall within 1-2 weeks of each other
- **Amplifying interactions**: Catalyst A positive outcome increases probability or magnitude of Catalyst B positive outcome (e.g., strong earnings before FDA decision boosts investor confidence for risk-taking)
- **Offsetting interactions**: Catalyst A positive outcome is neutralized by Catalyst B negative outcome (e.g., great product launch overshadowed by sector-wide selloff from macro data)
- **Sequencing dependency**: Order matters -- Catalyst A must resolve before Catalyst B has meaning (e.g., regulatory approval must come before product launch catalyst activates)

**Correlation Matrix** (for clustered catalysts):

| | Catalyst A | Catalyst B | Catalyst C |
|---|---|---|---|
| **Catalyst A** | -- | Amplifying (+0.6) | Independent (0.0) |
| **Catalyst B** | Amplifying (+0.6) | -- | Offsetting (-0.3) |
| **Catalyst C** | Independent (0.0) | Offsetting (-0.3) | -- |

Correlation values: -1.0 (perfectly offsetting) to +1.0 (perfectly amplifying), 0.0 = independent.

**Cluster Risk Assessment**:
- What is the combined scenario if all catalysts in the cluster resolve bullishly?
- What is the combined scenario if all resolve bearishly?
- What is the most probable mixed outcome?

### Phase 4: Response Matrix Construction and Ranking

Execute with precision to build the actionable output. Apply step-by-step reasoning to construct if-then response plans.

**Top 5 Catalyst Ranking** (by portfolio-adjusted impact):

```
Rank = Impact Score x Portfolio Weight x Time Urgency Factor

Where:
  Time Urgency Factor = 1.0 / sqrt(days_until_catalyst / 30)
  (Nearer catalysts receive higher urgency weighting)
```

**Pre-Planned Response Matrix** (for each top-5 catalyst):

| If This Happens | Then Do This | Rationale | Time Horizon |
|---|---|---|---|
| Bull case materializes | [Specific action: trim into strength / add to related position / hold] | [Why this response] | [Immediate / 1 week / 1 month] |
| Base case materializes | [Specific action: hold / minor adjustment] | [Why this response] | [Time horizon] |
| Bear case materializes | [Specific action: cut losses / hedge / add on weakness if thesis intact] | [Why this response] | [Time horizon] |

**Asymmetric Opportunity Identification**:
- Flag catalysts where Asymmetry Factor > 2.0 (bull upside more than 2x bear downside)
- Flag catalysts where market appears to be pricing in the wrong probability distribution
- Flag catalysts where implied volatility is mispriced relative to historical catalyst moves

---

## Output Format

```markdown
# Catalyst Timeline: [Ticker / Portfolio Name]
## Analysis Date: [Date] | Time Horizon: [X weeks/months]

### Catalyst Inventory
[Table: Date | Category | Catalyst | Date Precision | Impact Score]

### Top 5 Catalysts by Expected Portfolio Impact
1. [Catalyst] -- Impact Score: X.X | Date: [date] | Asymmetry: X.X
   - Bull: [outcome, +X%] | Bear: [outcome, -X%]
   - Response: [if-then matrix summary]
2. ...

### Catalyst Clustering Windows
[Date range]: [Catalyst A] + [Catalyst B]
- Combined bull scenario: [description, +X%]
- Combined bear scenario: [description, -X%]
- Correlation: [amplifying/offsetting/independent]

### Asymmetric Opportunities
[Catalysts with Asymmetry > 2.0 or mispriced implied vol]

### Pre-Planned Response Matrix
[Full if-then table for top 5 catalysts]

### Timeline Visualization
[Chronological catalyst map with scoring annotations]
```

---

## Quality Criteria

- [ ] All material catalysts identified across all 8 taxonomy categories
- [ ] Date precision clearly labeled (confirmed vs estimated vs window)
- [ ] Impact scores grounded in historical comparable moves, not guesswork
- [ ] Bull/bear probabilities sum to approximately 100% for each catalyst
- [ ] Catalyst clustering windows identified with correlation assessment
- [ ] Response matrix contains specific, actionable instructions (not vague "monitor")
- [ ] Asymmetric opportunities flagged with supporting evidence
- [ ] Top 5 ranking accounts for portfolio weight and time urgency
- [ ] Self-check: No major catalyst category omitted; scoring internally consistent

---

## Common Pitfalls

1. **Ignoring second-order catalysts**: A macro event (FOMC) can dominate any company-specific catalyst. Always include relevant macro and sector-level events, not just company-specific ones.

2. **Treating all catalysts as independent**: Catalysts interact. An FDA approval means nothing if the company simultaneously reports a cash crunch in earnings. Always assess clustering and correlation.

3. **Anchoring magnitude estimates to recent volatility**: A stock that has been calm for 6 months can move 30% on a binary FDA catalyst. Use category-specific historical comparables, not recent realized vol.

4. **Pre-planning only the bull case**: The response matrix must cover bear and base cases with equal rigor. The value is in eliminating emotional decision-making during drawdowns, not in celebrating gains.

5. **Stale timeline maintenance**: A catalyst timeline is a living document. Catalysts resolve, new ones emerge, dates shift. Flag the refresh cadence (weekly or after each catalyst resolves).

---

## Examples

### Example 1: Biotech Pre-FDA Catalyst Stack

**Context**: ACME Therapeutics (fictional), a mid-cap biotech with Phase 3 readout and PDUFA date converging within 8 weeks. Portfolio weight: 6%.

**Catalyst Inventory**:

| Date | Category | Catalyst | Precision | Impact Score |
|---|---|---|---|---|
| Apr 15 | FDA | Advisory Committee vote on lead drug | Confirmed | 8.4 |
| May 28 | FDA | PDUFA decision date | Confirmed | 9.1 |
| Apr 22 | Earnings | Q1 earnings report | Confirmed | 3.2 |
| Apr 10 | Insider | Lockup expiration (IPO +180 days) | Confirmed | 2.8 |
| Ongoing | Legal | Patent challenge from generic competitor | Estimated Q2 | 4.5 |

**Top Catalyst**: PDUFA decision (Impact 9.1)
- Bull: Approval -- +40% to +60%, unlocks EU filing, commercial ramp
- Bear: CRL issued -- -50% to -65%, cash runway becomes critical
- Asymmetry Factor: 0.8 (negative skew -- bear downside exceeds bull upside)

**Clustering Window**: Apr 10-22 (lockup + AdCom + earnings within 12 days)
- Amplifying: Positive AdCom vote + strong earnings = momentum into PDUFA
- Offsetting: Lockup selling pressure may cap upside from positive AdCom
- Correlation: Lockup-to-AdCom = offsetting (-0.3); AdCom-to-Earnings = independent (0.0)

**Response Matrix (PDUFA)**:
| Outcome | Action | Rationale |
|---|---|---|
| Approval | Trim 40% of position into gap-up; hold remainder for EU catalyst | Lock partial gains; binary risk resolved |
| CRL with path forward | Hold 50%, cut 50%; reassess resubmission timeline | Preserve optionality if fixable |
| CRL with no clear path | Exit entire position within 48 hours | Thesis broken; preserve capital |

**Asymmetric Opportunity**: The stock is pricing ~55% probability of approval. If AdCom votes 10-3 in favor, the PDUFA probability jumps to ~85%+. This creates a post-AdCom asymmetric entry: the market will partially reprice approval odds, but not fully, leaving upside skew into PDUFA.

---

### Example 2: Tech Company Earnings + Product Launch Convergence

**Context**: MegaCloud Corp (fictional), large-cap cloud platform. Upcoming earnings and annual developer conference fall within 3 weeks. Portfolio weight: 12%.

**Catalyst Inventory**:

| Date | Category | Catalyst | Precision | Impact Score |
|---|---|---|---|---|
| Jul 24 | Earnings | Q2 earnings + FY guidance update | Confirmed | 6.8 |
| Aug 8 | Product Launch | Annual developer conference; new AI platform tier announced | Confirmed | 5.2 |
| Jul 11 | Macro | June CPI print | Confirmed | 3.0 |
| Aug 15 | Technical | Options expiration (heavy open interest at $180 strike) | Confirmed | 2.1 |
| Q3 est. | M&A | Rumored acquisition of data analytics startup | Estimated | 3.8 |

**Top Catalyst**: Q2 Earnings (Impact 6.8)
- Bull: Revenue beat + raised guidance + AI revenue breakout disclosed -- +8% to +14%
- Bear: Revenue miss or flat guidance + rising costs from AI investment -- -10% to -18%
- Asymmetry Factor: 0.9 (roughly symmetric, slightly negative skew)

**Clustering Window**: Jul 24 - Aug 8 (earnings + conference within 15 days)
- Amplifying: Strong earnings validate AI strategy; conference then provides product catalyst for re-rating
- Offsetting: Weak earnings create skepticism lens through which conference announcements are viewed
- Correlation: Strongly amplifying (+0.7) -- sentiment from earnings colors conference reception

**Response Matrix (Earnings)**:
| Outcome | Action | Rationale |
|---|---|---|
| Beat + raised guidance | Hold full position into conference; consider adding 2% on post-earnings dip if it occurs | Earnings validates thesis; conference is next catalyst |
| In-line, guidance maintained | Hold; no action | Base case, wait for conference catalyst |
| Miss or lowered guidance | Trim to 8% weight; set stop-loss at -15% from current | Reduce exposure; conference unlikely to overcome earnings disappointment |

**Asymmetric Opportunity**: If earnings beat but the stock sells off on "not enough AI detail," the conference 15 days later directly addresses that gap. Historical pattern: post-earnings dips before major conferences recover 70% of the time within the conference week. This creates a defined asymmetric entry window.

---

## Integration

**Upstream dependencies**: Requires current company filings, IR calendars, regulatory body schedules, and macro economic calendar. Pair with `filing-decoder` for risk factor context on upcoming catalysts.

**Downstream outputs**: Feed the response matrix into portfolio rebalancing workflows. Use catalyst scores to inform position sizing decisions. Connect to `earnings-call-translator` when earnings is an upcoming catalyst to prepare question-dodge detection framework in advance.

**Refresh cadence**: Rebuild weekly or immediately after any catalyst resolves. Update impact scores as new information emerges (e.g., AdCom vote changes PDUFA probability).
