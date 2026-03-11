---
name: jtbd-analysis
description: "Analyze customer motivations using Jobs-to-be-Done — functional, social, and emotional jobs, pains, gains, and Forces of Progress. Use when uncovering unmet needs, understanding why customers switch, repositioning a product, or improving discovery and messaging."
---

## Jobs-to-be-Done Analysis

Understand why customers "hire" and "fire" products. JTBD (Christensen/Moesta) reframes competition: you're not competing against similar products, you're competing against whatever the customer currently uses to get the job done — including doing nothing.

### Context

You are conducting a Jobs-to-be-Done analysis for **$ARGUMENTS**.

If the user provides files (interview transcripts, research data, product briefs), read them first.

### When to Use

- Early-stage discovery (before you know the solution)
- Validating product-market fit (does your solution address the right jobs?)
- Prioritizing roadmap (which jobs are most painful/important?)
- Competitive analysis (what are customers "hiring" competitors for?)
- Marketing messaging (speak to jobs, not features)
- Understanding why customers switch products
- When existing personas feel too surface-level or demographic

### When NOT to Use

- For trivial features (don't over-analyze small tweaks)
- As a substitute for quantitative validation (JTBD informs hypotheses; data validates them)
- When you have no customer research (JTBD grounded in assumptions is just guessing)

### Instructions

#### Step 1: Define the Context

Before exploring JTBD, clarify:
- **Target customer segment:** Who are you studying?
- **Situation:** In what context does the job arise? (e.g., "When managing a project deadline...")
- **Current solutions:** What do they use today? (competitors, workarounds, doing nothing)

If missing context: Conduct customer interviews, contextual inquiries, or switch interviews (why they switched from a previous solution).

#### Step 2: Write the Job Statement

Structure every job as: **"When [situation], I want to [motivation], so I can [expected outcome]."**

Examples:
- "When I finish a customer call, I want to capture key insights quickly, so I can share them with my team before I forget the context."
- NOT: "Users want better note-taking." (Too vague, no situation, no outcome.)

The situation is critical — the same person has different jobs in different contexts.

#### Step 3: Explore Customer Jobs

**Functional Jobs** — What tasks are they trying to complete?
- Verb-driven: "send," "analyze," "coordinate"
- Solution-agnostic: Don't say "use email to communicate" — say "communicate with remote teammates"
- Specific: "Manage finances" is too broad; "Track business expenses for tax deductions" is specific

**Social Jobs** — How do they want to be perceived by others?
- Audience-specific: Who are they trying to impress? (boss, clients, peers)
- Often drives adoption more than functional jobs
- Examples: "Be seen as a strategic thinker by my exec team," "Appear responsive to clients"

**Emotional Jobs** — What emotional state do they want to achieve or avoid?
- Include both positive ("feel in control") and negative ("avoid embarrassment")
- Root in research, not fabrication — use customer quotes
- Examples: "Feel confident I'm not missing important details," "Avoid anxiety of manual data entry errors"

#### Step 4: Identify Pains

**Challenges:** What obstacles prevent completing the job?
- "Tools don't integrate, forcing manual data entry"

**Costliness:** What takes too much time, money, or effort?
- "Generating monthly reports takes 8 hours of manual work"

**Common Mistakes:** What errors could be prevented?
- "Accidentally overwriting someone else's work in shared files"

**Unresolved Problems:** What do current solutions fail to address?
- "Current CRM doesn't track customer health scores"

#### Step 5: Uncover Gains

**Expectations:** What would make them love a solution?
- "Automatically categorizes expenses without manual tagging"

**Savings:** What reductions in time, money, or effort would delight?
- "Reduce report generation from 8 hours to 10 minutes"

**Adoption Factors:** What would make them switch?
- "Free trial with no credit card," "Migration support to import existing data"

**Life Improvement:** How would their life be better?
- "I could leave work on time instead of staying late to finish reports"

#### Step 6: Map Forces of Progress

Four forces determine whether someone switches to your product. Map all four:

```
DRIVING ADOPTION                    RESISTING ADOPTION
================                    ==================
Push: Pain with current solution    Anxiety: Fear of the new solution
Pull: Attraction of new solution    Habit: Comfort with current way
```

**Push** (away from current solution) — What's broken or frustrating? Stronger push = more urgency.
- "I spend 3 hours every week manually copying data between tools."

**Pull** (toward your solution) — What's attractive about the new way? This is your value proposition.
- "Automatic sync means I never copy data again."

**Anxiety** (about the new solution) — Switching costs, learning curves, data migration, reliability.
- "What if the sync breaks and I lose data?"

**Habit** (of the current solution) — Muscle memory, sunk costs, "good enough."
- "I've built all my templates in the current tool over 2 years."

**To win: Push + Pull must be stronger than Anxiety + Habit.**

If anxiety is high, reduce it (free trials, migration tools, guarantees). If habit is strong, find the trigger moment when the current solution fails hard enough to break inertia.

#### Step 7: Identify the Trigger Event

What specific moment made them start looking for a new solution? This is your marketing gold.

Interview recent switchers — people who adopted your product (or a competitor) in the last 90 days. Their memory is fresh.

Map the timeline: First thought -> Passive looking -> Active looking -> Decision -> Purchase -> First use -> Ongoing use.

#### Step 8: Prioritize and Validate

- **Rank pains by intensity:** Acute vs. mild annoyances. Ask "If we only solved one pain, which would have the biggest impact?"
- **Identify must-have vs. nice-to-have gains:** What drives adoption vs. what's just a bonus?
- **Cross-reference with personas:** Do different personas have different jobs/pains/gains?
- **Find patterns across 5+ interviews.**
- **Validate with data:** Survey a broader audience to confirm JTBD insights.

### Anti-Patterns

- **Confusing jobs with solutions:** "I need to use Slack" is not a job. Ask "Why?" 5 times until you reach the real job.
- **Generic jobs:** "Be more productive" is too vague. Get specific: "Reduce time spent generating monthly reports from 8 hours to 1 hour."
- **Ignoring social/emotional jobs:** Only documenting functional jobs misses powerful motivators. People often buy based on emotional/social needs.
- **Fabricating JTBD without research:** Filling out the template from assumptions makes the analysis worthless.
- **Treating all pains as equal:** List 20 pains without prioritization = no clarity. Rank by intensity.
- **Only mapping Push and Pull:** Teams ignore Anxiety and Habit — the reasons people DON'T switch.
- **Interviewing only happy customers:** Interview people who evaluated you and chose a competitor. They reveal your weaknesses.
- **Defining jobs as features:** "I want to export to PDF" is a feature request. The job is "I want to share a polished document with my investors."

### Output Template

```
## JTBD Analysis: [Product/Feature Area]

### Context
**Customer Segment:** [Who]
**Situation:** [When/where the job arises]
**Current Solutions:** [What they use today]

### Job Statement
"When [situation], I want to [motivation], so I can [expected outcome]."

### Customer Jobs
**Functional:** [Tasks to complete]
**Social:** [How they want to be perceived]
**Emotional:** [How they want to feel]

### Pains
**Challenges:** [Obstacles]
**Costliness:** [Time/money/effort waste]
**Common Mistakes:** [Preventable errors]
**Unresolved Problems:** [Gaps in current solutions]

### Gains
**Expectations:** [What would delight]
**Savings:** [Time/money/effort reduction]
**Adoption Factors:** [What would make them switch]
**Life Improvement:** [How life gets better]

### Forces of Progress
**Push:** [Pain with current solution]
**Pull:** [Attraction of new solution]
**Anxiety:** [Fear of switching]
**Habit:** [Comfort with status quo]

### Trigger Event
[What specific moment made them start looking]

### Priority Ranking
1. [Highest-intensity pain / most critical job]
2. [Second priority]
3. [Third priority]
```

---

### Further Reading

- Clayton Christensen, *Competing Against Luck* (2016) — Origin of Jobs-to-be-Done theory
- Bob Moesta, *Demand-Side Sales 101* (2020) — Forces of Progress and switch interviews
- Tony Ulwick, *Outcome-Driven Innovation* (2016) — Quantifying jobs and outcomes
- Alexander Osterwalder, *Value Proposition Canvas* (2014) — Customer jobs/pains/gains framework
- [Jobs-to-be-Done Masterclass with Tony Ulwick and Sabeen Sattar](https://www.productcompass.pm/p/jobs-to-be-done-masterclass-with) (video course)
- [How to Design a Value Proposition Customers Can't Resist?](https://www.productcompass.pm/p/how-to-design-value-proposition-template)
