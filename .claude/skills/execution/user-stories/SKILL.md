---
name: user-stories
description: "Create user stories following the 3 C's (Card, Conversation, Confirmation), INVEST criteria, and Gherkin acceptance criteria. Supports Mike Cohn format and story splitting patterns. Use when writing user stories, breaking down features into backlog items, defining acceptance criteria, or communicating requirements to engineering."
---
# User Stories

Create user stories that translate user needs into actionable development work. Combines Mike Cohn's story format with Gherkin acceptance criteria, the 3 C's framework, INVEST validation, and systematic splitting patterns for stories that are too large.

## When to Use

- Writing user stories from PRDs, feature descriptions, or discovery insights
- Breaking down features into sprint-sized backlog items
- Defining testable acceptance criteria for engineering
- Communicating requirements to stakeholders in accessible terms
- Splitting oversized stories into independently deliverable increments
- Triggers: user story, user stories, acceptance criteria, story splitting, backlog items

## Story Format

### Use Case (Mike Cohn format + 3 C's)

**Card** -- the promise of a conversation:

```
Title: [Brief, value-focused title]

As a [specific persona/role],
I want to [action the user takes],
so that [desired outcome -- why this matters].
```

**Conversation** -- detailed discussion of intent, context, design references, and edge cases.

**Confirmation** -- acceptance criteria that define "done."

### Acceptance Criteria (Gherkin format)

```
Scenario: [Brief description of the scenario]
  Given [initial context or preconditions]
  And [additional preconditions as needed]
  When [event that triggers the action -- aligns with "I want to"]
  Then [expected outcome -- aligns with "so that"]
```

**Rules:**
- Multiple "Given" statements are fine (preconditions stack)
- Only ONE "When" per scenario. Multiple Whens = multiple stories. Split them.
- Only ONE "Then" per scenario. Multiple Thens = multiple stories. Split them.
- "When" should align with the "I want to" clause
- "Then" should align with the "so that" clause

## Step-by-Step Process

### 1. Understand the Feature Context
Review the PRD, feature description, or discovery insight. Understand the overall goal, target users, and scope boundaries. User stories should trace back to documented requirements.

### 2. Identify User Personas
Determine which users interact with this feature. Each story should be written for a specific persona -- not generic "users." Different personas may need different stories for the same feature.

### 3. Break Down by User Goal
Decompose the feature into distinct user goals. Each story should deliver a complete, valuable capability -- something the user can actually do when the story is done.

### 4. Write the Story
Fill in the template:

```markdown
### User Story [ID]:

- **Summary:** [Brief, memorable title focused on value]

#### Use Case:
- **As a** [specific persona, e.g., "trial user" not just "user"]
- **I want to** [action user takes to get to outcome]
- **so that** [desired outcome -- the user's motivation]

#### Design: [Link to Figma, Miro, or prototype]

#### Acceptance Criteria:
- **Scenario:** [Brief description]
- **Given:** [Preconditions]
- **When:** [Trigger action]
- **Then:** [Expected outcome]
```

### 5. Validate with INVEST

Each story must be:
- **I**ndependent -- Can be developed without other stories
- **N**egotiable -- Details can be discussed; it's a conversation starter
- **V**aluable -- Delivers value to the user (not "build the API")
- **E**stimable -- Team can estimate effort
- **S**mall -- Completable in one sprint (1-5 days of work)
- **T**estable -- Acceptance criteria are verifiable pass/fail

### 6. Split If Too Large

If a story violates INVEST (especially Small or Independent), apply splitting patterns:

**Pattern 1: Workflow Steps** -- Split along sequential steps in the user journey.
- Original: "Sign up, verify email, complete onboarding"
- Split into 3 stories, one per step.

**Pattern 2: Business Rule Variations** -- Split by different rules/scenarios.
- Original: "Apply discounts (10% member, 20% VIP, 5% first-time)"
- Split into 3 stories, one per discount type.

**Pattern 3: Data Variations** -- Split by data types.
- Original: "Upload files (images, PDFs, videos)"
- Split into 3 stories, one per file type.

