# System Architecture

Kelly's PM Operating System is a three-layer architecture that turns Claude into a full-service product management partner. Each layer builds on the one below it: **Skills** provide domain knowledge, **Subagents** apply perspectives to that knowledge, and **Automations** orchestrate both on a recurring schedule.

```
+------------------------------------------------------------------+
|                                                                  |
|   LAYER 3: AUTOMATIONS (6 recurring rituals)                     |
|   Scheduled workflows that chain skills + subagents              |
|                                                                  |
|   /standup  /weekly-feedback  /sprint-kickoff                    |
|   /retro    /competitive-scan /quarterly-review                  |
|                                                                  |
+---------|---------------------|-------------------|--------------+
          |                     |                   |
          v                     v                   v
+------------------------------------------------------------------+
|                                                                  |
|   LAYER 2: SUBAGENTS (7 PM perspectives)                         |
|   Evaluate decisions through specialized lenses                  |
|                                                                  |
|   customer-advocate    business-strategist    data-analyst        |
|   growth-pm            engineering-lead       design-lead         |
|   risk-assessor                                                  |
|                                                                  |
+---------|---------------------|-------------------|--------------+
          |                     |                   |
          v                     v                   v
+------------------------------------------------------------------+
|                                                                  |
|   LAYER 1: SKILLS (152 across 15 domains)                        |
|   Frameworks, templates, and guided workflows                    |
|                                                                  |
|   discovery/  strategy/  execution/  leadership/  finance/       |
|   career/  ai-practice/  sales/  go-to-market/  toolkit/         |
|   data-analytics/  soft-skills/  engineering-adjacent/            |
|   market-research/  marketing-growth/                             |
|                                                                  |
+------------------------------------------------------------------+
```

---

## Layer 1: Skills

Skills are the knowledge base. Each skill encodes a single PM framework, methodology, or guided workflow as a `SKILL.md` file that Claude can load and apply.

### What a skill is

A skill is a structured markdown file with YAML frontmatter. It teaches Claude how to help with a specific PM task -- writing a PRD, running a pre-mortem, sizing a market, facilitating a retro. Skills are not prompts. They are reusable knowledge modules that Claude draws on when the situation calls for it.

### How skills are organized

```
.claude/skills/
  discovery/                    # 20 skills
    behavioral-product-design/
      SKILL.md
    interview-script/
      SKILL.md
    ...
  strategy/                     # 18 skills
  execution/                    # 24 skills
  leadership/                   # 17 skills
  engineering-adjacent/         # 11 skills
  marketing-growth/             # 9 skills
  market-research/              # 8 skills
  career/                       # 7 skills
  ai-practice/                  # 7 skills
  sales/                        # 6 skills
  go-to-market/                 # 6 skills
  toolkit/                      # 5 skills
  data-analytics/               # 4 skills
  soft-skills/                  # 3 skills
  finance/                      # 3 skills
```

Each skill lives in its own directory under its domain: `.claude/skills/{domain}/{skill-name}/SKILL.md`.

### SKILL.md format

Every skill follows a consistent structure:

```yaml
---
name: behavioral-product-design
description: >-
  Help users apply behavioral science to product design. Use when someone
  is designing for habit formation, reducing friction, or applying
  psychology to UX.
intent: >-
  A longer explanation of the skill's purpose, audience, and scope.
type: interactive          # component | interactive | workflow
best_for:
  - "Designing for habit formation"
  - "Reducing friction in user flows"
scenarios:
  - "Help me apply loss aversion to our onboarding"
  - "How can I use defaults to improve activation?"
---

# Behavioral Product Design

Help the user apply behavioral science principles to product design.

## How to Help

1. **Understand the target behavior** - Ask what action they want users to take
2. **Identify behavioral barriers** - Diagnose what prevents the desired behavior
3. **Suggest relevant principles** - Apply concepts like loss aversion or present bias
4. **Design interventions** - Create features that leverage these principles

## Core Principles

### Loss aversion drives retention
"Once you hit seven days, loss aversion kicks in, and you retain."
Design experiences that create something users feel they'd lose by leaving.

## Common Mistakes to Flag

- Dark patterns that manipulate rather than help
- Over-engineering friction when simple solutions work
- Ignoring cultural context

## Related Skills

- User Onboarding
- Retention & Engagement
- Designing Growth Loops
```

**Frontmatter fields:**

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Matches directory name. Max 64 characters. |
| `description` | Yes | What the skill does and when to trigger it. Max 200 characters. |
| `intent` | Yes | Longer repo-facing summary of purpose and scope. |
| `type` | Yes | `component` (one artifact), `interactive` (adaptive Q&A), or `workflow` (multi-phase). |
| `best_for` | No | List of ideal use cases. |
| `scenarios` | No | Example user prompts that should trigger this skill. |

**Body sections:**

