---
name: user-story-mapping
description: "Create a user story map that visualizes the user journey as activities, steps, and tasks organized by priority and release slices. Use when planning a workflow-based backlog, defining MVP scope, aligning teams on the user journey, or identifying gaps in the user experience."
---
# User Story Mapping

Visualize the user journey by creating a hierarchical map that breaks down high-level activities into steps and tasks, organized left-to-right as a narrative flow and top-to-bottom by priority. Use this to build shared understanding across product, design, and engineering, prioritize features based on user workflows, and plan releases along the user journey.

## When to Use

- Kicking off a new product or major feature
- Defining MVP scope based on user workflows (not feature lists)
- Aligning stakeholders on how users accomplish their goals
- Prioritizing backlog items within the context of a user journey
- Identifying gaps, pain points, or opportunities in the user experience
- Planning releases that deliver complete (if minimal) user journeys
- Onboarding new team members to the product vision
- Triggers: story map, user story map, user journey, MVP planning, release planning

## The Jeff Patton Story Mapping Framework

### Map Structure

**Horizontal axis (left-to-right):** User journey over time
- **Backbone (Activities):** High-level activities the user performs (3-5)
- **Steps:** Specific actions within each activity (3-5 per activity)
- **Tasks:** Detailed work required to complete each step (5-7 per step)

**Vertical axis (top-to-bottom):** Priority and releases
- **Top rows:** Essential tasks (MVP / Release 1)
- **Middle rows:** Important but not critical (Release 2)
- **Bottom rows:** Nice-to-have (Future releases)

```
Segment -> Persona -> Narrative (User's goal)
---------------------------------------------
[Activity 1]   [Activity 2]   [Activity 3]   [Activity 4]
     |              |              |              |
  [Step 1.1]     [Step 2.1]     [Step 3.1]     [Step 4.1]
  [Step 1.2]     [Step 2.2]     [Step 3.2]     [Step 4.2]
     |              |              |              |
  [Task 1.1.1]  [Task 2.1.1]  [Task 3.1.1]  [Task 4.1.1]  <- Release 1 (MVP)
  --------------- RELEASE LINE --------------------------------
  [Task 1.1.2]  [Task 2.1.2]  [Task 3.1.2]  [Task 4.1.2]  <- Release 2
  --------------- RELEASE LINE --------------------------------
  [Task 1.1.3]  [Task 2.1.3]  [Task 3.1.3]  [Task 4.1.3]  <- Future
```

## Step-by-Step Process

### Step 1: Define the Context

**Segment:** Who are you building for?
- Be specific: "enterprise IT admins" or "freelance designers," not just "users"

**Persona:** Describe the persona within this segment:
- Demographics, behaviors, pains, goals
- Example: "Sarah, 35-year-old freelance graphic designer, manages 5-10 client projects at once, struggles with invoicing and payment tracking"

**Narrative:** What is the user trying to accomplish? Frame as one sentence:
- "Complete a client project from kickoff to final payment"
- Outcome-focused, not product-focused ("deliver a client project" not "use the product")

### Step 2: Identify Activities (Backbone)

List 3-5 high-level activities the persona engages in to fulfill the narrative. These form the backbone.

```
1. Negotiate project scope and pricing
2. Execute design work
3. Deliver final assets to client
4. Send invoice and receive payment
```

**Quality checks:**
- Sequential: activities happen in order (left-to-right)
- User actions: describe what the user *does*, not what the product *provides*
- 3-5 activities: too few = oversimplified, too many = overwhelming

### Step 3: Break Activities into Steps

For each activity, list 3-5 steps that detail how the activity is carried out.

```
Activity 1: Negotiate project scope and pricing
  - Step 1: Review client brief
  - Step 2: Draft project proposal
  - Step 3: Negotiate timeline and budget
  - Step 4: Sign contract
```

**Quality checks:**
- Actionable: each step is something the user does
- Observable: you could watch someone perform this step
- Logical sequence within each activity

### Step 4: Break Steps into Tasks

For each step, list 5-7 tasks that must be completed.

```
Activity 1, Step 1: Review client brief
  - Task 1: Read client brief document
  - Task 2: Identify key deliverables
  - Task 3: Note budget constraints
  - Task 4: Clarify timeline expectations
  - Task 5: List open questions for client
```

### Step 5: Prioritize Vertically

Arrange tasks top-to-bottom by priority. Draw horizontal "release lines":

- **Top rows (MVP / Release 1):** Must-have tasks that deliver a complete but minimal journey
- **Middle rows (Release 2):** Important improvements and additional capabilities
- **Bottom rows (Future):** Nice-to-have features and enhancements

The key insight: MVP should be a thin horizontal slice across ALL activities (a walking skeleton), not a deep vertical slice of one activity.

### Step 6: Identify Gaps and Opportunities

Review the map and ask:
- Are there missing steps or tasks?
- Are there pain points we're not addressing?
- Are there opportunities to delight users?
- Do all activities flow logically?
- Where are the biggest risks or unknowns?

### Step 7: Convert to User Stories

Tasks from the map become user stories (see `user-stories` skill):
- Each task maps to one or more stories
- Stories inherit context from their parent activity and step
- Prioritization from the map determines backlog order

## Presenting the Map

Keep it to one page or one screen for the overview. Use tools like Miro, FigJam, or a physical wall with sticky notes. The visual format is the point -- it creates shared understanding that a flat backlog cannot.

| Horizon | Activity 1 | Activity 2 | Activity 3 | Activity 4 |
|---------|-----------|-----------|-----------|-----------|
| MVP | [Task] | [Task] | [Task] | [Task] |
| Release 2 | [Task] | [Task] | [Task] | [Task] |
| Future | [Task] | [Task] | [Task] | [Task] |

## Common Pitfalls

- **Activities are features, not user behaviors** -- "Use the dashboard" should be "Monitor project progress." Map the user, not the product.
- **Too many activities** -- 10+ activities means you're mixing activities with steps. Consolidate to 3-5.
- **Tasks too vague** -- "Do the thing" can't be prioritized or estimated. Be specific.
- **Ignoring vertical prioritization** -- All tasks at the same level means no MVP definition. Force hard choices. Draw release lines.
- **Mapping in isolation** -- PM creates the map alone. Run a collaborative workshop with product, design, and engineering.
- **Deep vertical slice for MVP** -- Building one activity completely while ignoring others. MVP should be a thin horizontal slice across all activities.

---

### References

**Frameworks:**
- Jeff Patton, *User Story Mapping* (2014) -- Origin of the story mapping technique
- Teresa Torres, *Continuous Discovery Habits* (2021) -- Opportunity solution trees (complementary)

**Related Skills:**
- `user-stories` -- Tasks from the map become user stories with acceptance criteria
- `job-stories` -- Alternative story format focused on situations and motivations
- `outcome-roadmap` -- Story maps inform roadmap outcomes and release planning
- `prioritize-features` -- Prioritization within the map's vertical axis