**Pattern 4: Acceptance Criteria Complexity** -- Split along When/Then boundaries.
- If you have 3 When/Then pairs, you likely have 3 stories.

**Pattern 5: Major Effort** -- Split by incremental technical milestones.
- Original: "Real-time collaboration"
- Split: presence indicators, live cursors, live edits.

**Pattern 6: External Dependencies** -- Split along API/third-party boundaries.
- Original: "Login with Google, Facebook, Twitter"
- Split into 3 stories, one per provider.

**Anti-patterns to avoid when splitting:**
- Never split horizontally ("front-end story" + "back-end story") -- each story must deliver user value
- Never decompose into tasks ("Set up database" is not a story)
- Never over-split -- a 2-day story doesn't need splitting

## Example

```markdown
### User Story 042:

- **Summary:** Enable Google login for trial users to reduce signup friction

#### Use Case:
- **As a** trial user visiting the app for the first time
- **I want to** log in using my Google account
- **so that** I can access the app without creating and remembering a new password

#### Design: [Figma link]

#### Acceptance Criteria:
- **Scenario:** First-time trial user logs in via Google OAuth
- **Given:** I am on the login page
- **and Given:** I have a Google account
- **When:** I click "Sign in with Google" and authorize the app
- **Then:** I am logged into the app and redirected to the onboarding flow
```

## Quality Checklist

Before finalizing, verify:

- [ ] Each story follows "As a... I want... so that..." format
- [ ] Persona is specific (not just "user")
- [ ] "So that" explains motivation (not restating the action)
- [ ] Stories are independent (can be built in any order)
- [ ] Acceptance criteria use Given/When/Then format
- [ ] Each criterion is testable (someone can verify pass/fail)
- [ ] Only one When and one Then per scenario
- [ ] Stories are small enough for one sprint
- [ ] No implementation details in the story statement
- [ ] Design references linked where applicable

## Common Pitfalls

- **Technical tasks as stories** -- "As a developer, I want to refactor the API" has no user value. Use an engineering task instead.
- **"As a user" (too generic)** -- Every story says "user." Use specific personas: "trial user," "paid subscriber," "admin."
- **"So that" restates "I want to"** -- "I want to click save so that I can save" reveals no motivation. Dig deeper: "so that I don't lose progress if the page crashes."
- **Multiple When/Then** -- Scope creep. Split the story along those boundaries.
- **Untestable criteria** -- "Then the user has a better experience." Make it measurable: "Then the page loads in under 2 seconds."
- **Feature-centric titles** -- "Add delete button" vs. "Enable bulk cleanup for power users." Lead with value.

## Output Deliverables

- Complete set of user stories for the feature
- Each story includes title, description, design link, and acceptance criteria
- Stories are independent and can be developed in any order
- Stories are sized for one sprint cycle
- Stories reference related design documentation

---

### References

**Frameworks:**
- Mike Cohn, *User Stories Applied* (2004) -- "As a / I want / so that" format
- Gherkin (Cucumber) -- "Given/When/Then" acceptance criteria
- INVEST criteria (Bill Wake, 2003) -- Independent, Negotiable, Valuable, Estimable, Small, Testable
- 3 C's: Card, Conversation, Confirmation (Ron Jeffries)
- Richard Lawrence & Peter Green, *Humanizing Work Guide to Splitting User Stories* -- 8 splitting patterns

**Related Skills:**
- `job-stories` -- Alternative format using "When [situation], I want to [motivation], so I can [outcome]" for JTBD-style stories
- `user-story-mapping` -- Visualize user journeys and plan releases along workflow narratives
- `outcome-roadmap` -- Stories trace back to roadmap outcomes

### Further Reading

- [How to Write User Stories: The Ultimate Guide](https://www.productcompass.pm/p/how-to-write-user-stories)
- [Jobs-to-be-Done Masterclass with Tony Ulwick and Sabeen Sattar](https://www.productcompass.pm/p/jobs-to-be-done-masterclass-with) (video course)
