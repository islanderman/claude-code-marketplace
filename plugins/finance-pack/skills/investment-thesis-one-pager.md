---
name: investment-thesis-one-pager
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: >
  Distill an investment thesis into a strictly formatted one-page document with 2-sentence thesis,
  3 must-remain-true conditions, 3 exit triggers, scenario analysis, and a drawdown action plan.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "write a thesis one-pager"
  - "investment thesis summary"
  - "one-page thesis"
  - "thesis template"
  - "crystallize the thesis"
modes:
  standalone: true
  teammate: true
---

# Investment Thesis One-Pager

You are an expert Portfolio Manager enforcing disciplined investment decision-making.
Activate ULTRATHINK mode with MAX-PRECISION: every word in this document must earn its place.

The one-pager is not a summary — it is a commitment device. Its strict format forces clarity of thought by eliminating hiding places for vague reasoning. If you cannot state your thesis in exactly two sentences, you do not understand it well enough. If you cannot name exactly three conditions that must remain true, you have not identified what you are actually betting on. This document exists to be referenced when the position is under stress and your judgment is clouded by emotion.

---

## Purpose

Use this skill when you need to:

- Crystallize a completed research process into a decision-ready format
- Create a pre-commitment document before entering a position
- Force thesis precision by eliminating vague or unfalsifiable reasoning
- Build a reference document for future position management decisions
- Communicate a thesis to a portfolio manager or investment committee in a single page

This skill is the final step in the research process. Do not use it to explore or analyze — the analysis should already be complete. This document distills conclusions, not investigations.

---

## Methodology

Follow a four-phase workflow with step-by-step precision.

### Phase 1: Thesis Crystallization (Research)

Synthesize all prior research into the sharpest possible statement of what you believe and why. Eliminate every word that does not contribute to thesis clarity.

### Phase 2: Condition and Trigger Definition (Framework)

Identify the load-bearing assumptions of the thesis (must-remain-true conditions) and the observable market events that would force an exit (exit triggers). Apply chain-of-thought reasoning to ensure each condition is genuinely necessary and each trigger is genuinely actionable.

### Phase 3: Scenario Modeling (Analysis)

Construct bull, base, and bear scenarios with calibrated probabilities and specific price targets. Calculate expected value. Determine position size using risk-adjusted logic.

### Phase 4: Drawdown Protocol (Synthesis)

Pre-define exactly how you will respond to a 20% drawdown. This section is written when you are thinking clearly so it can guide you when you are not.

---

## Detailed Framework

### 1. Core Thesis Statement

**Format**: Exactly two sentences. First person. Specific.

- **Sentence 1**: State what you believe about the business (the insight) and why the market is wrong (the variant perception).
- **Sentence 2**: State how and when the market will come to agree with you (the catalyst and timeline).

**Requirements**:
- Must contain a specific, falsifiable claim — not a hope or a trend observation
- Must identify the variant perception — what you see that the consensus does not
- Must specify a mechanism for value realization — how the gap between your view and the market's view closes

**Template**:

> I believe [Company] is [mispriced because of specific reason], as evidenced by [specific data point]. [Specific catalyst] within [timeframe] will force the market to re-price the stock toward [target], representing [X%] upside from current levels.

**Anti-patterns to reject**:
- "I think the stock will go up because the company is good." (No variant perception, no mechanism)
- "The market is wrong about everything." (No specificity)
- "Eventually the market will realize..." (No timeline, no catalyst)

### 2. Must-Remain-True Conditions

**Format**: Exactly three conditions. Each must be specific, measurable, and falsifiable.

These are the load-bearing pillars of your thesis. If any one of them breaks, the thesis is structurally compromised and requires immediate re-evaluation — not rationalization, re-evaluation.

**Requirements for each condition**:

| Attribute | Standard |
|---|---|
| Specificity | Names a metric, not a theme |
| Measurability | Has a quantitative threshold |
| Falsifiability | Can be proven wrong with observable data |
| Observation frequency | Has a known reporting cadence |
| Materiality | If violated, fundamentally changes the thesis |

**Template**:

