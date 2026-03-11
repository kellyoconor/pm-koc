# How to Create New Skills

This guide walks you through creating a new skill for Kelly's PM Operating System. A skill is a structured knowledge module that teaches Claude how to help with a specific PM task. By the end of this guide, you will have a working skill that follows all repo standards.

---

## Before you start

Make sure you understand:
- **What a skill is.** A `SKILL.md` file with YAML frontmatter and a structured markdown body. It encodes a PM framework, methodology, or guided workflow.
- **Where skills live.** `.claude/skills/{domain}/{skill-name}/SKILL.md`
- **The three skill types.** Component (produces one artifact), Interactive (adaptive Q&A with the user), Workflow (multi-phase orchestration).

If you are unsure whether your idea should be a new skill, an update to an existing skill, or something else entirely, check for overlaps first:

```bash
./scripts/find-a-skill.sh --keyword "your-topic"
```

---

## Skill file structure

Every skill has two parts: YAML frontmatter (metadata) and a markdown body (the actual content Claude uses).

### YAML frontmatter

The frontmatter tells the system what the skill is and when to use it. This is the minimum viable frontmatter:

```yaml
---
name: your-skill-name
description: >-
  What this skill does and when to use it. Max 200 characters.
  Must describe BOTH the capability AND the trigger condition.
intent: >-
  A longer explanation of purpose, audience, and scope.
  This is the repo-facing summary — more detail than description.
type: interactive
---
```

**Required fields:**

| Field | Rules | Example |
|-------|-------|---------|
| `name` | Lowercase kebab-case. Must match directory name. Max 64 characters. | `sprint-risk-radar` |
| `description` | What + when. Max 200 characters. | `Identify and score risks in a sprint plan. Use when reviewing sprint commitments or when a sprint feels overloaded.` |
| `intent` | Fuller summary for contributors and search. No hard character limit. | `Helps PMs systematically identify execution risks before a sprint starts, using historical retro data and team capacity signals.` |
| `type` | One of: `component`, `interactive`, `workflow` | `interactive` |

**Optional fields:**

| Field | Purpose | Example |
|-------|---------|---------|
| `best_for` | List of ideal use cases | `["Reviewing sprint plans", "Capacity planning"]` |
| `scenarios` | Example prompts that should trigger this skill | `["Help me find risks in our sprint", "Is this sprint overcommitted?"]` |

### Choosing the right type

| Type | Use when | Example |
|------|----------|---------|
| `component` | The skill produces one artifact or template | A PRD template, a competitive battlecard |
| `interactive` | The skill asks 3-5 adaptive questions, then produces output | Interview script generator, prioritization advisor |
| `workflow` | The skill runs multiple phases in sequence | Full discovery flow, quarterly strategy review |

### Markdown body

The body is what Claude actually reads and applies. Here are the sections, in order:

**Required sections:**

1. **Title** (H1) -- matches the skill name in human-readable form
2. **Description / How to Help** -- what the skill does and how Claude should apply it
3. **Process / Steps** -- numbered steps Claude follows when this skill is invoked
4. **Output Format** -- what the deliverable looks like, with an example if possible

**Optional sections (recommended):**

5. **Frameworks / Principles** -- domain knowledge, mental models, or reference material
6. **When to Use** -- explicit guidance on when this skill is the right choice
7. **Common Mistakes / Anti-Patterns** -- what to avoid
8. **Related Skills** -- cross-references for follow-up work
9. **Questions to Help Users** -- prompts Claude can use to gather input
10. **Examples** -- worked examples showing input and output

---

## Naming conventions

- **Skill name:** lowercase-kebab-case, max 64 characters. Descriptive but concise.
  - Good: `sprint-risk-radar`, `customer-journey-map`, `feature-investment-advisor`
  - Bad: `risk`, `my-cool-skill`, `sprint_risk_radar` (no underscores)
- **Directory name:** must exactly match the `name` field in frontmatter.
- **Domain:** choose the most specific domain that fits. If genuinely cross-domain, pick the primary one.

---

## Step-by-step: Creating a skill from scratch

