---
name: opportunity-solution-tree
description: "Build an Opportunity Solution Tree (OST) to structure product discovery — map a desired outcome to opportunities, solutions, and experiments. Based on Teresa Torres' Continuous Discovery Habits. Use when structuring discovery work, mapping opportunities to solutions, deciding what to build next, or converting stakeholder requests into structured discovery."
---

## Opportunity Solution Tree (OST)

A visual framework for structuring continuous product discovery. Connects a desired **outcome** to customer **opportunities**, possible **solutions**, and **experiments** to validate them. Prevents the two biggest PM mistakes: building solutions without clear problems, and chasing problems disconnected from business goals.

### Domain Context

The **Opportunity Solution Tree** (Teresa Torres, *Continuous Discovery Habits*) is the backbone of modern product discovery. It prevents teams from jumping to solutions by forcing them to first map the opportunity space.

**Structure (4 levels):**

```
Desired Outcome (business metric you're trying to move)
  |
  +-- Opportunity 1 (customer need/pain/desire)
  |     +-- Solution A
  |     |     +-- Experiment 1
  |     |     +-- Experiment 2
  |     +-- Solution B
  |           +-- Experiment 3
  |
  +-- Opportunity 2
  |     +-- Solution C
  |     +-- Solution D
  |           +-- Experiment 4
  |
  +-- Opportunity 3
        +-- Solution E
        +-- Solution F
```

1. **Desired Outcome** (top) — The measurable business or product outcome the team is pursuing. Should be a single, clear metric (e.g., "increase 7-day retention to 40%"). NOT: "Improve onboarding" (not measurable). This comes from your OKRs or product strategy.

2. **Opportunities** (second level) — Customer needs, pain points, or desires discovered through research. These are problems worth solving — not features. Frame from the customer's perspective: "I struggle to..." or "I wish I could..." NOT: "Add an onboarding wizard" (solution masquerading as opportunity). Prioritize using **Opportunity Score: Importance x (1 - Satisfaction)** (Dan Olsen, *The Lean Product Playbook*). Each opportunity is independent — addressing one doesn't depend on another.

3. **Solutions** (third level) — Possible ways to address each opportunity. Generate at least 3 per opportunity — don't commit to the first idea. The **Product Trio** (PM + Designer + Engineer) should ideate together. "Best ideas often come from engineers."

4. **Experiments** (bottom) — Fast, cheap tests to validate whether a solution actually addresses the opportunity. Use assumption testing (Value, Usability, Viability, Feasibility risks). Prefer experiments with "skin-in-the-game" (Alberto Savoia) over opinion-based validation. Experiments should be designed to DISPROVE your solution, not just confirm it.

### Context

You are helping a product team build an Opportunity Solution Tree for **$ARGUMENTS**.

If the user provides files (research data, stakeholder requests, PRD drafts, OKR documents, interview summaries), read them first.

### When to Use

- Starting discovery for a new product area
- Stakeholder requests a feature or product initiative (convert to structured discovery)
- Clarifying vague OKRs or strategic goals
- Prioritizing which problems to solve first
- After user research to connect insights to action
- When you have too many feature ideas and need structure
- Communicating product strategy to stakeholders

### When NOT to Use

- When the problem is already validated (move to solution testing)
- For tactical bug fixes or technical debt (no discovery needed)
- When stakeholders demand a specific solution (address alignment issues first)

### Key Principles

- **One outcome at a time.** Don't try to solve everything. Focus the tree on a single desired outcome.
- **Opportunities, not features.** "Never allow customers to design solutions. Prioritize opportunities (problems), not features."
- **Compare and contrast.** Always generate at least 3 solutions per opportunity before choosing. Avoid the "first idea" trap.
- **Discovery is not linear.** Loop back if experiments fail. Kill solutions that don't validate. Explore new branches.
- **Continuous, not periodic.** Update the tree weekly as you learn from interviews, analytics, and experiments.
- **Evidence-based.** Opportunities come from research — interviews, data, support tickets — not brainstorming. Each opportunity needs evidence from 3+ sources.

### Instructions

#### Input Requirements
- A desired outcome or business metric to improve
- Customer research data (interviews, surveys, analytics, feedback)
- Optionally: existing opportunities or solution ideas to organize
- Optionally: stakeholder request or feature request to reframe

#### Step 1: Define the Desired Outcome

Confirm or help articulate a single, measurable outcome at the top of the tree.

Ask: "What business or product metric are you trying to move?"

Common outcome categories:
- **Revenue growth** — Increase ARR, expand revenue, new revenue streams
- **Customer retention** — Reduce churn, increase activation, improve engagement
- **Customer acquisition** — Increase sign-ups, trial conversions, new user growth
- **Product efficiency** — Reduce support costs, decrease time-to-value

Make it specific and measurable: "Increase trial-to-paid conversion from 15% to 25%" not "Improve conversion."

#### Step 2: Map Opportunities

From provided research, identify 3-7 customer opportunities (needs/pains). Group related opportunities. Frame each from the customer's perspective.

