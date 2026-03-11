---
name: pricing-strategy
description: "Design and optimize pricing strategies including pricing models, competitive analysis, willingness-to-pay estimation, tier design, and price experimentation. Use when setting prices for the first time, evaluating pricing models, preparing for a pricing change, comparing freemium vs paid approaches, or optimizing monetization."
---
# Pricing Strategy

Design a pricing strategy grounded in value delivery, competitive positioning, and willingness to pay. Combines strategic pricing design with practical implementation guidance from 46+ product leaders.

## When to Use

- Setting prices for a new product
- Evaluating or changing pricing models (flat-rate, per-seat, usage-based, tiered, freemium)
- Conducting competitive pricing analysis
- Designing pricing tiers and feature gating
- Planning pricing experiments and A/B tests
- Comparing freemium vs paid approaches
- Optimizing monetization for an existing product
- Triggers: pricing, pricing model, how to price, freemium, willingness to pay, pricing tiers

**Note:** For evaluating the *financial impact* of a specific pricing change (ARPU, churn risk, conversion, NRR), see the `finance-based-pricing-advisor` skill in the finance folder -- that skill is purpose-built for go/no-go decisions on proposed pricing moves.

## Core Principles

### Price is a measure of value
Madhavan Ramanujam: "When we think about price, we think about it as a measure. Like liter is a measure of volume, price is a measure of value. And when you think of it this way, it really stands for, do people actually want your product?" Use willingness to pay (WTP) as a proxy for product value and conduct WTP conversations early in the development cycle.

### Never set it and forget it
Naomi Ionita: "Do not set it and forget it. I see companies do this, where they labor over designs and features... And then pricing's sort of plucked out of thin air, and then they don't revisit it." Treat pricing as a living part of the product roadmap, revisiting it every 6-12 months as new value is added.

### Self-serve has a ceiling
Elena Verna: "Self-serve monetization has a cap of about $10,000. That's just how much we're able to process on the credit cards before they start getting flagged and declined." Transition to sales-led motions for contracts exceeding $10,000-$15,000.

### Sample premium features in the free experience
Albert Cheng: "What if we actually sampled a number of different paid suggestions and interspersed them to free users across their writing? All of a sudden, people were seeing Grammarly as a much more powerful tool." Interspersing paid features within the free experience is more effective for conversion than keeping them hidden behind a hard paywall.

### Reduce early friction to unlock success
Archie Abrams: "When you can lower the barriers to monetary friction in some form... you can actually causally change your ability to become successful." Reducing early monetary friction can causally improve user success by extending their runway to find value.

### Prioritize roadmap by willingness to pay
Madhavan Ramanujam: "You cannot prioritize a product roadmap without having a willingness to pay conversation." Prioritize the 20% of features that drive 80% of the willingness to pay.

### Pricing changes are two-way doors
Eeke de Milliano: "Move faster on reversible decisions like pricing by grandfathering existing users." Most pricing changes can be reversed or adjusted, especially when you protect existing customers through grandfathering.

## Context

You are developing a pricing strategy for **$ARGUMENTS**.

If the user provides files (competitor pricing, survey data, financial models, or usage data), read them first. Use web search to research competitor pricing if needed.

## Instructions

### 1. Understand the Value Delivered

- What is the core value proposition?
- What is the customer's alternative (and its cost)?
- What quantifiable outcomes does the product deliver? (time saved, revenue gained, cost reduced)
- What is the customer's willingness to pay based on that value?
- What value does your product create, and for which customer segment is that value highest?

### 2. Evaluate Pricing Models -- Recommend the Best Fit

| Model | Best For | Example |
|---|---|---|
| **Flat-rate** | Simple products, predictable costs | Basecamp ($99/mo flat) |
| **Per-seat** | Collaboration tools, team products | Slack, Figma |
| **Usage-based** | Infrastructure, API products | AWS, Twilio |
| **Tiered** | Products with distinct user segments | Most SaaS (Free/Pro/Enterprise) |
| **Freemium** | Products with viral/network effects | Spotify, Notion |
| **Freemium + usage** | Platform products | Vercel, OpenAI API |
| **Value-based** | High-impact enterprise tools | Salesforce, Palantir |

