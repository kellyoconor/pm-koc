---
name: summarize-interview
description: "Synthesize customer interview transcripts into structured summaries with JTBD, patterns, verbatim quotes, and actionable recommendations. Use when processing interview recordings or transcripts, synthesizing discovery interviews, or creating interview summaries for stakeholders."
---

## Summarize Customer Interview

Transform interview transcripts into structured summaries focused on Jobs to Be Done, patterns, and actionable insights. Works for single interviews or cross-interview synthesis.

### Context

You are summarizing customer interview(s) for the product discovery of **$ARGUMENTS**.

The user will provide interview transcript(s) — either as attached files (text, PDF, audio transcription) or pasted directly. Read any attached files first.

### Instructions

#### For a Single Interview

1. **Read the full transcript** carefully before summarizing.

2. **Fill in the summary template** below. Use "-" if information is unavailable.

3. **Use clear, simple language** — a primary school graduate should be able to understand the summary.

4. **Preserve verbatim quotes** — capture 3-5 direct quotes that powerfully illustrate insights. Always attribute to participant ID.

5. **Distinguish observation from interpretation** — "Users mentioned X" is observation; "Users need Y because of Z" is interpretation. Include both.

#### Single Interview Output Template

```
## Interview Summary

**Date**: [Date and time of the interview]
**Participant**: [ID / role / relevant characteristics — no PII]
**Background**: [Background information about the customer]
**Interview Method**: [Mom Test / JTBD / Switch / Journey mapping]

---

### Jobs to Be Done
**Functional Job**: [What task they're trying to accomplish]
**Social Job**: [How they want to be perceived]
**Emotional Job**: [How they want to feel]

### Current Solution
[What solution they currently use and how]

### What Works About Current Solution
- [Job to be done, desired outcome, importance, and satisfaction level]

### Problems With Current Solution
- [Job to be done, desired outcome, importance, and satisfaction level]
- [Pain intensity: Acute / Moderate / Mild]

### Forces of Progress (if switching behavior observed)
- **Push**: [What's driving them away from current solution]
- **Pull**: [What's attracting them to alternatives]
- **Anxiety**: [What worries them about switching]
- **Habit**: [What keeps them doing it the old way]

### Workarounds
- [What they've built, hacked, or jury-rigged to cope]

### Key Quotes
- "[Verbatim quote 1]" — context
- "[Verbatim quote 2]" — context
- "[Verbatim quote 3]" — context

### Surprise Findings
- [Unexpected findings that challenged assumptions]

### Signal Strength
- **Frequency**: [How often they encounter the problem]
- **Intensity**: [How painful — blocks work / major friction / annoying / minor]
- **Workaround investment**: [Time/money spent on alternatives]
- **Willingness to pay**: [Evidence of spending or commitment]

### Action Items
- [Date, Owner, Action — e.g., "2025-01-15, PM, Follow up with customer about pricing"]
```

#### For Cross-Interview Synthesis (3+ interviews)

When provided with multiple interview transcripts or summaries, perform a synthesis across all interviews.

1. **Create participant profiles** — Document each participant with relevant context: role, segment, tenure, notable characteristics. Helps readers assess representativeness.

2. **Identify recurring themes** — Tag observations by topic. Look for themes that appear across 3+ participants. Distinguish frequently mentioned topics from one-off comments.

3. **Extract meaningful quotes** — Capture 3-5 verbatim quotes per theme that powerfully illustrate the insight.

4. **Synthesize into insight statements** — Transform themes into insights. An insight goes beyond observation ("users mentioned X") to interpretation ("users need Y because of Z"). Connect what you heard to why it matters.

5. **Formulate prioritized recommendations** — Based on insights, propose actions. Each recommendation ties directly to an insight. Note confidence level based on strength of evidence.

6. **Document limitations** — Acknowledge what you didn't learn, sample biases, or areas needing further research.

#### Cross-Interview Synthesis Output Template

```
## Interview Synthesis: [Research Topic]

**Date Range**: [First interview] to [Last interview]
**Participants**: [Count and brief segment description]
**Research Objective**: [What we set out to learn]
**Interview Method**: [Methodology used]

---

### Participant Overview

| ID | Role | Segment | Tenure | Notable |
|----|------|---------|--------|---------|
| P1 | ...  | ...     | ...    | ...     |

---

### Theme 1: [Theme Name]
**Frequency**: [X of Y participants mentioned this]
**Insight**: [Interpretation — why this matters]

**Evidence**:
- P1: "[verbatim quote]"
- P3: "[verbatim quote]"
- P5: "[verbatim quote]"

**Recommendation**: [Specific, actionable next step]
**Confidence**: [High / Medium / Low — based on evidence strength]

---

### Theme 2: [Theme Name]
[Same structure]

---

### Theme 3: [Theme Name]
[Same structure]

---

### Pattern Summary

**Strongest signals** (3+ participants, high intensity):
- [Pattern 1]
- [Pattern 2]

**Emerging signals** (2 participants, worth watching):
- [Pattern 3]

**One-off observations** (1 participant, note for future):
- [Observation]

---

### Jobs to Be Done (Aggregated)

**Primary functional jobs**:
- [Most common job across interviews]

**Primary emotional jobs**:
- [Most common emotional need]

**Primary social jobs**:
- [Most common social need]

---

### Recommendations (Prioritized)

1. **[Recommendation]** — Tied to Theme X. Confidence: High.
2. **[Recommendation]** — Tied to Theme Y. Confidence: Medium.
3. **[Recommendation]** — Tied to Theme Z. Confidence: Low.

---

### Limitations & Open Questions
- [What we didn't learn]
- [Sample biases — e.g., only interviewed power users]
- [Areas needing further research]
- [Assumptions that remain unvalidated]
```

### Quality Checklist

Before finalizing, verify:

- [ ] Themes are supported by evidence from 3+ participants
- [ ] Quotes are verbatim and attributed to participant IDs
- [ ] Insights explain "why" not just "what"
- [ ] Recommendations are specific and actionable
- [ ] Participant identities are protected (no PII)
- [ ] Limitations and biases are acknowledged
- [ ] Signal strength is assessed (frequency, intensity, workarounds, WTP)
- [ ] Surprise findings are highlighted — if nothing surprised you, you may be filtering

Save the summary as a markdown document in the user's workspace.

---

### Further Reading

- [User Interviews: The Ultimate Guide to Research Interviews](https://www.productcompass.pm/p/interviewing-customers-the-ultimate)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (video course)