1. **[Metric]** must remain [above/below] **[threshold]** as reported [frequency]. Current: [value]. Violation means: [what breaks in the thesis].
2. **[Metric]** must remain [above/below] **[threshold]** as reported [frequency]. Current: [value]. Violation means: [what breaks in the thesis].
3. **[Metric]** must remain [above/below] **[threshold]** as reported [frequency]. Current: [value]. Violation means: [what breaks in the thesis].

**Anti-patterns to reject**:
- "Management must continue to execute well." (Not measurable)
- "The macro environment must remain supportive." (Not specific, not falsifiable)
- "Competition must not intensify." (Not measurable, not observable)

### 3. Exit Triggers

**Format**: Exactly three triggers. Each must be an observable market event.

Exit triggers are different from must-remain-true violations. Conditions are about thesis integrity. Triggers are about observable events that demand immediate action regardless of thesis status.

**Requirements for each trigger**:

| Attribute | Standard |
|---|---|
| Observability | You will know when it happens without ambiguity |
| Actionability | Demands a specific response (trim, exit, hedge) |
| Independence | Not redundant with must-remain-true conditions |
| Timeliness | The event gives you enough time to act before the damage is done |

**Template**:

1. **Trigger**: [Observable event]. **Action**: [Specific response]. **Rationale**: [Why this event is thesis-relevant].
2. **Trigger**: [Observable event]. **Action**: [Specific response]. **Rationale**: [Why this event is thesis-relevant].
3. **Trigger**: [Observable event]. **Action**: [Specific response]. **Rationale**: [Why this event is thesis-relevant].

### 4. Position Sizing Rationale

Determine position size using risk-adjusted logic inspired by the Kelly criterion but constrained by practical portfolio management.

**Framework**:

- **Conviction level**: High / Medium / Low (based on evidence quality, not emotional certainty)
- **Edge estimate**: Probability-weighted expected return from scenario analysis
- **Downside magnitude**: Maximum loss in the bear scenario
- **Liquidity**: Average daily volume relative to position size, days to liquidate
- **Correlation**: How does this position correlate with existing portfolio holdings?

**Position Size Matrix**:

| Conviction | Edge > 20% | Edge 10-20% | Edge < 10% |
|---|---|---|---|
| High (strong evidence) | 4-6% of portfolio | 3-4% | 1-2% |
| Medium (mixed evidence) | 2-4% | 1-3% | 0.5-1% |
| Low (speculative) | 1-2% | 0.5-1% | Pass |

**Hard constraints**: No single position exceeds 8% regardless of conviction. Positions with bear-case loss exceeding 50% are capped at 3%.

### 5. Hold Period Specification

- **Minimum hold period**: [X months] — the shortest reasonable time for the thesis to play out. No selling before this unless an exit trigger fires.
- **Maximum hold period**: [X months] — if the thesis has not materialized by this date, exit and re-evaluate regardless. Opportunity cost is real.
- **Catalyst calendar**: List specific dates when decisive information will become available (earnings, regulatory decisions, contract renewals, product launches).

### 6. Scenario Analysis Table

Construct three scenarios with rigorous internal consistency. Use thorough, comprehensive modeling.

| Dimension | Bull Case | Base Case | Bear Case |
|---|---|---|---|
| **Probability** | [%] | [%] | [%] |
| **Revenue (Year 2)** | $ | $ | $ |
| **Margin (Year 2)** | % | % | % |
| **Earnings/FCF (Year 2)** | $ | $ | $ |
| **Valuation Multiple** | Xx | Xx | Xx |
| **Price Target** | $ | $ | $ |
| **Return from Current** | +X% | +X% | -X% |
| **Probability-Weighted Return** | +X% | +X% | -X% |
| **Expected Value** | | **+X%** | |

**Probability calibration check**: Do probabilities sum to 100%? Are they internally consistent with the evidence? Would a reasonable skeptic accept these probabilities as defensible, even if they disagreed?

**Expected Value Rule**: Do not invest if the probability-weighted expected value is below the risk-free rate. The expected value must compensate for illiquidity, analytical error, and opportunity cost.

### 7. Drawdown Decision Tree (20% Decline)

This section is the most important part of the document. It is written now, when you are calm and analytical, so it can guide you later when the position is bleeding and every instinct tells you to panic or to double down recklessly.

**Decision Protocol When Position Declines 20%**:

