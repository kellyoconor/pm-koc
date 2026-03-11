---
name: problem-statement
description: "Frame a user-centered problem statement with empathy-driven narrative, validation scoring, and HMW formulation. Combines problem framing, validation, and the MITRE Problem Framing Canvas. Use when kicking off discovery, aligning stakeholders, writing a PRD, or deciding whether a problem is worth solving."
---

## Problem Statement

Articulate a problem from the user's perspective and validate whether it's worth solving. This skill combines empathy-driven framing (who is blocked, what they're trying to do, why it matters, how it feels), evidence-based validation scoring, and structured reframing techniques.

This is not a requirements doc or a solution in disguise — it's a human-centered problem narrative that ensures you're solving a problem worth solving.

### Context

You are framing a problem statement for **$ARGUMENTS**.

If the user provides files (research data, interview summaries, support tickets, analytics), read them first.

### When to Use

- Kicking off discovery or problem validation work
- Aligning stakeholders before solutioning
- Socializing a problem with engineering, design, or exec teams
- When you have feature requests but unclear underlying problems
- Evaluating whether a proposed solution actually addresses the core problem
- Realigning a drifted project back to its original intent
- Communicating up to leadership about priorities

### When NOT to Use

- When you haven't done any user research yet (don't guess — interview first)
- For internal operational problems (this is for user-facing problems)
- As a substitute for a PRD (this frames the problem; PRD defines the solution)
- When the problem is already well-understood and validated (move to solution design)
- For tactical bug fixes or technical debt (no deep framing needed)

### Instructions

#### Step 1: Gather User Context

Before drafting, ensure you have:
- **User interviews or research:** Direct quotes, observed behaviors, pain points
- **Jobs-to-be-Done insights:** What users are "hiring" your product to do
- **Persona clarity:** Who specifically experiences this problem
- **Constraints data:** Geographic, tech, time, demographic limitations

If missing context: Run discovery interviews. Don't fabricate problems.

#### Step 2: Look Inward (Challenge Assumptions)

Before framing the problem, examine your own biases (from MITRE Problem Framing Canvas):

- **What is the problem as you currently understand it?** Describe symptoms.
- **Why hasn't it been solved yet?** (New, hard, low priority, lack of resources, systemic inequity?)
- **How might you be part of the problem?** Common biases:
  - Assuming you know what customers want (confirmation bias)
  - Optimizing for internal ease, not user value (internal bias)
  - Overlooking specific user segments (survivorship bias)
  - Solution-first thinking — "we need [feature X]" before understanding root problem (premature convergence)

#### Step 3: Look Outward (Understand Who Is Affected)

- **Who experiences this problem?** Specific personas, roles, segments
- **When and where?** Triggering events, contexts, physical/digital locations
- **What are the consequences?** Impact on users (time, money, reputation, emotion)
- **Who else has this problem?** Other companies, industries, domains — and how do they deal with it?
- **Who doesn't have this problem?** What's different about them?
- **Who's been left out of the conversation?** Marginalized voices, edge cases, overlooked stakeholders
- **Who benefits when the problem exists?** Who gains from the status quo?

#### Step 4: Draft the Problem Framing Narrative

Fill in from the persona's point of view:

```
**I am:** [Describe the persona — 3-4 key characteristics]
**Trying to:** [Desired outcomes the persona cares most about]
**But:** [Barriers preventing the outcomes]
**Because:** [Root cause of the problem]
**Which makes me feel:** [Emotional impact — use actual quotes from research]
```

Quality checks:
- **"I am" specificity:** Can you picture this person? "A sales rep managing 50+ leads in spreadsheets" not "busy professionals"
- **"Trying to" clarity:** Is this an outcome (measurable) or just a task (activity)?
- **"But" depth:** Are these real barriers or just inconveniences?
- **"Because" honesty:** Is this the root cause or just a symptom? Keep asking "why" until you hit root cause.
- **"Makes me feel" authenticity:** Do these emotions come from research or assumptions?

#### Step 5: Validate the Problem (Scoring)

Rate each dimension 1-5 based on evidence:

**Frequency** (How often does this happen?)
- 5: Daily or multiple times per day
- 4: Weekly
- 3: Monthly
- 2: Quarterly
- 1: Rarely or once

**Intensity** (How painful is it when it happens?)
- 5: Blocks critical work, causes real losses (money, time, reputation)
- 4: Major friction, significant workarounds needed
- 3: Annoying but manageable
- 2: Minor inconvenience
- 1: Barely noticeable

