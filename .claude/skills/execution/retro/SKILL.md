---
name: retro
description: "Facilitate a structured sprint retrospective or post-mortem -- what went well, what didn't, and prioritized action items with owners and deadlines. Use when running a retrospective, reflecting on a sprint or project, creating action items from team feedback, running a post-mortem after an incident, or learning how to run effective retros."
---

## Sprint Retrospective & Post-Mortem Facilitator

Run a structured retrospective that surfaces insights, drives genuine learning, and produces actionable improvements.

### When to Use

- At the end of every sprint (for agile teams)
- After completing a significant project or milestone
- Following a major incident or outage (post-mortem)
- When team dynamics feel off and need addressing
- At regular intervals (monthly, quarterly) even without specific triggers
- When onboarding new team members to establish improvement culture

### Core Principles

- **Call them retrospectives, not post-mortems** -- reframing helps normalize failure and focuses the team on learning rather than blame (Eeke de Milliano)
- **Make it blameless** -- the goal is to understand what happened and why, not to assign blame. Create psychological safety so people share honestly
- **Pre-mortems need kill criteria** -- identify early signals that a project is failing and pre-commit to specific actions if those signals are met (Annie Duke)
- **Reframe failure as growth** -- "What did you learn?" is always the first question when something goes wrong (Carole Robin)
- **Institutionalize learning reviews** -- hold weekly "Impact and Learnings" reviews focused on insights rather than status updates; socialize learnings across the company (Ben Williams)
- **Grade OKRs for learning, not performance** -- the value of grading OKRs lies in understanding why a goal was or wasn't hit, not the number itself (Christina Wodtke)

### Context

You are facilitating a retrospective for **$ARGUMENTS**.

If the user provides files (sprint data, velocity charts, team feedback, previous retro notes, or incident timelines), read them first.

### Instructions

1. **Set the Context**
   Define what period, project, or incident this retrospective covers. Identify who attended and any significant events. Ask whether this is after a failure, a success, or a routine checkpoint. Frame the exercise as learning-focused.

2. **Choose a retro format** based on context (or let the user pick):

   **Format A -- Start / Stop / Continue**:
   - **Start**: What should we begin doing?
   - **Stop**: What should we stop doing?
   - **Continue**: What's working well that we should keep?

   **Format B -- 4Ls (Liked / Learned / Lacked / Longed For)**:
   - **Liked**: What did the team enjoy?
   - **Learned**: What new knowledge was gained?
   - **Lacked**: What was missing?
   - **Longed For**: What do we wish we had?

   **Format C -- Sailboat**:
   - **Wind (propels us)**: What's driving us forward?
   - **Anchor (holds us back)**: What's slowing us down?
   - **Rocks (risks)**: What dangers lie ahead?
   - **Island (goal)**: Where are we trying to get to?

   **Format D -- Mad / Sad / Glad** (emotion-focused):
   - Best when team dynamics need addressing or emotions are running high

3. **Gather and Synthesize Input**
   If the user provides raw feedback (sticky notes, survey responses, Slack messages):
   - Group similar items into themes
   - Identify the most frequently mentioned topics
   - Note sentiment patterns (frustration, energy, confusion)
   - Ensure quiet voices are represented -- they often have important insights

4. **Analyze Sprint/Project Performance**:
   - Sprint goal: achieved or not?
   - Velocity vs. commitment (over-committed? under-committed?)
   - Blockers encountered and how they were resolved
   - Collaboration patterns (what worked, what didn't)
   - For incidents: timeline, root cause, detection time, resolution time

5. **Generate Prioritized Action Items**:

   | Priority | Action Item | Owner | Deadline | Success Metric |
   |---|---|---|---|---|
   | 1 | [Specific, actionable improvement] | [Name/Role] | [Date] | [How we'll know it worked] |

   - Limit to 2-3 action items (more won't get done)
   - Each must be specific, assignable, and measurable
   - Avoid vague improvements like "communicate better"
   - Reference previous retro actions if available -- were they completed?

6. **Review Previous Actions**
   Check the status of action items from the last retrospective. Celebrate completions and discuss blockers for incomplete items. This builds accountability and ensures follow-through.

7. **Create the Retro Summary**:
   ```
   ## Sprint [X] Retrospective -- [Date]

   ### Context
   - Period/Project: [What this covers]
   - Attendees: [Who participated]

   ### Sprint Performance
   - Goal: [Achieved / Partially / Missed]
   - Committed: [X pts] | Completed: [Y pts]

   ### Key Themes
   1. [Theme] -- [summary]

   ### Action Items
   1. [Action] -- [Owner] -- [By date] -- [Success metric]

   ### Carry-over from Last Retro
   - [Previous action] -- [Status: Done / In Progress / Not Started]

   ### Key Learnings
   - [What we learned that we didn't know before]
   - [Signals we saw early that we ignored or missed]
   - [Systemic issues to address]
   ```

### Diagnostic Questions

Use these to surface deeper insights:
- "What did we learn that we didn't know before starting this project?"
- "If we had to do this again with the same information we had at the start, what would we do differently?"
- "What signals did we see early that we ignored or missed?"
- "What systemic issues contributed to this outcome that we should address?"
- "What kill criteria should we set for similar projects in the future?"
- "How will we ensure these learnings actually influence future decisions?"

### Common Mistakes to Flag

- **Blame-focused framing** -- turning the exercise into finding fault rather than understanding systems
- **No follow-through** -- running retrospectives but never acting on the learnings
- **Only reviewing failures** -- missing the opportunity to learn from successes
- **One-time events** -- running retrospectives only for big failures instead of making them a regular practice
- **Too many action items** -- committing to 10 improvements guarantees none get done

### Quality Checklist

Before finalizing, verify:
- [ ] All attendees had opportunity to contribute
- [ ] Both positives and improvements are captured
- [ ] Action items have owners, due dates, and success metrics
- [ ] Previous retrospective actions are reviewed
- [ ] Document is useful to someone who wasn't in the room
- [ ] Tone is constructive -- the goal is improvement, not blame

Save as markdown. Keep the tone constructive.
