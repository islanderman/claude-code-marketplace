---
name: competitive-moat-audit
version: 1.0.0
author: Jerry Yang <jerry@chenyang.us>
description: Score and evaluate competitive moats across 6 dimensions with evidence-based scoring, head-to-head comparison matrices, trajectory assessment, and composite moat scorecards.
category: finance-pack
agents:
  - finance-pack:portfolio-analyst
triggers:
  - "analyze moat"
  - "competitive advantage"
  - "moat assessment"
  - "moat comparison"
  - "switching costs"
  - "network effects"
  - "competitive durability"
modes:
  standalone: true
  teammate: true
---

# Competitive Moat Audit

## ULTRATHINK Activation

**Mode**: EXPERT MODE with MAX-PRECISION -- institutional-grade competitive moat analysis
**Optimization**: Evidence-based scoring with multi-layer validation across 6 moat dimensions
**Focus**: Durable competitive advantage identification, trajectory assessment, and disruptor threat modeling

---

## Purpose

Deliver a rigorous, evidence-backed assessment of competitive moats that goes beyond surface-level labels. This skill produces quantified moat scores across 6 dimensions, head-to-head competitor matrices, moat trajectory projections, and disruptor threat assessments. The output enables precise positioning decisions grounded in structural competitive analysis rather than narrative.

**When to use**: Evaluating a company's defensibility before initiating or sizing a position, comparing two competitors in the same space, or stress-testing an existing holding's competitive durability.

---

## Methodology (4-Phase)

### Phase 1: Analysis -- Moat Dimension Decomposition

Analyze with deliberation using step-by-step reasoning to decompose the company's competitive position across all 6 moat dimensions. Gather evidence for each dimension before assigning scores. Evaluate assumptions about competitive advantages by examining actual customer behavior, pricing power data, and market share trends.

### Phase 2: Plan -- Scoring Framework Application

Apply the standardized scoring rubric to each dimension. Produce 3 candidate scores for ambiguous dimensions (optimistic, neutral, skeptical) then unify into a single justified score. Cross-reference scores against observable market data. Verify logic by checking whether scores are internally consistent (a company cannot score 9 on switching costs while losing market share to cheaper alternatives).

### Phase 3: Execution -- Comparative Matrix and Trajectory

Build head-to-head comparison matrices against primary competitors. Assess moat trajectory (widening, stable, or narrowing) with specific evidence for each dimension. Model disruptor threats and durability timelines. Use context-sensitive reflection to ensure scores reflect the specific competitive environment, not generic industry assumptions.

### Phase 4: Validation -- Composite Scorecard and Self-Check

Produce the weighted composite scorecard. Self-check the entire analysis: Does the composite score match intuitive assessment? Are there contradictions between dimensions? Would a skeptical analyst reach substantially different conclusions? Flag any dimension where evidence is thin.

---

## Detailed Framework

### 6 Moat Dimensions and Scoring Rubric

Each dimension is scored 1-10. Every score MUST include specific evidence. Scores without evidence are rejected.

#### 1. Switching Costs

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **Low**: Customers can switch with minimal friction, no data lock-in, commodity product | Churn rate >15% annually, low contract lengths, multiple active alternatives |
| 4-5 | **Moderate**: Some integration effort required, partial data portability, moderate retraining | Churn rate 8-15%, 1-2 year contracts typical, migration takes weeks |
| 6-7 | **High**: Deep workflow integration, significant retraining cost, data migration complexity | Churn rate 3-8%, multi-year contracts, migration takes months |
| 8-10 | **Very High**: Mission-critical embedding, regulatory or compliance lock-in, prohibitive migration cost | Churn rate <3%, 3-5+ year contracts, migration takes quarters/years, would require system redesign |

#### 2. Network Effects

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **Absent/Weak**: Product value independent of user count, no meaningful cross-side effects | Single-player utility, no marketplace dynamics, linear value scaling |
| 4-5 | **Emerging**: Some value increase with users, but not yet self-reinforcing | Early marketplace with supply/demand gaps, growing but not dominant |
| 6-7 | **Strong**: Clear value-per-user increase, cross-side effects established, defensible liquidity | >50% market share in core network, measurable engagement increases with scale |
| 8-10 | **Dominant**: Winner-take-most dynamics, multi-sided reinforcement, near-impossible to replicate | >70% market share, exponential value curves, failed competitor attempts documented |

#### 3. Cost Advantages

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **None**: Similar cost structure to competitors, no structural advantage | Gross margins within 5pp of peers, no proprietary supply chain |
| 4-5 | **Moderate**: Some scale benefits, incremental efficiency advantages | Gross margins 5-10pp above peers, some fixed-cost leverage |
| 6-7 | **Significant**: Structural cost advantages from scale, geography, or process | Gross margins 10-20pp above peers, demonstrable economies of scale |
| 8-10 | **Dominant**: Insurmountable cost position, resource ownership, or technology-driven cost floor | Gross margins >20pp above peers, proprietary resources, cost curve that competitors cannot replicate |