Let's walk through creating a real skill: a **sprint risk radar** that helps PMs identify and score risks in an upcoming sprint.

### Step 1: Check for overlaps

```bash
./scripts/find-a-skill.sh --keyword "sprint risk"
```

You might find `execution/pre-mortem` is related but distinct -- pre-mortem is project-level, our skill is sprint-level. Good to proceed.

### Step 2: Create the directory

```bash
mkdir -p .claude/skills/execution/sprint-risk-radar
```

### Step 3: Write the SKILL.md

Create `.claude/skills/execution/sprint-risk-radar/SKILL.md`:

```yaml
---
name: sprint-risk-radar
description: >-
  Identify and score execution risks in a sprint plan. Use when reviewing
  sprint commitments, during kickoff, or when a sprint feels overloaded.
intent: >-
  Helps PMs systematically surface execution risks before a sprint starts.
  Draws on historical retro data, team capacity, dependency maps, and
  scope clarity to produce a scored risk inventory with mitigations.
type: interactive
best_for:
  - "Reviewing sprint plans before commitment"
  - "Identifying overcommitment early"
  - "Preparing for sprint kickoff meetings"
scenarios:
  - "Help me find risks in our upcoming sprint"
  - "Is this sprint plan realistic given our team capacity?"
  - "What could go wrong with this sprint?"
---

# Sprint Risk Radar

Help the user identify, score, and mitigate execution risks in an upcoming
sprint before the team commits.

## How to Help

When the user asks for help assessing sprint risks:

1. **Gather sprint context** - Ask for the sprint goal, committed items,
   team size, and any known constraints
2. **Check scope clarity** - For each committed item, assess whether it has
   clear acceptance criteria and sizing
3. **Identify risk categories** - Systematically check for:
   - Scope risks (unclear requirements, missing specs)
   - Dependency risks (blocked by other teams, external APIs)
   - Capacity risks (overcommitment, planned time off, on-call)
   - Technical risks (new technology, complex integrations)
   - Carryover risks (unfinished work from last sprint)
4. **Score each risk** - Rate likelihood (1-5) and impact (1-5)
5. **Recommend mitigations** - For any risk scoring 3+ on both dimensions

## Questions to Ask the User

- "What is the sprint goal in one sentence?"
- "How many story points (or items) are committed vs. team capacity?"
- "Are there items carried over from the previous sprint?"
- "Is anyone on the team out or on-call this sprint?"
- "Which items have unclear or missing acceptance criteria?"
- "Are there dependencies on other teams or external services?"

## Output Format

Sprint Risk Radar for [Sprint Name]:

| Risk | Category | Likelihood (1-5) | Impact (1-5) | Score | Mitigation |
|------|----------|-------------------|---------------|-------|------------|
| Auth service dependency on Platform team | Dependency | 4 | 5 | 20 | Identify fallback scope; sync with Platform by Day 2 |
| Search rewrite has no acceptance criteria | Scope | 3 | 4 | 12 | Write AC before sprint starts; descope if not ready |
| 2 engineers out Thursday-Friday | Capacity | 5 | 3 | 15 | Front-load their items to Mon-Wed |

Overall Risk Level: [Low / Medium / High / Critical]
Confidence in Sprint Success: [X/10]
Top Action Item: [The single most important thing to do before sprint starts]

## Common Mistakes to Flag

- **Optimism bias** - Teams consistently underestimate risk. If the user says
  "we have no risks," push back gently.
- **Ignoring carryover** - Unfinished items from last sprint are the #1
  predictor of this sprint's problems.
- **Dependency hand-waving** - "They said they'd have it ready" is not a
  mitigation plan.
- **Capacity math errors** - Sprint capacity is not (people x days). Account
  for meetings, on-call, code review, and interrupt-driven work.

## Related Skills

- execution/pre-mortem (project-level risk assessment)
- execution/sprint-plan (sprint planning fundamentals)
- execution/bet-sizing (scope and effort estimation)
- execution/deliver-edge-cases (identifying missing requirements)
```

### Step 4: Validate

