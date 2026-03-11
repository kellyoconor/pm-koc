# AI Product Requirements: Full Research (March 2026)

**Research Date:** March 11, 2026
**Purpose:** Comprehensive reference on how AI is transforming product requirements, discovery, and the PM lifecycle

---

## Part 1: External Landscape

### 1.1 Major Tools and Platforms

#### Tier 1: Purpose-Built AI PM Platforms

| Tool | What It Does | Pricing | Notable |
|------|-------------|---------|---------|
| **ChatPRD** | AI PRD generation, coaching, Linear integration, SOC 2 compliant | $8/mo basic, $24/user/mo team | 100K+ PMs, #1 in category. Generates PRDs from brief ideas, breaks into epics/stories in Linear |
| **Zeda.io** | AI-powered product discovery, feedback aggregation, revenue-aligned roadmaps | $499/mo+ | Integrates Salesforce, HubSpot, Amplitude. Teams report 50% sales growth, 90+ hrs saved |
| **BuildBetter** | Meeting insights, customer signal extraction, automated discovery | Varies | Saves 18 hrs/sprint, eliminates 26 meetings/month, 40% less operational work |
| **Productboard** | AI feedback categorization, feature prioritization, customer insight linking | Enterprise pricing | ML links customer feedback to feature ideas in seconds |

#### Tier 2: AI Features in Established Platforms

| Tool | AI Capabilities | Price |
|------|----------------|-------|
| **Figma Make** | AI PRD generator + interactive flow generation from requirements | Included |
| **Miro AI** | Generates PRDs with user stories, acceptance criteria, technical considerations | Included |
| **Notion AI** | Converts meeting notes to structured PRDs, generates acceptance criteria | $8/user/mo |
| **Coda AI** | Creates technical specs from user stories | $10/user/mo |
| **Atlassian Intelligence** | Summarizes threads, generates test cases for Jira, drafts PRDs in Confluence | Included |
| **Linear** | AI task prioritization, completion time prediction | $8/user/mo |
| **ClickUp AI** | Progress reporting automation, resource conflict detection | $7/user/mo |

#### Tier 3: AI-Native Newcomers

| Tool | Focus |
|------|-------|
| **Height** | AI-native project management, fast agentic iteration |
| **Dart AI** | AI-native task management |
| **Beam** | Agentic PRD workflows from briefs/notes/research |
| **WriteMyPRD** | Specialized PRD acceleration |
| **QuillBot PRD Generator** | Free structured PRD generation |

**Key Trend:** AI-native tools built around AI from inception iterate faster on agentic features than legacy platforms retrofitting AI. This gap will widen.

### 1.2 Thought Leadership

#### Miqdad Jaffer (Product Lead, OpenAI; former Director of Product, Shopify)

- Created the **4D Method for Building AI Products** with the AI PRD as foundational blueprint
- Key insight: AI products require **dual success metrics** — traditional user metrics (engagement, retention, conversion) AND AI-specific metrics (accuracy, hallucination rates, response quality)
- Applied the framework to Shopify's "Auto Write" LLM-powered feature

#### Aakash Gupta (Product Growth newsletter, 100K+ subscribers)

- Published "How to Write PRDs in the AI Era" and "AI Killed the 10-Page PRD"
- Core argument: The bad PRD is dead, not the PRD itself. Modern PRDs are "lighter, sharper, and example-heavy"
- Key shifts for AI-era PRDs:
  - Focus on boundaries and trade-offs rather than exhaustive specs
  - Include example prompts and expected outputs (AI is probabilistic, not deterministic)
  - Address deployment strategy upfront
  - The skill has shifted from doing the design to writing the PRD

#### Lenny Rachitsky (Lenny's Newsletter/Podcast)

- "Make Product Management Fun Again with AI Agents" (May 2025) with Tal Raviv
- "How AI is Reshaping the Product Role" with Oji and Ezinne Udezue
- Key message: Operationalizing AI agents is harder than the hype suggests, but productivity gains are real

