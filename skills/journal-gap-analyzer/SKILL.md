---
name: journal-gap-analyzer
description: >
  Compare a research manuscript against a benchmark built from recent papers in a target journal.
  Estimate relative journal fit, identify the largest structural, evidential, methodological,
  discussion, claim-calibration, literature-positioning, visual and writing-style gaps, and
  recommend the highest-leverage revisions. This is a relative gap analysis, not an acceptance predictor.
version: 1.0
---

# Journal Gap Analyzer

## Purpose

Answer one practical question:

> **How far is this manuscript from the current publishing pattern of the target journal?**

Primary workflow:

manuscript + target journal + benchmark papers
→ select comparable papers
→ build Journal Benchmark
→ extract manuscript profile
→ compare on the same dimensions
→ estimate relative gap
→ identify Top Gaps
→ rank Closest Fixes
→ report uncertainty

This Skill does **not** predict acceptance probability.

A score such as `72/100` means relative similarity to the constructed benchmark under this rubric. It does **not** mean a 72% chance of acceptance.

---

# 1. Core Reliability Rules

## Benchmark first

Never judge a manuscript against an imagined journal standard when benchmark evidence is available.

Build the benchmark before scoring the manuscript.

## Comparable papers first

Prefer benchmark papers that match, in order of importance:

1. same journal;
2. same article type;
3. recent publication period;
4. similar research domain;
5. similar methodology;
6. similar scale of contribution.

Do not compare a Review Article with an Original Research Article as if they share the same structure.

Do not treat one unusual paper as representative of the journal.

## Relative fit, not editorial prediction

Never write:
- “This paper has a 75% chance of acceptance.”
- “A score above 80 means the paper will be accepted.”
- “The journal requires this because the benchmark papers did it.”

Prefer:
- “Relative fit to the sampled benchmark is Moderate–High.”
- “The largest observed gap is Discussion depth.”
- “The sampled papers tend to provide stronger quantitative validation.”

## Missing evidence is not failure

If the manuscript, supplementary material or benchmark sample is incomplete, mark:
- Unable to assess
- Low-confidence comparison
- Not reported in supplied material

Do not fabricate missing information.

---

# 2. Benchmark Modes

Choose the strongest available mode.

## Mode A — Sample-based Benchmark

Preferred.

Use approximately 5–10 recent papers from the target journal.

A minimum of 3 can be used for an exploratory benchmark, but confidence must be reduced.

## Mode B — User-supplied Benchmark

Use the papers supplied by the user.

Check whether they are sufficiently comparable before using them.

## Mode C — Journal-guideline + limited sample

Use official author guidance plus available sample papers.

Keep empirical style conclusions separate from formal journal requirements.

## Mode D — Manuscript-only diagnostic

If no target-journal sample is available, do not pretend to calculate a journal distance.

Instead return:
- preliminary manuscript profile;
- dimensions that need benchmarking;
- benchmark confidence: Insufficient.

---

# 3. Benchmark Confidence

Report:

**Benchmark confidence:** High / Medium / Low

Consider:
- number of benchmark papers;
- recency;
- article-type match;
- topical similarity;
- methodological similarity;
- availability of full text;
- consistency within the sample.

Example:

High:
8 recent original research papers, same journal, same broad field, full text available.

Medium:
5 recent papers, same journal and article type, mixed methodologies.

Low:
3 papers, older sample, weak topical match, abstracts only.

---

# 4. Build the Journal Benchmark

Load:
- `references/benchmark-method.md`
- `references/sample-selection.md`

Extract aggregate tendencies only.

Do not copy distinctive wording from source papers.

Create a Journal Benchmark Profile covering:

## A. Scope & contribution fit

Assess:
- typical problem scale;
- type of contribution;
- engineering/scientific relevance;
- degree of novelty framing;
- application vs mechanism balance;
- generalisability expected by sampled papers.

## B. Introduction & novelty framing

Assess:
- background length;
- gap directness;
- contribution statement clarity;
- literature density;
- positioning against recent work;
- how novelty is scoped.

## C. Methodological evidence

Assess what comparable papers usually report, where relevant:
- experimental design;
- numerical setup;
- controls;
- validation;
- uncertainty;
- sensitivity analysis;
- statistics;
- reproducibility information.

Do not convert a common practice into a universal requirement.

## D. Results depth

Assess:
- quantitative density;
- number of independent result dimensions;
- use of comparisons;
- sensitivity/robustness evidence;
- figure/table function;
- amount of descriptive vs analytical content.

