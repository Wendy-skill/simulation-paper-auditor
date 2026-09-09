# Simulation Paper Auditor

An evidence-first AI Skill series for checking simulation-based research manuscripts before submission.

The current rules are strongest for **CFD / ANSYS Fluent / CFD-DPM**, while the framework is designed to expand to FEM, COMSOL and other numerical simulation workflows.

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

Typical checks include:

- turbulence model;
- steady / transient formulation;
- boundary conditions;
- discretisation schemes;
- pressure–velocity coupling;
- convergence criteria;
- time-step settings;
- DPM settings;
- UDF / script-controlled settings.

Core rule:

> **Missing evidence is not a mismatch.**

### 3. Physics Sanity Check

Path: `skills/physics-sanity-check/`

Checks whether simulation results, contours, trends and physical explanations are actually plausible.

It separates **observation** from **mechanism** and asks what evidence is required before a physical explanation can be treated as supported.

Current specialist references cover:

- CFD flow fields;
- heat transfer;
- particle transport / DPM.

Core rule:

> **Plausible is not proven.**

It also uses a mechanism-evidence ladder from qualitative speculation to strong convergent evidence.

### 4. Claim–Evidence Checker

Path: `skills/claim-evidence-checker/`

Checks whether the strength and scope of manuscript claims match the evidence actually provided.

It focuses on:

- validation and accuracy claims;
- causal / mechanistic statements;
- statistical language;
- comparative and “optimal” claims;
- generalisation;
- novelty language;
- strong-certainty wording such as `validated`, `accurate`, `robust`, `proves`, `significant` and `superior`.

Core rule:

> **Claim strength must not exceed evidence strength.**

The Skill suggests the minimum necessary wording downgrade when a claim is overstated.

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
│   ├── cfd.md
│   ├── cfd-dpm.md
│   └── validation.md
├── templates/
│   └── audit-report.md
└── skills/
    ├── fluent-setting-checker/
    ├── physics-sanity-check/
    └── claim-evidence-checker/
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

## Recommended inputs

Depending on the Skill, useful inputs include:

- manuscript;
- figures and tables;
- supplementary material;
- Fluent / solver report;
- mesh report;
- residual history;
- journal or script files;
- UDFs or custom numerical settings.

## Planned series

Possible next modules:

- Reviewer View;
- FEM specialist rules;
- COMSOL specialist rules;
- manuscript-vs-solver automated consistency workflow.

Created by **Wendy.z**.
