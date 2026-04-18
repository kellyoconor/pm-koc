---
name: growth-loops
description: "Identify growth loops (flywheels) for sustainable traction. Evaluates loop types (Viral, Usage, Collaboration, User-Generated, Referral, Paid) and acquisition channels. Use when designing growth mechanisms, building product-led traction, evaluating acquisition channels, reducing reliance on paid acquisition, or understanding how growth loops work."
---

# Growth Loops

## Overview

Identify and design growth loops (flywheels) that create sustainable traction. Evaluates growth loop mechanisms and acquisition channels to reduce reliance on paid acquisition and build product-led growth.

## When to Use

- Designing growth mechanisms for a product
- Building sustainable viral or referral traction
- Reducing reliance on paid acquisition
- Evaluating whether to scale, test, or kill an acquisition channel
- Analyzing competitor growth strategies
- Optimizing product for product-led growth
- Deciding how to allocate marketing budget across channels

## Core Principles (from 54 Product Leaders)

### One dominant loop matters most
"It's usually just one loop that you need to get right. Most successful companies scale primarily through one dominant, well-executed growth loop." Focus on identifying and dominating one primary loop before diversifying (Luc Levesque).

### Product-led acquisition has zero marginal cost
"By me trying to use PayPal in its everyday intention, I'm automatically enticing someone else to become a PayPal customer." PLA is the most scalable channel because it's entirely within the company's control (Julian Shapiro).

### LTV unlocks paid loops
"If you have really healthy LTVs, then there is a big opportunity to play paid and lean into paid growth loops." Calculate if single-player LTVs are high enough to support sustainable paid acquisition (Yuriy Timen).

### Word-of-mouth requires frequency
"Word-of-mouth you can only have if you have high frequency of use. If you're using Waze every day, then every day you have an opportunity to tell someone else." Sustainable WOM is tied to usage frequency (Uri Levine).

### 40-50% organic is the healthy ratio
"A good metric is that 40 to 50% of your new customers should ideally come from organic channels. If 90% come from paid, at some point the music is going to stop" (Gokul Rajaram).

### Referral programs amplify, not create
Referrals amplify existing word-of-mouth; they can't create it from scratch. If users aren't already talking about your product, a referral program won't fix that.

### Map loops qualitatively and quantitatively
"Being able to identify the various micro and macro loops, how they're all connected, being able to document them in a qualitative model provides a shared understanding and guides intentional investment" (Ben Williams).

## The Growth Loop Types

### 1. Viral Loop
Product content gets shared on external platforms, bringing new users back.
- **Mechanism**: Users create in-product -> Share on social/external -> New users discover and signup
- **Example**: Figma designs shared as links, Loom videos shared in emails
- **Strength**: Exponential acquisition if content is inherently shareable
- **Challenge**: Requires highly shareable output and strong incentive to share

### 2. Usage Loop
Users create content or value, share it, inviting new users or driving re-engagement.
- **Mechanism**: User creates -> Shares creation -> Others consume -> Become engaged users
- **Example**: Twitter threads, Medium articles, Notion templates
- **Strength**: Growth tied directly to product usage and network effects
- **Challenge**: Requires content creation friction to be very low

### 3. Collaboration Loop
Users invite colleagues to co-create, expanding the user base within organizations.
- **Mechanism**: User creates -> Invites colleagues -> Colleagues discover product value
- **Example**: Google Docs, Figma team projects, Slack channels
- **Strength**: Deep organizational penetration and high retention
- **Challenge**: Works best for collaborative/team-based products

### 4. User-Generated Loop
Users discover content through others' creations, then create and share their own.
- **Mechanism**: User discovers content -> Creates similar content -> Shares -> Others discover
- **Example**: TikTok, Pinterest, YouTube trends
- **Strength**: Creates content flywheel and network effects
- **Challenge**: Requires critical mass of quality content

### 5. Referral Loop
Users invite others in exchange for rewards, incentives, or social recognition.
- **Mechanism**: User refers -> Referred user joins -> Referrer gets reward -> Shares more
- **Example**: Dropbox referral bonus, Uber rider referrals
- **Strength**: Directly incentivizes acquisition; easy to measure ROI
- **Challenge**: Requires valuable incentive without eroding unit economics

