---
name: north-star-metric
description: "Define a North Star Metric and 3-5 supporting input metrics that form a metrics constellation. Classify the business game (Attention, Transaction, Productivity), validate against criteria for an effective North Star, and add counter-metrics to prevent gaming. Use when choosing a North Star Metric, setting up a metrics framework, learning about the North Star Framework, or deciding what to measure."
---

# North Star Metric

Identify a North Star Metric and 3-5 Input Metrics that form a metrics constellation. Classifies the business game being played and validates against criteria for an effective North Star.

## Domain Context

NSM is **NOT**: multiple metrics, a revenue/LTV metric (must be customer-centric), an OKR (that's a goal-setting technique), or a strategy (but choosing the right NSM is a strategic choice).

NSM **IS**: a single, customer-centric KPI that reflects the value customers get from the product and serves as a leading indicator of long-term business success. You can use Key Results (OKRs) to express expected change in NSM.

**Test:** If this metric goes up, does the company sustainably grow? If yes, it's your North Star.

Free resource: [The North Star Framework 101 (PDF)](https://learn.productcompass.pm/nsm101)

## When to Use

- Defining your company's key metric framework
- Setting up a metrics tracking system
- Choosing what to measure and optimize for
- Evaluating potential North Star candidates
- Aligning the team around a single success measure

## Core Principles (from 27 Product Leaders)

### Measure value delivered, not captured
"The North Star metric measures how much value we create for the market. WhatsApp measured messages sent because every message is incremental value. Airbnb used nights booked." Select a metric that tracks core utility provided to the customer, not business extraction (Itamar Gilad).

### Avoid lagging indicators
"Retention is a terrible thing to goal on. It's almost impossible to drive in a meaningful way in a short term. Find a short-term metric you can measure that drives a long-term output." Identify proxy metrics that are sensitive to experimentation (Jess Lachs).

### Simple beats sophisticated
"If people understand it, if they have an intuition around it, if it's something people can talk about across the company, it's going to be a much better metric than your made up composite score." Avoid composite metrics with complex coefficients (Jess Lachs).

### Measure from the customer's perspective
"What was the value we're trying to produce for the customer, and can we measure it from their perspective? We suggested 'companies with zero support tickets.'" Define metrics based on the absence of friction or the presence of success moments (Jeff Weinstein).

### Name metrics evocatively
"Picking metric titles that make you feel something. 'Companies with zero support' -- the brevity and customer mindset built into the chart name can become currency inside the company." Use simple, evocative names instead of technical database field names (Jeff Weinstein).

### Codify definitions precisely
"Everyone will talk about the same metric but have different nuances. What is a daily active user? Pick a definition, instrument it, codify it. No confusion." Metrics only drive alignment when backed by precise definitions and accurate instrumentation (Manik Gupta).

### Avoid revenue as North Star
"Monthly purchases is great because it maps to value people are getting. Units of value from the customer perspective is more important than overall revenue." Revenue should be a product of doing things right, not the guiding metric (Sean Ellis).

### Select a hard activation metric
"An activation rate that falls in a lower percentage range, maybe 5-15%, is better than a high percentage because it means there's likely much higher correlation with long-term retention." High-bar activation metrics that few users reach are often more valuable (Lauryn Isford).

### Revisit periodically
"A North Star metric should be a measure of what you plan to do. Revisit North Star metrics every 6-12 months to ensure they still align with business goals" (Lauryn Isford).

## The Three Business Games

Before identifying your North Star, classify your business:

- **Attention Game**: How much time do customers spend using your product? (Facebook, Spotify, YouTube, TikTok)
- **Transaction Game**: How many transactions occur between customers and your platform? (Amazon, Uber, Airbnb, PayPal)
- **Productivity Game**: How efficiently can someone complete their work or achieve their goals? (Canva, Dropbox, Loom, Notion)

## Prompt

You are a metrics strategist specializing in North Star metrics and growth measurement frameworks.

Given the following business context: $ARGUMENTS

**Step 1: Classify the Business Game**
Determine which game this company plays: Attention, Transaction, or Productivity.

**Step 2: Identify the North Star Metric**
Suggest a single metric that meets all seven criteria:

1. **Easy to Understand**: Clear definition that everyone in the organization comprehends
2. **Customer-Centric**: Reflects value delivered to customers, not just revenue or activity
3. **Sustainable Value**: Indicates habits and long-term customer engagement
4. **Vision Alignment**: Represents meaningful progress toward the company's vision
5. **Quantitative**: Measurable with clear, numeric tracking
6. **Actionable**: Teams can directly influence it through product, marketing, and operational changes
7. **Leading Indicator**: Predicts future business success and revenue growth

Provide the exact formula/definition. "Active user" means nothing -- specify exactly what counts.

**Step 3: Build the Input/Output Tree**
Define 3-5 Input Metrics that drive the North Star:

```
North Star: [Your NSM]
  |
  +-- Acquisition: [metric]
  |     +-- [sub-metric]
  |     +-- [sub-metric]
  |
  +-- Activation: [metric]
  |     +-- [sub-metric]
  |     +-- [sub-metric]
  |
  +-- Engagement: [metric]
  |     +-- [sub-metric]
  |
  +-- Retention: [metric]
        +-- [sub-metric]
```

Each leaf should be a metric a team can directly influence. The tree shows HOW inputs drive the North Star.

**Step 4: Define Counter-Metrics**
EVERY metric gets a counter-metric to prevent gaming:

| Metric | Counter-Metric |
|--------|---------------|
| Signup conversion rate | Activation rate (don't lower the bar to get signups) |
| Time to first value | 30-day retention (don't rush users past learning) |
| Feature adoption | Task completion rate (don't push features that confuse) |
| Revenue per user | Churn rate (don't squeeze users into leaving) |

If the metric improves but the counter-metric degrades, you've optimized the wrong thing.

## Diagnostic Questions

- "What specific moment represents a user getting value from your product?"
- "Could a non-technical person in your company understand and discuss this metric?"
- "Can teams actually influence this metric through their work in a quarter?"
- "What would happen if you gamed this metric -- what would break?"
- "Does this metric measure value delivered to users or value extracted from them?"
- "Is this a leading indicator or a lagging one that's hard to move?"

## Common Mistakes to Flag

- **Revenue as North Star** -- revenue is an outcome; focus on the customer value that drives it
- **Complex composite metrics** -- if you can't explain it simply, teams can't rally around it
- **Lagging indicators like retention** -- find the leading metrics that predict retention
- **Gaming vulnerability** -- add counter-metrics to prevent optimization that hurts users
- **Undefined terms** -- 'active user' means nothing until you codify exactly what counts
- **Vanity metrics** -- total signups, page views, total users. These only go up and tell you nothing
- **Too many metrics** -- never track more than 5-7 metrics actively. If your dashboard has 20 charts, nobody looks at any of them

## Tips for Best Results

- Provide details about your business model and revenue model
- Share your company's vision, mission, or long-term goals
- Include current metrics you're tracking
- Mention key customer segments and use cases
- Describe the primary value you deliver to customers
- Set a baseline before setting a target

## Guidelines

- ALWAYS pair every metric with a counter-metric. No exceptions.
- NEVER use vanity metrics as North Star candidates.
- ALWAYS define metrics with exact formulas.
- ALWAYS set a baseline before setting a target.
- NEVER set targets without understanding the current number and why it's where it is.
- ALWAYS measure outcomes (user behavior) over outputs (features shipped).

---

### Further Reading

- [The North Star Framework 101](https://www.productcompass.pm/p/the-north-star-framework-101)
- [AARRR (Pirate) Metrics: The 5-Stage Framework for Growth](https://www.productcompass.pm/p/aarrr-pirate-metrics)
- [The Google HEART Framework: Your Guide to Measuring User-Centric Success](https://www.productcompass.pm/p/the-google-heart-framework)
- [The Ultimate List of Product Metrics](https://www.productcompass.pm/p/the-ultimate-list-of-product-metrics)
