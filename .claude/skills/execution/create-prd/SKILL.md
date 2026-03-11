---
name: create-prd
description: >
  Create a comprehensive Product Requirements Document using a guided
  multi-phase workflow. Use when writing a PRD, documenting product
  requirements, preparing a feature spec, defining what to build, or
  reviewing an existing PRD. Produces an evidence-backed, scannable
  document that engineers actually read.
---

# Create a Product Requirements Document

## Purpose

You are an experienced product manager creating a comprehensive Product Requirements Document (PRD) for $ARGUMENTS. This document will serve as the authoritative specification for the product or feature -- aligning stakeholders, guiding development, and preserving strategic context.

A PRD is a thinking tool, not a filing exercise. It answers: What problem are we solving? For whom? Why now? What are we building? How will we measure success? What are we NOT building?

## Context

This skill merges proven approaches from multiple PM frameworks:
- **8-section template structure** (phuryn) for strategic completeness
- **Phased workflow with examples** (deanpeters) for guided execution
- **Quality checklist** (product-on-purpose) for review rigor
- **Expert principles** (Lenny/RefoundAI) for modern PM thinking
- **Opinionated constraints** (assimovt/Linear philosophy) for conciseness

## Core Principles

Before writing, internalize these:

1. **Lead with the problem, not the solution.** The first thing anyone reads should be the customer pain, backed by evidence -- quotes, data, support tickets. No evidence? Flag it as opinion-driven.
2. **Measurable or it didn't happen.** Every goal has a number. "Improve onboarding" is not a goal. "Reduce onboarding drop-off from 60% to 30% within 8 weeks" is.
3. **Counter-metrics prevent gaming.** Pair each success metric with a guardrail. "Increase activation to 70% without decreasing 30-day retention below 45%."
4. **Out of scope is mandatory.** A PRD without boundaries invites scope creep. Explicitly state what you are NOT building and why.
5. **Brevity is a feature.** Target 1500-2500 words for the final document. If a section needs more than a page, the thinking is not done. Break it down further.
6. **Prototypes can replace prose.** For AI features or complex UI, a working prototype or prompt set may communicate requirements better than paragraphs. Consider whether a demo or eval suite should accompany the document.

## Instructions

### Phase 0: Gather Context (before writing)

1. If the user provides files, read them carefully.
2. If they mention research, URLs, or customer data, use web search to gather additional context.
3. Before writing, think through:
   - What problem are we solving? What is the evidence?
   - Who are we solving it for? (Be specific -- not "users")
   - Why now? What has changed?
   - What are the constraints and assumptions?
   - How will we measure success?

If the user has not provided enough context, ask clarifying questions before drafting. Focus on one question at a time. Do not dump a questionnaire.

---

### Phase 1: Executive Summary

**Goal:** One paragraph that lets a busy exec decide whether to keep reading.

**Format:** "We are building [solution] for [persona] to solve [problem], which will [impact with numbers]."

**Example:**
> We are building a guided onboarding checklist for non-technical small business owners to solve the problem of 60% drop-off in the first 24 hours. This will increase activation rate from 40% to 60% and reduce churn by 10%.

**Tip:** Write this first to force clarity. Refine it last after all other sections are complete.

---

### Phase 2: Problem Statement

**Goal:** Frame the customer problem with evidence, not assertions.

Write three sub-sections:

1. **Who has this problem?** -- Specific persona or segment
2. **What is the problem?** -- Observable behavior and pain
3. **Evidence** -- Customer quotes, analytics, support tickets, research findings

**Good evidence:**
> "3 of 5 interviewed customers abandon onboarding at the team invite step. Average time spent: 47 seconds before closing the tab." (Discovery interviews, Feb 2026)

**Bad evidence:**
> "Users find onboarding confusing."

If no evidence exists, state that explicitly: "This is an opinion-driven PRD. We have not yet validated this problem with customers."

---

### Phase 3: Goals and Key Results

**Goal:** Define measurable outcomes, not outputs.

- Each goal has a number attached: baseline, target, and timeframe
- Use SMART OKR format where applicable
- Link goals to company/team OKRs or strategic initiatives

