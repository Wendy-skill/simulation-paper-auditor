# Simulation Paper Auditor

An evidence-first AI Skill series for checking simulation-based research manuscripts before submission.

The current rules are strongest for **CFD / ANSYS Fluent / CFD-DPM**, while the framework is designed to expand to FEM, COMSOL and other numerical simulation workflows.

## Available Skills

### 1. Simulation Paper Auditor

The core pre-submission audit Skill.

It focuses on six areas that commonly affect simulation-paper credibility:

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

### 2. Fluent Setting Checker

Path: `skills/fluent-setting-checker/`

This Skill cross-checks the manuscript Methods section against the actual ANSYS Fluent setup.

It can compare:

- turbulence models;
- steady / transient formulation;
- solver type;
- mesh information;
- boundary conditions;
- discretisation schemes;
- pressure–velocity coupling;
- convergence criteria;
- time-step settings;
- DPM / particle settings;
- UDF / script-controlled settings.

Its core rule is:

> **Missing evidence is not a mismatch.**

It first extracts manuscript settings and Fluent settings independently, then compares them. This helps distinguish a true configuration conflict from a reporting gap or an unverifiable item.

Example:

```text
Manuscript:
Turbulence model = SST k-ω

Fluent production case:
Turbulence model = Realizable k-ε

Status:
Critical mismatch
```

## Evidence-first rule

The core reliability rule across this repository is:

> **Not reported ≠ not performed.**

The Skills must first identify what evidence is actually present in the manuscript or supplied files. If something cannot be confirmed, they should use labels such as:

- `Not reported`
- `Not identified in supplied material`
- `Unable to verify`

They must not invent missing solver settings, mesh information, validation results, numerical parameters or journal requirements.

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
    └── fluent-setting-checker/
        ├── SKILL.md
        ├── references/
        │   └── dpm.md
        ├── templates/
        │   └── consistency-report.md
        └── README.md
```

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

When DPM or Lagrangian particle tracking is detected, the Skills can additionally check:

- particle size, density and injection definition;
- one-way / two-way coupling;
- turbulent dispersion;
- force-model justification;
- particle-wall interaction;
- deposition criteria;
- particle-number sensitivity;
- the actual validation scope of particle/deposition predictions.

## Recommended use in Codex

For the main audit:

```text
Use $simulation-paper-auditor to audit this manuscript.

First build the Evidence Map.
Do not infer that a method was not performed merely because it is not reported.
Prioritise methodology, numerical credibility and reviewer risks over language editing.
```

For the Fluent consistency check:

```text
Use $fluent-setting-checker to compare the manuscript Methods with the supplied Fluent files.

Extract manuscript and Fluent settings independently before comparing them.
Do not treat missing evidence as a mismatch.
Identify the production run before flagging configuration conflicts.
```

## Recommended inputs

For the strongest checks, provide as many of these as available:

- manuscript;
- figures and tables;
- supplementary material;
- Fluent / solver report;
- mesh report;
- residual history;
- journal or script files;
- UDFs or custom numerical settings where relevant.

## Planned series

Next modules may include:

- Reviewer View;
- Claim–Evidence Checker;
- Physics Sanity Check;
- FEM specialist rules;
- COMSOL specialist rules.

Created by **Wendy.z**.
