# A Day in the Life: PM with the PM Operating System

**The honest version.**

---

## What This System Actually Does

It removes the blank page from every step in your workflow.

It doesn't replace your judgment, your relationships, or your knowledge of the politics. It means you spend 20 minutes editing a first draft instead of 2 hours writing one from scratch. The time you get back goes into the parts of the job that are actually hard: deciding what NOT to build, navigating stakeholders, and making calls with incomplete information.

---

## Monday Morning

You open Slack. Three things are waiting:

1. Your VP wants a recommendation on 55+ subscriber churn by Friday
2. Engineering pinged about scope creep on last sprint's carryover
3. A customer success manager forwarded an angry enterprise account email

None of these are "run a skill" moments. They're PM moments. But the system helps at specific points.

### The VP Ask

You already have a hypothesis from last week's support ticket patterns. You run:

```
/discover streaming churn in 55+ demographic
```

This takes 10 minutes. It doesn't give you the answer -- it organizes your thinking. You get back a structured discovery plan: hypotheses ranked by risk, assumptions to test, and 3 cheap experiments you could run this week. You pull the two that are actually feasible given your timeline and share them in the Slack thread.

Without the system: you'd spend 30 minutes staring at a doc trying to structure your thinking, or worse, you'd jump straight to a solution.

### The Scope Creep

This is a conversation, not a command. You talk to the engineer. But afterward, when you need to recut scope for the stakeholder update:

```
/write-prd [paste the revised scope and context]
```

You get a first draft in minutes. You spend 15 minutes editing it -- removing the things Claude doesn't know (the reason the payments team can't support the original scope is political, not technical) and sharpening the trade-offs. You send it out.

Without the system: 45 minutes to an hour writing from scratch, plus the mental overhead of formatting.

### The Angry Customer

You read the email. This is a relationship problem, not a skills problem. You reply yourself. No AI involved.

---

## Wednesday — Customer Interviews

You had two customer calls today. They were already on your calendar. The system didn't schedule them or make them happen.

After each call, you paste the transcript:

```
/interview summarize
```

5 minutes each. You get back structured summaries: Jobs-to-be-Done, pain points, workarounds, verbatim quotes. After 3 interviews this week, you notice a pattern you might have missed skimming your handwritten notes: all three users mentioned the same workaround (using their phone instead of the remote to switch inputs).

Without the system: you'd have rough notes from the calls, maybe review them Thursday night before the Friday deadline. The pattern might surface, might not.

---

## Thursday — Writing the PRD

You have the interview evidence, the data pull from analytics, and the competitive context (you already know YouTube TV's remote story is simpler). Time to write.

```
/write-prd simplified input switching for 55+ subscribers
```

Claude generates an 8-section first draft. Here's what you do with it:

**Keep:** The structure, the metrics framework, the scope boundary format. This is scaffolding you'd waste time rebuilding every time.

**Edit heavily:** The problem statement (Claude's version is accurate but doesn't land the way your VP thinks about this problem). The success metrics (Claude suggested 15% churn reduction in 90 days -- you know 120 is more realistic given the firmware release cycle). The dependencies section (Claude doesn't know the device team is a bottleneck).

**Add:** The political context. Why this matters *now* (contract renewals are Q3). Why the last attempt failed (different team, different approach, but stakeholders will remember).

**Delete:** Two P1 requirements that are technically correct but will scare engineering off before you get alignment on the P0s.

Total time: 20 minutes editing. Not 2 hours writing.

### Then You Stress-Test

You ask the subagents to review. Today they give generic feedback. Once tailored, they'd know:

- The device team ships firmware quarterly, not on your sprint cycle
- 55+ is the highest-ARPU segment, so even small churn improvements are high-value
- The last remote UX initiative died because no one looped in the hardware team early enough

That context turns "have you considered dependencies?" into "flag the Q3 firmware lock date -- you have 6 weeks to get on the manifest."

---

## Friday — Sprint Planning Prep

You run:

```
/sprint
```

You get a starting point: capacity estimate, story selection, dependency map, risks. You adjust it based on what you know:

- Sarah is the only engineer who understands the firmware layer and she's out next week
- The QA team is already overloaded from the last release
- Your designer has bandwidth but needs the research summary first

None of that is in the system. You add it. The system gave you the structure so you didn't have to build it from scratch.

---

## What the System Does and Doesn't Do

### It does:

- **Remove the blank page.** Every PRD, sprint plan, interview script, and discovery plan starts from a structured first draft instead of nothing.
- **Catch things you'd miss.** The pre-mortem surfaces risks you weren't thinking about. The interview summary catches patterns across calls. The subagents ask the question you forgot.
- **Save 5-8 hours a week.** Spread across a dozen small moments, not one big ceremony.
- **Compound over time.** Retro lessons feed into the next sprint. Competitive scans keep strategy current. Feedback analysis surfaces the next discovery opportunity.

### It doesn't:

- **Replace your judgment.** It generates options. You decide.
- **Know your organization.** The politics, the relationships, the history of why things are the way they are -- that's yours.
- **Do the hard parts.** Having the difficult conversation with your VP. Saying no to the sales team. Making the call with 60% confidence. That's the job.
- **Work without you.** Every output needs editing. If you ship Claude's first draft without review, you'll get caught. It's a starting point, not a finished product.

### The honest pitch:

> "This doesn't make you a better PM. It makes you a faster PM at the mechanical parts -- first drafts, synthesis, prioritization math, structure. The time you save goes back into the parts that actually differentiate great PMs: judgment, relationships, and politics."

---

## The Compound Effect (Week 2+)

The system gets more valuable over time, but not because it "learns." It's because *your artifacts accumulate:*

| Ritual | What accumulates |
|--------|-----------------|
| Monday: `/weekly-feedback` | Patterns in customer sentiment you'd otherwise miss |
| Sprint start: `/sprint-kickoff` | Consistent sprint structure across cycles |
| Sprint end: `/retro` | Lessons that inform the next sprint plan |
| Monthly: `/competitive-scan` | Running competitive awareness without dedicated research time |
| Quarterly: `/quarterly-review` | Strategy check that references the last quarter's actual results |

Each cycle's output becomes the next cycle's input. That's the compounding loop -- and it's not magic, it's just good PM discipline enforced by automation instead of willpower.

---

## For Teams: The Fork Model

When a team adopts this:

1. **Clone the repo.** All 152 skills available immediately.
2. **Fork it.** Tailor the 7 subagents to your product, customers, and competitive landscape.
3. **Start with Tier 1.** The 8 daily-driver skills. Run `/write-prd` on a real problem.
4. **Accumulate context.** Every retro, every competitive scan, every feedback summary makes the fork smarter -- not through AI magic, but through organizational memory that doesn't live in one PM's head.

The fork is the team's product intelligence layer. When a PM leaves, the context stays.
