# CFD / ANSYS Fluent Audit Reference

Use this file only when the manuscript contains CFD or a closely related flow simulation.

## 1. Mesh and near-wall resolution

Check whether the manuscript reports enough evidence that spatial discretisation does not materially change the main conclusions.

Look for:
- mesh topology / cell type
- total cell count
- local refinement
- mesh quality
- coarse/medium/fine or equivalent refinement strategy
- monitored quantity
- quantitative deviation
- rationale for final mesh
- GCI or other uncertainty metric if used
- representative or demanding mesh-test condition

Do not impose “exactly three meshes” as a universal requirement.

### Near-wall checks

When relevant:
- y+
- y+ range
- first-layer height
- inflation/prism layers
- growth rate
- wall treatment
- refinement near separation / reattachment / wakes / jets / thermal boundary layers

For SST k-ω, do not blindly require y+ = 1.
Judge whether near-wall treatment and reported resolution are mutually consistent.

## 2. Boundary conditions and domain

Check:
- inlet type and provenance
- outlet type
- wall condition
- roughness
- symmetry / periodic assumptions
- upstream/downstream distance
- top and lateral clearance
- blockage
- artificial confinement
- outlet reverse flow if visible/reported

Flag apparently arbitrary conditions, especially when conclusions are sensitive to them.

## 3. Turbulence-model choice

Check whether the model choice is justified for the dominant physics.

Examples:
- standard k-ε
- RNG k-ε
- realizable k-ε
- SST k-ω
- RSM
- LES
- DES

Do not require a multi-model comparison unless scientifically necessary.

## 4. Solver and convergence

Check:
- steady/transient
- pressure/density based where relevant
- SIMPLE / SIMPLEC / PISO / Coupled
- gradient and pressure discretisation
- momentum/turbulence/energy order
- first vs second order
- under-relaxation if materially changed
- Courant number where relevant
- pseudo-transient settings
- residual thresholds
- physical monitor convergence

Residuals alone do not establish convergence.

Look for stabilisation of relevant quantities such as:
- drag/lift
- pressure drop
- mass flow
- temperature
- heat flux
- deposition fraction

## 5. Transient CFD

Check:
- time step
- temporal independence
- inner iterations per step
- total duration
- spin-up removal
- averaging window
- sampling frequency
- periodic/statistical convergence

For LES/unsteady turbulence also consider:
- flow-through time
- stationarity
- sampling duration
- temporal resolution

## 6. Physical plausibility

Where figures/data allow, inspect:
- stagnation
- separation
- reattachment
- recirculation
- wakes
- pressure gradients
- reverse flow
- mass imbalance
- streamline penetration of solids
- outlet artefacts

Use cautious language unless contradiction is unequivocal.
