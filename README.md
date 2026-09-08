# Simulation Paper Auditor

An evidence-first AI Skill for checking simulation-based research manuscripts before submission.

The current rules are strongest for **CFD / ANSYS Fluent / CFD-DPM**, while the core framework is designed to expand to FEM, COMSOL and other numerical simulation workflows.

## What it checks

The Skill focuses on six areas that commonly affect simulation-paper credibility:

1. mesh and numerical resolution;
2. boundary conditions and physical models;
3. convergence and solver settings;
4. verification and validation;
5. physical plausibility;
6. reproducibility and reporting completeness.

It also includes:

- an Evidence Map;
- claim–evidence checks for words such as `validated`, `accurate` and `robust`;
- reviewer-risk prediction;
- submission-readiness assessment;
- an action plan separating quick fixes, analysis fixes and cases where new simulation may be justified.

## Evidence-first rule

The core reliability rule is:

> **Not reported ≠ not performed.**

The Skill must first identify what evidence is actually present in the manuscript or supplied files. If something cannot be confirmed, it should use labels such as:

- `Not reported`
- `Not identified in supplied material`
- `Unable to verify`

It must not invent missing solver settings, mesh information, validation results, numerical parameters or journal requirements.

## Progressive loading

The Skill is split into a compact core plus specialist references:

```text
simulation-paper-auditor/
├── SKILL.md
├── references/
│   ├── cfd.md
│   ├── cfd-dpm.md
│   └── validation.md
└── templates/
    └── audit-report.md
```

CFD rules are loaded only for CFD studies. CFD-DPM rules are loaded only when particle tracking is present. This keeps the core workflow compact and reduces unnecessary context use when reviewing long manuscripts.

## CFD / Fluent coverage

The CFD module checks topics such as:

- mesh independence and spatial resolution;
- y+ and near-wall treatment where relevant;
- local refinement;
- domain size and boundary-condition provenance;
- turbulence-model justification;
- residual and physical-monitor convergence;
- discretisation schemes;
- transient time-step independence;
- separation, recirculation and other physical-plausibility indicators.

The rules deliberately avoid treating common recommendations as universal laws. For example, the Skill does **not** automatically require exactly three meshes, GCI for every CFD paper, or y+ = 1 for every SST k-ω simulation.

## CFD-DPM coverage

When DPM or Lagrangian particle tracking is detected, the Skill additionally checks:

- particle size, density and injection definition;
- one-way / two-way coupling;
- turbulent dispersion;
- force-model justification;
- particle-wall interaction;
- deposition criteria;
- particle-number sensitivity;
- the actual validation scope of particle/deposition predictions.

## Recommended use in Codex

```text
Use $simulation-paper-auditor to audit this manuscript.

First build the Evidence Map.
Do not infer that a method was not performed merely because it is not reported.
Prioritise methodology, numerical credibility and reviewer risks over language editing.
```

For CFD-DPM:

```text
This is a CFD-DPM study. Load the CFD and CFD-DPM specialist references.
Pay particular attention to validation scope, particle-wall interaction,
force models, coupling assumptions and deposition credibility.
```

## Recommended inputs

For the strongest audit, provide as many of these as available:

- manuscript;
- figures and tables;
- supplementary material;
- Fluent / solver report;
- mesh report;
- residual history;
- journal or script files;
- UDFs or custom numerical settings where relevant.

A text-only audit is still useful, but checks that depend on figures or solver files should remain `Unable to verify` when those materials are unavailable.

## Planned extensions

The repository is designed to grow into a broader simulation-paper auditing series, including:

- Reviewer View;
- Claim–Evidence Checker;
- Physics Sanity Check;
- Fluent Setting Checker;
- manuscript-vs-solver consistency checking;
- FEM specialist rules;
- COMSOL specialist rules.

Created by **Wendy.z**.