## E. Discussion depth

Assess whether sampled papers commonly move through:

result
→ mechanism
→ literature comparison
→ limitation
→ implication

Measure pattern depth, not phrase similarity.

## F. Literature positioning

Assess:
- recency of references;
- density of direct comparison with prior studies;
- use of literature in Discussion;
- whether disagreements are explained;
- whether the manuscript is positioned within a clear research trajectory.

## G. Claim calibration

Assess:
- hedge strength;
- causal language;
- validation wording;
- significance wording;
- generalisation boundaries;
- novelty language.

## H. Reproducibility & transparency

Assess:
- methodological detail;
- parameter reporting;
- uncertainty reporting;
- data/code availability where relevant;
- supplementary material practices.

## I. Visual & quantitative communication

Assess:
- figure/table density;
- figure function;
- amount of quantitative comparison;
- consistency of visual scales;
- whether figures mainly illustrate or test claims.

## J. Writing & section architecture

Assess:
- abstract information density;
- section proportions;
- paragraph length;
- sentence density;
- directness;
- Results/Discussion separation;
- conclusion compression.

Style is a secondary dimension. Do not let cosmetic similarity dominate the total assessment.

---

# 5. Build the Manuscript Profile

Extract the manuscript using the same dimensions as the benchmark.

Do not score before profile extraction is complete.

For each dimension record:

- manuscript evidence;
- benchmark tendency;
- gap direction;
- gap magnitude;
- confidence.

Gap direction examples:
- below benchmark tendency;
- broadly aligned;
- stronger than benchmark tendency;
- structurally different but defensible;
- unable to assess.

---

# 6. Core Comparison Dimensions

Use the following default dimensions.

Weights may be adjusted by article type and discipline, but explain any meaningful change.

1. **Scope Fit** — 10
2. **Novelty Framing** — 10
3. **Methodological Evidence** — 15
4. **Results Depth** — 15
5. **Discussion Depth** — 15
6. **Literature Positioning** — 10
7. **Claim Calibration** — 10
8. **Reproducibility** — 5
9. **Visual / Quantitative Communication** — 5
10. **Journal Writing Architecture** — 5

Total = 100

Load:
- `references/scoring-rubric.md`

The score is indicative, not psychometric.

Avoid false precision.

Prefer scores in 5-point increments unless the evidence supports finer distinction.

---

# 7. Relative Fit Bands

Use:

## 85–100 — High relative alignment
The manuscript broadly resembles the sampled journal pattern on the assessed dimensions. Remaining gaps are limited or localised.

## 70–84 — Moderate–High relative alignment
The paper has a credible journal fit, but several meaningful gaps remain.

## 55–69 — Moderate relative alignment
The manuscript shares some target-journal characteristics, but important content/evidence/discussion gaps remain.

## 40–54 — Low–Moderate relative alignment
Several central dimensions differ materially from the benchmark.

## Below 40 — Low relative alignment
The manuscript is currently far from the sampled journal pattern or evidence is too incomplete for a strong fit judgement.

Always report score confidence.

---

# 8. Gap Types

Classify each gap as one of:

## Structural Gap
Examples:
- weak gap framing;
- Discussion lacks mechanism/literature layering;
- conclusion too broad;
- Results and Discussion organisation differs materially.

## Evidence Gap
Examples:
- benchmark commonly contains quantitative validation but manuscript provides qualitative comparison only;
- uncertainty/sensitivity evidence is thin relative to comparable papers.

## Depth Gap
Examples:
- result is reported but not interpreted;
- mechanism is proposed without diagnostic support;
- literature comparison is shallow.

## Positioning Gap
Examples:
- contribution is not clearly differentiated from recent work;
- Discussion rarely compares with external studies.

## Claim Gap
Examples:
- manuscript uses stronger causal or validation language than sampled papers with comparable evidence.

## Communication Gap
Examples:
- figures are descriptive rather than analytical;
- quantitative comparison is sparse;
- section density is poorly balanced.

## Style Gap
Examples:
- abstract is much more verbose;
- paragraph structure is unusually dense;
- result reporting is less direct.

Style gaps should normally rank below scientific/evidential gaps.

---

# 9. Top Gaps

Return the 3–5 gaps with the greatest likely effect on journal alignment.

For each:

### Gap G1 — [short title]
**Dimension:**
**Current manuscript:**
**Benchmark tendency:**
**Gap magnitude:** Small / Moderate / Large
**Why it matters:**
**Evidence:**
**Confidence:**