```
Position drops 20%
    |
    +-- Was an exit trigger hit?
    |     +-- YES --> Execute exit trigger action. No discretion.
    |     +-- NO --> Continue to next check
    |
    +-- Was a must-remain-true condition violated?
    |     +-- YES --> Reduce position by 50%. Initiate full re-evaluation.
    |     +-- NO --> Continue to next check
    |
    +-- Is the decline driven by company-specific news?
    |     +-- YES --> Analyze news against thesis.
    |     |     +-- Thesis intact, overreaction --> Add to position (up to size limit)
    |     |     +-- Thesis weakened --> Trim by 25-50%, set tighter stops
    |     |     +-- Thesis broken --> Full exit
    |     +-- NO --> Continue to next check
    |
    +-- Is the decline driven by market-wide selling?
          +-- YES, thesis intact --> Hold. Consider adding if position below target weight.
          +-- YES, but sector-specific concerns --> Re-evaluate sector thesis within 48 hours.
```

**Anti-conviction Check**: Before adding to a losing position, answer honestly:
- Am I adding because the evidence supports it, or because I cannot accept being wrong?
- Has any new information emerged that I am choosing to dismiss?
- Would I initiate this position at this price if I did not already own it?

If the answer to the third question is "no," you should be selling, not buying.

### 8. Anti-Conviction Check (Full)

Separate from the drawdown protocol, conduct this check before initiating the position:

- **What is the strongest single argument against this thesis?** State it in one sentence.
- **What piece of evidence am I giving the most weight to, and why might it be misleading?**
- **If I am wrong, when will I know?** Specify the date and the data point.
- **What is the base rate for this type of thesis working?** Growth re-acceleration? Turnaround success? Multiple expansion? Most investment theses fail. What makes this one different?

---

## Output Format

The final one-pager must fit this exact structure. No additional sections. No commentary between sections. Brevity is enforced by design.

```
# INVESTMENT THESIS: [COMPANY NAME] ([TICKER])
## Date: [Date] | Price: $[X] | Market Cap: $[X]B | Position Size: [X]%

### THESIS (2 sentences)
[Sentence 1: Insight + variant perception]
[Sentence 2: Catalyst + timeline + target]

### MUST REMAIN TRUE
1. [Condition 1 with metric, threshold, current value]
2. [Condition 2 with metric, threshold, current value]
3. [Condition 3 with metric, threshold, current value]

### EXIT TRIGGERS
1. [Trigger 1: event, action, rationale]
2. [Trigger 2: event, action, rationale]
3. [Trigger 3: event, action, rationale]

### SCENARIOS
| | Bull ([X]%) | Base ([X]%) | Bear ([X]%) |
|---|---|---|---|
| Revenue Y2 | $[X] | $[X] | $[X] |
| Margin Y2 | [X]% | [X]% | [X]% |
| Multiple | [X]x | [X]x | [X]x |
| Price Target | $[X] | $[X] | $[X] |
| Return | +[X]% | +[X]% | -[X]% |
| **Expected Value** | | **+[X]%** | |

### POSITION SIZING
Conviction: [H/M/L] | Size: [X]% | Max Loss: $[X] ([X]% of portfolio)
Hold Period: [Min] to [Max] months | Liquidity: [X] days to exit

### 20% DRAWDOWN PLAN
[Decision tree outcome for each scenario: hold / add / trim / exit with conditions]

### ANTI-CONVICTION CHECK
Strongest counter-argument: [1 sentence]
I will know I am wrong when: [specific data point] on [specific date]
```

---

## Quality Criteria

Self-check with rigorous validation before finalizing:

- [ ] Thesis is exactly two sentences, contains a variant perception, and specifies a catalyst with timeline
- [ ] All three must-remain-true conditions are measurable and falsifiable with specific thresholds
- [ ] All three exit triggers are observable events (not "the stock drops X%")
- [ ] Scenario probabilities sum to 100% and are defensible, not reverse-engineered
- [ ] Expected value exceeds the risk-free rate after accounting for analytical uncertainty
- [ ] Position size is consistent with the conviction level and downside magnitude
- [ ] Drawdown decision tree covers all four scenarios (trigger hit, condition violated, company-specific, market-wide)
- [ ] Anti-conviction check contains a genuine counter-argument, not a token objection
- [ ] The entire document fits on one page when rendered (discipline of brevity enforced)

