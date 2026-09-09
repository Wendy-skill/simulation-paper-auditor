# DPM Cross-check Reference

Load only when Fluent DPM / Lagrangian tracking is present.

Cross-check:

## Injection
- injection type/location
- particle diameter/distribution
- density
- velocity
- mass flow
- number of streams/parcels
- injection duration

## Physical models
- gravity
- drag law
- turbulent dispersion / DRW
- Saffman lift
- Brownian force
- thermophoresis
- pressure-gradient force
- added mass where relevant

Do not require every force model.

## Coupling
- one-way / two-way
- continuous-phase update frequency
- particle–particle interaction if relevant

## Wall interaction
- trap / reflect / escape
- rebound law
- restitution coefficient
- sticking / deposition logic
- UDF-based deposition
- resuspension if present

## Tracking numerics
- integration scheme
- step controls
- maximum steps
- accuracy controls
- stochastic tries

Treat explicit production-run mismatches in particle sizes, gravity, coupling, injection velocity, wall fate, deposition criterion or central force models as potentially Critical/Major.
