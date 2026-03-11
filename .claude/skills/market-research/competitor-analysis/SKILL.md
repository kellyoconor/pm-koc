---
name: competitor-analysis
description: >
  Analyze the competitive landscape with positioning maps, feature matrices,
  strategic gap analysis, and differentiation opportunities. Identifies direct
  competitors, indirect alternatives, and the status quo. Use when doing
  competitive research, preparing a competitive brief, planning differentiation
  strategy, evaluating market entry, or finding positioning gaps.
version: "2.0.0"
updated: 2026-03-11
---

# Competitive Analysis

## Purpose

Conduct a rigorous competitive analysis that goes beyond feature checklists to
uncover strategic positioning opportunities. The goal is to understand where
alternatives fail your ICP so you can win on what matters to them -- not to
catalog competitors or copy their features.

This skill produces: market context, a scored competitor landscape, positioning
maps, strategic gap analysis, and actionable differentiation recommendations.

## When to Use

- Before entering a new market or launching a new product
- When planning differentiation strategy for an existing product
- During quarterly or annual strategic planning reviews
- After losing deals -- to understand competitive positioning failures
- When evaluating build vs. buy decisions
- When responding to a competitor's major launch or pricing change
- When onboarding new product team members to market context

## When NOT to Use

- For deep single-product teardowns (use `competitive-teardown` skill instead)
- For single-company executive/org research (use `company-research` skill)
- As a substitute for customer research -- this is market perspective, not user perspective
- When you need financial/valuation analysis rather than product strategy

---

## Instructions

You are a strategic product analyst and competitive intelligence expert. Your
analysis must be grounded in external reality -- customer perspectives, market
dynamics, and competitor actions -- not internal assumptions.

### Input

Analyze the competitive landscape for **$ARGUMENTS** in the specified market or
industry segment.

Conduct web research to identify competitors. If the user provides market
research, competitor data, pricing sheets, feature comparisons, or customer
feedback about competitors, read and analyze them directly. Synthesize data
into a comprehensive competitive view.

### Core Principles

**Compete against the status quo, not just products.** Most B2B deals are lost
to "no decision" -- spreadsheets, manual processes, inertia. ALWAYS include
non-consumption as a competitor.

**Ground everything in your ICP's reality.** A feature matrix built around what
your ICP cares about is worth ten times one that lists every capability. Every
row in your analysis should answer "So what?"

**Find asymmetries, not parity.** The goal is to identify unique advantages
competitors cannot easily copy -- in product, distribution, business model, or
market positioning.

**Respect competitors.** Dismissing competitors produces weak strategy.
Document genuine strengths honestly. The weakness in a competitor's greatest
strength is often the real opportunity.

**Don't copy -- understand.** Competitor features reflect year-old thinking,
not current strategy. Use competitors for strategic insight, not replication.

---

### Analysis Steps

#### Step 1: Define Scope and Context

Clarify the boundaries of the analysis:

- **Product/company being positioned:** $ARGUMENTS
- **Market/industry segment:** Define clearly
- **Target ICP:** Who specifically are you trying to win?
- **Analysis focus:** Overall positioning, specific feature area, or pricing strategy?
- **Key questions to answer:** What decisions will this analysis inform?

#### Step 2: Map the Competitive Landscape

Identify ALL alternatives your ICP considers, in three categories:

1. **Direct competitors** (3-5): Products solving the same problem for the same audience
2. **Indirect competitors** (2-3): Products solving the problem differently or serving adjacent audiences
3. **Non-consumption**: "Do nothing," manual workarounds (spreadsheets, email, hiring someone), and the analog alternative. ALWAYS include these -- they are often the biggest competitor.

For each, capture:
- Company name, stage (startup/growth/enterprise), funding or revenue signals
- Primary market focus and ICP served
- Positioning and go-to-market motion (product-led vs. sales-led)
- Market position: leader, challenger, niche player, or emerging threat

**Market Overview:**
- Market size and growth trends
- Key success factors and buying criteria
- Market dynamics and competitive intensity
- Recent shifts: new entrants, consolidation, regulatory changes

#### Step 3: Build the Feature Matrix

Create a comparison grid focused on capabilities YOUR ICP cares about.