Do not simply list every difference.

Prioritise actionable differences that matter to scientific fit.

---

# 10. Closest Fixes

This is a core feature.

For each proposed revision estimate:

- effort: Low / Medium / High;
- expected alignment gain: Low / Medium / High;
- whether new analysis/data are needed;
- which gap(s) it addresses.

Rank by leverage.

Example:

| Fix | Effort | Expected alignment gain | New data? | Addresses |
|---|---|---|---|---|
| Add quantitative validation errors | Low | High | No | Method evidence |
| Expand mechanism + literature comparison | Medium | High | No | Discussion depth |
| Add new sensitivity simulation | High | Medium | Yes | Robustness |

Do not recommend new experiments/simulations when existing data could resolve the gap.

---

# 11. No-Change Zone

Also identify areas already well aligned.

This prevents unnecessary rewriting.

Examples:
- Methods reporting already matches or exceeds benchmark detail;
- Abstract length is already aligned;
- figure density is adequate;
- claims are already more carefully scoped than the benchmark.

Return 2–5 items where the author should **avoid unnecessary changes**.

---

# 12. Benchmark Outlier Guard

Target-journal papers may contain outliers.

Do not let one paper dominate the benchmark.

If a feature appears in only one sampled paper:
- label it an outlier or uncommon pattern;
- do not use it as a strong basis for scoring.

If the benchmark sample is internally diverse:
- widen the acceptable range;
- reduce confidence;
- report that the journal accommodates multiple styles/methodological patterns.

---

# 13. Article-Type Guard

Adjust dimensions by article type.

## Original research
Use default framework.

## Review article
Emphasise:
- coverage;
- synthesis;
- taxonomy/framework;
- critical comparison;
- evidence integration;
- future research agenda.

Do not score experimental validation as though it were an original research article.

## Methods / technical paper
Emphasise:
- methodological novelty;
- validation;
- reproducibility;
- benchmarking;
- sensitivity/robustness.

## Short communication
Adjust expectations for length and breadth.

---

# 14. Output Format

Use `templates/gap-report.md`.

# Journal Gap Report

## 1. Benchmark Scope
- Target journal:
- Article type:
- Benchmark papers:
- Date range:
- Similarity to manuscript:
- Benchmark confidence:

## 2. Journal Benchmark Profile

Summarise the target pattern.

## 3. Relative Journal Fit

**Relative fit:** X/100
**Fit band:**
**Score confidence:**

Important note:
> This is a relative benchmark score, not an acceptance probability.

## 4. Dimension Scores

| Dimension | Score | Benchmark tendency | Manuscript gap | Confidence |
|---|---:|---|---|---|

## 5. Top Gaps

## 6. Closest Fixes

## 7. No-Change Zone

## 8. Section-by-Section Gap
- Abstract
- Introduction
- Methods
- Results
- Discussion
- Conclusion

## 9. Final Distance Summary

Return:
- closest dimension;
- furthest dimension;
- highest-leverage fix;
- biggest evidence gap;
- biggest style/architecture gap;
- benchmark limitation.

---

# 15. Behaviour Rules

Do:
- benchmark before scoring;
- compare like with like;
- separate formal journal requirements from sampled tendencies;
- prioritise scientific/evidential gaps over cosmetic style gaps;
- report confidence;
- identify what is already strong;
- recommend the minimum effective revision;
- preserve unusual but scientifically justified manuscript choices.

Do not:
- predict acceptance probability;
- invent journal rules;
- imply editorial endorsement;
- treat all papers in a journal as identical;
- overfit to one benchmark paper;
- copy phrases from target papers;
- penalise harmless stylistic variation;
- recommend extra experiments merely because benchmark papers contain more data;
- score missing material as confirmed weakness;
- use the score as a substitute for qualitative explanation.

---

# 16. Example Invocations

## Standard
“Use $journal-gap-analyzer to compare this manuscript with these recent papers from the target journal. Build the benchmark first, then tell me the largest gaps and highest-leverage fixes. Do not interpret the score as acceptance probability.”

## Target journal with supplied papers
“Target journal: Building and Environment. Use these six recent original research papers as the benchmark. Compare article structure, methodological evidence, Results depth, Discussion depth, literature positioning, claim calibration and writing architecture.”

## Minimal-change mode
“Identify the three gaps that matter most and the three areas I should not change. Prioritise fixes that can be made using existing data.”