#### 4. Brand Power

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **Weak**: Low unaided awareness, no pricing premium, brand not a purchase driver | Competes primarily on price, low NPS, minimal brand recall |
| 4-5 | **Moderate**: Recognized brand with some loyalty, modest pricing premium | 10-20% pricing premium sustainable, moderate NPS, some repeat purchase behavior |
| 6-7 | **Strong**: Top-3 brand in category, meaningful pricing power, emotional connection | 20-40% pricing premium, high NPS (>50), strong repeat purchase rates |
| 8-10 | **Iconic**: Category-defining brand, significant pricing power, cultural status | >40% pricing premium, NPS >70, brand is verb/noun for category, decades of equity |

#### 5. Regulatory / IP Barriers

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **Minimal**: Low regulatory barriers, weak or expiring IP, easy to enter | No meaningful patents, light regulation, low compliance burden |
| 4-5 | **Moderate**: Some regulatory requirements, active patent portfolio but workarounds exist | Regulatory approval takes 1-2 years, patents but with design-around options |
| 6-7 | **Strong**: Significant regulatory moat, broad IP coverage, high compliance costs deter entrants | Regulatory approval takes 2-5 years, strong patent portfolio, high compliance CapEx |
| 8-10 | **Fortress**: Government-granted monopoly/oligopoly, foundational patents, extreme regulatory barriers | FDA/FAA-level approvals (5-10+ years), essential patents with decades remaining, regulatory capture |

#### 6. Data / Scale Advantages

| Score | Criteria | Evidence Required |
|-------|----------|-------------------|
| 1-3 | **Minimal**: Data is commodity, scale provides little marginal benefit | Publicly available data, linear scaling economics, no data flywheel |
| 4-5 | **Moderate**: Proprietary dataset growing, some scale-driven improvements | Unique data assets emerging, product improving with usage, moderate data moat |
| 6-7 | **Strong**: Large proprietary dataset drives product superiority, scale creates compounding advantage | Years of accumulated data, measurable product quality gap vs smaller competitors |
| 8-10 | **Dominant**: Irreplicable data asset, scale enables capabilities others cannot match | Decades of data accumulation, data flywheel in full effect, new entrants face cold-start problem |

### Head-to-Head Comparison Matrix

Build a comparison matrix for the target company against 2-3 primary competitors:

```
| Dimension            | Company A | Company B | Company C | Advantage Holder |
|----------------------|-----------|-----------|-----------|------------------|
| Switching Costs      | X/10      | X/10      | X/10      | [Company]        |
| Network Effects      | X/10      | X/10      | X/10      | [Company]        |
| Cost Advantages      | X/10      | X/10      | X/10      | [Company]        |
| Brand Power          | X/10      | X/10      | X/10      | [Company]        |
| Regulatory/IP        | X/10      | X/10      | X/10      | [Company]        |
| Data/Scale           | X/10      | X/10      | X/10      | [Company]        |
|----------------------|-----------|-----------|-----------|------------------|
| Composite (weighted) | X/10      | X/10      | X/10      | [Company]        |
```

### Moat Trajectory Assessment

For each dimension, classify trajectory as:

- **Widening**: Specific evidence of moat strengthening (new patents granted, network density increasing, switching costs rising via deeper integration)
- **Stable**: Moat maintained but not growing (market share flat, pricing power unchanged, competitive dynamics steady)
- **Narrowing**: Specific evidence of moat erosion (new entrants gaining share, pricing pressure increasing, technology disruption enabling substitutes)

### Moat Durability Timeline

Estimate in years how long the competitive advantage persists under three scenarios:

- **Base case**: Current competitive dynamics continue
- **Disruption case**: A well-funded competitor targets the moat directly
- **Technology shift case**: A platform or paradigm change occurs

### Disruptor Threat Assessment

Identify the top 3 most credible threats to the moat. For each threat:

1. **Who**: Specific company, technology, or market shift
2. **How**: The mechanism by which the moat could be breached
3. **When**: Estimated timeline for meaningful impact
4. **Probability**: Low (<20%), Moderate (20-50%), High (>50%)
5. **Mitigation**: What the company is doing or could do to defend

### Composite Scorecard

Apply dimension weights based on business type:

| Business Type | Switching | Network | Cost | Brand | Reg/IP | Data/Scale |
|---------------|-----------|---------|------|-------|--------|------------|
| SaaS/Platform | 25% | 25% | 10% | 10% | 10% | 20% |
| Consumer Brand | 10% | 15% | 15% | 30% | 10% | 20% |
| Industrial | 20% | 5% | 30% | 10% | 25% | 10% |
| Pharma/Biotech | 5% | 5% | 10% | 15% | 50% | 15% |
| Financial Svc | 25% | 20% | 15% | 15% | 15% | 10% |

**Composite Score Interpretation**:
- 8.0-10.0: **Wide Moat** -- Dominant, durable competitive advantage. Premium valuation justified.
- 6.0-7.9: **Narrow Moat** -- Meaningful advantages but requires monitoring. Moderate premium.
- 4.0-5.9: **Emerging/Fragile Moat** -- Some advantages but vulnerable. Discount or close monitoring.
- 1.0-3.9: **No Moat** -- Commodity business. Must justify on valuation alone.