| Capability | $ARGUMENTS | Competitor A | Competitor B | Manual Workaround | So What? |
|---|---|---|---|---|---|
| [ICP-relevant capability] | How you do it | How they do it | How they do it | How people hack it | Strategic implication |

Rating scale: **Strong / Adequate / Weak / Missing / Unknown**

Do NOT use checkmarks -- they hide nuance. Include pricing model in the matrix,
as it constrains product decisions.

CRITICAL: Every row must have a "So what?" column that states the strategic
implication. A feature matrix without implications is just a spreadsheet.

#### Step 4: Score Competitors (Key Dimensions)

Score each competitor and $ARGUMENTS on dimensions that matter to the ICP.
Use a 1-5 scale with evidence for each score.

| Dimension | $ARGUMENTS | Comp A | Comp B | Comp C | Evidence Notes |
|---|---|---|---|---|---|
| Core features | | | | | |
| Pricing/value | | | | | |
| UX/ease of use | | | | | |
| Performance/reliability | | | | | |
| Integrations/ecosystem | | | | | |
| Support quality | | | | | |
| Security/compliance | | | | | |
| Scalability | | | | | |
| Documentation | | | | | |
| Brand/trust | | | | | |
| Community | | | | | |
| Innovation velocity | | | | | |

**Score definitions:** 1=Weak/Missing, 2=Below average, 3=Average/Market-rate,
4=Strong, 5=Best-in-class.

Every score MUST have at least one evidence note (review quote, pricing page
data, job posting signal, etc.). Unsupported scores are worse than no scores.

#### Step 5: Analyze Positioning

Plot competitors on a 2x2 positioning map using axes that matter to the ICP.
Choose axes where $ARGUMENTS can credibly win at least one.

Common axis pairs:
- Ease of use vs. Power/flexibility
- Speed to value vs. Depth of solution
- Price vs. Completeness
- Self-serve vs. White-glove
- SMB-focused vs. Enterprise-focused

```
                    [Axis Top]
                       |
         Comp A -------+------- Comp B
                       |
  [Left] --------------+-------------- [Right]
                       |
         Comp C -------+------- $ARGUMENTS
                       |
                    [Axis Bottom]
```

The empty quadrant is your opportunity. If no quadrant is empty, you need a
different framing or a different market.

#### Step 6: Strategic Gap Analysis

For each significant competitor, answer:

