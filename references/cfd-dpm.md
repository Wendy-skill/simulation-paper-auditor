# CFD-DPM / Particle Transport Audit Reference

Use only when a Lagrangian particle, DPM or closely related particle-tracking model is present.

## 1. Particle definition

Check:
- particle size / size distribution
- density
- shape assumption
- number of particles/parcels
- injection location
- injection velocity
- injection rate
- injection duration where relevant

## 2. Coupling and tracking

Check:
- one-way vs two-way coupling
- justification using particle loading if available
- stochastic tracking / turbulent dispersion
- integration settings
- particle time step if applicable
- sensitivity to tracked-particle number

## 3. Force model

Potential forces include:
- drag
- gravity
- Saffman lift
- Brownian motion
- thermophoresis
- pressure-gradient force
- added mass

Do not demand every force.

For an omitted force, ask whether it is negligible for the reported:
- particle size
- density
- flow regime
- temperature field

If this cannot be established, use Unknown rather than Incorrect.

## 4. Particle-wall interaction

Check:
- trap
- reflect
- escape
- rebound model
- restitution coefficient
- sticking/deposition criterion
- resuspension if relevant

Ensure the wall-interaction model is compatible with what the paper calls “deposition”.

## 5. Deposition credibility

Ask:
- Is airflow validated?
- Is particle transport independently validated?
- Is deposition independently validated?
- Are only trends assessed?
- Are conclusions stronger than validation scope?

Do not call the full CFD-DPM framework validated when only airflow has been validated.

## 6. Physical-plausibility prompts

For particle trends, use:

- Observed trend
- Possible mechanism
- Alternative explanations
- Evidence required
- Author verification

Possible mechanisms may include:
- inertia
- gravitational settling
- turbulent dispersion
- residence time
- recirculation
- impaction
- near-wall transport
- particle-wall behaviour

Avoid assigning a single mechanism without supporting evidence.
