# Claim–Evidence Checker

A research-paper Skill focused on one question:

> **Is the manuscript saying more than the evidence can support?**

It checks scientific claims against the evidence actually present in the paper.

## Typical targets

The Skill pays special attention to wording such as:

- validated
- accurate
- robust
- reliable
- proves
- confirms
- demonstrates
- significant
- optimal
- superior
- caused by
- dominated by
- generalisable
- first / novel

## Core rule

**Claim strength must not exceed evidence strength.**

For example:

```text
Claim:
“The validated CFD-DPM framework accurately predicts particle deposition.”

Evidence:
Airflow velocity validated.
Surface pressure validated.
No independent deposition validation identified.

Verdict:
Overstated.

Safer wording:
“The validated airflow field was used to evaluate particle-transport and deposition trends.”
```

## Evidence levels

- Level 0 — no identifiable evidence
- Level 1 — qualitative consistency
- Level 2 — quantitative support
- Level 3 — independent corroboration
- Level 4 — strong convergent evidence

## What it audits

- validation scope
- causal/mechanistic claims
- statistical language
- comparative / “optimal” claims
- generalisation
- novelty claims
- strong-certainty wording

## Suggested use

```text
Use $claim-evidence-checker to audit this manuscript.

Find claims whose strength or scope exceeds the evidence.
Distinguish unsupported, overstated, partially supported and supported claims.
Suggest the minimum necessary wording change rather than weakening everything.
```

Created by **Wendy.z**.
