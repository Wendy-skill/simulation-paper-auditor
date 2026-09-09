# Fluent Setting Checker

An evidence-first Skill for checking whether a CFD manuscript's Methods section matches the ANSYS Fluent setup actually used.

Core question:

> **Does the Methods section match the simulation that was actually run?**

## Checks
- turbulence model
- steady / transient formulation
- solver type
- mesh information
- boundary conditions
- discretisation schemes
- pressure–velocity coupling
- convergence criteria
- time-step settings
- DPM / particle settings
- UDF / script-controlled settings

## Reliability rule
**Missing evidence is not a mismatch.**

The Skill separates:
- Match
- Mismatch
- Reporting gap
- Manuscript-only claim
- Unable to verify

It first builds two independent evidence tables—manuscript settings and Fluent settings—then compares them.

## Example

```text
Manuscript:
Turbulence model = SST k-ω

Fluent production case:
Turbulence model = Realizable k-ε

Status:
Critical mismatch
```

It also avoids false alarms from startup/test runs. For example, first-order initialisation followed by second-order production should not automatically be treated as a conflict if the manuscript refers to the production run.

## Recommended inputs
- manuscript / Methods
- Fluent case report / setup summary
- journal / transcript / solver log
- residual history
- mesh report
- UDFs / scripts where relevant

## Suggested use

```text
Use $fluent-setting-checker to compare the manuscript Methods with the supplied Fluent files.

Extract manuscript and Fluent settings independently before comparing them.
Do not treat missing evidence as a mismatch.
Identify the production run before flagging configuration conflicts.
```

A DPM specialist reference is included for particle size, injection, force models, coupling, wall interaction, deposition and tracking settings.

Created by **Wendy.z**.
