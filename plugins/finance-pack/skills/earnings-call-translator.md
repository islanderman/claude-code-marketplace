---
name: earnings-call-translator
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: >
  Decode earnings calls by analyzing management language through forensic lenses --
  translating corporate euphemisms, classifying commitment levels, detecting question
  dodges, separating new guidance from repackaged narratives, and extracting actionable
  signals from what was said, how it was said, and what was conspicuously not said.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "analyze earnings call"
  - "translate earnings call"
  - "decode earnings call"
  - "earnings call analysis"
  - "management language analysis"
  - "earnings transcript review"
  - "what did management really say"
modes:
  standalone: true
  teammate: true
---

# Earnings Call Translator

## ULTRATHINK Activation

**Mode**: ANALYSIS MODE with MAX-PRECISION -- forensic linguistics applied to corporate communication
**Optimization**: Multi-layer language decoding, commitment spectrum classification, pattern-matched dodge detection
**Focus**: Extract ground truth from management narratives by analyzing language precision, evasion patterns, tone shifts, and strategic omissions

---

## Purpose

Earnings calls are performative communications. Management teams are coached by IR consultants to frame results favorably, deflect difficult questions, and maintain narrative control. The gap between what is said and what is meant contains the most valuable information for investors. This skill provides a systematic framework to decode that gap.

**Core Value**: Transform a 60-minute earnings call from a passive listening exercise into a structured forensic analysis that identifies commitment levels, detects evasion, flags red flags, and extracts the 3-5 signals that actually matter for investment decisions.

---

## Methodology (4-Phase Framework)

### Phase 1: Prepared Remarks Analysis

Analyze with deliberation the structured portion of the call where management controls the narrative entirely.

**Euphemism Translation Layer**:

Apply the corporate euphemism translation table to every material statement in prepared remarks. Flag instances where euphemistic language replaces previously direct language.

| Corporate Euphemism | Real Translation | Severity |
|---|---|---|
| "Challenging macro environment" | Our revenue missed and we are blaming external factors | Medium |
| "Rightsizing the organization" | Layoffs | High |
| "Investing for the long term" | Spending more, returns not visible yet | Medium |
| "Transitioning our business model" | Current model is broken, new one is unproven | High |
| "Optimizing our cost structure" | Cutting costs because revenue growth stalled | High |
| "Strategic review of alternatives" | The company may be for sale | High |
| "Normalizing growth rates" | Growth is decelerating and we want you to accept it | Medium |
| "Healthy pipeline" | We have nothing to announce right now | Low |
| "Robust demand environment" | Things are fine but we are over-emphasizing it | Low |
| "Prudent capital allocation" | We are not buying back stock or raising dividends | Low |
| "Rationalizing our portfolio" | Selling underperforming divisions | Medium |
| "Streamlining operations" | Layoffs disguised as efficiency | Medium |
| "Measured approach to growth" | We are growing slowly and want credit for caution | Low |
| "Temporary headwinds" | Problem we hope goes away but may not | Medium |
| "Idiosyncratic factors" | Something went wrong and we want to isolate it | Medium |
| "Building a platform for future growth" | No growth now; please be patient | High |
| "Early innings" | We have no idea when this pays off | Medium |
| "Encouraged by early results" | Sample size is tiny but directionally positive | Low |
| "Maintaining discipline" | We wanted to do something aggressive but our board/CFO said no | Low |
| "Constructive dialogue with regulators" | Regulatory risk is real and ongoing | Medium |
| "Derisking the balance sheet" | We took on too much debt and are now unwinding | High |
| "Evolving competitive landscape" | New competitors are taking share from us | High |

**Guidance Analysis Framework**:

| Dimension | Question to Answer |
|---|---|
| **New vs Repackaged** | Is this genuinely new information or a restatement of prior guidance in new words? |
| **Direction** | Raised, maintained, lowered, or withdrawn? |
| **Specificity** | Precise range (e.g., "$4.2B-$4.4B") vs vague ("mid-single-digit growth")? |
| **Conditionality** | Unconditional or hedged with "assuming," "barring," "subject to"? |
| **Time horizon** | Next quarter, full year, or "long-term" (conveniently unmeasurable)? |
| **Metric selection** | Are they guiding on revenue, operating income, EBITDA, or non-GAAP earnings? Why that metric? |

**Self-check**: Compare every guidance statement to the prior quarter's guidance. Has anything actually changed, or has the same message been repackaged with slightly different language?

### Phase 2: Q&A Forensic Analysis

