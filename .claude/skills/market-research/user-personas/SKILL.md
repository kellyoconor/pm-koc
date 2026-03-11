---
name: user-personas
description: "Create refined user personas from research data -- full personas with JTBD, pains, gains, behavioral insights, and confidence levels. Supports both proto-personas (hypothesis-driven, early-stage) and validated personas (research-backed). Use when building personas from survey data, creating user profiles from research, segmenting users for product decisions, or aligning teams on target users."
---

# User Personas

## Purpose

Create detailed, actionable user personas from research data that capture the true diversity of your user base. This skill generates research-backed personas with jobs-to-be-done, pain points, desired outcomes, and unexpected behavioral insights to guide product decisions.

Supports two modes:
- **Proto-persona** (early-stage): Hypothesis-driven, created quickly from available knowledge. Mark assumptions with [ASSUMPTION -- VALIDATE].
- **Validated persona** (research-backed): Created from extensive user research with high confidence.

## When to Use

- Early-stage product development (proto-personas to align teams quickly)
- After user research to synthesize findings into validated personas
- When teams disagree on priorities and need behavior-grounded framing
- Before drafting PRDs, journey maps, or GTM artifacts
- When kicking off a new feature or pivot
- When segmenting users for product decisions

## When NOT to Use

- As a substitute for user research (personas inform research; research validates them)
- For mature products with already-validated personas (update instead of recreating)

## Instructions

You are an experienced product researcher specializing in persona development and user research synthesis.

### Input

Your task is to create personas for **$ARGUMENTS**.

If the user provides CSV, Excel, survey responses, interview transcripts, or other research data files, read and analyze them directly. Extract key patterns, demographics, motivations, and behaviors.

### Analysis Steps

1. **Data Collection**: Read and review all provided research data and documents
2. **Pattern Recognition**: Identify recurring characteristics, goals, pain points, and behaviors across users
3. **Segmentation**: Group similar users into distinct personas based on shared motivations and jobs-to-be-done
4. **Enrichment**: For each persona, synthesize data into a coherent profile
5. **Validation**: Cross-reference insights to ensure personas are grounded in actual research findings. Where data is thin, mark as [ASSUMPTION -- VALIDATE].

### Output Structure

For each persona (typically 2-3), provide:

**1. Identity**
- **Name**: Alliterative, memorable name (e.g., "Manager Mike," "Startup Sarah") -- makes it easier for teams to reference
- **Bio & Demographics**: Age range, role/title, company size (if B2B), career status, key characteristics
- **Online presence and behaviors**: How they engage with tools, communities, information
- Context-relevant details only -- demographics that don't influence product decisions are noise

**2. Voice (Quotes)**
- 2-3 real or representative quotes revealing mindset, frustrations, and attitudes
- Use real quotes from interviews/support tickets when available
- Weak: "I need better tools." Strong: "I'm drowning in manual work and can't focus on strategy."
- If no real quotes exist, mark as [PLACEHOLDER -- NEEDS RESEARCH]

**3. Primary Job-to-be-Done**
- The core outcome the persona is trying to achieve
- Context and frequency of the job
- Observable behaviors: not "get promoted" but "deliver projects ahead of schedule"

**4. Top 3 Pain Points**
- Specific challenges or obstacles preventing job completion
- Impact and severity of each pain
- Specific, not vague: "Spends 3 hours/week manually copying data between tools" not "frustrated with tools"

**5. Top 3 Desired Gains / Goals**
- Benefits, outcomes, or solutions the persona seeks
- How they measure success
- Include both short-term tactical and long-term aspirational goals

**6. One Unexpected Insight**
- A counterintuitive behavioral pattern or motivation derived from the data
- Why this matters for product decisions

**7. Attitudes & Influences**
- **Decision-Making Authority**: Can they buy? Who approves above their level?
- **Decision Influencers**: Peers, analyst reports, communities, social channels
- **Beliefs & Attitudes**: Skepticism, values, biases that affect adoption

**8. Product Fit Assessment**
- How the product addresses (or could address) this persona's needs
- Potential friction points or unmet needs

**9. Evidence & Confidence**
- **Confidence Level**: High / Medium / Low with rationale
- **Validated**: What is supported by research
- **Assumed**: What needs validation (tag [ASSUMPTION -- VALIDATE])
- **Open Questions**: What we still don't know
- **Research Plan**: Next steps to fill gaps

## Best Practices

- Ground all insights in actual data; avoid fabrication
- Use direct quotes from research when available
- Identify behavioral patterns, not just demographic categories
- Make personas distinct and non-overlapping where possible
- Flag any data gaps or areas requiring additional research
- Start with 1-2 personas (primary + secondary). Add more as you validate and expand.
- One persona per journey map or artifact. Mixing them creates confusion.

## Common Pitfalls

- **Demographics without behavior**: Age and location don't explain product usage. Add behavioral context.
- **Treating proto-personas as fact**: They're hypotheses. Tag assumptions and plan interviews to test.
- **Creating too many personas**: 10 personas = analysis paralysis. Start with 2-3.
- **Fabricating quotes**: Fake personas lead to fake empathy. Use real quotes or mark placeholders.
- **Never validating**: A proto-persona created 6 months ago and never updated is designing for a hypothesis that may be wrong.

---

### Further Reading

- [User Interviews: The Ultimate Guide to Research Interviews](https://www.productcompass.pm/p/interviewing-customers-the-ultimate)
- [Market Research: Advanced Techniques](https://www.productcompass.pm/p/market-research-advanced-techniques)
- [Jobs-to-be-Done Masterclass with Tony Ulwick and Sabeen Sattar](https://www.productcompass.pm/p/jobs-to-be-done-masterclass-with)

### References

- Alan Cooper, *The Inmates Are Running the Asylum* (1998) -- origin of persona concept
- Jeff Gothelf, *Lean UX* (2013) -- proto-personas as hypothesis-driven research tools
- Indi Young, *Mental Models* (2008) -- behavior-driven persona development
