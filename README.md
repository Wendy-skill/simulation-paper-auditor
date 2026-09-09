# Simulation Paper Auditor

An evidence-first AI Skill series for checking research manuscripts before submission.

The current technical rules are strongest for **CFD / ANSYS Fluent / CFD-DPM**, while the series also includes broader manuscript-level tools such as journal benchmarking and claim–evidence analysis.

## Available Skills

### 1. Simulation Paper Auditor

Core pre-submission audit for:

- mesh and numerical resolution;
- boundary conditions and physical models;
- convergence and solver settings;
- verification and validation;
- physical plausibility;
- reproducibility and reporting completeness.

It also produces an Evidence Map, reviewer-risk assessment, claim–evidence check, submission-readiness assessment and action plan.

### 2. Fluent Setting Checker

Path: `skills/fluent-setting-checker/`

Cross-checks the manuscript Methods against the actual ANSYS Fluent setup.

Core rule:

> **Missing evidence is not a mismatch.**

### 3. Physics Sanity Check

Path: `skills/physics-sanity-check/`

Checks whether simulation results, contours, trends and physical explanations are plausible.

Core rule:

> **Plausible is not proven.**

### 4. Claim–Evidence Checker

Path: `skills/claim-evidence-checker/`

Checks whether the strength and scope of manuscript claims match the evidence actually provided.

Core rule:

> **Claim strength must not exceed evidence strength.**

### 5. Journal Gap Analyzer

Path: `skills/journal-gap-analyzer/`

Builds a benchmark from comparable recent papers in a target journal, then estimates how closely the manuscript aligns with that benchmark.

It compares:

- scope fit;
- novelty framing;
- methodological evidence;
- results depth;
- discussion depth;
- literature positioning;
- claim calibration;
- reproducibility;
- visual / quantitative communication;
- journal writing architecture.

Key outputs include:

- Relative Journal Fit;
- Benchmark Confidence;
- Top Gaps;
- Closest Fixes;
- No-Change Zone;
- section-by-section distance analysis.

Important rule:

> **Journal distance is not acceptance probability.**

A score such as `72/100` describes relative alignment with the constructed benchmark. It does not mean a 72% chance of acceptance.

## Shared reliability rules

Across the series:

> **Not reported ≠ not performed.**

The Skills distinguish missing evidence, reporting gaps, true contradictions and unsupported claims.

They must not invent solver settings, mesh information, validation results, numerical parameters, statistics or journal requirements.

## Repository structure

```text
simulation-paper-auditor/
├── SKILL.md
├── references/
├── templates/
└── skills/
    ├── fluent-setting-checker/
    ├── physics-sanity-check/
    ├── claim-evidence-checker/
    └── journal-gap-analyzer/
```

## Recommended use in Codex

Main audit:

```text
Use $simulation-paper-auditor to audit this manuscript.
First build the Evidence Map.
Prioritise methodology, numerical credibility and reviewer risks over language editing.
```

Fluent consistency:

```text
Use $fluent-setting-checker to compare the manuscript Methods with the supplied Fluent files.
Extract manuscript and Fluent settings independently before comparing them.
```

Physics check:

```text
Use $physics-sanity-check to review the Results and Discussion.
Separate direct observations from physical explanations and identify alternative mechanisms.
```

Claim check:

```text
Use $claim-evidence-checker to audit the manuscript.
Find claims whose strength or scope exceeds the evidence and suggest the minimum necessary wording change.
```

Journal distance:

```text
Use $journal-gap-analyzer to compare this manuscript with recent comparable papers from the target journal.
Build the Journal Benchmark first, then identify the largest gaps and highest-leverage fixes.
Do not interpret the fit score as acceptance probability.
```

## Planned series

Possible next modules:

- Reviewer View;
- FEM specialist rules;
- COMSOL specialist rules;
- manuscript-vs-solver automated consistency workflow.

Created by **Wendy.z**.
