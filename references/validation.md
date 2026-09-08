# Verification, Validation and Claim-Scope Reference

## 1. Verification

Verification concerns whether the numerical problem is solved with acceptable numerical error.

Typical evidence:
- mesh independence
- grid convergence
- temporal independence
- discretisation sensitivity
- solver convergence
- code verification
- numerical uncertainty

Mesh independence is not experimental validation.

## 2. Validation

Validation concerns whether the model represents physical reality adequately for the intended use.

Evidence may include:
- independent experiments
- field measurements
- canonical benchmark data
- analytical solutions
- independent published datasets
- code-to-code comparison

These evidence types do not all provide equal physical validation strength.

## 3. Build a validation-scope map

Example:

| Quantity / submodel | Validation status | Evidence |
|---|---|---|
| Mean velocity | Validated | Wind-tunnel profile comparison |
| Pressure coefficient | Validated | Cp comparison |
| Turbulence intensity | Partially compared | Limited stations |
| Particle deposition | Not independently validated | No direct deposition comparison identified |

Never broaden a validation claim beyond this map.

## 4. Quantitative comparison

Where appropriate, look for:
- relative error
- MAE
- RMSE
- MAPE
- uncertainty bands
- profile comparison
- point-wise comparison

Flag purely visual “good agreement” claims when quantitative evidence is reasonably expected.

## 5. Validation range

Check whether the validation envelope covers relevant:
- Reynolds number
- geometry
- flow regime
- temperature
- particle size
- operating conditions
- boundary conditions

Extrapolation beyond the validation range should usually be framed as a limitation, not automatically as invalid.

## 6. Strong claim check

High-risk words:
- validated
- accurate
- reliable
- robust
- predictive
- realistic
- proves
- confirms
- excellent agreement
- generalisable

For each strong claim ask:
1. What exact evidence supports it?
2. What variable/model component was validated?
3. Is the evidence quantitative?
4. Does the validation range cover the reported application?
5. Is the limitation acknowledged?
