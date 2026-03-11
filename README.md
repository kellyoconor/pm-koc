# PM Operating System

**A complete AI-powered product management skill system for Claude Code.**

152 skills | 15 domains | 7 subagents | 6 automations | 36 commands

---

## Start Here

Most PMs reach for this system in one of five moments. Pick yours:

| I need to...                        | Run this            |
|-------------------------------------|---------------------|
| Write a PRD from scratch            | `/write-prd`        |
| Prepare for a customer interview    | `/interview prep`   |
| Run a full discovery cycle          | `/discover`         |
| Plan a product launch               | `/plan-launch`      |
| Define my north star metric         | `/north-star`       |

Every command accepts a plain-English argument. For example:

```
/write-prd AI-powered search for our developer docs
/discover onboarding flow for enterprise customers
/plan-launch v2 mobile app redesign
```

---

## Quick Start

**Prerequisites:** [Claude Code](https://docs.anthropic.com/en/docs/claude-code) or [Claude Cowork](https://docs.anthropic.com/en/docs/cowork) installed and configured.

**Step 1.** Clone this repository into your working directory.

```bash
git clone https://github.com/your-org/pm-koc.git
cd pm-koc
```

**Step 2.** Open Claude Code in this directory. The `.claude/` folder is detected automatically -- skills, subagents, automations, and commands are all available immediately.

```bash
claude
```

**Step 3.** Run your first command.

```
/write-prd a feature you are currently thinking about
```

That is it. No configuration files, no API keys, no build step. The system loads on launch.

---

## Architecture

The PM Operating System is built on three layers, each designed to do one thing well.

```
Commands (36 entry points)
    |
    v
Skills (knowledge)  -->  Subagents (perspectives)  -->  Automations (rituals)
    |                          |                              |
  152 skills               7 evaluators                  6 schedules
  across 15 domains        that critique                 that run
  of PM practice           from different                recurring PM
                           angles                        workflows
```

### Skills -- The Knowledge Layer

Each skill is a standalone SKILL.md file containing structured instructions, frameworks, and templates for a specific PM activity. Skills follow a consistent format with YAML frontmatter, domain context, step-by-step instructions, and output templates.

**Location:** `.claude/skills/{domain}/{skill-name}/SKILL.md`

Skills are the atomic building blocks. They can be used individually, chained together by commands, or drawn upon by subagents during evaluation.

### Subagents -- The Perspective Layer

Subagents are role-based evaluators. When you need a product decision stress-tested from multiple angles, subagents provide seven distinct PM perspectives. Each subagent draws on relevant skills to inform its analysis.

**Location:** `.claude/subagents/{name}.md`

### Automations -- The Ritual Layer

Automations encode the recurring rhythms of good product management. They chain skills and subagents together on a cadence -- daily standups, weekly feedback reviews, sprint ceremonies, monthly competitive scans, and quarterly strategy reviews.

**Location:** `.claude/automations/{name}.md`

---

## Skill Reference

152 skills organized across 15 product management domains. Each skill is a self-contained, reusable unit of PM knowledge.

### Discovery -- 22 skills

The largest domain. Covers the full spectrum from problem identification through validation.

| Skill | What it does |
|-------|-------------|
| analyze-feature-requests | Triage and prioritize incoming feature requests |
| behavioral-product-design | Apply behavioral psychology to product decisions |
| brainstorm-experiments-existing | Generate experiment ideas for existing products |
| brainstorm-experiments-new | Generate experiment ideas for new products |
| brainstorm-ideas-existing | Ideation for existing product improvements |
| brainstorm-ideas-new | Ideation for greenfield products |
| designing-surveys | Create effective user research surveys |
| dogfooding | Structure internal product usage programs |
| epic-hypothesis | Frame epics as testable hypotheses |
| identify-assumptions-existing | Surface hidden assumptions in existing products |
| identify-assumptions-new | Surface hidden assumptions in new products |
| interview-script | Create structured interview scripts (Mom Test + YC Five Questions) |
| jtbd-analysis | Jobs-to-be-Done analysis and opportunity mapping |
| metrics-dashboard | Design metrics dashboards for discovery tracking |
| opportunity-solution-tree | Map opportunities to solutions (Teresa Torres) |
| pol-probe | Problem-Opportunity-Leverage probing framework |
| pol-probe-advisor | Guided POL probe facilitation |
| prioritize-assumptions | Rank assumptions by risk and impact |
| prioritize-features | Structured feature prioritization (RICE, ICE, MoSCoW) |
| problem-statement | Craft clear, actionable problem statements |
| storyboard | Visual storyboarding for user scenarios |
| summarize-interview | Extract insights from interview transcripts |

### Execution -- 25 skills

From PRD to shipped product. Sprint planning, story writing, release management, and retrospectives.

| Skill | What it does |
|-------|-------------|
| bet-sizing | Size bets using Shape Up methodology |
| brainstorm-okrs | Generate and refine OKR candidates |
| create-prd | Full PRD creation with guided multi-phase workflow |
| deliver-edge-cases | Identify and document edge cases |
| dummy-dataset | Generate realistic test data |
| epic-breakdown-advisor | Break epics into shippable increments |
| iterate-lessons-log | Maintain a running lessons-learned log |
| iterate-refinement-notes | Capture refinement session outcomes |
| job-stories | Write job stories (When... I want to... So I can...) |
| managing-timelines | Timeline estimation and tracking |
| outcome-roadmap | Build outcome-driven roadmaps |
| pre-mortem | Run pre-mortems on plans and PRDs |
| prioritization-frameworks | Apply RICE, ICE, MoSCoW, Kano, and others |
| product-operations | Define product ops processes and tooling |
| release-notes | Write clear, user-facing release notes |
| retro | Facilitate structured retrospectives |
| scope-cutting | Systematically cut scope without losing value |
| shipping-products | End-to-end shipping checklists and playbooks |
| sprint-plan | Sprint planning and capacity allocation |
| stakeholder-map | Map stakeholders by influence and interest |
| summarize-meeting | Extract action items from meeting transcripts |
| test-scenarios | Generate test scenarios from specs or stories |
| user-stories | Write user stories with acceptance criteria |
| user-story-mapping | Jeff Patton-style story mapping |
| wwas | "What Went As Surprise" analysis |

### Strategy -- 18 skills

Vision, positioning, competitive analysis, and business model design.

| Skill | What it does |
|-------|-------------|
| ansoff-matrix | Growth direction analysis (market vs. product) |
| business-model | Business model canvas creation |
| lean-canvas | Lean Canvas for startup validation |
| marketplace-liquidity | Analyze and improve marketplace dynamics |
| measuring-product-market-fit | Frameworks for PMF measurement |
| monetization-strategy | Revenue model design and evaluation |
| pestle-analysis | Political, Economic, Social, Tech, Legal, Environmental scan |
| platform-strategy | Platform and ecosystem strategy |
| porters-five-forces | Competitive landscape analysis |
| pricing-strategy | Pricing model design and optimization |
| product-strategy | End-to-end product strategy development |
| product-vision | Craft compelling product vision statements |
| startup-canvas | Startup-specific planning canvas |
| startup-ideation | Structured startup ideation |
| startup-pivoting | Evaluate and plan pivots |
| swot-analysis | Strengths, Weaknesses, Opportunities, Threats |
| systems-thinking | Model systems, feedback loops, and leverage points |
| value-proposition | Design and test value propositions |

### Leadership -- 17 skills

People management, org design, coaching, and executive readiness.

| Skill | What it does |
|-------|-------------|
| altitude-horizon-framework | Navigate strategic altitude and time horizons |
| building-team-culture | Design and reinforce team culture |
| coaching-pms | Coach and develop PM team members |
| cross-functional-collaboration | Improve cross-team coordination |
| delegating-work | Effective delegation frameworks |
| director-readiness-advisor | Assess readiness for Director-level PM roles |
| executive-onboarding-playbook | 30-60-90 day plans for executive onboarding |
| having-difficult-conversations | Navigate hard conversations productively |
| managing-up | Build effective relationships with leadership |
| onboarding-new-hires | Design PM onboarding programs |
| organizational-design | Structure PM organizations for impact |
| organizational-transformation | Lead org-level change initiatives |
| running-effective-1-1s | Get more out of one-on-one meetings |
| running-effective-meetings | Meeting design and facilitation |
| running-offsites | Plan and run productive offsites |
| team-rituals | Define and maintain team rituals |
| vp-cpo-readiness-advisor | Assess readiness for VP/CPO roles |

### Engineering-Adjacent -- 11 skills

The technical side of product management -- ADRs, tech debt, design systems, and architecture decisions.

| Skill | What it does |
|-------|-------------|
| design-engineering | Bridge design and engineering collaboration |
| design-systems | Evaluate and contribute to design systems |
| develop-adr | Write Architecture Decision Records |
| develop-design-rationale | Document design decision rationale |
| develop-solution-brief | Create lightweight solution briefs |
| develop-spike-summary | Summarize technical spike outcomes |
| engineering-culture | Understand and shape engineering culture |
| evaluating-new-technology | Framework for technology adoption decisions |
| managing-tech-debt | Prioritize and communicate tech debt |
| saas-scaffolder | Scaffold SaaS product architectures |
| ui-design-system | Design system component documentation |

### Marketing and Growth -- 9 skills

Content, community, positioning, and growth marketing.

| Skill | What it does |
|-------|-------------|
| community-building | Design community programs and engagement |
| content-marketing | Plan and create content marketing strategies |
| landing-page-generator | Generate high-converting landing page copy |
| marketing-ideas | Brainstorm marketing campaigns and tactics |
| media-relations | Plan media outreach and press strategy |
| north-star-metric | Define and validate north star metrics |
| positioning-ideas | Generate positioning statement candidates |
| product-name | Brainstorm and evaluate product names |
| value-prop-statements | Craft value proposition statements |

### Market Research -- 8 skills

Competitors, personas, journey maps, and market sizing.

| Skill | What it does |
|-------|-------------|
| competitive-teardown | Deep-dive product teardowns of competitors |
| competitor-analysis | Structured competitive landscape analysis |
| customer-journey-map | Map end-to-end customer journeys |
| market-segments | Identify and evaluate market segments |
| market-sizing | TAM/SAM/SOM market sizing |
| sentiment-analysis | Analyze customer sentiment from feedback data |
| user-personas | Create evidence-based user personas |
| user-segmentation | Segment users by behavior and attributes |

### AI Practice -- 7 skills

AI strategy, LLM development, evaluation, and readiness assessment.

| Skill | What it does |
|-------|-------------|
| ai-evals | Design evaluation frameworks for AI features |
| ai-product-strategy | Develop AI-specific product strategies |
| ai-shaped-readiness-advisor | Assess organizational AI readiness |
| building-with-llms | Guide for building LLM-powered products |
| context-engineering-advisor | Optimize context for AI systems |
| recommendation-canvas | Design recommendation system strategies |
| vibe-coding | Framework for rapid AI-assisted prototyping |

### Career -- 7 skills

Promotions, transitions, negotiation, and personal development.

| Skill | What it does |
|-------|-------------|
| building-a-promotion-case | Build a structured case for promotion |
| career-transitions | Navigate PM career transitions |
| energy-management | Manage energy for sustained performance |
| finding-mentors-sponsors | Find and cultivate mentors and sponsors |
| managing-imposter-syndrome | Strategies for imposter syndrome |
| negotiating-offers | Negotiate compensation and offers |
| personal-productivity | Personal productivity systems for PMs |

### Go-to-Market -- 7 skills

GTM motions, battlecards, growth loops, and ICP definition.

| Skill | What it does |
|-------|-------------|
| beachhead-segment | Identify beachhead market segments |
| competitive-battlecard | Create sales-ready competitive battlecards |
| growth-loops | Design and analyze growth loops |
| gtm-motions | Evaluate GTM motion options |
| gtm-strategy | Full go-to-market strategy development |
| ideal-customer-profile | Define ideal customer profiles |
| launch-checklist | Pre-launch readiness checklists |

### Sales -- 6 skills

Enterprise sales, founder-led sales, PLG, and compensation.

| Skill | What it does |
|-------|-------------|
| building-sales-team | Plan and structure sales team growth |
| enterprise-sales | Navigate enterprise sales cycles |
| founder-sales | Guide founder-led sales processes |
| product-led-sales | Design product-led sales motions |
| sales-compensation | Design sales compensation plans |
| sales-qualification | Lead qualification frameworks |

### Toolkit -- 5 skills

Utilities -- legal templates, writing tools, and meta-skills.

| Skill | What it does |
|-------|-------------|
| draft-nda | Generate NDA drafts |
| grammar-check | Grammar and style review |
| privacy-policy | Generate privacy policy drafts |
| review-resume | Review and improve PM resumes |
| skill-authoring-workflow | Create new skills for this system |

### Data and Analytics -- 4 skills

Experimentation, cohort analysis, and instrumentation.

| Skill | What it does |
|-------|-------------|
| ab-test-analysis | Analyze A/B test results with statistical rigor |
| cohort-analysis | Run cohort analysis on user data |
| measure-instrumentation-spec | Write instrumentation specifications |
| sql-queries | Generate SQL queries from plain English |

### Finance -- 3 skills

SaaS economics, pricing impact, and feature ROI.

| Skill | What it does |
|-------|-------------|
| feature-investment-advisor | Evaluate feature ROI and investment decisions |
| finance-based-pricing-advisor | Pricing analysis grounded in financial models |
| saas-economics-efficiency-metrics | SaaS efficiency metrics and benchmarking |

### Soft Skills -- 3 skills

Presentations, writing, and storytelling.

| Skill | What it does |
|-------|-------------|
| brand-storytelling | Craft compelling brand narratives |
| giving-presentations | Prepare and deliver effective presentations |
| written-communication | Improve PM writing and documentation |

---

## Subagents

Seven perspective-based evaluators that stress-test product decisions from different angles. Use them when you need a decision reviewed, a PRD critiqued, or a strategy pressure-tested.

| Subagent | Perspective | When to use |
|----------|------------|-------------|
| **customer-advocate** | Voice of the customer. Pushes back when solutions lack validated user pain. | Evaluating feature proposals, reviewing PRDs, checking discovery rigor |
| **business-strategist** | Competitive positioning, moats, flywheels, and market dynamics. | Strategy reviews, market entry decisions, business model evaluation |
| **data-analyst** | Quantitative rigor. Flags when decisions rely on intuition over evidence. | Metrics reviews, experiment design, OKR evaluation |
| **growth-pm** | Acquisition, activation, retention, revenue, referral. Thinks in loops and funnels. | Growth strategy, funnel analysis, retention initiatives |
| **engineering-lead** | Technical feasibility, engineering cost, system complexity, and tech debt. | Scope reviews, technical tradeoffs, architecture decisions |
| **design-lead** | UX quality, accessibility, and experience craft. | UX reviews, design critiques, accessibility audits |
| **risk-assessor** | Pre-mortem engine. Stress-tests for business, execution, market, and reputation risk. | Launch readiness, major bets, high-stakes decisions |

Subagents are currently generic templates. For best results, tailor them to your specific product, team, and domain context by editing the files in `.claude/subagents/`.

---

## Automations

Six recurring rituals that encode the rhythms of effective product management. Each automation chains skills and subagents together on a cadence.

| Ritual | Cadence | Trigger | What it does |
|--------|---------|---------|-------------|
| Daily standup prep | Every workday morning | `/standup` | Prepares standup notes, flags blockers, surfaces priorities |
| Weekly feedback analysis | Monday morning | `/weekly-feedback` | Synthesizes customer feedback from the past week |
| Sprint kickoff review | Sprint start | `/sprint-kickoff` | Reviews sprint scope, identifies risks, aligns the team |
| Sprint retro + lessons | Sprint end | `/retro` | Facilitates retrospective, captures lessons learned |
| Monthly competitive scan | First week of month | `/competitive-scan` | Scans competitive landscape for changes and threats |
| Quarterly strategy review | End of quarter | `/quarterly-review` | Reviews strategy progress, recalibrates priorities |

---

## Commands Quick Reference

All 36 slash commands, grouped by workflow.

### Discovery and Research

| Command | What it does |
|---------|-------------|
| `/discover` | Full discovery flow for a product or feature |
| `/interview prep` | Create a customer interview script |
| `/interview summarize` | Extract insights from an interview transcript |
| `/research-users` | Analyze user research data |
| `/brainstorm` | Generate ideas or experiments (ideas or experiments, existing or new) |
| `/triage-requests` | Prioritize incoming feature requests |

### Strategy and Planning

| Command | What it does |
|---------|-------------|
| `/strategy` | Product strategy deep-dive |
| `/business-model` | Business model canvas (lean, full, startup, or value-prop) |
| `/value-proposition` | Design value propositions |
| `/plan-okrs` | Generate and refine OKRs |
| `/north-star` | Define north star metrics |
| `/pricing` | Pricing model analysis |
| `/transform-roadmap` | Convert feature lists to outcome roadmaps |

### Execution and Delivery

| Command | What it does |
|---------|-------------|
| `/write-prd` | Guided PRD creation |
| `/write-stories` | Write user stories, job stories, or WWAs |
| `/sprint` | Sprint planning, retros, or release notes |
| `/test-scenarios` | Generate test scenarios from specs |
| `/pre-mortem` | Run a pre-mortem on a plan |
| `/stakeholder-map` | Map stakeholders for a project |
| `/meeting-notes` | Summarize meetings into action items |

### Go-to-Market and Growth

| Command | What it does |
|---------|-------------|
| `/plan-launch` | Go-to-market launch planning |
| `/growth-strategy` | Growth strategy and loops |
| `/market-product` | Marketing strategy and campaigns |
| `/battlecard` | Competitive battlecard creation |
| `/competitive-analysis` | Structured competitive analysis |
| `/market-scan` | Competitive landscape scan (SWOT + PESTLE + Porter's) |

### Data and Analytics

| Command | What it does |
|---------|-------------|
| `/setup-metrics` | Design metrics and instrumentation |
| `/analyze-test` | Analyze A/B test results |
| `/analyze-cohorts` | Run cohort analysis |
| `/analyze-feedback` | Synthesize customer feedback |
| `/write-query` | Generate SQL from plain English |
| `/generate-data` | Create realistic test datasets |

### Utilities

| Command | What it does |
|---------|-------------|
| `/proofread` | Grammar and style check |
| `/review-resume` | Review a PM resume |
| `/tailor-resume` | Tailor a resume to a job description |
| `/draft-nda` | Generate an NDA draft |
| `/privacy-policy` | Generate a privacy policy draft |

---

## Sources and Attribution

This system was built by merging and curating skills from six open-source PM skill repositories:

| Source | Contribution |
|--------|-------------|
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | Baseline system -- 63 skills, 36 commands, core architecture |
| [RefoundAI/lenny-skills](https://github.com/RefoundAI/lenny-skills) | 46 unique skills -- leadership, career, sales domains |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | 15 unique skills -- finance, validation, leadership transitions |
| [product-on-purpose/pm-skills](https://github.com/product-on-purpose/pm-skills) | 8 unique skills -- engineering-adjacent, edge cases |
| [alirezarezvani/claude-skills](https://github.com/alirezarezvani/claude-skills) | 4 unique skills -- landing pages, SaaS scaffolding, teardowns |
| [assimovt/productskills](https://github.com/assimovt/productskills) | 2 unique skills -- Shape Up bet-sizing, scope-cutting |

Skills were deduplicated, resolved for overlaps, and organized into a unified domain structure. Original authors and frameworks are credited within individual skill files.

Selected skills draw on the work of Teresa Torres, Marty Cagan, Alberto Savoia, Dan Olsen, Ash Maurya, Christina Wodtke, and others. Full attribution is preserved in each SKILL.md file.

---

## Project Structure

```
.claude/
  skills/              152 skills across 15 domains
    discovery/           22 skills
    execution/           25 skills
    strategy/            18 skills
    leadership/          17 skills
    engineering-adjacent/ 11 skills
    marketing-growth/     9 skills
    market-research/      8 skills
    ai-practice/          7 skills
    career/               7 skills
    go-to-market/         7 skills
    sales/                6 skills
    toolkit/              5 skills
    data-analytics/       4 skills
    finance/              3 skills
    soft-skills/          3 skills
  subagents/           7 perspective-based evaluators
  automations/         6 recurring ritual definitions
  commands/            36 slash commands
```

---

## License

MIT