#### Shreyas Doshi (former Stripe, Twitter, Google)

- Continues shaping PM frameworks (LNO, pre-mortems) being adapted for AI-augmented workflows
- Teaching "Managing Your PM Career in 2025 and Beyond" on Maven
- Focus: High-agency PM traits matter more in an AI world

#### LogRocket: "3 AI Shockwaves Reshaping Product Management in 2026"

- AI agents are now users too — they consume APIs, trigger flows, negotiate pricing, and make decisions
- PMs must design for both human AND machine users
- "2026 is the first year when product management must consciously evolve beyond the classical skill set"

#### Harvard Business Review (Feb 2026)

- "To Drive AI Adoption, Build Your Team's Product Management Skills"
- PM skills (problem definition, experimentation, tool integration) are the key to enterprise AI adoption
- Without a product-minded approach, employees' AI use remains "shallow or short-lived"

### 1.3 Emerging Frameworks

1. **Copilot-to-Agentic Maturity Model** — Evaluates 51 tools across a spectrum. Only 25% score 4-5 on agentic capability.
2. **Dual Metrics Framework** (Miqdad Jaffer/OpenAI) — Every AI feature needs both traditional product metrics and AI-quality metrics.
3. **The Living PRD** (Aakash Gupta) — PRDs as continuously updated artifacts rather than static handoff documents.
4. **Manager of Robots** (Product Leaders Day India) — The PM as orchestrator of autonomous AI agents.

### 1.4 How the PM Role Is Shifting

#### What Is Being Automated

| Activity | Before AI | After AI |
|----------|-----------|----------|
| PRD first drafts | 4-8 hours | 10-30 minutes |
| User story writing | 2-4 hours per epic | Minutes |
| Feedback synthesis | 30% of weekly time | Continuous AI aggregation |
| Competitive research | Days of analysis | Continuous monitoring |
| Meeting notes/action items | Manual | Automatic transcription + insight |
| Data gathering/reporting | Hours of dashboard building | AI surfaces anomalies proactively |

**Average time savings: 6-9 hours per week per PM** (multiple sources corroborate).

#### What Is Becoming More Important

1. Strategic judgment — deciding what NOT to build
2. Problem framing — ensuring the right problems are being solved
3. Stakeholder alignment — more options means more conflicts
4. AI governance — what AI agents can do autonomously vs. requiring human review
5. Prompt engineering / AI literacy
6. Cross-functional orchestration — managing human + AI workforce
7. Ethical oversight — bias, hallucination, privacy, trust

#### The New PM Archetype

"The PM role has become a hybrid of strategist, systems thinker, and AI-literate builder" (LogRocket). PMs are becoming "Managers of Robots" (Product Leaders Day India).

Job market data:
- "AI Product Manager" roles command premium salaries
- US management occupations projected to grow faster than average 2025-2034
- Demand is for PMs who understand AI, not PMs replaced by AI

### 1.5 Open-Source PM Skills Ecosystem

| Project | Author | Skills | Focus |
|---------|--------|--------|-------|
| **phuryn/pm-skills** | Pawel Huryn | 65+ skills, 36 commands | Full PM workflow |
| **RefoundAI/lenny-skills** | Refound AI | 86 skills | Distilled from 100+ Lenny's Podcast episodes |
| **deanpeters/Product-Manager-Skills** | Dean Peters | 46 skills, 6 workflows | Battle-tested, multi-turn. Updated March 9, 2026 |
| **product-on-purpose/pm-skills** | Product on Purpose | 24+ skills | Best-practice plug-and-play |
| **alirezarezvani/claude-skills** | Alireza Rezvani | 4 unique skills | Landing pages, SaaS scaffolding |
| **assimovt/productskills** | Assimov | 2 unique skills | Shape Up bet-sizing, scope-cutting |