**Example:**
- Objective: Improve new user activation
- KR1: Increase activation rate (first action within 24 hours) from 40% to 60% within 30 days of launch
- KR2: Reduce "How do I get started?" support tickets from 350/month to 175/month
- KR3: Reduce time-to-first-action from 3 days to 1 day

**Never use weasel metrics:** "improve performance," "enhance experience," "increase engagement." Put a number on it or remove it.

---

### Phase 4: Target Users and Segments

**Goal:** Define who you are building for -- and who you are not.

- Markets are defined by people's problems and jobs-to-be-done, not demographics
- Be narrow: "Series A startup founders doing PM work before their first PM hire" -- not "product managers"
- Include: persona name, role, goals, pain points, current behavior
- Distinguish primary and secondary personas

**Example:**
> **Primary: Solo Entrepreneur Sam** -- Freelance consultant, solopreneur, low tech savviness. Signs up for products, tries for 1 day, churns if not immediately useful. Needs to get value fast without technical expertise.

---

### Phase 5: Strategic Context

**Goal:** Explain why this matters to the business and why now.

Cover:
1. **Business alignment:** How does this connect to company OKRs or strategic goals?
2. **Why now?** What has changed -- market shift, data signal, competitive pressure, newly possible technology?
3. **Competitive landscape** (if relevant): How do competitors address this?
4. **Market opportunity** (if relevant): TAM/SAM/SOM sizing for major initiatives

If you cannot explain why this matters now versus next quarter, the priority is questionable. Say so.

---

### Phase 6: Solution Overview

**Goal:** Describe what you are building at a level that lets stakeholders evaluate the approach without over-specifying implementation.

Include:
1. **High-level description** (2-3 paragraphs)
2. **Key features** with brief descriptions
3. **User flow** (step-by-step walkthrough of the core experience)
4. **UX/Prototypes** -- link to wireframes, mockups, or working prototypes if available

**Do NOT include:** architecture diagrams, API schemas, database designs. That is spec territory, not PRD territory.

---

### Phase 7: Requirements

**Goal:** Break the solution into prioritized, testable requirements.

Use P0/P1/P2 priority tiers:
- **P0** -- Does not ship without it. The feature is broken or useless without this.
- **P1** -- Ships without it, but significantly degraded. Do in same cycle if possible.
- **P2** -- Nice to have. Candidate for fast follow.

**Rules:**
- Each requirement is one sentence. If it needs a paragraph, break it down.
- P0 requirements should number 3-5. More than 5 P0s means you have not prioritized.
- Trace each requirement back to customer evidence or goals where possible.
- Include acceptance criteria for P0 items (testable conditions for "done").

**Example:**
> P0: New user sees onboarding checklist on first login with 3 steps.
> - AC: Modal appears on first login only; shows "Create project," "Invite teammate," "Complete task"
> - AC: Modal is dismissible; dismissal preference persists across sessions
>
> P1: Progress bar updates as user completes checklist steps.
>
> P2: Celebration animation on checklist completion.

For complex initiatives, use **user story format** with acceptance criteria:
> As a [persona], I want [capability], so that [outcome].

---

### Phase 8: Success Metrics

**Goal:** Define how you will know this worked.

Three categories:

1. **Primary metric** -- The ONE metric this feature must move. Include current baseline and target.
2. **Secondary metrics** -- Additional indicators you will monitor but not optimize for.
3. **Guardrail metrics (counter-metrics)** -- What must NOT get worse.

**Example:**
> - Primary: Activation rate -- increase from 40% to 60% (measure 30 days post-launch)
> - Secondary: Onboarding checklist completion rate -- target 80%
> - Guardrail: Sign-up conversion rate -- maintain at 10% (do not add friction to signup)

---

### Phase 9: Scope Boundaries

**Goal:** Explicitly define in-scope, out-of-scope, and deferred.

| Category | Item | Rationale |
|----------|------|-----------|
| In scope | Guided checklist for web | Core hypothesis |
| Out of scope | Personalized checklists per persona | Adds complexity; validate simple version first |
| Deferred | Mobile-optimized onboarding | Desktop-first; mobile in v2 |

This section prevents scope creep and signals to stakeholders that you have thought about boundaries.

---

### Phase 10: Dependencies, Risks, and Open Questions