---

## Output Format

```markdown
## Competitive Moat Audit: [Company Name]

### Moat Dimension Scores
[6 dimensions with scores, evidence, and trajectory]

### Head-to-Head Matrix
[Comparison table against 2-3 competitors]

### Moat Trajectory
[Widening/Stable/Narrowing for each dimension with evidence]

### Durability Timeline
[Base/Disruption/Tech-shift scenarios with year estimates]

### Disruptor Threats
[Top 3 threats with Who/How/When/Probability/Mitigation]

### Composite Scorecard
[Weighted score, classification, confidence level]

### Investment Implications
[What this means for position sizing and conviction]
```

---

## Quality Criteria

- Every score backed by specific, verifiable evidence (not narrative)
- Trajectory assessments include directional data points (not opinions)
- Disruptor threats are specific (named entities and mechanisms), not vague
- Composite weights match the actual business type
- Self-check: Could a skeptical analyst reach the same scores given the same evidence?
- No moat dimension left unscored or scored without justification

---

## Common Pitfalls

1. **Narrative moat inflation**: Assigning high scores based on brand reputation or media sentiment rather than measurable competitive advantages. A company "everyone knows" is not automatically an 8 on brand power -- check pricing premium data.

2. **Static moat assumption**: Treating moats as permanent when they are actively eroding. Always check the trajectory. Blockbuster had a wide moat in 2005.

3. **Ignoring the disruptor vector**: Focusing only on direct competitors while missing adjacent-market entrants or technology shifts. The biggest moat threat often comes from outside the current competitive set.

4. **Conflating size with moat**: Large revenue or market cap does not equal a moat. Many large companies compete in commodity markets with no structural advantage. Score the mechanism, not the outcome.

5. **Evidence-free scoring**: Assigning scores based on "it feels like a 7." Every score must point to a specific data point, metric, or observable behavior. If you cannot cite evidence, the score is 5 (neutral) until proven otherwise.

---

## Examples

### Example 1: SaaS vs On-Prem Competitor Moat Comparison

**Context**: Evaluating ServiceNow (NOW) vs BMC Software in IT service management.

**Switching Costs**: NOW 8/10 (avg contract 3+ years, deep workflow customization, 95%+ renewal rate, migration requires months of re-implementation) vs BMC 6/10 (legacy integration depth but customers actively migrating away). **Trajectory**: NOW widening (expanding platform surface area), BMC narrowing (cloud-native alternatives reducing lock-in value).

**Network Effects**: NOW 5/10 (marketplace growing, partner ecosystem building, but product utility not directly user-count dependent) vs BMC 3/10 (limited ecosystem effects). **Advantage**: NOW, but network effects are secondary moat for both.

**Composite**: NOW 7.4/10 (Narrow-to-Wide Moat, widening trajectory) vs BMC 4.8/10 (Fragile Moat, narrowing trajectory). Weight allocation: SaaS/Platform profile with 25% switching, 25% network, 10% cost, 10% brand, 10% reg/IP, 20% data/scale.

**Investment implication**: NOW's moat supports premium valuation and higher position sizing. BMC's eroding moat warrants caution despite optically cheaper valuation.

### Example 2: Consumer Brand vs Private Label Moat Analysis

**Context**: Evaluating Procter & Gamble (PG) vs Kirkland Signature (Costco private label) in household goods.

**Brand Power**: PG 7/10 (portfolio of #1-2 brands per category, 15-25% pricing premium sustained, high unaided awareness, decades of equity) vs Kirkland 6/10 (growing brand trust, but moat is Costco distribution, not brand emotional connection). **Trajectory**: PG stable (premiums holding but growth slowing), Kirkland widening (expanding categories, building standalone brand equity).

**Cost Advantages**: PG 5/10 (scale benefits offset by advertising spend) vs Kirkland 8/10 (Costco's buying power, minimal marketing spend, private-label margin structure). **Advantage**: Kirkland, and this is the core competitive threat.

**Disruptor Threat #1**: Amazon private label expansion. **How**: Leveraging purchase data to target highest-margin PG categories with algorithmically optimized alternatives. **When**: Ongoing, 3-5 years for meaningful impact. **Probability**: Moderate (35%). Amazon has struggled with CPG private label execution despite data advantages.

**Composite**: PG 6.2/10 (Narrow Moat, stable) vs Kirkland 6.8/10 (Narrow Moat, widening). Weight allocation: Consumer Brand profile with 10% switching, 15% network, 15% cost, 30% brand, 10% reg/IP, 20% data/scale.

---

## Integration

- **Feeds into**: `valuation-sanity-check` (moat score informs appropriate valuation premium/discount)
- **Feeds into**: `sector-theme-mapper` (moat durability affects which players are "winners" in a theme)
- **Receives from**: `portfolio-overlap-detector` (concentrated positions need stronger moat justification)
- **Companion analysis**: Run moat audit before sizing any position above 3% of portfolio