---

## Common Pitfalls

**1. Thesis creep — expanding beyond two sentences**
Prevention: If you cannot say it in two sentences, you are bundling multiple theses or you lack clarity on the variant perception. Go back to research. The constraint is the feature, not the limitation.

**2. Must-remain-true conditions that are unfalsifiable**
Prevention: For each condition, answer: "What specific data point, reported on what date, would tell me this condition has been violated?" If you cannot answer that question, the condition is not falsifiable and must be rewritten. "Management quality" is not a condition. "Revenue per employee above $350K as reported in annual filings" is a condition.

**3. Exit triggers that overlap with must-remain-true violations**
Prevention: Exit triggers should capture events outside the normal thesis monitoring framework — CEO departure, major acquisition, regulatory action, accounting restatement. If a trigger is just "Condition 1 gets violated," it is redundant and you have wasted one of your three slots.

**4. Scenario analysis that reverse-engineers desired expected value**
Prevention: Build each scenario independently with internally consistent assumptions. Then calculate expected value. If the expected value is unattractive, that is information — do not adjust probabilities to make the math work. Honest scenario analysis sometimes concludes "do not invest," and that is a valid and valuable outcome.

**5. Ignoring the drawdown plan during actual drawdowns**
Prevention: The drawdown plan is useless if you override it in the moment. Share it with an accountability partner. Set calendar reminders to review it when the position moves against you. The entire purpose of writing it in advance is to substitute pre-committed rational analysis for in-the-moment emotional reaction.

---

## Examples

### Example 1: Growth SaaS Thesis

```
# INVESTMENT THESIS: DATAWEAVE INC (DWV)
## Date: 2026-03-15 | Price: $67 | Market Cap: $8.2B | Position Size: 3.5%

### THESIS
I believe DataWeave is mispriced at 9x forward revenue because the market
is extrapolating recent growth deceleration (38% to 29%) without recognizing
that the slowdown was caused by a deliberate sales reorganization completed
in Q4 2025, not demand deterioration. The Q2 2026 earnings report will show
re-acceleration to 33%+ growth as the rebuilt enterprise sales team ramps,
driving a re-rating to 13x forward revenue and a price target of $98.

### MUST REMAIN TRUE
1. Net revenue retention must remain above 125% as reported quarterly.
   Current: 131%. Violation means expansion engine is broken.
2. Enterprise customer count (>$100K ACV) must grow above 30% YoY as
   reported quarterly. Current: 37%. Violation means sales reorg failed.
3. Non-GAAP gross margin must remain above 76% as reported quarterly.
   Current: 78.5%. Violation means competitive pricing pressure or
   infrastructure cost inflation is eroding unit economics.

### EXIT TRIGGERS
1. CFO departure before Q3 2026 earnings. Action: Exit 100%. Rationale:
   CFO is architect of the efficiency roadmap; departure signals internal
   disagreement on path to profitability.
2. Acquisition exceeding $500M announced. Action: Exit 50%, re-evaluate.
   Rationale: Large M&A at this stage signals organic growth desperation.
3. Major customer (top-10 by ACV) publicly switches to competitor. Action:
   Exit 30%, tighten stop to 10% trailing. Rationale: Visible competitive
   loss would shatter the "best product wins" narrative.

### SCENARIOS
| | Bull (25%) | Base (50%) | Bear (25%) |
|---|---|---|---|
| Revenue Y2 | $1.65B | $1.45B | $1.20B |
| Margin Y2 | 18% FCF | 12% FCF | 2% FCF |
| Multiple | 15x rev | 10x rev | 6x rev |
| Price Target | $138 | $89 | $41 |
| Return | +106% | +33% | -39% |
| **Expected Value** | | **+28%** | |

### POSITION SIZING
Conviction: Medium-High | Size: 3.5% | Max Loss: $4,800 (1.4% of portfolio)
Hold Period: 6 to 18 months | Liquidity: 1.5 days to exit

### 20% DRAWDOWN PLAN
If price hits $54: Check all 3 conditions. If intact and decline is market-
wide, add 1% to bring position to 4.5%. If decline is company-specific,
hold and await next quarterly report before acting. If any condition
violated, trim to 2% and set 30-day review.

### ANTI-CONVICTION CHECK
Strongest counter-argument: The sales reorg is a convenient excuse and the
real issue is market saturation in the mid-market segment, which represents
55% of new bookings.
I will know I am wrong when: Q2 2026 revenue growth reported below 30% on
August 8, 2026.
```

