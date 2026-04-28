---
name: eval-layers-five-axis
description: Organize evals by scope — agent vs journey vs product. Use when the team is conflating eval types, when "why does this eval pass but production still fails" is the question, or when designing eval coverage for an AI system that has multiple agents, multi-step journeys, and cross-surface seams.
---

# Eval Layers — The Five-Axis Model

A vocabulary for organizing eval work that separates by **scope**, not by team preference or tooling. Built from XA repair eval practice; aligned with OpenAI / Google / Anthropic / Fowler-test-pyramid / LangSmith.

The model gives one framework for asking: *"What is this eval actually testing, and at what level?"* — which prevents the most common confusion: an eval that passes locally but fails in the system, or a system test that gets blamed on a single agent.

## The three layers (scope)

| Layer | What it tests | Typical inputs | Typical outputs | Main outcome |
|---|---|---|---|---|
| **Product evals** | System-level evaluation of the overall AI product across mixed intents, routing, handoffs, and real traffic patterns | Production transcripts, trace samples, routing logs, outcome data, repeat-contact data, cross-journey incidents | Product-level quality signals, release readouts, cross-cutting risks, prioritization decisions | Do we trust the product to behave well as a product, not just as a collection of agents? |
| **Journey evals** | End-to-end evaluation of a bounded customer workflow | Journey transcripts, curated journey scenarios, journey requirements, handoff examples, escalation cases, regression cases | Pass/fail on the journey, journey failure patterns, journey-level release gates, prioritized gaps | Does this experience work the way we intend from start to resolution? |
| **Agent evals** | Local evaluation of individual agents or agent stages | Tool contracts, prompt specs, agent examples, deterministic checks, golden scenarios, trajectory checks | Agent pass/fail results, tool-use correctness, response-quality results, local regressions | Does this agent do its own job correctly and reliably? |

These are not competing frameworks. They are concentric scopes. A product is composed of journeys; a journey runs across one or more agents.

## The five axes

Every real eval is a combination of all five.

### 1. Layer (scope)
What scope are we testing?
- product / journey / agent

### 2. Quality dimension (what we measure)
Any of these can appear at any layer.
- **Instruction following** — did the system follow the rules and constraints it was given?
- **Functional correctness** — did it do the right thing and produce the right result?
- **Tool use quality** — did it choose the right tool and pass the right arguments?
- **Trajectory quality** — did it take a sensible path through the workflow or tool sequence?
- **Text quality** — was the response clear, coherent, readable, well-formed?
- **Groundedness / hallucination** — was the answer supported by available evidence and tool context?
- **Conversation quality** — across turns, did the interaction stay coherent, responsive, useful?
- **Latency / reliability** — did it complete within acceptable speed and without brittle failure?
- **Safety / policy compliance** — did it avoid unsafe, disallowed, or privacy-violating behavior?

### 3. Case type (what dataset)
- **Golden** — canonical cases that absolutely should work
- **Adversarial** — messy, ambiguous, or failure-inducing cases
- **Edge** — rare but important corner cases
- **Regression** — real failures pulled from production that should not recur
- **Production sample / shadow** — recent real traffic used to spot drift or coverage gaps

### 4. Method (how we judge)
- **Code / metric-based** — deterministic checks (exact match, schema validity, tool-call accuracy, latency thresholds)
- **Human review** — people inspect outputs or traces using a rubric
- **LLM-as-judge** — another model scores against explicit criteria
- **Pairwise comparison** — two outputs compared directly to decide which is better

The same dimension can be evaluated with different methods. Tool-use quality might be checked with code; text quality with LLM-as-judge plus spot human review; conversation quality with human review or pairwise comparison.

### 5. Stage (when it runs)
- **Offline** — pre-deployment testing on curated datasets or known scenarios
- **Online** — production monitoring on real runs, traces, or conversations

Plain language: *offline = we chose the cases ahead of time; online = we are evaluating real production behavior.*

## The decision-rule sentence

When designing any eval, fill in this sentence:

> *We are testing **[layer]** for **[quality dimension]** using a **[case type]** set with **[method]** at the **[stage]** stage.*

Examples:

- *We are testing the **journey** for **trajectory quality** using a **regression** set with **human review** at the **offline** stage.*
- *We are testing **product** behavior for **trajectory quality** using a **production sample** with **human review** at the **online** stage.*
- *We are testing the **agent** for **tool use quality** using a **golden** set with **code** checks at the **offline** stage.*

**If that sentence sounds vague, the eval is probably still underspecified.**

## How to decide which layer owns a check

Use the **lowest reliable layer first**, then add a higher-layer eval if the behavior can still break through interactions.

Ask:

1. **Is the behavior local?** — If yes, start at the agent layer.
2. **Does it depend on multiple steps in one bounded workflow?** — If yes, journey layer.
3. **Does it fail at the seams between journeys, routing, handoffs, or real traffic mix?** — If yes, product layer.
4. **Could it pass locally but still fail in the real system?** — If yes, add coverage at a higher layer.

