---
name: prioritization-frameworks
description: "Reference guide to prioritization frameworks (RICE, ICE, Kano, MoSCoW, Opportunity Score, Value/Effort, Cost of Delay, and more) with formulas, when-to-use guidance, decision logic for choosing frameworks, and implementation templates. Use when selecting a prioritization method, comparing frameworks, or learning how different prioritization approaches work."
---
# Prioritization Frameworks Reference

A reference guide to help you select and apply the right prioritization framework for your context. Combines framework definitions with context-aware selection guidance.

## Core Principle

Never allow customers to design solutions. Prioritize **problems (opportunities)**, not features. Frameworks execute strategy; they don't create it.

## Framework Selection Guide

Match your framework to your context:

| Your Situation | Recommended Framework | Why |
|---|---|---|
| Pre-PMF, minimal data, small team | ICE or Value/Effort | Lightweight, fast, gut-check scoring |
| Early PMF, scaling, some analytics | RICE | Data-driven, adds Reach for granularity |
| Mature product, rich customer data | Opportunity Score or Kano | Customer-problem focused, satisfaction-gap analysis |
| Multiple stakeholders disagreeing | Weighted Scoring or RICE | Transparent scoring builds consensus |
| Balancing quick wins vs big bets | Value/Effort 2x2 | Visual, intuitive for stakeholder alignment |
| Time-sensitive features | Cost of Delay | Urgency-based, quantifies delay cost |
| Complex user journeys | Story Mapping (Impact Mapping) | Goal-driven, ties features to outcomes |
| Requirements scoping | MoSCoW | Forcing function for hard choices |

### When to Reassess Your Framework
- Product stage changes (e.g., PMF found, scaling begins)
- Team grows or reorganizes
- Stakeholder dynamics shift
- Current framework feels broken (too slow, ignores important factors)
- Stick with one framework for 6-12 months before switching

## Frameworks in Detail

### Opportunity Score (Dan Olsen, *The Lean Product Playbook*)

**Recommended for:** Prioritizing customer problems.

Survey customers on **Importance** and **Satisfaction** for each need (normalize to 0-1 scale).

- **Current value** = Importance x Satisfaction
- **Opportunity Score** = Importance x (1 - Satisfaction)
- **Customer value created** = Importance x (S2 - S1), where S1 = before, S2 = after

High Importance + low Satisfaction = highest Opportunity Score = best opportunities. Plot on an Importance vs Satisfaction chart -- upper-left quadrant is the sweet spot.

### ICE Framework

**Recommended for:** Quick prioritization of initiatives with limited data.

- **I** (Impact) = Opportunity Score x Number of Customers affected (or 1-10 gut score)
- **C** (Confidence) = How confident are we? (1-10)
- **E** (Ease) = How easy is it to implement? (1-10)

**Score** = I x C x E. Higher = prioritize first.

### RICE Framework

**Recommended for:** Data-driven teams with usage analytics.

- **R** (Reach) = Number of users/accounts affected in a set time period. Use real numbers from analytics.
- **I** (Impact) = How much will this move the metric per user? Score: 0.25 (minimal), 0.5 (low), 1 (medium), 2 (high), 3 (massive). Be honest -- most features are a 1.
- **C** (Confidence) = How sure are you? 100% = hard data. 80% = strong evidence. 50% = gut feel. NEVER score 100% without quantitative data.
- **E** (Effort) = Person-weeks of work. Include design, engineering, QA, cross-team coordination. Round up.

**Score** = (R x I x C) / E

### Enablers vs Blockers Lens (Linear Method)

After scoring, classify each feature:
- **Blocker:** Removes a barrier to adoption or retention. Users are churning or stuck because this is missing.
- **Enabler:** Delights existing users or deepens engagement.

**Rule: Prioritize blockers over enablers when growing.** Removing friction > adding delight when trying to grow. Flip when retention is strong but engagement is flat.

If two items are within 20% RICE score, use the blocker/enabler lens to break ties.

### Kano Model

**Recommended for:** Understanding customer expectations (classification, not scoring).

- **Must-be (Basic):** Expected; absence causes dissatisfaction; presence doesn't increase satisfaction
- **Performance (Linear):** More is better; directly correlated with satisfaction
- **Attractive (Delighters):** Unexpected; absence doesn't hurt; presence creates delight
- **Indifferent:** Customers don't care
- **Reverse:** Some customers actively dislike this

Use Kano to classify features, then apply ICE/RICE to score within categories.

### Value/Effort Matrix (2x2)

**Recommended for:** Quick triage and visual stakeholder alignment.

Plot features on two axes:
- **X-axis:** Effort (low to high)
- **Y-axis:** Value (low to high)

Quadrants: Quick Wins (high value, low effort) > Strategic Bets (high value, high effort) > Fill-ins (low value, low effort) > Avoid (low value, high effort)

### Weighted Decision Matrix

**Recommended for:** Multi-factor decisions requiring stakeholder buy-in.