Use depth-first reasoning to analyze each analyst question and management response pair.

**Commitment Spectrum Classifier**:

Score every material management response on the commitment spectrum:

| Level | Classification | Language Markers | Signal Strength |
|---|---|---|---|
| **5 - Definitive** | Clear, unconditional commitment | "We will," "We are committed to," specific numbers | Strong positive |
| **4 - Confident** | High confidence with minor hedging | "We expect," "We're on track," "We anticipate" | Moderate positive |
| **3 - Hedged** | Conditional or qualified statements | "Assuming," "If conditions," "We believe," "Our expectation is" | Neutral / caution |
| **2 - Deflected** | Redirected to different topic or timeframe | "What I'd say is," "The way to think about it," "Over the long term" | Negative signal |
| **1 - Dodged** | Question not answered despite being asked | Topic change, excessive generality, "We don't comment on" | Strong negative signal |

**Question Dodge Detection Techniques**:

| Technique | Description | Example |
|---|---|---|
| **Pivot** | Acknowledge the question, then answer a different one | "Great question. What I'd highlight is our momentum in [different area]..." |
| **Reframe** | Change the framing to avoid the specific metric asked about | Asked about margins, responds about "total shareholder returns" |
| **Partial answer** | Answer one component while ignoring the critical part | Asked about revenue AND margins, answers only revenue |
| **Forward redirect** | Push to a future date to avoid current answer | "We'll provide more detail at our investor day in September" |
| **Non-answer generality** | Respond with platitudes that contain no information | "We remain focused on executing our strategy and delivering value" |
| **Data dump** | Overwhelm with tangential data to obscure the non-answer | 90 seconds of metrics that do not address the question asked |
| **Peer deflection** | CEO passes to CFO or VP who answers a different question | "I'll let [name] take that one" followed by topic shift |

**Scoring each Q&A pair**:
1. What was the analyst actually asking? (Restate the core question in plain language)
2. Did management answer that specific question? (Yes / Partially / No)
3. What commitment level was the response? (1-5 scale)
4. What dodge technique was used, if any?
5. What is the information value of the response? (High / Medium / Low / Negative)

### Phase 3: Tone and Pattern Analysis

Apply context-sensitive reflection to detect shifts in confidence, narrative changes, and conspicuous absences.

**Tone Shift Detection**:
- Compare language confidence between prepared remarks and Q&A (management often more guarded under questioning)
- Compare tone on different topics (confident on revenue, evasive on margins = margin pressure)
- Compare current call tone to prior quarter (escalation or de-escalation of confidence)
- Note when CEO vs CFO tone diverges (CFO more cautious often signals financial reality vs CEO optimism)

**Notable Omission Tracker**:

What was NOT said is often more important than what was said.

| Omission Type | What to Check |
|---|---|
| **Topic absence** | Subjects discussed last quarter but absent this quarter (e.g., stopped mentioning a product line) |
| **Metric disappearance** | KPIs previously reported that are quietly dropped (e.g., stopped disclosing subscriber count) |
| **Customer absence** | Key customer names previously mentioned that vanish |
| **Geographic absence** | Regions previously highlighted that go unmentioned |
| **Forward language absence** | Reduced forward-looking statements (may signal reduced visibility) |
| **Competitor absence** | Stopped referencing competitive advantages (may signal competitive pressure) |

**Red Flag Pattern Recognition**:
- Excessive non-GAAP adjustments or new "one-time" charges appearing repeatedly
- Blame-shifting language (macro, FX, weather, one-time) escalating quarter over quarter
- Management selling stock while using bullish language on the call
- Increasing use of "long-term" framing to avoid near-term accountability
- CFO departure or auditor change announced quietly in the filing but not discussed on the call

### Phase 4: Synthesis and Actionable Extraction

Execute with rigor to distill the full analysis into the 3 signals that matter most.

**Management Credibility Scoring**:

| Dimension | Assessment | Score (1-5) |
|---|---|---|
| Promises vs delivery (last 4 quarters) | Did they hit the targets they previously guided to? | |
| Transparency on bad news | Do they address problems directly or bury them? | |
| Consistency of narrative | Does the story keep changing quarter to quarter? | |
| Insider alignment | Are insiders buying or selling relative to their language? | |
| Metric integrity | Do they stick with consistent KPIs or keep changing? | |
| **Composite Credibility Score** | Average of above | **/5** |

**Top 3 Actionable Takeaways**:

