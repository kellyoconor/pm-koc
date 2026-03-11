---
name: outcome-roadmap
description: "Plan and communicate outcome-focused product roadmaps using Now/Next/Later, theme-based, or timeline formats. Covers input gathering, epic definition, prioritization, sequencing, dependency mapping, and stakeholder communication. Use when building a roadmap, shifting from feature lists to outcomes, planning quarterly, or aligning stakeholders on what to build and why."
---
# Outcome-Focused Roadmap

Plan and communicate product roadmaps organized by outcomes and problems solved, not feature lists shipped. A roadmap answers "what problems are we solving and in what order?" -- not "what features will we ship and when?"

## When to Use

- Annual or quarterly planning cycles
- Transforming an output-focused roadmap into an outcome-focused one
- Translating strategy into a release plan teams can execute
- Aligning stakeholders (execs, product, engineering, sales, CS) on direction
- Reframing existing feature-list roadmaps with strategic narrative
- Deciding what to build next across competing priorities
- Triggers: roadmap, quarterly planning, what to build next, outcome roadmap, prioritize roadmap

## Core Principles

### Roadmaps are strategic plans, not commitments
Jackie Bavaro: "A roadmap in strategy is not a commitment. Instead, it's a way to double check if your plan makes any sense at all and is even anywhere near feasible." Use roadmaps to identify if you need to hire or take bigger swings, not as promises.

### Dates beyond 6 weeks are fiction
Dates on a roadmap beyond the current cycle are estimates at best. Treat them that way. Communicate flexible release windows (quarters, not specific dates) and update every cycle.

### Separate truth from hypothesis
Alex Hardimen: "Take all of these crazy inputs, trying to create a very structured model to figure out, 'Okay, what is true? Where do we have conviction? Where do we have questions?'" Categorize inputs by conviction level.

### Use "seasons" in fast-changing markets
Asha Sharma: "We think about it as what season are we in?" In rapidly changing environments, align the team on secular market shifts rather than rigid long-term roadmaps.

### Force big thinking in planning
Eeke de Milliano: "At the bottom of every team charter we have a section called, Think Bigger. 'With 20% more time, what would you do?'" Explicitly ask for big ideas to prevent purely incremental thinking.

### Balance cannonballs and lead bullets
Adriel Frederick: "Maybe it's 80% of your energies on those big cannonballs, 20% on the lead bullets." A healthy roadmap balances high-investment bets with incremental improvements.

### Kill low-usage features
Gibson Biddle: "These two percenters, I would kill them." Maintain product simplicity by removing features used by only a tiny fraction of users.

## Now / Next / Later Framework

Three time horizons, decreasing in certainty:

### Now (Committed -- this cycle)
- Currently in progress or about to start
- Fully shaped: problem defined, solution scoped, appetite set
- Team assigned, expected to ship this cycle
- 1-3 items maximum

### Next (Shaped -- next 1-2 cycles)
- Problem validated, solution partially shaped
- Not yet assigned to a team
- May change based on what we learn from "Now" items
- 3-5 items maximum

### Later (Raw -- ideas worth exploring)
- Problems we believe are real but haven't validated
- No solution shaped yet
- Will be promoted to "Next" when evidence supports it, or killed
- No limit, but prune quarterly

## Roadmap Item Format

Each item is framed as an outcome, not a feature:

**Bad (feature-list roadmap):**
- Build team collaboration features
- Add CSV export
- Redesign settings page

**Good (outcome-based roadmap):**
- Reduce time-to-first-value for team signups from 15 min to under 5 min
- Enable users to get their data out without contacting support
- Reduce settings-related support tickets by 50%

**Outcome Statement Template:**
```
Enable [customer segment] to [desired customer outcome] so that [business impact]
```

## Roadmap Planning Process

### Phase 1: Gather Inputs (Days 1-2)

**Business Goals:**
- Review company OKRs, exec strategy memos, board decks
- What are the top 3 priorities this year?
- What metrics must we move? (revenue, retention, acquisition, efficiency)

**Customer Problems:**
- Review discovery interviews, support tickets, NPS feedback, churn surveys
- What are the top 3-5 customer pain points?
- Which problems affect the most customers with highest intensity?

**Technical Constraints:**
- Review with engineering: scaling issues, tech debt, platform migrations
- What enables or blocks future work?

**Stakeholder Requests:**
- What are sales, marketing, and CS asking for?
- Capture but do not commit to these requests

### Phase 2: Define Initiatives as Epics (Days 3-4)

For each initiative, write an epic hypothesis:
```
We believe that [building X] for [persona] will achieve [outcome]
because [assumption].

Success Metric: [metric name]
Target: [current] -> [target]
Effort: S / M / L / XL
```