**Broader ecosystem signals:**
- Medium article: "Turn Claude Into a Product Manager: 100+ Open-Source PM Skills You Can Install Today"
- Product Compass featured PM Skills Marketplace as "An AI Operating System for Better Product Decisions"
- Dedicated site (ccforpms.com) offers tutorials on "Claude Code for Product Managers"

### 1.6 Maturity Levels

| Level | Description | % of Teams |
|-------|-------------|-----------|
| Level 1: Manual | Traditional PRD writing, no AI | ~20% |
| Level 2: AI-Assisted | Ad-hoc ChatGPT/Claude drafting | ~40% |
| Level 3: AI-Integrated | Purpose-built tools embedded in workflow | ~25% |
| Level 4: AI-Copilot | AI proactively suggests, reviews, improves | ~12% |
| Level 5: AI-Agentic | AI autonomously detects needs, runs validation | ~3% |

### 1.7 Risks and Watch Items

#### Risks

1. **Over-reliance on AI-generated requirements** — plausible-sounding but strategically wrong PRDs
2. **Governance gaps** — enterprise risk teams will demand answers about autonomous AI decisions
3. **Quality degradation** — PMs as editors rather than thinkers
4. **Tool fragmentation** — 51+ tools, risk of fatigue
5. **Data privacy** — customer feedback flowing through AI tools needs SOC 2 compliance

#### Watch (Next 12 Months)

1. Agentic PM tools maturing (25% today -> 50%+ by early 2027)
2. AI governance frameworks for PM tools
3. Tool landscape consolidation through acquisitions
4. Open-source PM skills challenging commercial tools
5. AI PM certification becoming expected on resumes

---

## Part 2: Kelly's PM Operating System — Internal Capabilities

### 2.1 The Requirements Pipeline (5 Phases)

```
DISCOVERY -> STRATEGY -> REQUIREMENTS -> DELIVERY -> LEARNING
    |            |            |              |            |
    v            v            v              v            v
 Validated    Strategic    Executable     Shipped      Lessons
 Problem      Direction    Backlog       Feature      Fed Back
```

### 2.2 Phase 1: Discovery (Understanding What to Build)

**Goal:** Validate a problem is worth solving before investing in a solution.

**Key Skills:**
- `/interview prep` — Mom Test + YC 5 Questions framework
- `interview-script` — Structured guides with JTBD probing
- `summarize-interview` — Transcripts -> structured summaries with JTBD, pains, verbatim quotes
- `problem-statement` — Empathy-driven narrative + validation scoring (Frequency x Intensity x Workarounds x WTP)
- `jtbd-analysis` — Functional, social, emotional jobs + Forces of Progress (Push/Pull/Anxiety/Habit)
- `identify-assumptions` — Surfaces risks across 8 categories (Value, Usability, Viability, Feasibility, Ethics, GTM, Strategy, Team)
- `opportunity-solution-tree` — Desired Outcome -> Opportunities -> Solutions (3+ each) -> Experiments

**Command:** `/discover [idea]` chains brainstorm -> assumptions -> prioritize -> experiments

**Output:** Validated problem + prioritized risks to test

### 2.3 Phase 2: Strategy (Deciding What Direction Wins)

**Key Skills:**
- `product-vision` — North star framing
- `product-strategy` — 9-section canvas (vision, segments, value props, trade-offs, metrics, growth, capabilities, defensibility)
- `epic-hypothesis` — If/then testable statements with lightweight validation
- `prioritize-features` — RICE, ICE, or Opportunity Score

**Subagents for stress-testing:**
- customer-advocate, business-strategist, data-analyst, growth-pm

**Command:** `/strategy [product]`

**Output:** Strategy document + validated hypothesis

### 2.4 Phase 3: Requirements (Specifying What to Build)

#### PRD Creation (`create-prd`)