Run the validation checks to make sure the skill meets repo standards:

```bash
./scripts/test-a-skill.sh --skill sprint-risk-radar --smoke
python3 scripts/check-skill-metadata.py skills/sprint-risk-radar/SKILL.md
```

Validation checks for:
- Frontmatter has all required fields (`name`, `description`, `intent`, `type`)
- `name` is 64 characters or fewer
- `description` is 200 characters or fewer
- `name` matches the directory name
- Section order is compliant
- Cross-references resolve

### Step 5: Test the skill

The best test is using it. Start a new Claude conversation and try:

```
"Help me assess the risks in our upcoming sprint. We have 8 items
committed, team of 4, and one engineer is out for 2 days."
```

Check that Claude:
- Loads the skill (you can tell from the structured response format)
- Asks clarifying questions from the skill's question list
- Produces output matching the defined Output Format
- Flags common mistakes appropriately

### Step 6: Update the catalog

If this is a new skill (not an update to an existing one):

1. Add an entry to the relevant README category table
2. Update the skill count in `CLAUDE.md` and `README.md`
3. Verify all link paths resolve

---

## Quick reference: Definition of Done

A skill is ready to ship when all of these are true:

- [ ] Frontmatter has `name`, `description`, `intent`, and `type`
- [ ] `name` matches directory name and is kebab-case, max 64 characters
- [ ] `description` is max 200 characters and states both what and when
- [ ] Body has Description, Process/Steps, and Output Format sections
- [ ] At least one concrete example or output template
- [ ] At least one anti-pattern or common mistake
- [ ] Validation scripts pass with no errors
- [ ] README catalog updated with new entry and correct counts
- [ ] Tested in a live Claude conversation

---

## The guided path: Using the skill-authoring-workflow

If you prefer a guided experience, the repo includes a meta-skill for creating skills. It lives at `.claude/skills/toolkit/skill-authoring-workflow/SKILL.md` and provides:

- **Three creation paths:**
  - `build-a-skill.sh` -- guided wizard when you have an idea but not final prose
  - `add-a-skill.sh` -- content-first generator when you already have source material
  - Manual edit + validate -- best for tightening an existing skill

- **Six phases:** Preflight (check for duplicates) --> Generate Draft --> Tighten --> Validate --> Integrate with Docs --> Optional Packaging

To use it:

```bash
# From source material (workshop notes, article, framework doc)
./scripts/add-a-skill.sh research/your-framework.md

# Guided prompts (interactive wizard)
./scripts/build-a-skill.sh

# Validate the result
./scripts/test-a-skill.sh --skill <skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<skill-name>/SKILL.md
```

---

## Common pitfalls

**Description says what but not when.** "Helps with sprint planning" is incomplete. "Create a sprint plan with goals, capacity, and commitments. Use at sprint start or when replanning mid-sprint." tells Claude when to trigger it.

**Wrong type selection.** If your skill just produces a template, it is a `component`, not a `workflow`. If it asks questions and adapts, it is `interactive`. Reserve `workflow` for multi-phase orchestrations.

**Description exceeds 200 characters.** The description gets silently truncated in some contexts. Keep it tight. Use `intent` for the longer explanation.

**Skipping validation.** Running `test-a-skill.sh` and `check-skill-metadata.py` takes 10 seconds and catches 90% of issues. Skipping it leads to broken references and inconsistent catalogs.

**Consultant-speak.** "Leverage synergistic frameworks to optimize stakeholder alignment" helps nobody. Write like you are explaining to a smart colleague.

---

## Further reading

- **[System Architecture](architecture.md)** -- How skills fit into the three-layer system
- **[Contributing Guide](../CONTRIBUTING.md)** -- How to submit your skill
- **[skill-authoring-workflow](../.claude/skills/toolkit/skill-authoring-workflow/SKILL.md)** -- The meta-skill for skill creation
- **[Anthropic's Guide to Building Skills](https://resources.anthropic.com/hubfs/The-Complete-Guide-to-Building-Skill-for-Claude.pdf)** -- Official reference
