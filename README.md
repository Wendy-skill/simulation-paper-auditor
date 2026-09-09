# Simulation Paper Auditor

An evidence-first AI Skill for checking simulation-based research manuscripts before submission.

The current technical rules are strongest for **CFD / ANSYS Fluent / CFD-DPM**.

## What it checks

The core audit focuses on:

- mesh and numerical resolution;
- boundary conditions and physical models;
- convergence and solver settings;
- verification and validation;
- physical plausibility;
- reproducibility and reporting completeness.

It also produces:

- an Evidence Map;
- reviewer-risk assessment;
- claim–evidence checks;
- submission-readiness assessment;
- an action plan separating quick fixes, analysis fixes and cases where additional simulation may be justified.

## Core reliability rule

> **Not reported ≠ not performed.**

If evidence is missing, the Skill should use labels such as:

- `Not reported`
- `Not identified in supplied material`
- `Unable to verify`

It must not invent solver settings, mesh information, validation results, numerical parameters or journal requirements.

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
└── README.md
```

## Recommended use in Codex

```text
Use $simulation-paper-auditor to audit this manuscript.

First build the Evidence Map.
Do not infer that a method was not performed merely because it is not reported.
Prioritise methodology, numerical credibility and reviewer risks over language editing.
```

## Related standalone Skills

Each related Skill now has its **own repository** and can be installed or shared independently:

### Fluent Setting Checker
https://github.com/Wendy-skill/fluent-setting-checker

Cross-checks manuscript Methods against the actual ANSYS Fluent setup.

Core rule: **Missing evidence is not a mismatch.**

### Physics Sanity Check
https://github.com/Wendy-skill/Physics-Sanity-Check

Checks whether simulation results, contours, trends and proposed physical mechanisms are plausible.

Core rule: **Plausible is not proven.**

### Claim–Evidence Checker
https://github.com/Wendy-skill/Claim-Evidence-Checker

Checks whether manuscript claims are stronger or broader than the evidence supporting them.

Core rule: **Claim strength must not exceed evidence strength.**

### Journal Gap Analyzer
https://github.com/Wendy-skill/Journal-Gap-Analyzer

Builds a benchmark from comparable recent papers in a target journal and identifies the manuscript's largest relative gaps and highest-leverage fixes.

Core rule: **Journal distance is not acceptance probability.**

Created by **Wendy.z**.
