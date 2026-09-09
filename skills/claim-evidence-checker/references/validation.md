# Validation Claim Reference

Use when claims include validated, accurate, predictive, reliable, agreement or related wording.

## Validation scope map

For each validation claim, identify:
- what quantity was compared
- what model component it tests
- what operating conditions were covered
- what metric quantified agreement
- whether the validation data are independent

Example:

| Quantity | Evidence | Scope |
|---|---|---|
| Mean velocity | wind-tunnel profile | airflow field |
| Pressure coefficient | experiment | surface pressure |
| Particle deposition | none identified | not independently validated |

Allowed:
“The airflow model was validated against wind-tunnel velocity and pressure data.”

Risky:
“The validated CFD-DPM framework accurately predicts deposition.”

## Accuracy language

Words such as accurate, excellent agreement, good agreement and reliable should ideally have quantitative support.

Visual similarity alone usually supports weaker language such as reasonable agreement, trend consistency or qualitative agreement, depending on context.

## Extrapolation

If validation covers only part of the parameter space, claims outside that range should be scoped or caveated.
