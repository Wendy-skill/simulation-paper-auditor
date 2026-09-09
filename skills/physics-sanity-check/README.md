# Physics Sanity Check

A simulation-result review Skill focused on one question:

> **Do the results and physical explanations actually make sense?**

It is designed to complement a methods audit and solver-setting check.

## What it does

The Skill separates:

**what is observed**
from
**why the authors think it happened**

Then it checks whether the proposed mechanism is genuinely supported.

Typical checks include:

- flow-field plausibility;
- separation / recirculation / wake behaviour;
- pressure and velocity consistency;
- heat-transfer trends;
- particle deposition mechanisms;
- dimensionless-regime consistency;
- figure credibility;
- over-interpretation of contour plots.

## Core rule

**Plausible is not proven.**

Instead of saying:

> “Higher deposition is caused by inertia.”

the Skill prefers:

```text
Observed:
Higher deposition occurs for this particle size.

Possible mechanism:
Increased inertia.

Alternative explanations:
Residence time, recirculation, wall interaction.

Evidence required:
Trajectory statistics / Stokes number / force comparison.

Verdict:
Plausible but under-supported.
```

## Mechanism evidence ladder

- Level 0 — speculation
- Level 1 — pattern consistency
- Level 2 — supporting diagnostic
- Level 3 — comparative evidence
- Level 4 — strong mechanistic support

## Supported areas

Current specialist references cover:
- CFD
- heat transfer
- particle transport / DPM

## Suggested use

```text
Use $physics-sanity-check to review the Results and Discussion.

Separate direct observations from physical explanations.
Do not treat a plausible mechanism as proven without supporting diagnostics.
Identify alternative explanations and the evidence needed to distinguish them.
```

Created by **Wendy.z**.
