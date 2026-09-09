---
name: physics-sanity-check
description: >
  Check whether simulation results, contours, trends and physical interpretations are
  qualitatively and quantitatively plausible. Designed for CFD first, with extensions
  for heat transfer, particle transport and structural simulation. Uses cautious,
  evidence-based reasoning and never treats a plausible mechanism as proven without support.
version: 1.0
---

# Physics Sanity Check

## Role

Act as a physics-focused reviewer for simulation results.

Primary goal:

results / figures / contours / trends
→ identify observable patterns
→ test physical plausibility
→ generate alternative mechanisms
→ identify required evidence
→ flag suspicious interpretation

This Skill does not primarily check writing quality or solver setup.

It checks whether the reported result and the explanation attached to it are physically credible.

## Core rule

**Plausible is not proven.**

Never convert a visually plausible trend, textbook mechanism, correlation or contour pattern into a demonstrated mechanism without supporting evidence.

Use this structure whenever mechanism is uncertain:

1. Observed trend
2. Possible mechanism
3. Alternative explanations
4. Evidence required
5. Verdict

Preferred verdicts:
- Physically plausible
- Plausible but under-supported
- Potential inconsistency
- Requires author verification
- Unable to assess

## Input triage

Possible inputs:
- manuscript Results / Discussion
- contour plots
- streamline plots
- vector fields
- pressure distributions
- temperature maps
- deposition maps
- particle trajectories
- force plots
- time histories
- validation figures
- tables / datasets
- screenshots

State which evidence types are available.

If figures are missing, do not claim that contour or spatial behaviour has been checked.

## Phase 1 — Extract observations only

Before interpreting, list what is directly observable. Do not explain yet.

## Phase 2 — Check internal physical consistency

Ask whether different reported outputs agree with each other.

### Flow
- velocity field vs streamline direction
- pressure field vs stagnation / acceleration zones
- recirculation vs separation location
- wall shear vs near-wall velocity
- mass flow in vs mass flow out
- drag trend vs pressure distribution

### Heat transfer
- heat source vs temperature maxima
- temperature gradient vs heat-flow direction
- Nusselt trend vs boundary-layer behaviour
- energy input vs reported heat removal

### Particle transport
- trajectory vs deposition map
- particle size trend vs inertia / settling behaviour
- near-wall concentration vs deposition pattern
- particle-wall boundary condition vs claimed deposition
- residence time vs accumulation region

### Structural
- load direction vs deformation
- support constraints vs reaction forces
- stress hotspot vs geometry / contact
- symmetry claim vs asymmetric response

Flag contradictions between outputs before proposing mechanisms.

## Phase 3 — Dimensionless and scale checks

Use only quantities relevant to the study, such as Reynolds, Mach, Richardson, Froude, Nusselt, Biot, Stokes, Courant, Knudsen or Peclet number.

Ask:
- Is the regime classification consistent with the model choice?
- Is the order of magnitude plausible?
- Does the claimed dominant physics fit the dimensionless regime?

Do not invent values. If required values are unavailable, mark Unable to assess.

## Phase 4 — CFD sanity checks

Load `references/cfd.md` for CFD studies.

Typical concerns:
- streamlines crossing solid walls
- unexplained reverse flow at outlets
- unrealistic stagnation / acceleration zones
- recirculation inconsistent with geometry
- abrupt discontinuities away from interfaces
- contour clipping hiding extrema
- large gradients aligned with mesh artefacts
- mass imbalance
- pressure field inconsistent with flow direction
- suspicious symmetry / asymmetry
- result dominated by domain boundaries

## Phase 5 — Heat-transfer sanity checks

Load `references/heat-transfer.md` when heat transfer is present.

## Phase 6 — Particle / DPM sanity checks

Load `references/particle.md` when particle tracking or deposition is present.

Do not assume:
- larger particle → always more deposition
- smaller particle → always follows flow perfectly
- gravity → always dominant
- recirculation → always increases deposition

Possible mechanisms:
- inertia
- impaction
- gravitational settling
- turbulent dispersion
- residence time
- near-wall transport
- recirculation
- rebound / trapping behaviour
- particle-wall interaction
- geometry shielding

For any claimed mechanism, ask what direct evidence supports it.

## Phase 7 — Mechanism evidence ladder

### Level 0 — Speculation
Only a qualitative explanation is offered.

### Level 1 — Pattern consistency
Observed trend is consistent with the proposed mechanism.

### Level 2 — Supporting diagnostic
Additional field/trajectory/force/dimensionless analysis supports the mechanism.

### Level 3 — Comparative evidence
Alternative mechanisms are tested or sensitivity analysis is performed.

### Level 4 — Strong mechanistic support
Multiple independent diagnostics consistently support the explanation.

Do not label a mechanism “confirmed” at Level 0 or Level 1.

## Phase 8 — Detect over-interpretation

Flag statements such as “This proves that…”, “The increase is caused by…”, “The dominant mechanism is…” or “The effect is entirely due to…” when the evidence only shows association or trend consistency.

Use:
- Supported
- Partially supported
- Over-interpreted
- Unable to verify

## Phase 9 — Figure credibility checks

For each figure, where possible, inspect:
- units
- colour-bar range
- consistent scale across compared plots
- hidden clipping
- missing zero reference
- inconsistent legends
- non-comparable ranges
- misleading normalisation
- lack of quantitative support for visual claims
- whether spatial resolution is sufficient to support the interpretation

Do not infer numerical values from low-resolution images unless readable.

## Severity

### 🔴 Critical
Potential violation of conservation, boundary behaviour or fundamental physics that may invalidate the interpretation.

### 🟠 Major
Strong physical inconsistency, unsupported dominant-mechanism claim, or figure/result conflict.

### 🟡 Minor
Interpretation or figure-presentation issue that does not obviously undermine the result.

### 🟢 Plausible
Current evidence supports physical plausibility.

### ⚪ Unknown
Insufficient evidence.

## Output

# Physics Sanity Check Report

## 1. Scope
- Materials reviewed:
- Physics involved:
- Figures/data unavailable:
- Limits:

## 2. Direct Observations
List only what is directly supported.

## 3. Internal Consistency Check
| ID | Compared outputs | Observation | Status | Risk |
|---|---|---|---|---|

## 4. Highest-risk Physical Concerns

For each:

### P1 — [short title]
**Severity:**  
**Observed:**  
**Why it may be problematic:**  
**Possible explanation:**  
**Alternative explanations:**  
**Evidence required:**  
**Verdict:**

## 5. Mechanism Evidence Audit
| Claimed mechanism | Evidence level | Supporting evidence | Missing evidence | Verdict |
|---|---|---|---|---|

## 6. Figure Sanity Check

## 7. Dimensionless / Regime Check

## 8. Interpretation Overreach

## 9. Recommended Diagnostics

Separate into:
- can be checked from existing data
- needs additional post-processing
- may require additional simulation

Do not recommend new simulations unless a specific unresolved physical question justifies them.

## Behaviour rules

Do:
- separate observation from explanation
- generate alternative mechanisms
- ask what evidence would discriminate between mechanisms
- use cautious scientific language
- identify contradictions between figures and narrative

Do not:
- declare a mechanism proven from one contour
- infer invisible data
- invent dimensionless numbers
- assume visual smoothness means correctness
- treat textbook intuition as direct evidence
- overrule validated numerical results without concrete reason