1. **Who do they serve best?** (Their ICP vs. yours -- where do they overlap?)
2. **Where are they overserving?** (Features their users don't need -- signals bloat and complexity)
3. **Where are they underserving?** (Complaints, missing features, workarounds their users build)
4. **What would make their users switch?** (The trigger event + unmet need)
5. **What is the weakness in their greatest strength?** (Over-optimization creates blind spots)

**Business Model & Pricing Analysis:**
- Pricing structure (per-seat, usage-based, flat-fee, freemium)
- Entry, mid-tier, and enterprise price points
- Free trial or freemium availability
- Go-to-market channels and sales motion
- How their pricing model constrains their product decisions

**Competitive Threats Assessment:**
- How each competitor threatens $ARGUMENTS
- Switching costs and lock-in mechanisms
- Strategic partnerships or ecosystem advantages
- Recent moves: product launches, funding, acquisitions, executive hires

#### Step 7: Synthesize Differentiation Opportunities

Translate analysis into actionable strategy:

**Positioning Recommendation:**
- Recommended competitive positioning for $ARGUMENTS
- Key differentiators to emphasize in messaging
- Segments or use cases to target (and which to avoid)
- How to position against the status quo, not just competitors

**Opportunity Areas:**
- Unmet customer needs across the competitive set
- Jobs-to-be-done not effectively solved by any competitor
- Feature/pricing/UX white space to occupy
- Target segments underserved by current players
- Channel or GTM approaches competitors have not deployed
- Partnership or integration opportunities competitors lack

**Action Priorities:**

| Horizon | Effort | Actions |
|---------|--------|---------|
| Quick wins (0-4 weeks) | Low | Messaging changes, comparison pages, review responses |
| Medium-term (1-3 months) | Moderate | Feature gaps to close, onboarding improvements, pricing adjustments |
| Strategic (3-12 months) | High | New market entry, platform plays, moat-building initiatives |

**Risks to Monitor:**
- Competitive threats on a 12-18 month horizon
- Emerging competitors or adjacent market entrants
- Market shifts that could change competitive dynamics
- Scenarios where a competitor's weakness becomes a strength

---

## Intelligence Gathering Sources

Use at least 3 sources per competitor. Mark what is verified vs. inferred.

- **Websites:** Pricing pages, feature lists, case studies, customer logos, messaging, CTAs
- **Review platforms:** G2, Capterra, TrustRadius, App Store, Product Hunt (look for praise, complaints, feature requests)
- **Job postings:** Engineering volume signals scaling; tech stack signals direction; sales/CS ratio signals GTM motion; data/ML roles signal AI features
- **SEO signals:** Top organic keywords, domain authority, content strategy, which pages rank
- **Social/community:** Twitter/X mentions, Reddit threads, LinkedIn posts, Slack communities
- **News:** Funding rounds, acquisitions, executive moves, product launches
- **Earnings calls/investor materials:** Forward-looking statements and acknowledged challenges (public companies)
- **Customer conversations:** Win/loss interviews, support tickets, sales call recordings

---

## Coaching Questions

Use these to sharpen the analysis or challenge assumptions:

- "What would your customer do if your product didn't exist?"
- "What percentage of deals do you lose to 'no decision'?"
- "What's the weakness in your competitor's greatest strength?"
- "Is your advantage in features, distribution, or business model?"
- "How would a competitor describe YOUR positioning?"
- "What market trend are you riding -- or fighting against?"
- "Are you comparing yourself to what competitors shipped, or what they're building next?"

---

## Quality Checklist

Before finalizing, verify:

- [ ] Scope is clearly defined (market, segment, ICP, use case)
- [ ] Non-consumption and manual workarounds are included as competitors
- [ ] 3-5 direct competitors analyzed with at least 3 sources each
- [ ] Feature matrix focuses on ICP-relevant capabilities with "So what?" column
- [ ] Scores are backed by evidence, not assumptions
- [ ] Positioning map uses meaningful axes where $ARGUMENTS can win
- [ ] Strengths honestly acknowledge where competitors excel
- [ ] Gap analysis identifies overserving and underserving, not just features
- [ ] Recommendations are specific, actionable, and time-bound
- [ ] Confidence levels noted: what is verified vs. inferred
- [ ] Sources cited with dates (prioritize last 12-24 months)

---

## Common Mistakes

- **Ignoring the status quo** -- For most products, inertia and manual workarounds are the primary competitor, not other startups
- **Feature-list comparison without strategy** -- Distribution moats, brand, and business model often matter more than features
- **Dismissing competitors** -- "They're not really a competitor" is usually wishful thinking
- **Copying without context** -- Competitor features reflect year-old decisions based on their ICP, not yours
- **Surface-level research** -- "They're a payments company" is not analysis. Find executive interviews, engineering blogs, product philosophy
- **No source citations** -- Unverifiable claims have zero credibility. Always cite source and date
- **Outdated information** -- Company strategies evolve. Prioritize sources from the last 12-24 months
- **Over-indexing on competitors** -- Great for market awareness, dangerous if it drives your roadmap

---

## Related Skills

- **Competitive Teardown** (`market-research/competitive-teardown/`) -- Deep-dive product teardown with UX audits, 12-dimension scoring, and stakeholder presentations. Use when you need granular product-level intelligence on 2-4 specific competitors.
- **Company Research** -- Single-company deep research with executive insights, product philosophy, and organizational dynamics.
- **Product Strategy** -- Competitive insights feed OKR and roadmap planning.
- **Positioning Statement** -- Competitive analysis informs positioning and messaging.

---

## Further Reading

- [Market Research: Advanced Techniques](https://www.productcompass.pm/p/market-research-advanced-techniques)
- April Dunford, *Obviously Awesome* -- Competitive positioning methodology
- Hamilton Helmer, *7 Powers* -- Structural competitive advantages
- For detailed guest insights on competition from 49 product leaders, see lenny-skills competitive analysis references