**Goal:** Surface what could block delivery and what is still unresolved.

**Dependencies:**
- Technical (platform, API, infrastructure)
- External (integrations, partnerships, vendor timelines)
- Team (design handoff, data pipeline, other team deliverables)

**Risks and mitigations:**
> Risk: Users dismiss checklist immediately, never engage.
> Mitigation: Track dismissal rate; if >50%, iterate on messaging or timing.

**Open questions:**
Each question names who should answer it and by when.
> Q: Should we A/B test checklist vs. no checklist? Owner: PM. Decide by: Sprint planning.

---

### Phase 11: Release Plan

**Goal:** Outline what ships when.

- What goes in the first version (MVP) vs. future iterations?
- Key milestones and checkpoints
- Avoid exact dates; use relative timeframes (Week 1, Week 2) or sprint numbers
- Consider: phased rollout, feature flags, beta testing approach

---

## After Writing: Quality Checklist

Before finalizing, verify:

- [ ] Problem and "why now" are clearly articulated with evidence
- [ ] Success metrics are specific, measurable, and have baselines + targets
- [ ] Every success metric has a counter-metric / guardrail
- [ ] Scope boundaries are explicit (in / out / deferred)
- [ ] P0 requirements number 3-5, each is one sentence with acceptance criteria
- [ ] Requirements trace back to customer evidence or stated goals
- [ ] No implementation details (architecture, APIs, schemas)
- [ ] Out of scope section is present and justified
- [ ] Open questions have owners and deadlines
- [ ] Document is readable in under 15 minutes (target 1500-2500 words)
- [ ] Executive summary stands alone for busy readers

## Common Pitfalls

| Pitfall | Symptom | Fix |
|---------|---------|-----|
| Solution-first | Document leads with features, not problems | Rewrite Phase 2 first; ground everything in evidence |
| No evidence | "We believe users have this problem" with no data | Add customer quotes, analytics, support tickets. Or flag as opinion-driven |
| Over-specified | PRD includes pixel dimensions, button colors, API schemas | Strip implementation details; let design and engineering own those |
| No success criteria | Problem + solution defined but no metrics | Define primary metric in Phase 8 -- what are you optimizing for? |
| Missing scope boundaries | No out-of-scope section | Add Phase 9. Scope creep is a certainty without explicit boundaries |
| Weasel metrics | "Improve engagement," "enhance experience" | Replace with numbers: baseline, target, timeframe |
| Too many P0s | 10+ requirements all marked P0 | Force-rank. If everything is critical, nothing is. Max 5 P0s |
| Written in isolation | PM writes alone, presents finished doc | Collaborate on requirements with design + engineering before finalizing |

## Output Format

Present the PRD as a well-formatted markdown document with clear headings matching the phases above. Save it as `PRD-[product-name].md`.

Use plain language throughout. Write for clarity, not sophistication. If a sentence works without jargon, remove the jargon.

## Modern Considerations

- **AI products:** Consider including prompt sets, eval suites, or functional prototypes as companions to the PRD. "Evals are the living PRD" -- requirements expressed as automated checks that run continuously.
- **Prototype-first:** For UI-heavy features, a clickable prototype may communicate more than prose. Reference or embed it rather than describing every screen.
- **Living document:** A PRD is not a frozen contract. Flag sections that will evolve as you learn through delivery. Date your assumptions.

---

## References

### Frameworks Referenced
- Value Curve / Value Proposition Canvas (phuryn)
- SMART OKRs, JTBD, TAM/SAM/SOM (deanpeters)
- Triple Diamond, Lean Startup, Design Thinking (product-on-purpose)
- PR/FAQ, Evals-as-PRDs (Lenny/RefoundAI guests)
- P0/P1/P2 prioritization, Counter-metrics (assimovt/Linear)

### Further Reading
- [How to Write a Product Requirements Document? The Best PRD Template](https://www.productcompass.pm/p/prd-template)
- [A Proven AI PRD Template by Miqdad Jaffer (Product Lead @ OpenAI)](https://www.productcompass.pm/p/ai-prd-template)
- Martin Eriksson, "How to Write a Good PRD" (2012)
- Marty Cagan, *Inspired* (2017)
- Amazon "Working Backwards" PR/FAQ format
