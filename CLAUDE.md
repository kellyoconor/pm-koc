# Kelly's PM Operating System

## Who
Kelly (koc) — Product Manager building a full AI-powered PM skill system.

## System Architecture

### Skills (148 across 15 domains)
Located in `.claude/skills/{domain}/{skill-name}/SKILL.md`

| Domain | Count | What |
|--------|-------|------|
| discovery | 20 | Interviews, assumptions, experiments, behavioral design |
| strategy | 18 | Vision, positioning, market analysis, business models |
| execution | 24 | PRDs, sprints, stories, sizing, shipping |
| leadership | 17 | Coaching, org design, transitions, culture |
| engineering-adjacent | 11 | ADRs, spikes, tech debt, design systems |
| marketing-growth | 9 | Content, community, landing pages, positioning |
| market-research | 8 | Competitors, personas, journey maps, sizing |
| career | 7 | Promotions, transitions, negotiation, mentors |
| ai-practice | 7 | AI strategy, evals, LLM building, readiness |
| sales | 6 | Enterprise, founder, PLG, compensation |
| go-to-market | 6 | GTM motions, battlecards, growth loops, ICP |
| toolkit | 5 | NDAs, privacy, resume, grammar, skill authoring |
| data-analytics | 4 | A/B tests, cohorts, SQL, instrumentation |
| soft-skills | 3 | Presentations, writing, storytelling |
| finance | 3 | SaaS metrics, pricing impact, feature ROI |

### Subagents (7 PM perspectives)
Located in `.claude/subagents/{name}.md`

Use these to evaluate any product decision from multiple angles:
- **customer-advocate** — Voice of the customer, evidence-based
- **business-strategist** — Competitive positioning, moats, market dynamics
- **data-analyst** — Metrics, measurement, statistical rigor
- **growth-pm** — Funnels, loops, AARRR, compounding effects
- **engineering-lead** — Feasibility, complexity, tech debt, scope
- **design-lead** — UX quality, accessibility, experience craft
- **risk-assessor** — Pre-mortem, assumptions, blast radius

**NOTE: Subagents are currently generic and need to be tailored to Kelly's specific product, team, and context.**

### Automations (6 recurring rituals)
Located in `.claude/automations/{name}.md`

| Ritual | Cadence | Trigger |
|--------|---------|---------|
| Daily standup prep | Every workday AM | `/standup` |
| Weekly feedback analysis | Monday AM | `/weekly-feedback` |
| Sprint kickoff review | Sprint start | `/sprint-kickoff` |
| Sprint retro + lessons | Sprint end | `/retro` |
| Monthly competitive scan | 1st week/month | `/competitive-scan` |
| Quarterly strategy review | End of quarter | `/quarterly-review` |

### Commands (36 slash commands)
Located in `.claude/commands/` — inherited from phuryn/pm-skills plugins.

Key entry points:
- `/discover` — Full discovery flow
- `/strategy` — Product strategy deep-dive
- `/write-prd` — Guided PRD creation
- `/plan-launch` — Go-to-market planning
- `/north-star` — Define key metrics

## Sources
Skills merged from 6 open-source repos:
1. phuryn/pm-skills (baseline — 63 skills, 36 commands)
2. RefoundAI/lenny-skills (46 unique — leadership, career, sales)
3. deanpeters/Product-Manager-Skills (15 unique — finance, validation, leadership transitions)
4. product-on-purpose/pm-skills (8 unique — engineering-adjacent, edge cases)
5. alirezarezvani/claude-skills (4 unique — landing pages, SaaS scaffolding, teardowns)
6. assimovt/productskills (2 unique — Shape Up bet-sizing, scope-cutting)

## Goals
- Use skills as building blocks for subagent-driven product decisions
- Automate recurring PM rituals (feedback analysis, competitive scans, retros)
- Build toward a self-improving PM system where lessons feed back into future decisions

## Conventions
- Skills follow SKILL.md format with YAML frontmatter
- Commands are slash-triggered workflows that chain skills
- Subagents are perspective-based evaluators that draw on relevant skills
- Automations are recurring workflows that chain skills + subagents on a schedule