Map each epic to a primary business outcome (retention, acquisition, engagement, efficiency).

### Phase 3: Prioritize (Day 5)

Select a prioritization framework appropriate to your context:
- **RICE** (Reach x Impact x Confidence / Effort) -- data-driven, good for scaling teams
- **ICE** (Impact x Confidence x Ease) -- lightweight, good for early-stage
- **Value/Effort 2x2** -- quick triage, visual
- **Opportunity Score** (Importance x (1 - Satisfaction)) -- customer-problem focused

Score epics, then adjust for strategic fit. A lower-scoring item may be promoted if it enables a strategic bet (e.g., Enterprise SSO scores lower but unlocks enterprise expansion).

**Key questions:**
- "If you could only ship one thing this quarter, what would it be and why?"
- "What's on your roadmap that you secretly believe won't move the needle?"
- "What would you do differently with 20% more resources? With 20% fewer?"

### Phase 4: Sequence Roadmap (Days 6-7)

**Map Dependencies:**
- Does Epic B depend on Epic A? (e.g., "Advanced Reporting" requires "Data Pipeline Upgrade")
- Are there technical blockers?

**Organize by Time Horizon:**

| Horizon | Outcome | Evidence | Status |
|---------|---------|----------|--------|
| Now | Reduce onboarding drop-off to under 30% | 5 interviews, 60% current drop-off | In progress |
| Next | Enable self-serve data export | 12 support tickets/month | Shaped |
| Later | Multi-workspace support | 3 enterprise prospects requested | Unvalidated |

**Validate with Engineering:**
- Is sequencing realistic given capacity and dependencies?
- Are there hidden technical blockers?
- Does scope need adjusting?

### Phase 5: Communicate Roadmap

**Presentation Structure (30-45 min):**
1. Strategic context (business goals, customer problems)
2. Roadmap overview (Now / Next / Later or Q1, Q2, Q3)
3. Deep dive per quarter (epics, hypotheses, success metrics)
4. What's NOT on the roadmap (and why)
5. Dependencies and risks

**Key messages:**
- "Here's why we're prioritizing X over Y" (strategic narrative)
- "Each epic drives [business outcome]" (outcome focus)
- "This is a plan, not a commitment; we'll adjust as we learn" (flexibility)

**Gather feedback, refine, and publish. Review at the start of every cycle.**

## Common Mistakes to Flag

- **Feature-driven roadmap** -- Lists features with no context. Frame epics as hypotheses with success metrics.
- **Prioritizing by HiPPO** -- Highest Paid Person's Opinion wins. Use a prioritization framework for transparency.
- **Roadmap as contract** -- Treated as a commitment with no flexibility. Communicate it as a strategic plan.
- **No dependencies mapped** -- Q2 epic blocked because Q1 dependency didn't finish. Map dependencies explicitly.
- **Solo PM roadmap** -- Created alone with no stakeholder input. Gather inputs broadly, present draft for feedback.
- **All incremental, no big bets** -- Filling roadmap with safe optimizations. Balance cannonballs and lead bullets.
- **Never saying no** -- Continuously adding without removing, leading to product bloat.
- **Too many Now items** -- If you're working on 8 things in "Now," you're finishing none of them. Limit to 1-3.
- **No evidence for items** -- A roadmap without evidence is a wish list.

## Discovery Questions (When Context is Sparse)

- "What are the company's top 3 priorities this year?"
- "What are the top 3-5 customer pain points from discovery and support data?"
- "What's the common currency you use to compare impact across different types of work?"
- "When did you last remove something from the product rather than add to it?"
- "What would need to be true for Later items to move to Next?"

---

### References

**Frameworks:**
- Now/Next/Later framework (C. Todd Lombardo, *Product Roadmaps Relaunched*, 2017)
- Shape Up cycle planning (Basecamp) -- betting table, cool-down, no carry-over
- RICE Prioritization (Intercom, 2016)
- Bruce McCarthy, *Product Roadmaps Relaunched* (2017) -- outcome-driven roadmaps

**Related Skills:**
- `prioritization-frameworks` -- Reference guide to 9 prioritization frameworks with formulas
- `prioritize-features` -- Action skill for scoring and ranking a specific feature backlog
- `user-story-mapping` -- For complex epics requiring release planning along user journeys

### Further Reading

- [Product Vision vs Strategy vs Objectives vs Roadmap: The Advanced Edition](https://www.productcompass.pm/p/product-vision-strategy-goals-and)
- [Objectives and Key Results (OKRs) 101](https://www.productcompass.pm/p/okrs-101-advanced-techniques)
- [Business Outcomes vs Product Outcomes vs Customer Outcomes](https://www.productcompass.pm/p/business-outcomes-vs-product-outcomes)