For each takeaway:
1. **The signal**: What specific language, omission, or pattern was detected
2. **The translation**: What it actually means in plain investor language
3. **The implication**: What action or monitoring it suggests
4. **Confidence level**: How confident is this interpretation (High / Medium / Low)

---

## Output Format

```markdown
# Earnings Call Translation: [Company] [Quarter] [Year]
## Call Date: [Date] | Analyst: [Your analysis date]

### Executive Summary
[3-4 sentences: Overall tone, key narrative, biggest discrepancy between message and reality]

### Corporate Euphemism Flags
[Table: Statement | Translation | Severity | Context]

### Guidance Analysis
[Table: Metric | Prior Guidance | Current Guidance | Change | New vs Repackaged | Specificity]

### Q&A Forensic Report
[For each notable Q&A pair:]
- **Analyst question (plain language)**: [restated]
- **Management response classification**: [Definitive/Confident/Hedged/Deflected/Dodged]
- **Dodge technique (if applicable)**: [technique name]
- **Information extracted**: [what we actually learned]

### Tone Shift Analysis
[Prepared remarks vs Q&A confidence comparison]
[Current quarter vs prior quarter tone comparison]
[CEO vs CFO alignment assessment]

### Notable Omissions
[Table: Topic/Metric | Last Mentioned | Significance | Possible Explanation]

### Red Flags
[Bulleted list with severity: GREEN / YELLOW / RED]

### Management Credibility Score: [X/5]
[Supporting evidence for score]

### Top 3 Actionable Takeaways
1. **Signal**: ... | **Translation**: ... | **Implication**: ... | **Confidence**: ...
2. ...
3. ...
```

---

## Quality Criteria

- [ ] Every material euphemism in prepared remarks identified and translated
- [ ] All guidance statements compared to prior quarter for new vs repackaged assessment
- [ ] Every analyst Q&A pair scored on commitment spectrum (1-5)
- [ ] Question dodge techniques specifically named, not vaguely described
- [ ] Tone shift analysis covers prepared-vs-Q&A, quarter-over-quarter, and CEO-vs-CFO
- [ ] Notable omissions checked against prior 2 quarters of call transcripts
- [ ] Red flags supported by specific evidence (quotes, metrics, patterns)
- [ ] Management credibility score based on measurable track record, not impression
- [ ] Top 3 takeaways are genuinely actionable (not "monitor the situation")
- [ ] Self-check: Would a portfolio manager change a position based on these takeaways?

---

## Common Pitfalls

1. **Taking prepared remarks at face value**: Prepared remarks are marketing documents read aloud. They are optimized to frame results favorably. The Q&A section, where management cannot fully control the narrative, contains higher-signal information.

2. **Confusing confidence of delivery with confidence of content**: A CEO who speaks fluently and charismatically can deliver evasive non-answers that sound authoritative. Score the content, not the delivery. A stammered honest answer is more valuable than a polished deflection.

3. **Ignoring the questions not asked**: If no analyst asks about a known problem area, it does not mean the problem is resolved. Check whether analysts are being managed (IR pre-screens questions on some calls) or whether the topic is being avoided by consensus.

4. **Treating guidance as prediction**: Guidance is a negotiation tool. Companies guide conservatively to create "beat" optics, or guide aggressively to maintain stock price during insider selling windows. Always assess guidance in context of management incentives.

5. **Missing the metric switch**: When a company stops reporting a previously featured KPI and introduces a new one, the old metric almost certainly deteriorated. This is one of the highest-signal red flags and is frequently overlooked.

---

## Examples

### Example 1: Tech Earnings with Growth Deceleration Spin

**Context**: CloudScale Inc. (fictional) reports Q3 earnings. Revenue growth decelerated from 32% to 24% YoY. Management narrative focuses on "durable growth" and "long-term platform opportunity."

**Euphemism Flags**:
| Statement | Translation | Severity |
|---|---|---|
| "Normalizing from elevated post-pandemic growth rates" | Growth is decelerating and we want to set lower expectations | Medium |
| "Investing aggressively in our AI capabilities" | Spending is up significantly; ROI is unproven | Medium |
| "Customer cohort expansion remains healthy" | Net new customer growth may have slowed, but existing customers spend more | Low |
| "We're in the early innings of a massive TAM opportunity" | No timeline for when AI investment generates returns | High |

**Q&A Forensic Highlight**:
- **Analyst asks**: "Can you quantify the revenue contribution from AI products this quarter?"
- **CEO responds**: "AI is embedded across our entire platform, so it's difficult to isolate. What I'd say is every customer conversation now includes an AI component, and we're incredibly excited about the pipeline." (Commitment Level: 2 - Deflected. Technique: Reframe + Non-answer generality)
- **Translation**: AI revenue is not material enough to disclose. If it were impressive, they would give a number.