11-phase template:
1. Executive Summary (1 sentence: what, for whom, why now, impact)
2. Problem Statement (persona, problem, evidence — no solutions)
3. Goals & Key Results (measurable OKRs with baselines & targets)
4. Target Users & Segments
5. Strategic Context (why now, competitive landscape)
6. Solution Overview (high-level, NOT implementation details)
7. Requirements (P0/P1/P2 with acceptance criteria; 3-5 P0s max)
8. Success Metrics (primary + secondary + guardrails/counter-metrics)
9. Scope Boundaries (in/out/deferred with rationale)
10. Dependencies, Risks, Open Questions
11. Release Plan (MVP vs. future iterations)

**Quality Checklist:**
- Problem + "why now" backed by evidence
- All metrics have counter-metrics
- P0 requirements number 3-5 (not 10+)
- Out-of-scope section present and justified
- No implementation details
- Readable in under 15 minutes
- Target 1500-2500 words

**Common Pitfalls:**
- Solution-first (rewrite to lead with problem)
- No evidence (flag as "opinion-driven")
- Over-specified (strip to PRD level)
- No scope boundaries (invites scope creep)
- Weasel metrics ("improve engagement" -> replace with numbers)
- Too many P0s (force-rank to max 5)

#### User Stories & Story Mapping

- `user-stories` — 3 C's (Card, Conversation, Confirmation) + INVEST validation + Gherkin acceptance criteria
- `user-story-mapping` — Jeff Patton framework: horizontal (activities over time) x vertical (priority)
- `epic-breakdown-advisor` — Humanizing Work's 9 splitting patterns applied in sequence

**Three formats supported:** User stories, Job stories (JTBD-style), WWA (business-context)

**Command:** `/write-stories [user|job|wwa] [feature/PRD]` -> 5-15 sprint-sized stories

### 2.5 Phase 4: Delivery (Getting to Shipped Code)

- `sprint-plan` — Capacity-based planning with dependencies and risk flags
- `scope-cutting` — Shape Up philosophy: appetite-first, variable scope, max 5 must-haves
- `test-scenarios` — Happy path, edge cases, error states
- `shipping-products` — Pre-launch checklist

### 2.6 Phase 5: Learning (Did It Work?)

- `outcome-roadmap` — Maps features back to outcomes (metric moved, not feature shipped)
- `retro` — What worked, what didn't, what to change
- `weekly-feedback-analysis` — Emerging patterns from customer feedback

### 2.7 Subagents: Multi-Perspective Evaluation

Available at any phase to stress-test decisions:

| Subagent | Focus |
|----------|-------|
| customer-advocate | Evidence-based customer problem validation |
| business-strategist | Competitive positioning, moats, market dynamics |
| data-analyst | Metrics, measurement, statistical rigor |
| growth-pm | Funnels, loops, AARRR, compounding effects |
| engineering-lead | Feasibility, complexity, tech debt, scope |
| design-lead | UX quality, accessibility, experience craft |
| risk-assessor | Pre-mortem, assumptions, blast radius |

### 2.8 Automations: Recurring Rituals

| Automation | Cadence | Purpose |
|-----------|---------|---------|
| Daily standup prep | Every workday AM | Surface blockers |
| Weekly feedback analysis | Monday AM | Identify emerging patterns |
| Sprint kickoff review | Sprint start | Align on goals + risks |
| Sprint retro + lessons | Sprint end | What worked, what to change |
| Monthly competitive scan | 1st week/month | Track competitive moves |
| Quarterly strategy review | End of quarter | Validate/pivot strategy |

### 2.9 Orchestrating Commands

| Command | Chains | Output |
|---------|--------|--------|
| `/discover` | brainstorm -> assumptions -> prioritize -> experiments | Discovery Plan |
| `/write-prd` | context gathering -> create-prd -> review loops | PRD (8 sections, 1500-2500 words) |
| `/write-stories` | user-stories -> story-mapping -> splitting | Prioritized backlog (5-15 stories) |
| `/strategy` | product-strategy -> all 9 sections | Strategy Canvas |
| `/interview prep` | interview-script (Mom Test) | Interview guide + note template |
| `/interview summarize` | summarize-interview | Insights with JTBD, pains, quotes |
| `/sprint` | sprint-plan | Capacity plan with risks |
| `/plan-launch` | GTM skills + pre-mortem | GTM strategy + launch checklist |