| Section | Required | Purpose |
|---------|----------|---------|
| Description / How to Help | Yes | What the skill does and how Claude should apply it. |
| Process / Steps | Yes | Step-by-step procedure Claude follows. |
| Output Format | Yes | What the deliverable looks like. |
| Frameworks / Principles | No | Domain knowledge Claude draws on. |
| When to Use | No | Guidance on when this skill is the right choice. |
| Common Mistakes / Anti-Patterns | No | What to avoid. |
| Related Skills | No | Cross-references for follow-up work. |

### How skills get invoked

Skills activate in two ways:

1. **Automatic.** Claude matches your request to a relevant skill based on its `description` and `scenarios` fields. Ask "help me write a PRD" and the `execution/create-prd` skill loads automatically.

2. **Explicit.** Use a slash command or name the skill directly. The system includes 36 slash commands that map to specific skills or skill chains:

```
/discover          Full discovery flow
/strategy          Product strategy deep-dive
/write-prd         Guided PRD creation
/plan-launch       Go-to-market planning
/north-star        Define key metrics
```

---

## Layer 2: Subagents

Subagents are PM perspective evaluators. Each one embodies a specific role on a product team and evaluates decisions through that lens. Where skills provide the *what* (frameworks, templates, processes), subagents provide the *how to think about it*.

### The seven perspectives

| Subagent | Role | Key Question |
|----------|------|--------------|
| **customer-advocate** | Voice of the customer | "Does this solve a problem customers actually have?" |
| **business-strategist** | Competitive positioning | "Is this strategically defensible?" |
| **data-analyst** | Metrics and measurement | "What does the data say, and is it statistically valid?" |
| **growth-pm** | Funnels and loops | "Does this compound over time?" |
| **engineering-lead** | Feasibility and complexity | "Can we actually build this, and should we?" |
| **design-lead** | UX quality and craft | "Is this a good experience?" |
| **risk-assessor** | Pre-mortem and assumptions | "What could go wrong, and what's the blast radius?" |

### Subagent structure

Each subagent file (`.claude/subagents/{name}.md`) defines:

- **Role** -- a clear identity and evaluation stance
- **Perspective** -- the specific questions this subagent asks about any decision
- **Skills to Draw On** -- which Layer 1 skills inform this perspective
- **When Invoked** -- guidance on when to use this subagent
- **Output Style** -- how the subagent structures its evaluation

For example, the risk-assessor subagent draws on `execution/pre-mortem`, `discovery/identify-assumptions-existing`, `strategy/swot-analysis`, and others. It categorizes risks as Tigers (real and urgent), Paper Tigers (feel big but are not), and Elephants (real but ignored), then rates each on likelihood, impact, and mitigation difficulty.

### Using a single subagent

Ask Claude to evaluate from one perspective:

```
"Evaluate this PRD from the customer-advocate perspective."

"Run the engineering-lead subagent on our proposed architecture."

"What would the risk-assessor say about launching without a beta?"
```

Claude loads the subagent definition, draws on its assigned skills, and produces an evaluation in that subagent's output style. The customer-advocate leads with evidence (or flags its absence), scores customer impact, and flags unvalidated assumptions. The business-strategist frames trade-offs and identifies moat implications.

### Running all seven subagents

For high-stakes decisions, invoke all perspectives:

```
"Run all 7 subagents on our Q3 roadmap proposal."

"Give me a comprehensive multi-perspective review of this feature spec."
```

This produces seven independent evaluations followed by a synthesis that identifies where perspectives align, where they conflict, and what the combined recommendation is. The quarterly strategy review automation does this by default.

---

## Layer 3: Automations

Automations are recurring PM rituals that run on a schedule. Each automation chains skills and subagents into a complete workflow, then produces a structured deliverable.

### The six rituals

| Automation | Cadence | Trigger | What It Produces |
|------------|---------|---------|-----------------|
| **Daily standup prep** | Every workday AM | `/standup` | 3-line update: Done / Doing / Blocked |
| **Weekly feedback analysis** | Monday AM | `/weekly-feedback` | Sentiment trends, top themes, recommended actions |
| **Sprint kickoff review** | Sprint start | `/sprint-kickoff` | Readiness report with confidence score (1-10) |
| **Sprint retro + lessons** | Sprint end | `/retro` | Retro summary, action items, updated risk patterns |
| **Monthly competitive scan** | 1st week of month | `/competitive-scan` | Competitive brief with updated battlecards |
| **Quarterly strategy review** | End of quarter | `/quarterly-review` | Full strategy package with multi-perspective synthesis |

### Automation structure

Each automation file (`.claude/automations/{name}.md`) defines:

- **Schedule** -- when it runs
- **What It Does** -- plain-language description
- **Workflow** -- numbered steps that reference specific skills and subagents
- **Skills Used** -- which Layer 1 skills are invoked
- **Subagents** -- which Layer 2 perspectives are applied
- **Output** -- the structured deliverable format
- **Trigger** -- the slash command to run it manually

### How automations connect the layers

The power of automations is in how they chain the layers together and create feedback loops. Here is the data flow:

