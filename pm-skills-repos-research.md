# PM Skills, Frameworks & Plugins for AI Assistants -- Repository Research

**Date:** 2026-03-11
**Purpose:** Comprehensive inventory of GitHub repos containing product management skills, frameworks, or plugins designed for AI assistants (Claude Code, Cursor, Codex, ChatGPT, etc.)

---

## TIER 1: Major PM Skills Frameworks (Comprehensive, Well-Structured, Active)

### 1. phuryn/pm-skills (PM Skills Marketplace)
- **URL:** https://github.com/phuryn/pm-skills
- **Contains:** 100+ agentic skills, commands, and plugins
- **Structure:** Three-layer architecture: Skills (domain knowledge/frameworks), Commands (user-triggered workflows via /command-name), Plugins (grouped skill+command packages by PM domain)
- **PM Domains:** Discovery, strategy, execution, launch, growth. Covers PRDs, OKRs, roadmaps, sprints, retros, release notes, pre-mortems, stakeholder management, user stories, prioritization
- **Scale:** 65 PM skills, 36 chained workflows, 8 plugins
- **Frameworks Used:** Teresa Torres, Marty Cagan, Alberto Savoia
- **Adaptability:** Already in plugin format. This is the reference repo the user mentioned. Excellent structure to model after.

### 2. deanpeters/Product-Manager-Skills
- **URL:** https://github.com/deanpeters/Product-Manager-Skills
- **Contains:** 46 ready-to-use PM skills + 6 reusable command workflows
- **Structure:** SKILL.md format, works with Claude Code, Cowork, Codex, ChatGPT, Gemini
- **PM Domains:** Problem framing, opportunity hunting, validation experiments, killing bad bets, classic business strategy (Ansoff, BCG, Porter's 5 Forces, Blue Ocean, SWOT), PM career arc (PM to Director to VP/CPO)
- **Version:** v0.7 (released March 9, 2026)
- **Docs:** Includes guides for using with Claude, Codex, ChatGPT, and building custom skills
- **Adaptability:** Very mature. Well-documented. Multi-platform support. High merge potential.

### 3. product-on-purpose/pm-skills
- **URL:** https://github.com/product-on-purpose/pm-skills
- **Contains:** 25 production-ready skills (24 phase skills + 1 foundation persona skill) + workflow bundles
- **Structure:** Triple Diamond Framework organizing Discover/Define/Develop/Deliver/Measure/Iterate phases. Slash commands (/prd, /hypothesis). SKILL.md files. Follows Agent Skills Specification.
- **PM Domains:** Full product lifecycle via Triple Diamond. PRD generation, hypothesis testing, discovery
- **Compatibility:** Claude Code (slash commands), GitHub Copilot, Cursor, Windsurf (via AGENTS.md auto-discovery)
- **License:** Apache 2.0
- **Adaptability:** Excellent structure. Standards-compliant. Easy to merge.

### 4. alirezarezvani/claude-skills
- **URL:** https://github.com/alirezarezvani/claude-skills
- **Contains:** 180+ production-ready skills & plugins across multiple domains
- **Structure:** Organized by team/domain (product-team/, engineering/, marketing/, compliance/, c-level/). Each skill has SKILL.md. Install via /plugin marketplace or npx agent-skills-cli.
- **PM Domains (product-team/):** Product Manager Toolkit (RICE, MoSCoW, Kano, JTBD, customer interview analysis, PRD templates, discovery frameworks, GTM strategies), Product Strategist, UI Design System
- **Scripts:** Includes Python scripts (e.g., rice_prioritizer.py)
- **Adaptability:** Massive collection. Product-team subfolder is directly relevant. Modular structure allows cherry-picking.

### 5. RefoundAI/lenny-skills
- **URL:** https://github.com/RefoundAI/lenny-skills
- **Contains:** 86 product management skills distilled from Lenny's Podcast
- **Structure:** Markdown skill files. Install via `npx skills add`. Individual skill selection supported.
- **PM Domains:** Hiring, user research, strategy, shipping, product operations, AI product strategy, team management, career development
- **Sources:** Wisdom from Shreyas Doshi, Marty Cagan, Elena Verna, and 90+ leaders from 100+ podcast episodes
- **Adaptability:** Unique content source (podcast wisdom). High-quality PM thinking. Good for supplementing frameworks with real-world advice.

---

## TIER 2: Focused PM Skill Collections (Smaller but High Quality)

### 6. menkesu/awesome-pm-skills
- **URL:** https://github.com/menkesu/awesome-pm-skills
- **Contains:** 28 AI-powered PM skills from Lenny's Podcast
- **Structure:** Organized by use case (e.g., "I'm starting a new AI feature" activates multiple skills). Clone into Cursor/Claude Code workspace.
- **PM Domains:** Zero-to-launch, continuous discovery, AI product patterns, strategic builds
- **Sources:** Brian Chesky, Shreyas Doshi, Kevin Weil, Dylan Field, Marty Cagan, 40+ leaders
- **Author:** Udi Menkes, AI Product Leader at Intuit
- **Adaptability:** Well-organized by use case. Could merge as a "Lenny's Wisdom" plugin.

### 7. pratikshadake/claude-product-management-skills
- **URL:** https://github.com/pratikshadake/claude-product-management-skills
- **Contains:** Production-grade Claude Code skills for product thinking
- **Structure:** SKILL.md format. Install via `npx add-skill`. Auto-activation or explicit invocation.
- **PM Domains:** Problem Clarity Engine (assumption ranking: desirability/feasibility/viability), JTBD translator, prioritization scoring (impact/revenue/alignment/confidence/effort), user segmentation (pain severity/willingness to pay/reachability)
- **Adaptability:** Focused and deep. Each skill is well-defined. Easy to merge as discovery/prioritization plugins.

### 8. Digidai/product-manager-skills
- **URL:** https://github.com/Digidai/product-manager-skills
- **Contains:** PM skill for Claude Code, Codex, Cursor, Windsurf
- **Structure:** Pure Markdown. Single comprehensive skill file.
- **PM Domains:** SaaS metrics diagnosis, PRD critique (flags bad framing, missing metrics, solution smuggling, delivery risk), roadmap/strategy pressure-testing, PM career coaching (PM to Director to VP transitions)
- **Adaptability:** Unique SaaS metrics and career coaching angle. Could supplement strategy plugins.

### 9. aakashg/pm-claude-skills
- **URL:** https://github.com/aakashg/pm-claude-skills
- **Contains:** 5 Claude Code skills for product managers
- **Structure:** Drop into .claude/skills/ folder. Natural language triggers.
- **PM Domains:** Idea validation, LinkedIn post writing, design review (UX), prompt engineering, status update writing
- **Adaptability:** Lightweight. Communication-focused skills are unique (LinkedIn, status updates).

### 10. aakashg/pm-claude-code-setup
- **URL:** https://github.com/aakashg/pm-claude-code-setup
- **Contains:** Production-ready CLAUDE.md config + 6 PM skills + 4 templates
- **Structure:** CLAUDE.md in project root (context, writing rules, sub-agent roles, output standards, skills reference, MCP connections). 60-second setup.
- **PM Domains:** General PM workflow configuration. Sub-agent perspectives. Part of larger "PM Operating System" (41+ skills, 7 sub-agent perspectives).
- **Adaptability:** The CLAUDE.md config approach is complementary to skills. Could serve as the "base configuration" layer.

### 11. lautarogiambroni/claude-code-for-pms
- **URL:** https://github.com/lautarogiambroni/claude-code-for-pms
- **Contains:** 10 curated Claude Code skills for Product Managers
- **Structure:** Skills work in sequence: Brainstorming (#1) -> Writing Plans (#2) -> Subagent Development (#4) -> Verification (#3). Skills 6-10 for independent research/communication.
- **PM Domains:** Brainstorming, planning, development execution, verification, research, presentations
- **Adaptability:** Nice workflow sequencing. Could inform command chaining logic.

### 12. assimovt/productskills
- **URL:** https://github.com/assimovt/productskills
- **Contains:** Product skills for AI agents
- **Structure:** 50-150 lines each, no fluff. Install via `npx skills add`. MIT-style.
- **PM Domains:** Discovery, strategy, prioritization, PRD writing
- **Frameworks Used:** Mom Test, Shape Up, Obviously Awesome, Teresa Torres
- **Author:** Tair Asim
- **Adaptability:** Lean and opinionated. Each skill encodes a specific book/framework. Great for focused, framework-specific plugins.

---

## TIER 3: PRD-Specific Tools & Generators

### 13. christerjohansson/ai-product-requirement-document
- **URL:** https://github.com/christerjohansson/ai-product-requirement-document
- **Contains:** Markdown files for AI-assisted PRD workflow
- **Structure:** Three files: create-prd.md, generate-tasks.md, process-task-list.md
- **Workflow:** PRD creation -> task breakdown -> step-by-step execution with approval gates
- **Compatibility:** Cursor, Claude Code, Windsurf
- **Adaptability:** Simple but effective workflow. Could be a single "prd-to-tasks" command/skill.

### 14. anombyte93/prd-taskmaster
- **URL:** https://github.com/anombyte93/prd-taskmaster
- **Contains:** Claude Code skill for PRD generation with Taskmaster integration
- **Structure:** Installed to ~/.claude/skills/prd-taskmaster/
- **PM Domains:** PRD generation, task breakdown, effort estimation, TDD workflow, validation
- **Features:** AI product manager Q&A -> comprehensive PRD -> AI task generation. TDD by default, blind-validator agent, parallel tasks, quality gates.
- **Adaptability:** Unique Taskmaster integration. Bridge between PM and engineering execution.

### 15. Njengah/prd-dxt
- **URL:** https://github.com/Njengah/prd-dxt
- **Contains:** Claude Desktop Extension (DXT) for PRD generation from README files
- **Structure:** DXT package format. One-click install.
- **PM Domains:** PRD generation (project overview, description, key features, technical requirements)
- **Adaptability:** Lightweight. DXT format is different from skills format but concept is portable.

### 16. Saml1211/PRD-MCP-Server
- **URL:** https://github.com/Saml1211/PRD-MCP-Server
- **Contains:** MCP server for PRD generation from codebase context
- **Structure:** Node.js MCP server. Template library. PRD validator.
- **PM Domains:** PRD generation, PRD validation against industry standards, template management
- **Adaptability:** MCP server approach is complementary to skills. Could be integrated as an MCP tool alongside skills.

---

## TIER 4: Prompt Collections & Development Frameworks

### 17. deanpeters/product-manager-prompts
- **URL:** https://github.com/deanpeters/product-manager-prompts
- **Contains:** Generative AI prompts for product managers
- **Structure:** Conversational prompts (not templates). Comments teach AI how to be helpful.
- **PM Domains:** Jobs-to-be-Done, User Story Templates, stakeholder management, roadmaps
- **Compatibility:** ChatGPT, Claude, Gemini (copy-paste into any AI)
- **Adaptability:** Prompts could be converted to SKILL.md format. Good source of PM methodology.

### 18. TechNomadCode/AI-Product-Development-Toolkit
- **URL:** https://github.com/TechNomadCode/AI-Product-Development-Toolkit
- **Contains:** User-centered product development prompt templates
- **Structure:** Phase-based: MVP, Ultra-Lean-MVP, Testing, v0-Design, PRD
- **PM Domains:** Product specification, MVP planning, testing, design prototyping
- **Adaptability:** Template-based. Could be adapted into skills with guided Q&A flow.

### 19. benjaminshoemaker/ai_coding_project_base
- **URL:** https://github.com/benjaminshoemaker/ai_coding_project_base
- **Contains:** Structured prompt framework for building software products with AI
- **Structure:** Three phases: Specify (produces PRODUCT_SPEC.md + TECHNICAL_SPEC.md), Plan (EXECUTION_PLAN.md + AGENTS.md), Execute (task-by-task with verification)
- **PM Domains:** Product specification, technical design, implementation planning, requirement traceability
- **Adaptability:** Comprehensive spec-driven framework. Could inform a "full-cycle" workflow bundle.

### 20. jinjin1/Cursor-for-Product-Managers
- **URL:** https://github.com/jinjin1/Cursor-for-Product-Managers
- **Contains:** AI-assisted PM workflow using Cursor IDE
- **Structure:** Directory template with company context (OKRs, vision, strategy, team), active initiatives (interviews, opportunity maps, assumption tests, solutions, design briefs, PRDs, analytics), meeting notes
- **PM Domains:** Continuous discovery (Teresa Torres), evidence-guided development (Itamar Gilad), product strategy review, ICE scoring
- **Adaptability:** Directory structure approach. Skills could be extracted from the workflow commands.

---

## TIER 5: Curated Lists & Meta-Resources

### 21. heilcheng/awesome-agent-skills
- **URL:** https://github.com/heilcheng/awesome-agent-skills
- **Contains:** Curated list of skills, tools, tutorials for AI coding agents
- **PM Domains:** Catalogs PM skills among other categories
- **Adaptability:** Reference/discovery resource, not directly mergeable.

### 22. dend/awesome-product-management
- **URL:** https://github.com/dend/awesome-product-management
- **Contains:** Curated list of PM resources for learning and growth
- **PM Domains:** Broad PM education resources
- **Adaptability:** Reference list. Not structured as AI skills but could inform skill content.

### 23. ProductHired/open-product-management
- **URL:** https://github.com/ProductHired/open-product-management
- **Contains:** Curated list of PM advice for technical people
- **PM Domains:** General PM knowledge
- **Adaptability:** Reference material, not AI-skill formatted.

### 24. carlvellotti/claude-code-pm-course
- **URL:** https://github.com/carlvellotti/claude-code-pm-course
- **Contains:** Interactive course teaching PMs to use Claude Code
- **Structure:** Module-based (fundamentals, advanced PM work). Practice company (TaskFlow). Includes .claude/skills/ folder with skills.
- **PM Domains:** PRD writing, product data analysis, competitive strategy, file operations
- **Adaptability:** Educational resource with embedded skills. Skills could be extracted.

---

## TIER 6: Commercial/Hybrid Resources (Not Fully Open Source)

### 25. ChatPRD (chatprd.ai)
- **URL:** https://www.chatprd.ai/ (commercial, not open source)
- **Contains:** AI platform for PRD generation, document review, coaching
- **PM Domains:** PRDs, user stories, technical specs, GTM briefs
- **Integrations:** GitHub, Linear, Notion, Slack, v0, Lovable, bolt.new
- **Pricing:** From $5/month
- **Adaptability:** Commercial product. ChatPRD's system prompt was leaked/documented at github.com/tjadamlee/GPTs-prompts (45.ChatPRD.md). That prompt could inform skill design.

### 26. prodmgmt.world
- **URL:** https://www.prodmgmt.world/claude-code
- **Contains:** 180+ Claude Code Skills for PMs ($29 paid)
- **PM Domains:** User research, product strategy, stakeholder management, decision making
- **Format:** Individual Markdown files usable as /skills in Claude Code, importable to Obsidian/Notion
- **Adaptability:** Paid resource. Cannot directly merge but can inform what skills to build.

---

## SUMMARY TABLE

| # | Repo | Skills Count | Format | Key Differentiator | Merge Priority |
|---|------|-------------|--------|-------------------|---------------|
| 1 | phuryn/pm-skills | 65+ skills, 36 workflows | Plugins/Commands/Skills | Reference architecture | BASELINE |
| 2 | deanpeters/Product-Manager-Skills | 46 skills, 6 workflows | SKILL.md | Battle-tested, multi-platform | HIGH |
| 3 | product-on-purpose/pm-skills | 25 skills + bundles | SKILL.md + Triple Diamond | Standards-compliant | HIGH |
| 4 | alirezarezvani/claude-skills | 180+ (PM subset) | SKILL.md + scripts | Broadest collection | HIGH |
| 5 | RefoundAI/lenny-skills | 86 skills | Markdown | Podcast-sourced wisdom | HIGH |
| 6 | menkesu/awesome-pm-skills | 28 skills | Markdown | Use-case organized | MEDIUM |
| 7 | pratikshadake/claude-product-management-skills | 4 deep skills | SKILL.md | Discovery/prioritization depth | MEDIUM |
| 8 | Digidai/product-manager-skills | 1 comprehensive | Markdown | SaaS metrics + career coaching | MEDIUM |
| 9 | aakashg/pm-claude-skills | 5 skills | SKILL.md | Communication skills | LOW |
| 10 | aakashg/pm-claude-code-setup | 6 skills + CLAUDE.md | Config + Skills | Base config approach | MEDIUM |
| 11 | lautarogiambroni/claude-code-for-pms | 10 skills | SKILL.md | Workflow sequencing | LOW |
| 12 | assimovt/productskills | ~5 skills | Markdown | Framework-per-skill | MEDIUM |
| 13 | christerjohansson/ai-product-requirement-document | 3 prompts | Markdown | PRD-to-tasks workflow | LOW |
| 14 | anombyte93/prd-taskmaster | 1 skill | SKILL.md | Taskmaster integration | MEDIUM |
| 15 | Njengah/prd-dxt | 1 DXT | DXT package | Claude Desktop extension | LOW |
| 16 | Saml1211/PRD-MCP-Server | MCP server | Node.js MCP | PRD from codebase context | MEDIUM |
| 17 | deanpeters/product-manager-prompts | ~20 prompts | Markdown prompts | Conversational PM prompts | MEDIUM |
| 18 | TechNomadCode/AI-Product-Development-Toolkit | ~5 templates | Markdown | MVP/lean templates | LOW |
| 19 | benjaminshoemaker/ai_coding_project_base | 3-phase framework | Markdown + commands | Spec-driven development | MEDIUM |
| 20 | jinjin1/Cursor-for-Product-Managers | Workflow template | Directory structure | Teresa Torres + Itamar Gilad | MEDIUM |
| 21-24 | Meta-resources / courses | N/A | Various | Discovery/education | REFERENCE |

---

## HOW TO ACTUALLY USE PM SKILLS (Beginner to Power User)

### Beginner: "I just want to get started"

**What you need:** Claude Code (CLI) or Claude Cowork (desktop app). That's it.

**Step 1: Install skills (one-time, ~2 minutes)**

The easiest path — install pm-skills marketplace in Claude Cowork:
1. Open Cowork → Customize (bottom-left) → Browse plugins → Personal → +
2. Select "Add marketplace from GitHub"
3. Enter: `phuryn/pm-skills`
4. Done. All 8 plugins install automatically.

Or in Claude Code CLI:
```bash
claude plugin marketplace add phuryn/pm-skills
claude plugin install pm-toolkit@pm-skills
claude plugin install pm-product-strategy@pm-skills
claude plugin install pm-product-discovery@pm-skills
# ... install whichever plugins you need
```

**Step 2: Just talk to Claude like a colleague**

You don't need to memorize commands. Start with natural language:

| You say... | What happens |
|------------|-------------|
| "I have a new app idea for dog walkers" | Claude activates discovery skills automatically |
| "Help me write a PRD" | Claude loads the PRD skill and walks you through it step by step |
| "Who are my competitors?" | Claude runs competitive analysis frameworks |
| "How should I prioritize my backlog?" | Claude pulls in RICE, MoSCoW, or Kano depending on context |

Skills load automatically when relevant — you don't have to invoke them explicitly.

**Step 3: Use slash commands when you want a specific workflow**

When you want a guided, structured process:

| Command | What it does | When to use it |
|---------|-------------|----------------|
| `/discover` | Chains: brainstorm → assumptions → prioritize → experiments | Starting from scratch with a new idea |
| `/strategy` | Product strategy deep-dive | Defining vision, positioning, differentiation |
| `/write-prd` | Guided PRD creation | Ready to spec out a feature |
| `/plan-launch` | Go-to-market planning | Preparing to ship |
| `/north-star` | Define your key metric | Setting up measurement |
| `/competitive-analysis` | Structured competitor review | Understanding your market |
| `/value-proposition` | Value prop canvas | Clarifying why customers should care |

Each command walks you through questions, produces a structured output, and suggests what to do next.

**Beginner tips:**
- Start with `/discover` for new ideas or `/write-prd` for features you already understand
- Don't worry about picking the "right" skill — Claude matches skills to context
- Each command finishes by suggesting the logical next command to run
- Save outputs to files — Claude will reference them in future conversations

---

### Intermediate: "I know the basics, now what?"

**Layer in more skill repos for deeper coverage:**

```bash
# Add battle-tested strategy frameworks (BCG, Blue Ocean, Porter)
npx skills add deanpeters/Product-Manager-Skills

# Add Lenny's Podcast wisdom (86 skills from top PMs)
npx skills add RefoundAI/lenny-skills

# Add lean framework skills (Mom Test, Shape Up, Obviously Awesome)
npx skills add assimovt/productskills
```

**Combine commands into workflows:**

Skills are designed to chain. A typical product cycle:

```
/discover          → Validate the problem space
/research-users    → Build personas and journey maps
/competitive-analysis → Map the competitive landscape
/strategy          → Define your product strategy
/value-proposition → Nail your positioning
/write-prd         → Spec the solution
/plan-launch       → Prepare for release
/north-star        → Set success metrics
```

**Use skills with your own data:**

Drop files into your project and reference them:
- "Analyze this user feedback CSV and run sentiment analysis"
- "Here are our app store reviews — what patterns do you see?"
- "Based on this competitor's pricing page, run a pricing strategy analysis"

Claude will combine the skill frameworks with your actual data.

**Set up a CLAUDE.md for your project:**

Create a `CLAUDE.md` in your project root to give Claude persistent context:
```markdown
# Product Context
We're building [product] for [audience].
Our north star metric is [metric].
Current stage: [discovery/growth/scale].

# Preferences
- Always use RICE for prioritization
- Format PRDs with our internal template
- Consider enterprise customers as primary segment
```

This means every conversation starts with Claude already understanding your product.

---

### Power User: "I want the full PM operating system"

**1. Build a merged superset of skills**

Install multiple repos and let them complement each other:

| Repo | What it adds to your stack |
|------|---------------------------|
| phuryn/pm-skills | Core workflows + command chaining |
| deanpeters/Product-Manager-Skills | Classic strategy (Ansoff, BCG, Porter, Blue Ocean) |
| RefoundAI/lenny-skills | Real-world wisdom from 90+ product leaders |
| alirezarezvani/claude-skills | RICE/MoSCoW/Kano with Python scoring scripts |
| product-on-purpose/pm-skills | Triple Diamond framework + standards compliance |
| assimovt/productskills | Lean, opinionated framework-per-skill (Mom Test, Shape Up) |

**2. Configure sub-agent perspectives**

Inspired by aakashg/pm-claude-code-setup, set up Claude to evaluate ideas from multiple angles:

```markdown
# In CLAUDE.md
When evaluating product decisions, consider these perspectives:
- Customer Advocate: Does this solve a real pain point?
- Business Strategist: Does this align with our business model?
- Data Analyst: What does the data say? What metrics move?
- Engineering Lead: Is this technically feasible in our timeline?
- Designer: Is this experience intuitive and delightful?
- Growth PM: Does this drive acquisition, activation, or retention?
- Risk Assessor: What could go wrong? What are the dependencies?
```

**3. Chain skills into custom workflows**

Create your own slash commands by writing command files that chain skills:

```markdown
# /full-product-review
1. Run competitive analysis (competitor-analysis skill)
2. Audit current PRD against best practices (prd-critique skill)
3. Pressure-test the roadmap (roadmap-review skill)
4. Score priorities using RICE (rice-prioritizer skill)
5. Generate executive summary with recommendations
```

**4. Connect MCP servers for live data**

- **PRD-MCP-Server** (Saml1211): Generate PRDs from your actual codebase
- **Figma MCP**: Pull design context directly into product discussions
- **GitHub MCP**: Link skills to real issues, PRs, and project boards

**5. Build custom skills for your domain**

Create skills specific to your product/industry. A SKILL.md file is just structured markdown:

```markdown
# [Skill Name]

## Description
What this skill does and when to use it.

## Frameworks
The mental models and frameworks this skill applies.

## Process
Step-by-step guided workflow with questions to ask.

## Output Format
What the skill produces (table, document, decision matrix, etc.)
```

Drop it in `.claude/skills/your-skill/SKILL.md` and it's immediately available.

**6. Automate recurring PM rituals**

Set up scheduled workflows:
- Weekly: `/analyze-feedback` on new user feedback
- Sprint start: `/write-prd` for top-priority features
- Monthly: `/competitive-analysis` refresh
- Quarterly: `/strategy` review with updated market data

**Power user tips:**
- Skills stack — the more context Claude has (CLAUDE.md + installed skills + your data), the better the output
- Use Taskmaster integration (prd-taskmaster) to bridge PM output directly into engineering task breakdowns
- Export skill outputs to Notion/Linear/Jira via MCP integrations
- Fork and customize any skill — they're just markdown files

---

### Quick Reference: Which tool for which job?

| I want to... | As a beginner | As a power user |
|--------------|---------------|-----------------|
| Validate an idea | `/discover` | `/discover` + Mom Test skill + user interview data |
| Write a PRD | `/write-prd` | Custom PRD template + Taskmaster + codebase context via MCP |
| Understand competitors | `/competitive-analysis` | Porter's 5 Forces + Blue Ocean + live web research |
| Prioritize features | "Help me prioritize" | RICE script + Kano analysis + stakeholder alignment |
| Plan a launch | `/plan-launch` | GTM workflow + pricing strategy + channel analysis |
| Set metrics | `/north-star` | North star + SaaS metrics diagnosis + analytics setup |
| Make strategic decisions | `/strategy` | Multi-perspective evaluation + Ansoff + BCG + data |

---

## KEY OBSERVATIONS

1. **Standard Format Emerging:** SKILL.md is becoming the de facto standard for AI agent skills across Claude Code, Codex, Cursor, and Windsurf. The Agent Skills Specification is gaining adoption.

2. **Installation Standard:** `npx skills add <repo>` or `npx add-skill <repo>` is the emerging install pattern.

3. **Dominant PM Frameworks Referenced:** Teresa Torres (continuous discovery), Marty Cagan (product thinking), Shape Up, JTBD, RICE, MoSCoW, Kano, Mom Test, Obviously Awesome.

4. **Gap Areas:**
   - Market research / competitive analysis skills are underrepresented
   - Trend analysis / viral opportunity assessment is absent
   - Revenue modeling / unit economics skills are sparse
   - User psychology / behavioral design skills are rare
   - Growth hacking / viral mechanics skills do not exist in current repos

5. **Highest Merge Value:** Repos #1-5 together would create a comprehensive PM skills system covering 200+ unique skills across all PM domains.

6. **ChatPRD Prompt Available:** The ChatPRD system prompt is documented at github.com/tjadamlee/GPTs-prompts and could inform building a high-quality PRD skill.