### 3. Analyze Competitive Pricing

- Map competitor pricing tiers and what's included
- Identify where your product sits (premium, mid-market, budget)
- Find pricing gaps or opportunities
- Note any industry pricing conventions

### 4. Design the Pricing Structure

- **Tiers**: Define 2-4 tiers with clear differentiation
- **Feature gating**: Which features go in which tier? (Use value metrics, not arbitrary limits)
- **Value metric**: What unit do you charge on? (users, events, storage, API calls)
- **Anchor pricing**: Set the most popular tier to feel like the obvious choice
- **Annual discount**: Typically 15-20% off monthly pricing (limit to 10-15% to protect LTV)

### 5. Estimate Price Sensitivity

- Van Westendorp Price Sensitivity Meter (if survey data available):
  - Too cheap: quality concerns
  - Cheap: good value
  - Expensive: starting to hesitate
  - Too expensive: won't buy
- Alternatively, estimate based on competitor pricing and value delivered
- Ask directly: "What would customers pay for this if they had to pay today?"

### 6. Plan Pricing Experiments

- A/B test pricing pages (different price points, tier names, feature bundles)
- Founder-led sales conversations to test willingness to pay
- Landing page tests with different price anchors
- Cohort analysis of conversion rates by price point
- Grandfather existing users when testing new pricing on new signups

### 7. Output a Pricing Recommendation

```
Recommended Model: [Model type]
Value Metric: [What you charge on]

| Tier | Price | Target Segment | Key Features | Positioning |
|---|---|---|---|---|

Key Assumptions:
- [Assumption] -> [How to test]

Risks:
- [Risk] -> [Mitigation]

Next Steps:
- [Action item with timeline]
```

## Discovery Questions (When Context is Sparse)

- "What would customers pay for this if they had to pay today? Have you asked them directly?"
- "What value does your product create, and for which customer segment is that value highest?"
- "When did you last revisit your pricing? What has changed about your product since then?"
- "What's preventing you from charging more? Is it competition, value delivery, or assumption?"
- "How do free users experience the value of paid features today?"
- "At what price point does your sales motion need to change from self-serve to sales-assisted?"

## Common Mistakes to Flag

- **Pricing as afterthought** -- Setting prices based on gut feel rather than willingness-to-pay research
- **Never iterating** -- Launching with a price and never revisiting as the product evolves
- **Hard paywalls on premium** -- Hiding all premium value instead of sampling it in the free experience
- **Ignoring the self-serve ceiling** -- Trying to close $50K deals through credit card checkout
- **Racing to the bottom** -- Competing on price rather than differentiating on value
- **Annual discounts that hurt margin** -- 30% annual discount improves cash but destroys LTV; keep to 10-15%
- **Copycat pricing** -- Your customers, value prop, and cost structure differ from competitors
- **Premature optimization** -- Spending months on 5% pricing tweaks while missing 50% growth opportunities elsewhere

Think step by step. Save as markdown. Flag any assumptions that need validation before launch.

---

### References

**Frameworks:**
- Madhavan Ramanujam, *Monetizing Innovation* -- WTP-driven pricing
- Van Westendorp Price Sensitivity Meter -- WTP research methodology
- Patrick Campbell (ProfitWell) -- Pricing research and benchmarks

**Related Skills:**
- `positioning-ideas` -- Positioning and pricing are deeply intertwined
- `finance-based-pricing-advisor` (finance folder) -- Financial impact analysis of specific pricing changes (ARPU, churn, NRR, CAC payback)
- `outcome-roadmap` -- Roadmap priorities should reflect WTP signals

### Further Reading

- [Product Pricing Strategies 101](https://www.productcompass.pm/p/product-pricing-strategies-101)
- [The AI Product Pricing Masterclass: OpenAI Product Lead on Why SaaS Pricing Fails in AI (and How to Fix It)](https://www.productcompass.pm/p/ai-product-pricing) (video course)