1. Define criteria (e.g., customer impact, revenue potential, strategic fit, technical risk)
2. Assign weights to each criterion (must total 100%)
3. Score each option on each criterion (1-5 or 1-10)
4. Multiply scores by weights, sum for total

### MoSCoW

**Recommended for:** Requirements scoping and hard scope decisions.

- **Must have:** Non-negotiable for this release
- **Should have:** Important but not critical
- **Could have:** Nice to have if time allows
- **Won't have:** Explicitly out of scope (for now)

Caution: Project management origin. Lacks nuance for strategic product decisions.

### Cost of Delay

**Recommended for:** Time-sensitive features where delay has quantifiable cost.

Estimate the cost (lost revenue, lost customers, competitive disadvantage) of delaying each feature by one week/month. Prioritize by highest cost of delay relative to effort.

### Eisenhower Matrix

**Recommended for:** Personal PM task management.

- Urgent + Important: Do now
- Important + Not Urgent: Schedule
- Urgent + Not Important: Delegate
- Not Urgent + Not Important: Eliminate

## Full Comparison

| Framework | Best For | Key Insight |
|-----------|----------|-------------|
| Eisenhower Matrix | Personal tasks | Urgent vs Important |
| Impact vs Effort | Quick triage | Simple 2x2, not rigorous for strategic decisions |
| Risk vs Reward | Initiatives with uncertainty | Like Impact/Effort but accounts for risk |
| **Opportunity Score** | Customer problems | Importance x (1 - Satisfaction). Recommended. |
| Kano Model | Understanding expectations | Classification, not scoring |
| Weighted Decision Matrix | Multi-factor decisions | Stakeholder buy-in via transparent weights |
| **ICE** | Ideas/initiatives (lightweight) | Impact x Confidence x Ease |
| **RICE** | Ideas at scale (data-driven) | (Reach x Impact x Confidence) / Effort |
| MoSCoW | Requirements scoping | Must/Should/Could/Won't |
| Cost of Delay | Time-sensitive features | Quantifies delay cost |
| Enablers vs Blockers | Growth-stage products | Blockers before enablers when growing |

## Running a Prioritization Session

1. List all candidates with a one-sentence description
2. Score each on framework dimensions independently -- don't anchor on each other
3. Calculate scores and rank
4. Tag each as Blocker or Enabler (if applicable)
5. Check: are any Blockers ranked below Enablers? Justify or re-rank
6. Adjust for strategic fit -- framework scores are input, not automation
7. Top 3-5 items = your next cycle
8. Present ranked list with visible math to stakeholders

## Common Pitfalls

- **Wrong framework for your stage** -- Pre-PMF startup using weighted scoring with 10 criteria. Match framework to stage.
- **Framework whiplash** -- Switching frameworks every quarter creates team confusion. Stick for 6-12 months.
- **Treating scores as gospel** -- "A scored 8,000 vs B's 7,999, so A wins." Use frameworks as input; PM judgment overrides when needed.
- **Solo PM scoring** -- Lack of buy-in. Involve PM, design, engineering in collaborative scoring sessions.
- **No framework at all** -- "We prioritize by who shouts loudest." Even imperfect structure beats chaos.
- **Overweighting Effort** -- Don't avoid hard problems just because they score low. Some strategic bets require high effort.
- **Inflating Confidence** -- Be honest. 50% confidence is okay if data is scarce.
- **RICE for strategic bets** -- RICE favors incremental wins. For multi-quarter bets, use strategic judgment alongside scoring.

## Templates

- [Opportunity Score intro (PDF)](https://drive.google.com/file/d/1ENbYPmk1i1AKO7UnfyTuULL5GucTVufW/view)
- [Importance vs Satisfaction Template (Google Slides)](https://docs.google.com/presentation/d/1jg-LuF_3QHsf6f1nE1f98i4C0aulnRNMOO1jftgti8M/edit#slide=id.g796641d975_0_3)
- [ICE Template (Google Sheets)](https://docs.google.com/spreadsheets/d/1LUfnsPolhZgm7X2oij-7EUe0CJT-Dwr-/edit?usp=share_link&ouid=111307342557889008106&rtpof=true&sd=true)
- [RICE Template (Google Sheets)](https://docs.google.com/spreadsheets/d/1S-6QpyOz5MCrV7B67LUWdZkAzn38Eahv/edit?usp=sharing&ouid=111307342557889008106&rtpof=true&sd=true)

---

### References

**Frameworks:**
- Dan Olsen, *The Lean Product Playbook* -- Opportunity Score
- Intercom, *RICE Prioritization* (2016)
- Sean McBride, *ICE Scoring* (2012)
- Noriaki Kano, *Kano Model* (1984)
- Linear Method -- Enablers vs Blockers
- Luke Hohmann, *Innovation Games* (2006)

**Related Skills:**
- `prioritize-features` -- Action skill for scoring and ranking a specific feature backlog
- `outcome-roadmap` -- Roadmap planning that uses these frameworks

### Further Reading

- [The Product Management Frameworks Compendium + Templates](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Kano Model: How to Delight Your Customers Without Becoming a Feature Factory](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (video course)
