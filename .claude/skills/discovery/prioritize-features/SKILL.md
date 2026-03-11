---
name: prioritize-features
description: "Prioritize a backlog of feature ideas using RICE, ICE, or Opportunity Score with enabler/blocker classification and top-5 recommendations. Use when prioritizing a feature backlog, making scope decisions, ranking product ideas, or deciding what to build next."
---
# Prioritize Feature Backlog

Evaluate and rank a backlog of feature ideas to identify the highest-impact items to pursue. Uses scoring frameworks combined with strategic judgment and blocker/enabler classification.

## When to Use

- Prioritizing a feature backlog for the next cycle or quarter
- Making scope decisions under resource constraints
- Ranking competing product ideas from stakeholders
- Deciding between quick wins and strategic bets
- Breaking ties between similarly valuable features
- Triggers: prioritize, rank features, what to build next, backlog prioritization

## Context

You are helping prioritize features for **$ARGUMENTS**.

If the user provides files (spreadsheets, backlogs, opportunity assessments), read and analyze them directly.

## Instructions

### 1. Understand Priorities

Confirm the product objective and success metrics. Ask:
- What is the primary goal this cycle? (acquisition, retention, engagement, revenue, efficiency)
- What does success look like? What metrics are you trying to move?
- Are there strategic bets or constraints to account for?

### 2. Select Scoring Framework

For framework details, see the `prioritization-frameworks` skill. Quick selection guide:

- **Minimal data, small team:** ICE (Impact x Confidence x Ease)
- **Some analytics, scaling team:** RICE ((Reach x Impact x Confidence) / Effort)
- **Customer survey data available:** Opportunity Score (Importance x (1 - Satisfaction))

### 3. Score Each Feature

Evaluate each feature against:
- **Impact**: How much does it move the needle on desired outcomes? Use Opportunity Score if customer data is available.
- **Reach**: How many users/accounts are affected? Use real numbers from analytics.
- **Confidence**: How sure are you? 100% = hard data. 80% = strong evidence. 50% = gut feel. Never 100% without quantitative data.
- **Effort**: Person-weeks including design, engineering, QA, and cross-team coordination. Round up.

**Show the math.** A prioritization without visible scores is just an opinion list.

### 4. Classify as Blocker or Enabler

For each feature:
- **Blocker:** Removes a barrier to adoption or retention. Users are churning, stuck, or can't start because this is missing. Examples: missing SSO for enterprise, broken mobile experience, no data export.
- **Enabler:** Delights existing users or deepens engagement. Examples: keyboard shortcuts, advanced filters, integrations.

**Rule: Prioritize blockers over enablers when growing.** Removing friction > adding delight. Flip when retention is strong but engagement is flat.

If two items are within 20% score of each other, use the blocker/enabler lens to break ties, or pick the one with higher Confidence.

### 5. Recommend Top Features

Present:
- Clear ranking with scores visible
- Brief rationale for each selection
- Key trade-offs considered
- What was deprioritized and why
- Any items that need more data before confident scoring

### 6. Present as Prioritization Table

| Rank | Feature | Reach | Impact | Confidence | Effort | Score | Type |
|------|---------|-------|--------|------------|--------|-------|------|
| 1 | [Feature A] | [n] | [1-3] | [%] | [weeks] | [score] | Blocker |
| 2 | [Feature B] | [n] | [1-3] | [%] | [weeks] | [score] | Enabler |
| ... | ... | ... | ... | ... | ... | ... | ... |

**Deprioritized:**
| Feature | Score | Reason |
|---------|-------|--------|
| [Feature X] | [score] | [Why it's not in top N] |

## Common Pitfalls

- **Prioritizing by loudest voice** -- Use visible scoring, not stakeholder pressure
- **All incremental, no big bets** -- Check if your top items are all safe optimizations
- **Overweighting effort** -- Don't avoid hard problems just because they score low
- **Ignoring strategic context** -- Scores are input, not automation; adjust for vision
- **Never reprioritizing** -- Re-score every cycle; the world changes
- **Prioritizing more than one cycle** -- Don't rank 6 months of work. Score for the next cycle only.

## Discovery Questions (When Context is Sparse)

- "If you could only ship one thing this quarter, what would it be and why?"
- "What's on your backlog that you secretly believe won't move the needle?"
- "Which items are you most confident about? Least confident?"
- "Are any of these blocking adoption or causing churn right now?"
- "What would you do differently with 20% more resources? With 20% fewer?"

Think step by step. Save as markdown if the output is substantial.

---

### References

**Frameworks:**
- RICE (Intercom, 2016), ICE (Sean McBride, 2012), Opportunity Score (Dan Olsen)
- Enablers vs Blockers (Linear Method)

**Related Skills:**
- `prioritization-frameworks` -- Detailed reference for all 9+ frameworks with formulas and templates
- `outcome-roadmap` -- Prioritized features feed into the roadmap

### Further Reading

- [Kano Model: How to Delight Your Customers Without Becoming a Feature Factory](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [The Product Management Frameworks Compendium + Templates](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (video course)