Rules for good opportunities:
- Framed as customer needs, not product features
- "New users don't understand what to do first" (opportunity)
- NOT "Add an onboarding wizard" (solution masquerading as opportunity)
- Grounded in evidence from research
- Each opportunity is independent

For each opportunity, note:
- **Problem description** (from customer's perspective)
- **Evidence** (interview quotes, data, support tickets)
- **Opportunity Score** (if data available): Importance x (1 - Satisfaction)

#### Step 3: Prioritize Opportunities

Focus on the top 2-3 opportunities. Use Opportunity Score or qualitative assessment. You can't test everything — pick the opportunity with strongest evidence and highest potential impact.

Never pursue more than 2-3 opportunities simultaneously. Focus beats breadth.

#### Step 4: Generate Solutions

For each prioritized opportunity, brainstorm 3+ solutions from PM, Designer, and Engineer perspectives. Include wild ideas — they often reveal assumptions.

For each solution, specify:
- **Hypothesis:** "If we [implement solution], then [outcome metric] will [change] because [rationale]"
- **Assumptions:** What must be true for this to work?
- **Effort estimate:** Days/weeks/months

#### Step 5: Design Experiments

For the most promising solutions, design 1-2 fast experiments. For each:
- **Hypothesis:** What are you testing?
- **Method:** A/B test, prototype + usability test, concierge test, fake door, Wizard of Oz
- **Metric:** What will you measure?
- **Success threshold:** What result validates the hypothesis?
- **Duration:** How long will you run the experiment?

Experiment types (from cheapest to most expensive):
1. Manual concierge test — run the solution manually with 20 users
2. Prototype + usability test — clickable prototype, watch 10 users
3. Fake door test — measure intent before building
4. A/B test — build MVP, show to 50% of users, compare

#### Step 6: Evaluate and Select POC

Score solutions on:
- **Feasibility** (1-5): 1 = months of work, 5 = days/weeks
- **Impact** (1-5): 1 = minimal outcome movement, 5 = major outcome shift
- **Market Fit** (1-5): 1 = customers don't care, 5 = customers actively request this

Total Score = Feasibility + Impact + Market Fit. Recommend the highest-scoring solution as the starting POC.

#### Step 7: Visualize the Tree

Present the full OST in a clear hierarchical format:

```
## Desired Outcome
[Specific, measurable goal]

### Opportunity 1: [Name] (Score: X)
**Problem:** [Description from customer perspective]
**Evidence:** [Sources]

- Solution A: [Description]
  - Experiment: [Method, metric, threshold]
- Solution B: [Description]
  - Experiment: [Method, metric, threshold]
- Solution C: [Description]

### Opportunity 2: [Name] (Score: X)
[Same structure]

### Opportunity 3: [Name] (Score: X)
[Same structure]

## Selected POC
**Opportunity:** [Which one]
**Solution:** [Which one]
**Hypothesis:** "If we [X], then [Y] because [Z]"
**Experiment:** [Details]
**Success Criteria:** [What validates]
**Next Steps:**
1. [Build/design experiment]
2. [Run experiment for X duration]
3. [Measure results]
4. [If successful -> scale; if failed -> try next solution]
```

### Common Pitfalls

**Pitfall 1: Opportunities Disguised as Solutions**
"Opportunity: We need a mobile app." Reframe as customer problem: "Mobile-first users can't access the product on the go."

**Pitfall 2: Skipping Divergence**
"We know the solution is X, just need to build it." Generate at least 3 solutions per opportunity. Force divergence before convergence.

**Pitfall 3: Outcome Too Vague**
"Improve user experience." Make outcomes measurable: "Increase NPS from 30 to 50."

**Pitfall 4: No Experiments**
Picking a solution and moving straight to roadmap. Every solution must map to an experiment. No experiments = no OST.

**Pitfall 5: Analysis Paralysis**
Generating 20 opportunities, 50 solutions, never picking one. Limit to 3 opportunities, 3 solutions each (9 total). Pick POC, run experiment, learn, iterate.

**Pitfall 6: Skipping the Opportunity Layer**
Going from outcome directly to solutions. The opportunity layer is where the insight lives. NEVER skip it.

**Pitfall 7: Only One Solution Per Opportunity**
If you can't think of 3 solutions, you haven't explored the space.

---

### Further Reading

- Teresa Torres, *Continuous Discovery Habits* (2021) — Origin of Opportunity Solution Tree
- Dan Olsen, *The Lean Product Playbook* (2015) — Opportunity scoring
- Jeff Patton, *User Story Mapping* (2014) — Outcome-driven product planning
- Ash Maurya, *Running Lean* (2012) — Hypothesis-driven experimentation
- [The Extended Opportunity Solution Tree](https://www.productcompass.pm/p/the-extended-opportunity-solution-tree)
- [What Is Product Discovery? The Ultimate Guide Step-by-Step](https://www.productcompass.pm/p/what-exactly-is-product-discovery)
- [Product Trio: Beyond the Obvious](https://www.productcompass.pm/p/product-trio)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (video course)
