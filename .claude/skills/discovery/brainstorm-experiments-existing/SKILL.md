---
name: brainstorm-experiments-existing
description: "Design hypothesis-driven experiments to test assumptions for an existing product -- A/B tests, prototypes, fake doors, spikes, and other low-effort validation methods. Use when validating assumptions, testing feature ideas cheaply, planning product experiments, or setting up a test for a product change."
---

## Design Experiments (Existing Product)

Design low-effort experiments to test product assumptions before committing to full implementation. Most A/B tests fail because they test vague ideas, run too short, or peek at results. A well-designed experiment has a clear hypothesis, adequate power, and a pre-committed analysis plan.

### Context

You are helping a product team design experiments for **$ARGUMENTS**. The team has a feature idea and assumptions that need validation.

If the user provides files (PRDs, assumption lists, designs), read them first.

### Hypothesis Template

Every experiment starts with a written hypothesis before any work begins:

**"If we [make this specific change] for [this audience], then [this metric] will [change in this direction] by [this amount], because [this reason based on evidence]."**

Example:
> "If we replace the 5-step onboarding wizard with a single guided first-project flow for new signups, then 7-day activation rate will increase from 23% to 35%, because 4/6 interviewed users said they wanted to 'just start using it' not 'set everything up first.'"

Every part matters:
- **Specific change**: Not "improve onboarding" -- the exact change
- **Audience**: Who sees this? New users only? Free tier only?
- **Metric + direction + amount**: A number you'll measure
- **Because**: The evidence-based reason. No evidence = no experiment.

### Instructions

1. **Clarify the idea and assumptions**: Confirm what the team wants to build and what they need to validate.

2. **Suggest experiments** for each assumption. Consider methods like:
   - **Fake door / feature stub tests**: Measure demand before building
   - **First-click testing**: Task completion with a prototype
   - **Wizard of Oz**: Manual backend, automated frontend
   - **A/B tests on production**: With proper methodology (see below)
   - **Technical spikes**: Prove feasibility before committing
   - **Survey-based validation**: Behavioral questions, not opinion-based
   - **Concierge tests**: Deliver the value manually to test demand

3. **For each experiment, specify**:

   | Element | Detail |
   |---|---|
   | **Assumption** | What do we believe? |
   | **Hypothesis** | Full if/then/because statement |
   | **Method** | What exactly will we do to validate? |
   | **Primary Metric** | One metric the experiment is designed to move |
   | **Guardrail Metrics** | Metrics that must NOT degrade |
   | **Success Threshold** | The expected value if we are right |
   | **Sample Size** | How many users needed (calculate before running) |
   | **Duration** | How long to run (minimum 7 days for A/B tests) |
   | **Effort** | Low / Medium / High |

4. **For A/B tests specifically**:

   **Sample Size Calculation** (do BEFORE running):
   - Baseline conversion rate (current number)
   - Minimum detectable effect (smallest change worth caring about)
   - Statistical significance level (95% standard)
   - Power (80% minimum)

   If you need 50,000 users and get 500/week, the experiment takes 100 weeks. Either increase the MDE or don't run the experiment.

   **Analysis Plan** (write BEFORE launching):
   - What metric, what threshold, what you'll do if it wins/loses/is inconclusive
   - Pre-commit to avoid post-hoc storytelling

5. **Key principles**:
   - Measure actual behavior, not users' opinions
   - Test responsibly -- don't put users or the business at risk
   - For production tests, explain risk mitigation strategies
   - Aim for maximum validated learning with minimal effort
   - One change per experiment -- isolate variables

### Common Mistakes to Flag

- **Peeking**: Checking results daily and stopping when you see significance. Statistical significance at day 3 of a 14-day test is meaningless.
- **Underpowered tests**: Running with too few users to detect a meaningful effect. Result is "inconclusive" which teaches nothing.
- **Testing too many things**: Changing 5 things at once means you don't know what worked.
- **No guardrails**: Increasing signups by removing the password field "works" but breaks everything else.
- **Post-hoc storytelling**: If the test was inconclusive, accept it. Don't mine segments for "interesting trends."
- **No evidence for hypothesis**: If you can't state why you believe the change will work, you're not ready to test.

### Guidelines

- CRITICAL: Write the hypothesis and analysis plan BEFORE building anything.
- NEVER peek at results before the pre-determined end date.
- NEVER run an experiment without calculating required sample size first.
- ALWAYS include guardrail metrics.
- NEVER test more than one major change per experiment. Isolate variables.
- ALWAYS document learnings from inconclusive tests. "We couldn't detect an effect with N=5,000 users" is still useful information.

Think step by step. Present experiments in a clear table or structured format. Save as markdown if substantial.

---

### Further Reading

- [Testing Product Ideas: The Ultimate Validation Experiments Library](https://www.productcompass.pm/p/the-ultimate-experiments-library)
- [Assumption Prioritization Canvas: How to Identify And Test The Right Assumptions](https://www.productcompass.pm/p/assumption-prioritization-canvas)
- [What Is Product Discovery? The Ultimate Guide Step-by-Step](https://www.productcompass.pm/p/what-exactly-is-product-discovery)
- [A/B Testing 101 + Examples](https://www.productcompass.pm/p/ab-testing-101-for-pms)

### References

- Kohavi, Tang, Xu -- *Trustworthy Online Controlled Experiments* (controlled experimentation methodology)