**Existing Workarounds** (Are people already trying to solve it?)
- 5: Paying for imperfect solutions or built custom tools
- 4: Cobbled together multi-tool workflows
- 3: Have a basic process but it's tedious
- 2: Occasionally Google for solutions
- 1: Haven't tried to solve it

**Willingness to Pay** (Would they pay to make this go away?)
- 5: Already spending money on partial solutions
- 4: Have explicitly said they'd pay (and named a number)
- 3: Would "probably" pay (hypothetical — discount this)
- 2: Want it free
- 1: Haven't considered paying

**Validation Score = Frequency x Intensity x Workarounds x WTP**
- **250+**: Strong signal. Problem is worth solving.
- **100-249**: Promising. Needs more evidence on weak dimensions.
- **Under 100**: Weak. Pivot the framing or walk away.

Every score MUST cite evidence. Acceptable evidence types (strongest first):
1. Observed behavior
2. Spending on alternatives
3. Time invested in custom solutions
4. Direct quotes from interviews (Mom Test compliant)
5. Support tickets / forum posts
6. Survey responses (weakest)

#### Step 6: Craft the Final Problem Statement

Synthesize into one powerful sentence:

**Formula:** `[Persona] needs a way to [desired outcome] because [root cause], which currently [emotional/practical impact].`

**Example:** "Enterprise IT admins need a way to provision user accounts in under 5 minutes because current processes take 2+ hours with manual approvals, which causes project delays and frustrated end-users."

Quality checks:
- **One sentence:** If it requires multiple sentences, the problem isn't crisp yet
- **Measurable:** Can you tell if you've solved it?
- **Empathetic:** Does it resonate emotionally?
- **Shareable:** Could you say this in a meeting and have stakeholders nod?
- **Solution-free:** Does it prescribe "how"? If so, reframe around the outcome.

#### Step 7: Create "How Might We" Statement

Make it actionable:

**Formula:** `How might we [action that addresses the problem] as we aim to [objective/desired condition]?`

**Example:** "How might we guide non-technical users through onboarding with plain-language prompts as we aim to increase activation from 40% to 70%?"

The HMW should be broad enough to allow multiple solutions but narrow enough to be actionable. "How might we add a mobile app?" is too narrow (solution-first). "How might we enable mobile-first users to access core workflows on any device?" opens the solution space.

#### Step 8: Validate and Socialize

- **Test with users:** Read the problem statement aloud to people who experience the problem. Do they say "Yes, exactly!"?
- **Share with stakeholders:** Product, engineering, design, exec. Does it align everyone?
- **Iterate based on feedback:** If anyone says "I don't think that's the real problem," dig deeper.

### Anti-Patterns (What This Is NOT)

- **Not a solution in disguise:** "The problem is we lack AI-powered analytics" = sneaking in a solution
- **Not a business problem:** "Our revenue is down" isn't a user problem (it's a symptom). Christopher Miller: "Are we talking about a business problem? Are we talking about a customer problem?"
- **Not a feature request:** "Users need a dashboard" isn't a problem (what are they trying to do?)
- **Not generic:** "Users want better UX" is too vague to be actionable

### Common Pitfalls

**Pitfall 1: Solution Smuggling**
"The problem is we don't have [specific feature]." Reframe around the user's desired outcome, not the feature.

**Pitfall 2: Business Problem Disguised as User Problem**
"Users want to increase our revenue." Users don't care about your metrics. Dig into *why* users churn.

**Pitfall 3: Generic Personas**
"I am a busy professional trying to be more productive." Too broad. Get specific.

**Pitfall 4: Symptom Instead of Root Cause**
"Because the UI is confusing." Ask "Why is the UI confusing?" Keep asking until you hit root cause.

**Pitfall 5: Fabricated Emotions**
"Which makes me feel empowered and delighted." These sound like marketing copy. Real emotions from research: "frustrated," "overwhelmed," "anxious," "stuck."

**Pitfall 6: Skipping Validation**
Framing a problem beautifully doesn't make it worth solving. Always score with evidence.

---

### Further Reading

- Clayton Christensen, *Competing Against Luck* (2016) — Origin of outcome-focused problem framing
- Rob Fitzpatrick, *The Mom Test* (2013) — Gathering honest evidence for problem validation
- MITRE Innovation Toolkit, "Problem Framing Canvas v3" (2021) — Equity-driven problem framing
- Osterwalder & Pigneur, *Value Proposition Canvas* — Customer pains/gains/jobs
- Dave Gray, *Empathy Mapping* — Emotional framing techniques
- [What Is Product Discovery? The Ultimate Guide Step-by-Step](https://www.productcompass.pm/p/what-exactly-is-product-discovery)
