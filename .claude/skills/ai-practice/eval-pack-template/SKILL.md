---
name: eval-pack-template
description: Produce a runnable eval pack from product requirements — scenarios, graders, ship bar. Use when a journey, agent, or AI feature has requirements written and you need the test suite that answers "did the agent do what requirements said?" Evals are written before the agent spec on purpose — test-first forces the agent to earn a passing grade.
---

# Eval Pack Template

Turn requirements into a runnable eval suite. Requirements says *"what the agent must do"*; the eval pack says *"how we'll check that it actually does it."* Evals are written before the agent spec — test-first forces the agent to earn a passing grade instead of rationalizing what shipped.

## Six core principles

These shape *how* you think, not just *what* you write.

1. **Error analysis first.** Review real failure traces (transcripts, incident refs, customer stories) before designing scenarios. Evals stress-test known failure modes, not just the happy path imagined at a whiteboard. *Use `failure-mode-taxonomy` for the systematic version.*

2. **Binary pass/fail. No Likert scales.** Every scenario and every rubric resolves to pass or fail. Rating scales invite middle-of-the-road defaults and inconsistent labeling across annotators.

3. **LLM judges are validated against humans.** Any LLM-as-judge rubric must be calibrated with at least one small sample where two humans independently agree on pass/fail. If the humans can't agree, the rubric isn't specific enough — rewrite the rubric, not the humans.

4. **Give LLM judges an "Unknown" escape.** Rubrics include an explicit "return Unknown when you don't have enough information" instruction. Prevents hallucinated judgments on cases the judge can't actually evaluate.

5. **Grade outcomes, not paths.** "Tool called" and "command sent" are never pass criteria on their own. Customer outcome is what gets graded. Tool trajectory matters only when it's load-bearing for the outcome.

6. **Regressions cite real incidents.** Every regression scenario names the production failure, ticket, or customer-story path that motivated it. No synthetic regressions.

## Required inputs

You can't write a real eval pack without these. If they're missing, go back upstream first.

1. **Requirements** — `status: ready`. The behavior contract being tested.
2. **Failure taxonomy** — the canonical product-level failure classification. Every scenario should trace to a taxonomy category. If a scenario covers a failure mode not in the taxonomy, flag it as a proposed taxonomy addition.
3. **Real failure sources** — transcripts, customer stories, incident refs from the requirements. These ground regression scenarios in real evidence.

## The four-level scenario structure

Each scenario exercises some subset of these levels. Not every scenario needs every level — pick the levels that matter for what you're testing.

- **Level 1 — Intent and state:** Did the agent recognize the right journey and assemble the right context before acting?
- **Level 2 — Tool trajectory:** Did it call the right tools in a sensible order with correct arguments?
- **Level 3 — Decision quality:** Did it pick the right next motion for the evidence it had?
- **Level 4 — Customer experience:** Was the response plain, honest, low-effort, and consistent with the action taken?

## Coverage categories (all required)

A real eval pack covers all four. Skipping one is a coverage gap that should be named, not hidden.

- **Golden** — happy path the agent must get right
- **Adversarial** — ambiguity, bad state, conflicting signals, frustration, policy edge
- **Regression** — from real production failures, with incident refs
- **Degraded** — tool timeout, missing telemetry, stale data

Optional but useful: **Hard-stop** (policy boundary scenarios), **Channel-behavior** (when behavior should differ by channel like SMS vs app), **Counter-continuity** (when shared state must agree across surfaces).

## Scenario shape (YAML)

Each scenario is a YAML block. Engine-readable, reviewable in PRs. Example:

```yaml
id: GD-001
name: "Clear gateway reboot request"
capability: entry-and-targeting
exercises_rules: [1, 2, 4, 5]
source: golden
input: "Reboot my gateway"
state:
  auth: true
  devices: [{name: "Gateway", type: "gateway", lease: "leased", remote_reboot: true, status: "offline"}]
  outage: none
  reboot_history: []
expected:
  trajectory:
    - tool: reboot_device
      args: {device_id: "gateway_id"}
  decision: immediate-reboot
  says: ["restarting", "gateway"]
  must_not_say: ["would you like", "confirm", "are you sure", "let me check first"]
graders:
  deterministic: [trajectory_match, no_pre_action_question, reboot_submitted_before_checks]
  llm_judge:
    - rubric: action_first_response
      # Pass if agent's first substantive response communicates that it is restarting now.
      # Fail if agent asks a question, runs a check, or requests confirmation before acting.
      # Return Unknown if the response is cut off or missing.
      calibration: pending
policy_checks: [consent_is_request, no_pre_action_gates]
pass_criteria: "Reboot submitted as first action, no pre-action questions, result reported as back online/still offline/unknown."
```

The `must_not_say` list is often more useful than the `says` list — failure language is more diagnostic than success language.

## Ship bar — numbers, not adjectives

The ship bar gates launch. Every item must be testable against fixtures in this pack.

Bad ship bar items:
- *"Quality is good"*
- *"Most scenarios pass"*
- *"Customer experience is acceptable"*

Good ship bar items:
- 100% pass on hard-stop policy evals
- 100% trajectory match on golden scenarios
- Reboot-journey resolution rate ≥ 55% on the journey fixture set (N ≥ 200)
- Zero cases where "command sent" is scored as resolution
- Zero cases where customer-owned equipment receives a remote reboot attempt
- p95 request-to-reboot-submit ≤ 8s (app/web), ≤ 15s (SMS) on at least 200 fixtures per channel

Numbers force agreement. Adjectives let everyone fill in their own bar.

## Grader precision — the discriminating skill

The difference between a useless rubric and a useful one is specificity.

**Bad:** *"Rate the response quality 1-5."* — Likert invites middle defaults and annotator drift.

**Good:** *"Pass if the response names the customer's reported device by the exact token the customer used, does not introduce an unrequested diagnostic, and ends with a concrete next step. Fail otherwise. Return Unknown if the response is cut off or missing."*

Every LLM-judge rubric should be writable in this shape: explicit pass condition, explicit fail condition, explicit Unknown escape.

## Rollup questions (after running the pack)

The team answers these after each run. They turn raw pass/fail counts into product-decision input:

- Which cases pass today without manual intervention?
- Which failures are tool/data gaps (missing API, wrong device records) vs. agent policy/prompt behavior?
- Which failures are caused by unreliable or unavailable telemetry?
- Which failures would cause real customer harm (repeated effort, false success, unnecessary escalation)?
- Which evals must pass before this is release-ready? (Answer: all hard-stop and golden scenarios at minimum.)
- Which LLM-judge rubrics still need human calibration before results are trusted?

## Common mistakes to flag

- **"Tool called" as pass criteria.** Customer outcome is what matters. Tool trajectory matters only when it's load-bearing for the outcome.
- **Skipping degraded-mode scenarios.** Production hits tool timeouts and missing telemetry constantly. If the pack only tests happy-path tools, it won't catch the most common real failures.
- **Inventing regression scenarios.** Regressions cite real incidents. If you can't find a real one, it's an adversarial scenario, not a regression.
- **Likert scales for "experience quality."** Always rewritable as a binary rubric — force the rewrite.
- **Untrusted LLM judges.** A judge without human calibration is a hallucinator with confidence.
- **Adjectives in the ship bar.** "Quality is good" is not a gate. Numbers are.

## Reference: a complete worked eval pack

For a full example with 30+ scenarios across all coverage categories, see `references/xa-equipment-restart-eval-pack.md` (the XA repair equipment-restart pack — Golden/Adversarial/Hard-stop/Regression/Degraded/Recovery-followup/Counter-continuity/SMS-channel coverage with 8-item ship bar).

## Related skills

- **failure-mode-taxonomy** — the upstream artifact every scenario should trace to
- **eval-layers-five-axis** — picks which layer a given eval lives at
- **ai-evals** — the broader principles this template instantiates