```
WEEKLY FEEDBACK ANALYSIS (Monday AM)
  |
  |-- Runs sentiment-analysis skill (Layer 1)
  |-- Runs user-segmentation skill (Layer 1)
  |-- Invokes customer-advocate subagent (Layer 2) for interpretation
  |-- Invokes data-analyst subagent (Layer 2) for pattern validation
  |
  +-- Output: Theme clusters, emerging issues, suggested follow-ups
       |
       |-- Feeds into SPRINT KICKOFF (sprint start)
       |   Unresolved themes become backlog candidates
       |
       +-- Feeds into QUARTERLY STRATEGY REVIEW (end of quarter)
           Trend data informs strategy assessment


SPRINT RETRO + LESSONS (sprint end)
  |
  |-- Runs retro skill (Layer 1)
  |-- Captures lessons in iterate-lessons-log (Layer 1)
  |-- Feeds insights into risk-assessor subagent (Layer 2)
  |
  +-- Output: Updated risk patterns, action items
       |
       +-- Risk patterns inform NEXT SPRINT KICKOFF
           risk-assessor draws on historical lessons


MONTHLY COMPETITIVE SCAN (1st week)
  |
  |-- Runs competitor-analysis + competitive-teardown skills (Layer 1)
  |-- Updates competitive battlecards (Layer 1)
  |-- Invokes business-strategist subagent (Layer 2) for implications
  |
  +-- Output: Competitive brief, updated battlecards
       |
       +-- Feeds into QUARTERLY STRATEGY REVIEW
           Competitive landscape data informs strategy


QUARTERLY STRATEGY REVIEW (end of quarter)
  |
  |-- Draws on ALL accumulated data from other automations
  |-- Runs 15+ skills across strategy, discovery, execution, finance
  |-- Invokes ALL 7 subagents for multi-perspective evaluation
  |
  +-- Output: Strategy package with go/adjust/pivot recommendation
       |
       +-- Sets direction for next quarter's rituals
```

### The feedback loop

The system improves over time because outputs from one automation become inputs for others:

1. **Retro lessons inform risk assessments.** When something goes wrong in a sprint, the retro captures it. The risk-assessor subagent incorporates those patterns into future sprint kickoff reviews.

2. **Feedback analysis surfaces discovery opportunities.** Recurring user pain points identified in weekly feedback analysis flow into the quarterly strategy review as unmet customer needs.

3. **Competitive intelligence shapes strategy.** Monthly competitive scans accumulate a picture of market movement that the quarterly review synthesizes into strategic recommendations.

4. **Strategy decisions cascade into execution.** Quarterly review outputs (OKRs, bets, priorities) become the inputs for the next cycle of sprint planning and daily standups.

---

## How the pieces fit together

Here is the complete data flow from a user request through all three layers:

```
USER REQUEST
  "Review our Q3 roadmap from all angles"
         |
         v
  LAYER 3: AUTOMATION (quarterly-strategy-review)
         |
         +-- Step 1: Metrics Review
         |     |-- data-analytics/cohort-analysis (Layer 1)
         |     +-- finance/saas-economics (Layer 1)
         |
         +-- Step 2: Strategy Assessment
         |     |-- strategy/porters-five-forces (Layer 1)
         |     +-- strategy/pestle-analysis (Layer 1)
         |
         +-- Step 3: Multi-Perspective Evaluation
         |     |-- customer-advocate (Layer 2) --> draws on discovery/ skills
         |     |-- business-strategist (Layer 2) --> draws on strategy/ skills
         |     |-- data-analyst (Layer 2) --> draws on data-analytics/ skills
         |     |-- growth-pm (Layer 2) --> draws on marketing-growth/ skills
         |     |-- engineering-lead (Layer 2) --> draws on engineering-adjacent/ skills
         |     |-- design-lead (Layer 2) --> draws on soft-skills/ skills
         |     +-- risk-assessor (Layer 2) --> draws on execution/ skills
         |
         v
  STRUCTURED OUTPUT
    Executive summary, metrics, strategy assessment,
    proposed OKRs, risk profiles, go/adjust/pivot decision
```

Each layer adds value:
- **Skills** supply the analytical frameworks (Porter's, PESTLE, cohort analysis)
- **Subagents** apply judgment from different perspectives (is this defensible? is it feasible? will customers care?)
- **Automations** orchestrate the sequence and ensure nothing gets missed

---

## File locations

| Component | Location | Count |
|-----------|----------|-------|
| Skills | `.claude/skills/{domain}/{skill-name}/SKILL.md` | 152 |
| Subagents | `.claude/subagents/{name}.md` | 7 |
| Automations | `.claude/automations/{name}.md` | 6 |
| Commands | `.claude/commands/` | 36 |
| System config | `CLAUDE.md` | 1 |

---

## Next steps

- **[Skill Authoring Guide](skill-authoring.md)** -- How to create new skills
- **[Contributing Guide](../CONTRIBUTING.md)** -- How to contribute to the system
