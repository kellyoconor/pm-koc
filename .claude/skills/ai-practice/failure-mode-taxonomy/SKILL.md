---
name: failure-mode-taxonomy
description: Build a systematic failure taxonomy from production transcripts. Use when reviewing 50+ AI agent transcripts, trying to name what's actually breaking, building the input that grades and evals will reference, or when "the agent feels off" needs to become measurable categories.
---

# Failure Mode Taxonomy

A method for turning qualitative transcript review into a product-level taxonomy that downstream evals, graders, and prioritization can reference. Built from real practice (XA repair, ~100 transcripts, v2.1 taxonomy).

This is the front-end of eval work. Without a real taxonomy, eval scenarios get invented at a whiteboard and cover failure modes nobody actually has.

## The four-pass method

The taxonomy isn't written in one sitting — it survives contact with fresh data four times before it earns its name.

### Pass 1 — Open observation
- **Sample:** 20 transcripts, random
- **Method:** Read each transcript. Write 2-4 sentences of pure observation. No categorization. No judgment yet about whether something is a "failure" or not.
- **Output:** Raw observation notes
- **You are asking:** *What actually happens in these conversations?*

### Pass 2 — Taxonomy drafting (informal)
- **Sample:** No new transcripts — work from Pass 1 observations
- **Method:** Cluster similar observations. Name the clusters.
- **Output:** Taxonomy v1 (working draft)
- **You are asking:** *What patterns do my observations suggest?*

### Pass 3 — Validation
- **Sample:** 30 fresh transcripts (separate from Pass 1)
- **Method:** Classify each transcript using v1. Pay attention to what doesn't fit. Refine categories based on what breaks.
- **Output:** Taxonomy v2 (often includes a "No Clear Failure / Insufficient Evidence" category, which is analytically meaningful, not a trash bin)
- **You are asking:** *Does my taxonomy survive contact with data it wasn't built from?*

### Pass 4 — Counting
- **Sample:** 50 fresh transcripts (separate from Passes 1 and 3)
- **Method:** Classify using v2. Tag in your tracking system. Watch which categories persist, fluctuate, or surface late.
- **Output:** Tagged rows + early read on distributional stability
- **You are asking:** *Are the patterns I saw at 30 real, or artifacts of a small sample?*

The discipline is: **fresh sample at each pass.** Reusing transcripts inflates confidence in patterns the method should be testing.

## Anatomy of a category

Each category in the taxonomy carries five required fields:

1. **Definition** — one sentence, behavior-focused
2. **Plain-language handle** — how a non-expert would describe it ("Bouncing between jobs")
3. **Include when** — 3-5 bullets describing the behavior
4. **Exclude when** — 3-5 bullets that distinguish from adjacent categories (this is what prevents drift between annotators)
5. **Current frequency** — `N / total` from the counting pass
6. **Example session IDs** — 3-5 real transcripts as reference points

**Drop the rating scales.** Use one primary category per transcript for lightweight counting. You can add secondary categories or chains in v3 once the primary set is stable.

## Three operating practices

**1. Don't sort by frequency alone — sort by upstream position.**
The taxonomy needs a "current read" — your working hypothesis about which failure is most structurally upstream. Example: in XA repair, `Broken Flow Switching` was 15% (not the most frequent), but if the system stayed in one coherent job more reliably, some share of `Wrong Problem` (14%) and `Repair Turns Into Sales` (14%) might shrink with it. That hypothesis orders priority. Name what would weaken or disprove it.

**2. The "no clear failure" category is real, not a trash bin.**
Roughly 20-30% of transcripts won't have enough signal to classify. Name that explicitly. It usually collapses several meanings (genuinely fine, too short to judge, missing context, broadly successful) — flag those for v3 split.

**3. Acknowledge stacked failures without trying to capture them yet.**
Real conversations fail in chains: `Repeated Intake → Broken Flow Switching → Repair Turns Into Sales`. The four-pass method flattens this for tractability. That's a known limit, not a flaw — just document it as a v3 consideration.

## The Stage 5 hand-off (taxonomy → eval criteria)

The taxonomy is built for human classification. It does not yet specify the thresholds that machine graders need.

When the taxonomy meets the eval pack:

- **How many visible lane switches count as `Broken Flow Switching`?** (1? 2?)
- **How far can the system proceed in the wrong lane before it counts as `Wrong Problem`?**
- **When does a commercial pivot become material enough to count as `Repair Turns Into Sales`?**

These thresholds get defined when graders are written. When they're defined, reflect them back into the taxonomy file so taxonomy and eval criteria stay aligned. Otherwise the taxonomy and graders drift.

## Common mistakes to flag

- **Skipping the open-observation pass.** Going straight to clustering bakes in pre-existing assumptions. The point of Pass 1 is to see what's there before you have categories to fit it into.
- **Reusing the same transcripts across passes.** The taxonomy needs to survive on data it wasn't built from. Re-using inflates confidence.
- **Using a Likert scale for failure severity.** "How bad is this failure on 1-5?" produces drift across annotators. Keep it categorical.
- **Confusing taxonomy frequency with production prevalence.** A 15% rate in your sample is not a 15% production rate. It's a count from manually reviewed transcripts. Name that limit explicitly.
- **Letting the taxonomy live inside one journey folder.** It's a product-level artifact. Journeys reference it; they don't fork it.

## Reference: a working taxonomy shape

For a complete worked example with all 8 categories, frequencies, include/exclude rules, and example session IDs, see `references/xa-repair-taxonomy-v2.1.md` (the canonical XA repair taxonomy — 100 transcripts, 9 categories, current upstream hypothesis: `Broken Flow Switching`).

## Related skills

- **eval-pack-template** — the downstream artifact that consumes this taxonomy
- **eval-layers-five-axis** — the framework that organizes evals by scope (taxonomy maps to layers)
- **ai-evals** — the broader principles this method instantiates