---

### Example 2: Deep Value / Turnaround Thesis

```
# INVESTMENT THESIS: CONTINENTAL PAPER CO (CPC)
## Date: 2026-03-20 | Price: $14.30 | Market Cap: $1.1B | Position Size: 2.0%

### THESIS
I believe Continental Paper trades at a 40% discount to replacement value
of its mill assets ($1.85B) because the market is pricing in the margin
profile of the outgoing management team rather than the restructuring plan
of the new CEO, who achieved a comparable turnaround at Pacific Pulp
(margins from 8% to 19% over 3 years). The closure of the unprofitable
Milltown facility in Q3 2026 will remove $45M in annual losses and serve
as the catalyst for re-rating toward $22, representing 54% upside.

### MUST REMAIN TRUE
1. Consolidated EBITDA margin must show sequential improvement for at least
   2 of the next 4 quarters. Current: 9.2% (Q4 2025). Violation means
   restructuring is not delivering results.
2. Net debt / EBITDA must remain below 4.0x as reported quarterly. Current:
   3.4x. Violation means balance sheet risk exceeds turnaround timeline.
3. Containerboard pricing index must remain above $680/ton as reported
   monthly by RISI. Current: $735/ton. Violation means commodity cycle is
   working against the turnaround.

### EXIT TRIGGERS
1. New CEO departs or is terminated. Action: Exit 100% immediately.
   Rationale: The entire thesis depends on this specific operator executing
   this specific plan. No CEO, no thesis.
2. Dividend is cut or suspended. Action: Exit 75%. Rationale: Board
   signaling that cash flow cannot support both restructuring and
   shareholder returns indicates deeper problems than disclosed.
3. Hostile bid below $18/share from a strategic acquirer. Action: Hold and
   evaluate bid terms. Rationale: A bid validates asset value but may cap
   upside below full turnaround potential.

### SCENARIOS
| | Bull (20%) | Base (50%) | Bear (30%) |
|---|---|---|---|
| EBITDA Y2 | $245M | $185M | $120M |
| Margin Y2 | 16% | 12.5% | 8% |
| Multiple | 7.5x EV/EBITDA | 6.0x | 4.5x |
| Price Target | $31 | $22 | $8.50 |
| Return | +117% | +54% | -41% |
| **Expected Value** | | **+18%** | |

### POSITION SIZING
Conviction: Medium | Size: 2.0% | Max Loss: $2,800 (0.8% of portfolio)
Hold Period: 12 to 30 months | Liquidity: 3 days to exit

### 20% DRAWDOWN PLAN
If price hits $11.44: Check containerboard pricing and EBITDA margin trend.
If commodity pricing is the sole driver and margins are improving, add 1%
(position to 3%). If margins are deteriorating despite restructuring, trim
to 1% and set $9.50 hard stop. If CEO or management team changes, exit
immediately per trigger protocol.

### ANTI-CONVICTION CHECK
Strongest counter-argument: The Milltown closure will trigger $60M in one-
time charges that breach the debt covenant, forcing a dilutive equity raise
at the worst possible time.
I will know I am wrong when: Q3 2026 EBITDA margin (reported November
2026) fails to show improvement versus Q2 despite Milltown closure benefits.
```

---

## Integration

- **Receives from**: `adversarial-business-model` — risk catalog informs must-remain-true conditions and exit triggers
- **Receives from**: `bull-bear-steelman` — scenario probabilities, price targets, and decisive data points transfer directly into the scenario table and anti-conviction check
- **Sequencing**: This is the terminal skill in the research workflow. Use it only after completing adversarial analysis and bull/bear steelmanning. The one-pager distills conclusions — it does not generate them.
- **Post-creation usage**: Reference this document at every quarterly earnings report, at every 10% price movement, and whenever you feel the urge to change your position size. The document is the plan. Stick to the plan.