**Notable Omissions**:
- Stopped reporting "net dollar retention rate" which was 135% two quarters ago -- likely declined below 130%
- No mention of enterprise customer count (previously a headline metric)

**Top 3 Takeaways**:
1. **Signal**: Growth deceleration framed as "normalization" with no floor identified. **Translation**: Management does not know where growth stabilizes. **Implication**: Model downside scenarios to 18-20% growth. **Confidence**: High.
2. **Signal**: AI revenue not quantified despite direct question. **Translation**: AI is a narrative tool, not yet a revenue driver. **Implication**: Discount AI-driven valuation premium. **Confidence**: High.
3. **Signal**: Net dollar retention rate omitted. **Translation**: Expansion revenue from existing customers is slowing. **Implication**: This is a leading indicator of further revenue deceleration in 2-3 quarters. **Confidence**: Medium.

---

### Example 2: Retail Earnings with Margin Pressure Deflection

**Context**: ValueMart Holdings (fictional) reports Q2 earnings. Revenue up 6% (in-line) but gross margins compressed 180bps YoY. Management narrative emphasizes "top-line momentum" and "strategic investments in price."

**Euphemism Flags**:
| Statement | Translation | Severity |
|---|---|---|
| "Strategic investments in price to drive traffic" | We are cutting prices because we are losing customers to competitors | High |
| "Temporary mix shift toward consumables" | Customers are trading down; discretionary spending is weak | Medium |
| "Optimizing our real estate portfolio" | Closing underperforming stores | Medium |
| "Building a world-class omnichannel experience" | E-commerce is expensive and we are behind competitors | High |

**Q&A Forensic Highlight**:
- **Analyst asks**: "When do you expect gross margins to stabilize? Can you give us a timeline for the promotional environment normalizing?"
- **CFO responds**: "We're focused on delivering value to our customers, and we believe our pricing strategy positions us well for market share gains. Over the medium term, we expect the promotional environment to rationalize." (Commitment Level: 2 - Deflected. Technique: Forward redirect + Non-answer generality)
- **Translation**: They have no visibility on when margin pressure ends. "Medium term" is deliberately undefined. The word "rationalize" is doing heavy lifting to avoid saying "we don't know."

**Tone Shift Analysis**:
- Prepared remarks: Confident, forward-looking, emphasized revenue growth and market share
- Q&A on margins: Defensive, hedged, used conditional language ("if the environment," "subject to competitive dynamics")
- CEO vs CFO: CEO maintained optimistic framing; CFO notably more cautious on margin questions, twice qualifying CEO statements with "within the context of our current outlook"
- This divergence is a yellow flag: CFO is subtly signaling the optimistic narrative has financial limits

**Notable Omissions**:
- Same-store sales growth not broken out by category (previously disclosed; likely discretionary is negative)
- No mention of private label penetration (was a growth initiative; may have stalled)
- Customer acquisition cost not discussed (likely rising with increased promotions)

**Top 3 Takeaways**:
1. **Signal**: Margin compression framed as "strategic investment" with no stabilization timeline. **Translation**: Competitive pressure is forcing price cuts with no end in sight. **Implication**: Model 2-3 more quarters of margin pressure; assess whether market share gains offset profit decline. **Confidence**: High.
2. **Signal**: CEO-CFO tone divergence on margin outlook. **Translation**: Financial leadership is less confident than operational leadership is communicating. **Implication**: Weight CFO signals more heavily; consider that next quarter guidance may disappoint on profitability. **Confidence**: Medium.
3. **Signal**: Category-level same-store sales no longer disclosed. **Translation**: Discretionary categories are likely negative, masked by consumables strength. **Implication**: Recovery in discretionary spending is a prerequisite for margin recovery; monitor consumer confidence data. **Confidence**: Medium.

---

## Integration

**Upstream dependencies**: Requires earnings call transcript (full text, not summary). Prior quarter transcripts needed for omission tracking and tone comparison. Pair with `filing-decoder` to cross-reference management claims against actual financial statements.

**Downstream outputs**: Feed top 3 takeaways into `catalyst-timeline-builder` as resolved catalyst outcomes. Use management credibility score to weight forward guidance in financial models. Connect red flags to position sizing decisions.

**Refresh cadence**: Apply once per earnings call. Update management credibility score quarterly as a rolling assessment.
