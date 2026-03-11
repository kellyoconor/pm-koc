---
name: ab-test-analysis
description: "Analyze A/B test results with statistical significance, sample size validation, confidence intervals, segment analysis, and ship/extend/stop recommendations. Use when evaluating experiment results, checking if a test reached significance, interpreting split test data, deciding whether to ship a variant, or documenting experiment learnings."
---

## A/B Test Results Analysis

Evaluate A/B test results with statistical rigor and translate findings into clear product decisions.

### Context

You are analyzing A/B test results for **$ARGUMENTS**.

If the user provides data files (CSV, Excel, or analytics exports), read and analyze them directly. Generate Python scripts for statistical calculations when needed.

### Instructions

1. **Summarize the Experiment**:
   - What was the hypothesis? (Restate it to frame results interpretation)
   - What was changed (the variant)?
   - What is the primary metric? Any guardrail metrics?
   - How long did the test run?
   - What is the traffic split?
   - Link to original experiment design document if available

2. **Validate the Test Setup**:
   - **Sample size**: Is the sample large enough for the expected effect size?
     - Use the formula: n = (Z_alpha/2 x 2 x p x (1-p)) / MDE^2
     - Flag if the test is underpowered (<80% power)
   - **Duration**: Did the test run for at least 1-2 full business cycles (minimum 7 days)?
   - **Randomization**: Any evidence of sample ratio mismatch (SRM)?
   - **Novelty/primacy effects**: Was there enough time to wash out initial behavior changes?
   - **Peeking**: Was the test stopped early based on interim results? Flag inflated false positive risk.

3. **Calculate Statistical Significance**:
   - **Conversion rate** for control and variant
   - **Relative lift**: (variant - control) / control x 100
   - **p-value**: Using a two-tailed z-test or chi-squared test
   - **Confidence interval**: 95% CI for the difference
   - **Statistical significance**: Is p < 0.05?
   - **Practical significance**: Is the lift meaningful for the business?

   If the user provides raw data, generate and run a Python script to calculate these.

4. **Analyze Secondary and Guardrail Metrics**:
   - Did any guardrail metrics (revenue, engagement, page load time) degrade?
   - A winning primary metric with degraded guardrails may not be a true win
   - Note any secondary metrics that moved unexpectedly -- both positive and negative

5. **Segment the Data**:
   - Look for differential effects across user segments (platform, tenure, plan type, geography)
   - Sometimes overall results mask important segment-level insights
   - Be cautious: segment analysis with small samples generates noise, not signal

6. **Interpret Results**:

   | Outcome | Recommendation |
   |---|---|
   | Significant positive lift, no guardrail issues | **Ship it** -- roll out to 100% |
   | Significant positive lift, guardrail concerns | **Investigate** -- understand trade-offs before shipping |
   | Not significant, positive trend | **Extend the test** -- need more data or larger effect |
   | Not significant, flat | **Stop the test** -- no meaningful difference detected |
   | Significant negative lift | **Don't ship** -- revert to control, analyze why |

7. **Extract Learnings**:
   - What did you learn beyond the numbers?
   - Surprising findings, questions raised, implications for product hypothesis
   - Negative results are valuable learnings -- document them honestly
   - How does this inform future experiments?

8. **Provide the Analysis Summary**:
   ```
   ## A/B Test Results: [Test Name]

   **Hypothesis**: [What we expected]
   **Duration**: [X days] | **Sample**: [N control / M variant]

   | Metric | Control | Variant | Lift | p-value | Significant? |
   |---|---|---|---|---|---|
   | [Primary] | X% | Y% | +Z% | 0.0X | Yes/No |
   | [Guardrail 1] | ... | ... | ... | ... | ... |
   | [Guardrail 2] | ... | ... | ... | ... | ... |

   **Recommendation**: [Ship / Extend / Stop / Investigate]
   **Reasoning**: [Why]
   **Key Learnings**: [What we learned]
   **Next Steps**: [What to do]
   ```

### Common Mistakes to Flag

- **Peeking**: Checking results daily and stopping when significance appears. This inflates false positive rates. Set a duration and commit to it.
- **Underpowered tests**: Running with too few users to detect a meaningful effect. Result is "inconclusive" which teaches nothing.
- **Post-hoc storytelling**: "The test was inconclusive but we noticed an interesting trend in the 25-34 age group." That's noise, not signal.
- **No guardrails**: Increasing signups by removing friction may break downstream metrics.
- **Ignoring practical significance**: Statistically significant doesn't mean business-meaningful. A 0.1% lift with p=0.04 may not be worth shipping.

### Quality Checklist

Before finalizing, verify:
- [ ] Statistical methods and significance are clearly stated
- [ ] Confidence intervals are included (not just p-values)
- [ ] Segment analysis checked for differential effects
- [ ] Secondary/guardrail metrics are reported
- [ ] Learnings go beyond just the numbers
- [ ] Recommendation is clear and actionable
- [ ] Negative or inconclusive results are reported honestly

Think step by step. Save as markdown. Generate Python scripts for calculations if raw data is provided.

---

### Further Reading

- [A/B Testing 101 + Examples](https://www.productcompass.pm/p/ab-testing-101-for-pms)
- [Testing Product Ideas: The Ultimate Validation Experiments Library](https://www.productcompass.pm/p/the-ultimate-experiments-library)
- [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)