### 2.10 The Full Pipeline in Practice (Example)

**Scenario:** 60% drop-off during onboarding for non-technical small business owners.

**Step 1: Validate** (`/interview`) — 5-7 churn interviews. All 5 churners stuck at "invite teammate."

**Step 2: Frame** (`/discover`) — Opportunity: users don't understand team structure. 3 solution ideas generated. Prototype checklist tested with 10 users -> 80% completion.

**Step 3: Specify** (`/write-prd`) — PRD with evidence-backed problem, activation metric (40% -> 60%), guardrail (signup conversion stays at 10%).

**Step 4: Decompose** (`/write-stories user`) — 5 stories with Gherkin acceptance criteria.

**Step 5: Plan** (`/sprint`) — 10 story points committed, risks flagged, 2-week timeline.

**Step 6: Learn** (post-launch) — Activation hits 58% (near target). Checklist completion 75% (below 80% target). Next iteration identified.

---

## Part 3: Gap Analysis

### What This System Has That Others Don't

1. **Evidence-first requirements** — Every requirement traces to customer evidence
2. **Problem-before-solution discipline** — Strict phase gates prevent building the wrong thing
3. **AI-augmented at each phase** — Not just drafting, but discovery, decomposition, validation, and learning
4. **Outcome vs. output focus** — "Reduce abandonment by 20%" not "Ship dark mode"
5. **Scope discipline** — Shape Up appetite-first approach prevents feature creep
6. **7 simultaneous perspectives** — No other open-source system offers subagent architecture

### What's Missing or Immature

1. **Subagents are generic** — Don't know Kelly's product, customers, or market
2. **17 overlapping domains** — Multiple implementations need consolidation
3. **AI governance** — No framework for what agents can autonomously decide
4. **Machine-readable PRDs** — Not yet structured for downstream AI consumption
5. **Continuous discovery** — Skills are on-demand; cutting edge is always-on signal ingestion
6. **Dual metrics** — No AI-specific quality metrics framework
7. **Gap skills not yet built:** accessibility, data infrastructure, AI governance, revenue forecasting, compliance, remote team mgmt, product sunset

---

## Sources

### External
- ChatPRD — chatprd.ai
- Zeda.io — zeda.io
- BuildBetter — blog.buildbetter.ai
- Figma AI PRD Generator — figma.com/solutions/ai-prd-generator/
- Miro AI PRD Generator — miro.com/ai/product-development/ai-prd/
- Miqdad Jaffer AI PRD Template — productcompass.pm
- Aakash Gupta — news.aakashg.com
- Lenny Rachitsky — lennysnewsletter.com
- HBR (Feb 2026) — "To Drive AI Adoption, Build Your Team's Product Management Skills"
- LogRocket — "3 AI Shockwaves Reshaping Product Management in 2026"
- AI PM Tools Directory — aipmtools.org
- Product Leaders Day India — productleadersdayindia.org
- ccforpms.com — Claude Code for Product Managers

### Internal (This Repo)
- `.claude/skills/execution/create-prd/SKILL.md`
- `.claude/skills/discovery/interview-script/SKILL.md`
- `.claude/skills/discovery/problem-statement/SKILL.md`
- `.claude/skills/discovery/jtbd-analysis/SKILL.md`
- `.claude/skills/discovery/opportunity-solution-tree/SKILL.md`
- `.claude/skills/execution/user-stories/SKILL.md`
- `.claude/skills/execution/user-story-mapping/SKILL.md`
- `.claude/skills/execution/epic-breakdown-advisor/SKILL.md`
- `.claude/skills/execution/sprint-plan/SKILL.md`
- `.claude/skills/execution/scope-cutting/SKILL.md`
- `.claude/subagents/*.md`
- `.claude/automations/*.md`
- `.claude/commands/*.md`