This is the test pyramid pattern (Fowler) applied to AI: deterministic and cheap at the bottom, expensive and broad at the top, fewer at each higher level.

## How dimensions show up at each layer (typical emphasis, not exclusive)

**Agent evals** typically emphasize: instruction following, functional correctness, tool use quality, trajectory quality, text quality, groundedness, latency/reliability, safety.

**Journey evals** typically emphasize: instruction following (journey rules), functional correctness (problem assessment, next action, clean escalation), trajectory quality (no repeated intake, no wrong-problem drift), conversation quality (low friction, visible progress), latency/reliability (journey latency, handoff completeness).

**Product evals** typically emphasize: functional correctness (routing, cross-journey continuity, memory), trajectory quality (right lane, no incompatible bouncing), conversation quality (low effort, trust-preserving escalation), latency/reliability (resilience under production mix, repeat-contact impact).

## Worked example combinations

| Layer | Dimension | Case type | Method | Stage | What it tests |
|---|---|---|---|---|---|
| Agent | Tool use quality | Golden | Code | Offline | Does the agent call the right tools and produce the right recommendation for a standard case? |
| Agent | Safety / policy | Production sample | Code | Online | On live traffic, is the agent staying within privacy, safety, and action-boundary rules? |
| Journey | Trajectory quality | Regression | Human or LLM-judge | Offline | In a real transcript that previously failed, does the journey avoid `Wrong Problem` or `Repeated Intake` this time? |
| Journey | Conversation quality | Production sample | LLM-judge + spot human | Online | In recent live sessions, does the experience feel clear, low-friction, coherent? |
| Product | Trajectory quality | Adversarial | Human review | Offline | In a designed mixed-intent stress case, does the product keep the user in the right lane? |
| Product | Latency / reliability | Production sample | Code | Online | Under live traffic mix, is wrong-motion rate or repeat-contact rate drifting upward? |

## How failure modes fit

Failure modes from a `failure-mode-taxonomy` will *usually* live at a primary layer, but can show up at multiple. Examples from XA repair:

- `Repeated Intake` — primarily a journey failure mode. Could surface at product layer if it shows up across channels or journeys.
- `Wrong Problem` — can exist at all three layers depending on where the mistake originates.
- `Broken Flow Switching` — observed through journey transcripts but is a strong candidate for a product-level eval dimension because it lives at the seams between jobs.

## Best-practice guardrails

These keep the model honest as it grows.

- **Use multiple layers.** Don't rely on one broad score when failures can happen locally, in a workflow, or across the product.
- **Use the lowest reliable layer first.** Catch issues cheaply and deterministically when possible, then add higher-layer coverage for emergent behavior.
- **Evaluate both outcome and path.** Judge not only the final answer, but also the trajectory, tool use, and handoffs that produced it.
- **Combine methods.** Code where you can, human review where judgment matters, LLM-as-judge where scale is needed.
- **Use both offline and online.** Curated pre-deployment tests plus production monitoring.
- **Grow from production.** Production failures, traces, and feedback should become new regression and adversarial cases.
- **Keep broad-stack coverage small but important.** Have fewer expensive product-level checks, focused on the highest-value and highest-risk interactions.

## Common mistakes to flag

- **Treating layers as competing frameworks.** They're concentric scopes. A product is composed of journeys; journeys run on agents.
- **Skipping the decision-rule sentence.** If you can't fill in all five axes for an eval, the eval is still vague.
- **Putting product-layer evals where agent-layer evals belong.** Cheaper to catch a bug in a 5-second agent test than in a 5-minute end-to-end journey run.
- **Putting agent-layer evals where product-layer evals belong.** A bug at the seams between journeys won't surface in a single-agent test, no matter how thorough.
- **Cargo-culting big external rubrics.** Match coverage to your named failure modes plus hard-gate safety. Don't import OpenAI's 30-criterion eval suite wholesale because someone said it was best practice.

## Reference: source frameworks this aligns with

- **OpenAI:** task-specific evals, multiple evaluator types, production data, continuous evaluation
- **Google:** final-response and trajectory evaluation, agent metrics like tool use quality and text quality
- **Anthropic:** combine techniques to match system complexity; pair evals with production monitoring
- **Software testing practice (Fowler):** layered coverage with fewer expensive broad-stack checks
- **LangSmith:** offline vs online evaluation, evaluator methods, production-to-regression feedback loop

For full attribution and source links, see `references/source-frameworks.md`.

## Related skills

- **failure-mode-taxonomy** — supplies the failure categories that get tested
- **eval-pack-template** — the artifact that runs evals at one layer (typically journey or agent)
- **ai-evals** — the broader principles this layering instantiates
