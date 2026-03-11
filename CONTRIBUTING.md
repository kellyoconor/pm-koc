# Contributing to Kelly's PM Operating System

Thank you for your interest in improving this system. Whether you are fixing a typo, refining an existing skill, or proposing an entirely new subagent, this guide will help you contribute effectively.

---

## Ways to contribute

| Contribution | Complexity | Process |
|-------------|-----------|---------|
| Fix a typo or broken link | Low | Open a PR directly |
| Improve an existing skill | Low-Medium | Open a PR directly |
| Add a new skill | Medium | Open a PR with validation passing |
| Add a new subagent | Medium-High | Open an issue first to discuss |
| Propose a new automation | High | Open an issue first to discuss |
| Structural or architectural changes | High | Open an issue first to discuss |

**Rule of thumb:** if your change adds a new file, open an issue first. If your change only modifies existing files, a direct PR is fine.

---

## Adding a new skill

New skills are the most common contribution. Follow these steps:

### 1. Check for overlaps

```bash
./scripts/find-a-skill.sh --keyword "your-topic"
```

If a related skill already exists, consider improving it instead of creating a new one. Skills that overlap cause confusion.

### 2. Create the skill

Follow the [Skill Authoring Guide](docs/skill-authoring.md) for the full walkthrough. The short version:

```bash
mkdir -p .claude/skills/{domain}/{skill-name}
# Write your SKILL.md with required frontmatter and body sections
```

### 3. Validate

```bash
./scripts/test-a-skill.sh --skill <skill-name> --smoke
python3 scripts/check-skill-metadata.py skills/<skill-name>/SKILL.md
```

Both must pass with no errors before you open a PR.

### 4. Update the catalog

- Add the skill to the appropriate README category table
- Update skill counts in `CLAUDE.md` and `README.md`
- Verify all link paths resolve

### 5. Open a PR

See the PR format section below.

---

## Improving an existing skill

Improvements to existing skills are always welcome. Common improvements:

- **Add missing anti-patterns.** If you have seen a skill applied incorrectly, document the mistake.
- **Improve output format.** Make templates more practical based on real usage.
- **Add examples.** Concrete examples help Claude apply the skill more effectively.
- **Sharpen the description.** If the description does not clearly state both *what* and *when*, fix it.
- **Fix stale cross-references.** If a Related Skills link points to a skill that was renamed or removed, update it.

When improving a skill:

1. Read the existing skill thoroughly
2. Make your changes
3. Run validation: `python3 scripts/check-skill-metadata.py skills/<skill-name>/SKILL.md`
4. Test in a live Claude conversation to confirm the improvement works
5. Open a PR explaining what you changed and why

---

## Adding a new subagent

Subagents are PM perspective evaluators. Adding one means introducing a new viewpoint that the system currently lacks.

**Before proposing a new subagent, open an issue that answers:**

1. What perspective is missing from the current seven? (customer-advocate, business-strategist, data-analyst, growth-pm, engineering-lead, design-lead, risk-assessor)
2. What decisions would benefit from this perspective that are not already covered?
3. Which existing skills would this subagent draw on?
4. Provide a draft of the subagent file (see format below)

**Subagent file format** (`.claude/subagents/{name}.md`):

```markdown
# {Name} Subagent

## Role
One paragraph defining the perspective and evaluation stance.

## Perspective
- Question this subagent asks about every decision
- Another question
- ...

## Skills to Draw On
- domain/skill-name
- domain/skill-name

## When Invoked
When to use this subagent.

## Output Style
- How this subagent structures its evaluation
- Scoring criteria, categories, or frameworks it uses
```

---

## Proposing a new automation

Automations are recurring rituals that chain skills and subagents on a schedule. They are the most complex component of the system.

**Before proposing a new automation, open an issue that answers:**

1. What recurring PM activity is not currently automated?
2. What cadence should it run on? (daily, weekly, sprint, monthly, quarterly)
3. Which skills and subagents would it chain together?
4. What structured output would it produce?
5. How does it connect to existing automations? (What feeds into it? What does it feed?)

**Automation file format** (`.claude/automations/{name}.md`):

```markdown
# {Automation Name}

## Schedule
When it runs.

## What It Does
Plain-language description of the workflow.

## Workflow
1. Step one (references specific skills)
2. Step two (may invoke subagents)
3. ...

## Skills Used
- domain/skill-name

## Subagents
- subagent-name (why)

## Output
Structured output format.

## Trigger
`/command-name` or automated schedule
```

---

## PR format and expectations

Every pull request should follow this format:

### Title

Short, descriptive, and prefixed with the type of change:

```
[skill] Add sprint-risk-radar to execution domain
[fix] Update broken cross-reference in pre-mortem skill
[subagent] Add compliance-reviewer perspective
[automation] Add monthly team health check ritual
[docs] Improve skill authoring guide examples
```

### Description

```markdown
## What

One sentence describing what this PR does.

## Why

One to three sentences explaining the motivation. What problem does this
solve? What gap does it fill?

## Changes

- Bullet list of specific changes
- One bullet per file or logical change

## Validation

- [ ] `test-a-skill.sh` passes (for new/changed skills)
- [ ] `check-skill-metadata.py` passes (for new/changed skills)
- [ ] README counts updated (for new skills)
- [ ] Tested in live Claude conversation (for new skills)
```

### PR standards

- **One change per PR.** Do not bundle a new skill with a typo fix in an unrelated file.
- **Passing validation.** PRs with failing validation will not be reviewed.
- **No cross-plugin references in commands.** Suggest follow-ups in natural language only.
- **Skill `name` matches directory name.** This is enforced by validation but worth checking manually.

---

## Style guide

### Writing

- Write clearly and directly. Avoid jargon when plain language works.
- State both what a thing does and when to use it.
- Include at least one concrete example and one anti-pattern per skill.
- Do not use filler phrases ("It is important to note that..."). Get to the point.

### Naming

- **Skills:** lowercase-kebab-case, max 64 characters. Descriptive, not clever.
- **Domains:** use the existing 15 domains. If none fit, propose a new one in your issue.
- **Subagents:** lowercase-kebab-case, named for the role (not the person).
- **Automations:** lowercase-kebab-case, named for the ritual.

### Formatting

- Use markdown headers for structure (H1 for title, H2 for sections, H3 for subsections)
- Use tables for structured data
- Use code blocks for commands, templates, and output examples
- Use numbered lists for sequential steps
- Use bullet lists for non-sequential items

---

## Code of conduct

This project follows a straightforward standard of professional conduct:

- **Be respectful.** Treat every contributor's time and ideas with respect.
- **Be constructive.** Feedback should help improve the work, not criticize the person.
- **Be specific.** "This could be better" is not useful. "The description should mention when to trigger this skill" is.
- **Be honest.** If something does not work, say so clearly and suggest an alternative.

Harassment, personal attacks, and disrespectful behavior will not be tolerated. Maintainers reserve the right to remove any contribution or contributor that violates these standards.

---

## Questions?

If you are unsure about anything, open an issue. It is better to discuss an approach before investing time in implementation.

---

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE).