### 6. Paid Loop
Revenue from existing customers funds acquisition of new customers.
- **Mechanism**: Revenue -> Fund paid acquisition -> New customers -> Revenue
- **Requires**: LTV:CAC > 3:1 and payback < 12 months to be sustainable

## How It Works

### Step 1: Define Product Value
Clarify the core value users experience:
- Primary action users take in your product
- Value created per user action
- Network effects present (if any)
- Friction points in the experience
- Usage frequency (daily, weekly, monthly)

### Step 2: Evaluate Loop Fit
Assess which growth loops align with your product:
- Product type (collaborative, content-based, utility)
- Target user behavior and sharing habits
- Network effects already present
- Existing user base and engagement
- Current organic vs. paid ratio

### Step 3: Design Loop Mechanics
Create specific loop implementation:
- Trigger that initiates sharing or invitations
- Incentive for participation (intrinsic or extrinsic)
- Ease of sharing mechanism
- Conversion rate from invite to activation
- Frequency of loop repetition per user

### Step 4: Calculate Loop Coefficient
Estimate growth velocity:
- Invites/shares per user per cycle
- Conversion rate of invites to new users
- Net new users per cycle
- Time per cycle iteration

### Step 5: Evaluate Channel Economics
For each active or potential acquisition channel, assess:

| Factor | Metric | Threshold |
|---|---|---|
| Unit Economics | LTV:CAC ratio | > 3:1 to scale |
| Payback | Months to recover CAC | < 12 months |
| Customer Quality | Cohort retention by channel | At or above blended |
| Scalability | Magic Number (new MRR x 4 / S&M spend) | > 0.75 to scale |
| CAC Trend | Increasing, stable, or decreasing | Stable or decreasing |

**Channel Decision Matrix:**

| LTV:CAC | Payback | Quality | Scalability | Decision |
|---|---|---|---|---|
| > 3:1 | < 12mo | Good | High | **Scale aggressively** |
| 2-3:1 | 12-18mo | Average | Medium | **Test and optimize** |
| < 2:1 | > 18mo | Poor | Low | **Kill or fix** |

### Step 6: Build the Loop
Implement the highest-leverage loop first:
- Start with the most natural loop for your product
- Optimize messaging and friction
- Measure loop metrics and conversion rates
- Compound results over time

## Input Format

Use $ARGUMENTS to pass:
- Product description and primary user action
- Target user demographics and behavior
- Existing sharing/collaboration features
- Current growth channels and metrics
- Current organic vs. paid split
- Channel-level CAC and LTV (if available)
- Constraints or opportunities

## Output

A growth loops analysis including:
- Ranked evaluation of loop types for your product
- Recommended primary growth loop with implementation plan
- Secondary loops to layer over time
- Channel economics assessment (if data provided)
- Key metrics and measurement framework
- 30-60-90 day implementation roadmap
- Potential loop coefficient and growth projections

## Common Mistakes to Flag

- **Paid acquisition on freemium** -- consumer subscriptions relying on paid acquisition will predictably fail
- **Manufacturing network effects** -- network effects are usually inherent; hard to add as an afterthought
- **Diversifying too early** -- early-stage companies should focus on one working engine
- **Single-channel dependency** -- late-stage companies with 90%+ reliance on one channel are at extreme risk
- **Referral programs without organic WOM** -- referrals amplify; they can't create demand
- **Scaling broken channels** -- pouring money into LTV:CAC < 2:1 accelerates failure
- **Ignoring customer quality** -- low CAC with terrible retention is worse than high CAC with great retention
- **Over-relying on one channel** -- no single channel should be > 50% of new customer acquisition

## Tips

- Start with one loop and master it before adding complexity
- Viral loops compound fastest but take time to build
- Collaboration loops create strongest retention and LTV
- Measure loop health weekly during optimization phase
- Combine loops for multiplicative effect once operating at scale
- Give channels 3-6 months and 100+ customers before evaluating

---

### Further Reading

- [Product-Led Growth 101, Part 1/2](https://www.productcompass.pm/p/product-led-growth-101-12)
- [OpenAI's Product Leader Shares 3-Layer Distribution Framework To Win Mind & Market Share in the AI World](https://www.productcompass.pm/p/distribution-framework-ai-products)
- [How to Design a Value Proposition Customers Can't Resist?](https://www.productcompass.pm/p/how-to-design-value-proposition-template)
